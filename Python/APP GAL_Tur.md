
# 🗺️ Blueprint del Proyecto: Sistema Integral de Turismo Local (PWA + Inteligencia de Ruta)

Este documento es la especificación técnica y de producto completa para el desarrollo de la solución turística. Sirve como guía de referencia central para la arquitectura, pila tecnológica, lógica de negocio y plan de entrega por fases.

## 🎯 1. Visión General del Producto

### El Problema

Los mapas estáticos, PDFs e iframes integrados en webs de turismo carecen de dinamismo, no ofrecen guía peatonal interactiva en el terreno y no aprovechan el contexto del visitante (ubicación, tiempo disponible, clima o cansancio).

### La Solución

Un sistema híbrido **Web de Planificación + PWA de Navegación Peatonal** que:

1. Permite al turista planificar la ruta cómoda y visualmente desde la PC de su hotel/casa.
    
2. Guía al turista en la calle usando el GPS de su smartphone y la precisión peatonal de **Google Maps**.
    
3. Detecta automáticamente la llegada a los puntos turísticos mediante un **margen de tolerancia (Geofencing)**.
    
4. Adapta las rutas según el contexto (clima, tiempo disponible) usando **Lógica Difusa**.
    
5. Conecta al turista con el **comercio local** (puntos de descanso y promociones) sin resultar invasivo.
    

## 🏗️ 2. Arquitectura del Sistema

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                             CLIENTE (FRONTEND)                              │
│                                                                             │
│   [ PC / Laptop ]                     [ Teléfono Móvil ]                    │
│   Modo Planificación:                 Modo Acción / Guía Peatonal:          │
│   • Fotos HD, vistas de mapa          • Botón "Iniciar Ruta"                │
│   • Selección de itinerario           • Rastreos de GPS (navigator.geo)     │
│                                       • Service Worker (sw.js - Offline)    │
└──────────────────────────────────────┬──────────────────────────────────────┘
                                       │
                                       │ Peticiones HTTP / JSON
                                       ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                            SERVIDOR BROKER (API)                            │
│                                                                             │
│   Servidor ligero en C++ (o Go / Java):                                     │
│   • Recibe peticiones de la PWA.                                            │
│   • Comunica con el motor de Python.                                        │
│   • Devuelve las respuestas estructuradas en JSON.                          │
└──────────────────────────────────────┬──────────────────────────────────────┘
                                       │
                                       │ Ejecución de Scripts / Módulos
                                       ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                        MOTOR DE INTELIGENCIA (PYTHON)                       │
│                                                                             │
│   • Módulo Haversine: Cálculo de distancia GPS en metros.                   │
│   • Módulo Fuzzy Logic: Motor de recomendaciones (scikit-fuzzy).            │
│   • Módulo Clima: Integración con API externa (Open-Meteo).                 │
└──────────────────────────────────────┬──────────────────────────────────────┘
                                       │
                                       │ Consultas SQL
                                       ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                            BASE DE DATOS (SQLITE)                           │
│                                                                             │
│   `turismo.db`: Tabla de Sitios Turísticos, Comercios Adheridos,           │
│   Puntos de Descanso y Radios de Tolerancia GPS.                            │
└─────────────────────────────────────────────────────────────────────────────┘


```

## 🛠️ 3. Stack Tecnológico (100% Gratuito / Open Source)

- **Base de Datos:** SQLite (`turismo.db`) — Ligera, portátil, sin necesidad de instalación de servidor complejo.
    
- **Backend / Motor Inteligente:** Python 3 (Pandas, NumPy, `scikit-fuzzy`, `requests`).
    
- **Servidor Broker / API:** Servidor local ejecutable (C++ / Go / Java) encargado de la mensajería JSON.
    
- **Frontend Web/PWA:** HTML5, CSS3 (Responsive Design), JavaScript Vanilla + `sw.js` (Service Worker) + `manifest.json`.
    
- **Navegación Externa:** Deep Linking con Google Maps API de URLs de navegación peatonal (`travelmode=walking`).
    
- **API Clima (V3.0):** Open-Meteo (API pública sin costo ni clave requerida).
    
- **Empaquetado Móvil:** PWABuilder / Bubblewrap para generar el archivo ejecutable Android (`.aab` / `.apk`) para Google Play Store.
    

## 🗄️ 4. Modelo de Datos Base (`turismo.db`)

### Tabla: `sitios_turisticos`

| **Campo** | **Tipo** | **Descripción** |

| `id` | INTEGER (PK) | Identificador único del punto |

| `nombre` | TEXT | Nombre del monumento/lugar |

| `categoria` | TEXT | `monumento`, `plaza`, `museo`, `descanso` |

| `latitud` | REAL | Coordenada Y (Ej: `42.5975`) |

| `longitud` | REAL | Coordenada X (Ej: `-8.7672`) |

| `radio_tolerancia` | INTEGER | Margen de tolerancia GPS en metros (Ej: `30`) |

| `descripcion` | TEXT | Historia o datos curiosos |

| `imagen_url` | TEXT | Ruta de la foto |

| `cubierto` | BOOLEAN | `1` si es en interior (museo/iglesia), `0` si es al aire libre |

| `oferta_comercial` | TEXT | Texto del beneficio/descuento (si es tipo `descanso`) |

## 📐 5. Lógicas Clave del Sistema

### 5.1. Cálculo de Distancia Geodésica (Fórmula de Haversine)

Para determinar la distancia real sobre la curvatura de la Tierra entre las coordenadas del usuario $(lat_1, lon_1)$ y el punto turístico $(lat_2, lon_2)$:

$$d = 2R \cdot \arcsin\left(\sqrt{\sin^2\left(\frac{\Delta \phi}{2}\right) + \cos(\phi_1)\cos(\phi_2)\sin^2\left(\frac{\Delta \lambda}{2}\right)}\right)$$

Donde $R = 6371000$ metros (radio de la Tierra), $\phi$ es la latitud y $\lambda$ es la longitud en radianes.

### 5.2. Evaluación del Margen de Tolerancia (Geofencing)

- **Regla:** Si la distancia calculada $d \le \text{radio\_tolerancia}$, el sistema registra que el turista ha **alcanzado el punto**.
    
- **Acción:**
    
    1. El móvil vibra.
        
    2. Se desbloquea la ficha completa con fotos/audios del lugar.
        
    3. Se propone automáticamente el siguiente punto inteligente de la ruta.
        
- **Plan B (Calibración manual):** Botón flotante en pantalla: `¿Ya estás aquí? Marcar como visitado`.
    

### 5.3. Lanzamiento de Navegación Peatonal

Para transferir la guía a la app nativa de Google Maps sin pagar costes de API:

```
function irAlSiguientePunto(latDestino, lonDestino) {
    const url = `https://www.google.com/maps/dir/?api=1&destination=${latDestino},${lonDestino}&travelmode=walking`;
    window.location.href = url;
}


```

## 🗺️ 6. Hoja de Ruta por Fases (Roadmap)

### 🗓️ Versión 1.0 — Producto Mínimo Viable (MVP) (Plazo: 2 Meses)

- **Enfoque:** Funcionalidad pura ("Que haga lo que tiene que hacer").
    
- Base de datos SQLite con los primeros 5-10 puntos reales de la ciudad.
    
- Motor de Python que calcula distancias con Haversine y aplica la tolerancia en metros.
    
- Servidor Broker respondiendo las llamadas JSON.
    
- PWA básica en HTML/JS que lee el GPS del móvil, muestra la lista de sitios, detecta si estás a menos de 30m y abre el botón de navegación en Google Maps.
    

### 🎨 Versión 2.0 — Experiencia Dual y Diseño Refinado

- **Enfoque:** Estética, usabilidad y separación de modos.
    
- **Modo Web (Desktop):** Interfaz para planificar la ruta desde la PC del hotel/casa con fotos HD e itinerarios recomendados.
    
- **Modo App (Móvil):** Interfaz limpia con botones táctiles grandes, diseño adaptable y PWA instalable en la pantalla de inicio del teléfono.
    

### 🧠 Versión 3.0 — Asistente de Ruta Inteligente (Clima + Lógica Difusa)

- **Enfoque:** Contexto dinámico.
    
- Módulo de Lógica Difusa en Python (`scikit-fuzzy`):
    
    - **Variables:** Distancia, tiempo disponible del turista, estado del clima.
        
    - **Reglas:** Reordenación de visitas en caso de lluvia (prioriza museos/interiores) o frío/calor extremo.
        
- Integración con la API de clima Open-Meteo para obtener precipitación y temperatura en tiempo real.
    

### 🏪 Versión 3.3 — Impulso al Comercio Local y Puntos de Descanso

- **Enfoque:** Impacto económico y experiencia del turista.
    
- Algoritmo de detección de cansancio (ej. más de 45 minutos seguidos de caminata).
    
- Inserción de "Puntos de Descanso" (cafeterías, pastelerías artesanales, tiendas de recuerdos) intercalados en la ruta.
    
- Descuentos y ofertas especiales integrados en la pantalla de la PWA para incentivar el consumo local.
    

## 🚀 7. Estrategia de Lanzamiento a Tiendas (Google Play)

1. **Desarrollo Web PWA:** Todo el código reside en el servidor web.
    
2. **Empaquetado TWA (Trusted Web Activity):** Se utiliza la herramienta oficial **PWABuilder** / **Bubblewrap** para convertir la URL en un paquete Android de forma gratuita (`.aab` / `.apk`).
    
3. **Inscripción en Google Play Console:** Pago único de **$25 USD** (cuenta personal de desarrollador, válida de por vida para apps ilimitadas).
    
4. **Ventaja Crítica de Actualización:** Cualquier mejora en el HTML, Python o la base de datos se refleja instantáneamente en la app de todos los usuarios sin necesidad de volver a subir archivos a la Play Store.