
Para poner orden de inmediato a ese caos y estructurar una ruta de aprendizaje (Roadmap) de desarrollo web en tu bóveda de Obsidian, puedes usar una estructura basada en carpetas y un **archivo maestro de ruta** que centralice todo.

Aquí tienes una plantilla lista para aplicar ahora mismo siguiendo la estructura que diseñamos:

### 1. Estructura de carpetas para tu curso de Web Dev

Dentro de tu carpeta `02-courses-and-code/`, crea una carpeta específica para este curso:

Plaintext

```
02-courses-and-code/
└── web-development-master/
    ├── 00-roadmap-web.md            <-- Tu panel de control principal
    ├── 01-frontend/                 <-- HTML, CSS, JavaScript, Frameworks
    ├── 02-backend/                  <-- Node.js, Bases de datos, APIs
    └── 03-projects/                 <-- Prácticas y código que vayas creando
```

### 2. Plantilla para el archivo maestro (`00-roadmap-web.md`)

Crea una nota llamada `00-roadmap-web.md` y pega esta estructura dentro. Utiliza las casillas de verificación `- [ ]` para ir marcando lo que ya dominas:

Markdown

```
# 🗺️ Roadmap: Desarrollo Web Full Stack

> **Estado:** En progreso 🚀
> **Objetivo:** Dominar el desarrollo web desde cero hasta desplegar aplicaciones completas.

---

## 📌 Fase 1: Fundamentos de Frontend
- [x] Introducción a Internet y cómo funcionan los navegadores
- [ ] HTML5 semántico y estructuración de páginas
- [ ] CSS3 moderno (Flexbox, Grid, Responsive Design)
- [ ] Git y control de versiones básico

> **🔗 Enlaces y Recursos de esta fase:**
> * [Documentación oficial de HTML en MDN](https://developer.mozilla.org/)
> * Carpeta de Drive con mis libros de CSS: [[04-google-drive-hub]]

---

## ⚡ Fase 2: JavaScript Moderno (ES6+)
- [ ] Variables, funciones y estructuras de control
- [ ] Manipulación del DOM y eventos
- [ ] Asincronismo (Promises, Async/Await, Fetch API)

> **💻 Práctica asociada:** 
> * Ir guardando el código en la carpeta [[03-projects]]

---

## 🚀 Fase 3: Backend y Bases de Datos
- [ ] Node.js y Express básico
- [ ] Conexión a bases de datos (SQL / NoSQL)
- [ ] Creación y consumo de APIs REST

---

## 🛠️ Notas Rápidas del Día a Día
* ¿Tienes un comando que siempre olvidas? Escríbelo aquí o mándalo al `00-inbox`.
* Usa enlaces internos como `[[01-frontend]]` para saltar directamente a tus apuntes de esa tecnología.
```

### ¿Por qué funciona este sistema?

1. **Adiós al desorden:** Cada vez que veas un video o leas un artículo, marcas la casilla en tu Roadmap y guardas el apunte en su respectiva subcarpeta (`01-frontend`, etc.).
    
2. **Conexión total:** Al usar los corchetes dobles de Obsidian (`[[ ]]`), tu roadmap se conecta automáticamente con tus carpetas de código y con los enlaces de Google Drive que hablamos antes.
    
3. **Se respalda solo:** Como esto vive en tu bóveda, en cuanto pasen los minutos configurados, el plugin de Git se encargará de subirlo a GitHub para que lo tengas idéntico tanto en Windows como en Linux.