  

### 1. La opción oficial : **10 minutes to pandas**

La propia documentación oficial de Pandas tiene una sección diseñada exactamente con el mismo propósito que el capítulo de las _SciPy Lecture Notes_:

- **Sitio web:** [10 minutes to pandas (Guía Oficial)](https://pandas.pydata.org/docs/user_guide/10min.html)
    
- **Estilo:** Es una guía rápida, limpia y directa en formato tutorial. Te da un repaso conciso por la creación de `Series` y `DataFrames`, selección con `.loc` y `.iloc`, filtrado, operaciones, limpieza de datos faltantes y operaciones de agrupar (`groupby`) o unir tablas.
    

### 2. Formato idéntico a Scientific Python: **Python for Scientific Computing (Aalto University)**

Si buscas algo que use prácticamente la misma interfaz web o un esquema idéntico al de `lectures.scientific-python.org`:

- **Sitio web:** [Pandas — Python for Scientific Computing](https://aaltoscicomp.github.io/python-for-scicomp/pandas/)
    
- **Estilo:** Es la extensión en formato libro/nota de clase usada por varias universidades para completar justamente la parte de data science que a veces no viene tan desarrollada en el tutorial clásico de SciPy.
    

### 3. Opción interactiva rápida: **Kaggle Micro-Course: Pandas**

Si prefieres un formato super resumido con teoría mínima y ejercicios prácticos interactivos en Jupyter Notebooks:

- **Sitio web:** [Kaggle Pandas Course](https://www.kaggle.com/learn/pandas)
    
- **Estilo:** Son 6 lecciones cortas de unos 10-15 minutos cada una, enfocadas en ir directo al grano (creación, indexación, funciones de resumen, agrupar, tipos de datos y combinación).
    

### Recomendación de inicio

Si te gustó la claridad y brevedad del enlace de _Scientific Python_, empieza directamente por **10 minutes to pandas**. Aunque el nombre diga "10 minutos", en realidad es la chuleta/resumen definitivo para tener las operaciones básicas listas para consultar.

Si buscas un tutorial en vídeo que mantenga este mismo ritmo conciso y directo para repasar visualmente los fundamentos de Pandas en unos 30 minutos, este recorrido de Tech With Tim es una gran opción:

[Learn Pandas in 30 Minutes - Python Pandas Tutorial](https://www.youtube.com/watch?v=EXIgjIBu4EU)

Este vídeo explica de forma muy ágil la creación de DataFrames, carga de CSVs, indexado y filtrado de datos sin rodeos teóricos.



Sí, existen varias opciones muy directas y con el mismo formato o filosofía.

### 1. La opción oficial equivalent: **10 minutes to pandas**

La propia documentación oficial de Pandas tiene una sección diseñada exactamente con el mismo propósito que el capítulo de las _SciPy Lecture Notes_:

- **Sitio web:** [10 minutes to pandas (Guía Oficial)](https://pandas.pydata.org/docs/user_guide/10min.html)
    
- **Estilo:** Es una guía rápida, limpia y directa en formato tutorial. Te da un repaso conciso por la creación de `Series` y `DataFrames`, selección con `.loc` y `.iloc`, filtrado, operaciones, limpieza de datos faltantes y operaciones de agrupar (`groupby`) o unir tablas.
    

### 2. Formato idéntico a Scientific Python: **Python for Scientific Computing (Aalto University)**

Si buscas algo que use prácticamente la misma interfaz web o un esquema idéntico al de `lectures.scientific-python.org`:

- **Sitio web:** [Pandas — Python for Scientific Computing](https://aaltoscicomp.github.io/python-for-scicomp/pandas/)
    
- **Estilo:** Es la extensión en formato libro/nota de clase usada por varias universidades para completar justamente la parte de data science que a veces no viene tan desarrollada en el tutorial clásico de SciPy.
    

### 3. Opción interactiva rápida: **Kaggle Micro-Course: Pandas**

Si prefieres un formato super resumido con teoría mínima y ejercicios prácticos interactivos en Jupyter Notebooks:

- **Sitio web:** [Kaggle Pandas Course](https://www.kaggle.com/learn/pandas)
    
- **Estilo:** Son 6 lecciones cortas de unos 10-15 minutos cada una, enfocadas en ir directo al grano (creación, indexación, funciones de resumen, agrupar, tipos de datos y combinación).
    

### Recomendación de inicio

Si te gustó la claridad y brevedad del enlace de _Scientific Python_, empieza directamente por **10 minutes to pandas**. Aunque el nombre diga "10 minutos", en realidad es la chuleta/resumen definitivo para tener las operaciones básicas listas para consultar.

Si buscas un tutorial en vídeo que mantenga este mismo ritmo conciso y directo para repasar visualmente los fundamentos de Pandas en unos 30 minutos, este recorrido de Tech With Tim es una gran opción:

[Learn Pandas in 30 Minutes - Python Pandas Tutorial](https://www.youtube.com/watch?v=EXIgjIBu4EU)

Este vídeo explica de forma muy ágil la creación de DataFrames, carga de CSVs, indexado y filtrado de datos sin rodeos teóricos.






Totalmente de acuerdo: la documentación oficial de la _Standard Library_ de Python es impecable como manual de referencia, pero insufrible como guía de aprendizaje rápido.

Hay tres recursos muy específicos que hacen exactamente lo que pides: tomar la librería estándar (las funciones integradas o _built-in_ que ya vienen con Python sin instalar nada con `pip`) y explicarlas de forma súper visual, directa y sin rodeos.

### 1. La mejor para consulta rápida: **Python Module of the Week (PyMOTW)**

Es el equivalente en la comunidad a "las notas definitivas" de las librerías integradas.

- **Sitio web:** [PyMOTW 3 (Python Module of the Week)](https://pymotw.com/3/)
    
- **Por qué es perfecta:** El creador (Doug Hellmann) tomó cada módulo nativo (`os`, `sys`, `datetime`, `math`, `json`, `pathlib`, `collections`, etc.) y escribió una explicación de **1 o 2 páginas llena de snippets de código ejecutables**. Va directo a _para qué sirve_ cada módulo y cuáles son sus 3 o 4 funciones principales.
    

### 2. El "mapa mental" interactivo: **Python Built-in Modules Overview (Refactoring.Guru / Real Python)**

Si quieres ver qué existe antes de profundizar, hay dos opciones estructuradas por "categorías de uso":

- **Real Python — Standard Library Guide:** [Python's Standard Library (Guide)](https://www.google.com/search?q=https://realpython.com/python-modules-packages/%23python-standard-library)
    
- **Estilo:** En lugar de listar las 200 librerías por orden alfabético, las agrupa por lo que quieres hacer:
    
    - **Manejo de archivos y sistema:** `os`, `sys`, `pathlib`, `shutil`
        
    - **Formatos de datos:** `json`, `csv`, `sqlite3`
        
    - **Matemáticas y tiempo:** `math`, `datetime`, `random`
        
    - **Estructuras de datos avanzadas:** `collections`, `itertools`
        

### 3. La "Chuleta" Definitiva: **Python Standard Library Cheat Sheet**

Si quieres una única página para tener abierta en una pestaña mientras estás en PyCharm:

- **Sitio web:** [Gits / Interactive Cheat Sheets de Python Standard Library](https://www.google.com/search?q=https://gits.github.io/posts/python-standard-library-cheat-sheet/) o los mapas sintéticos de [pypup.com](https://pypup.com/).
    
- **Estilo:** Solo te muestra el nombre del módulo, la función más importante y un ejemplo de 1 línea.
    

### Los 8 módulos integrados que realmente necesitas el 90% del tiempo

Para que no te abrumes buscando entre las más de 100 librerías nativas, este es el "núcleo duro" que te solucionará casi todo:

|**Módulo**|**Para qué sirve realmente**|**Ejemplo de uso habitual**|
|---|---|---|
|**`pathlib`** / `os`|Trabajar con carpetas, rutas de archivos y el sistema operativo. _(Pista: `pathlib` es la versión moderna y más fácil de `os`)_|`Path("carpeta/archivo.txt").exists()`|
|**`sys`**|Pasar argumentos por consola al script o interactuar con el intérprete.|`sys.exit()` o `sys.argv`|
|**`json`**|Leer y escribir archivos JSON (clave para APIs y configuraciones).|`json.loads()` / `json.dumps()`|
|**`datetime`**|Manejar fechas, horas y calcular diferencias de tiempo.|`datetime.now()`|
|**`math`** / **`random`**|Operaciones matemáticas básicas y generación de números o selecciones al azar.|`random.choice(lista)`|
|**`collections`**|Estructuras de datos avanzadas (contadores, diccionarios por defecto).|`Counter("aabbbc").most_common(1)`|
|**`itertools`**|Bucles eficientes, combinaciones y permutaciones sin gastar memoria.|`itertools.chain()`|
|**`shutil`**|Copiar, mover o borrar carpetas y archivos completos fácilmente.|`shutil.copy("a.txt", "b.txt")`|

> **Un truco en PyCharm:** Cuando importes una de estas librerías (por ejemplo `import pathlib`), en lugar de ir a la web a buscar qué hace, deja pulsado `Ctrl` (o `Cmd` en Mac) y haz clic sobre el nombre de la librería. PyCharm te llevará directamente al archivo de Python nativo con comentarios muy claros sobre cada función.

Tal cual, ¡has captado exactamente la historia y la filosofía del diseño de Python!

Guido van Rossum (el creador de Python) diseñó el "núcleo" del lenguaje (la sintaxis, los bucles, las funciones básicas y los tipos de datos fundamentales como listas y diccionarios), pero lo que realmente hizo explotar a Python fue la filosofía de **"Batteries Included" (Baterías Incluidas)**.

### La filosofía de las "Baterías Incluidas"

A principios de los 90, Guido y la comunidad inicial de Python decidieron que cuando instalases Python en tu ordenador, **no deberías necesitar descargar nada más** para hacer tareas comunes de programación:

- Si necesitabas leer un archivo `.json`, conectarte a una base de datos `sqlite3`, calcular fechas con `datetime` o mover archivos con `shutil`, **todo eso ya debía venir dentro del instalador original**.
    
- De esa parte se encargó la **Python Software Foundation (PSF)** junto con cientos de desarrolladores voluntarios que escribieron la _Standard Library_ (las librerías integradas o _built-in_).
    

### ¿De qué está hecha la Librería Estándar?

Lo curioso es que dentro de la Librería Estándar hay dos "mundos":

1. **Módulos escritos en C puro:** Para que Python sea rápido, muchas librerías _built-in_ (como `math`, `sys` o partes de `json`) no están escritas en Python, sino en **C** (el lenguaje subyacente del intérprete CPython). Son hiperrápidas porque se comunican directo con el procesador.
    
2. **Módulos escritos en Python:** Otras librerías dentro de la Standard Library (como `pathlib` o `collections`) están escritas en código Python normal y corriente, agrupadas y testeadas por la comunidad para que no tengas que escribir tú esa lógica.
    

### Las tres capas de Python (Para no perderte)

Para tener el cuadro completo en tu cabeza, piensa en Python como un edificio de 3 pisos:

```
┌───────────────────────────────────────────────┐
│ 3. El Ecosistema Externo (PyPI / pip)         │  <-- Pandas, NumPy, SciPy, Matplotlib...
│    (Creado por empresas, científicos y la web)│
├───────────────────────────────────────────────┤
│ 2. La Librería Estándar (Built-ins)           │  <-- os, sys, math, json, datetime, pathlib...
│    (Las "baterías incluidas" por la comunidad)│
├───────────────────────────────────────────────┤
│ 1. El Núcleo de Python (Guido van Rossum + C) │  <-- print(), len(), for, if, def, class...
│    (La sintaxis base y el intérprete CPython) │
└───────────────────────────────────────────────┘
```

Por eso te parecía una montaña al principio: ¡estabas intentando procesar de golpe el núcleo, la librería estándar de 30 años de historia y el ecosistema gigantesco de Data Science!

Al usar guías rápidas, simplemente vas seleccionando qué habitación del "piso 2" o del "piso 3" necesitas abrir en cada proyecto dentro de PyCharm.


Cuando vendes un proyecto en un lenguaje interpretado como Python (o JavaScript/Node.js), la protección del código fuente tiene un matiz diferente al de los lenguajes compilados como C++ o Rust, donde solo entregas el archivo ejecutable (`.exe` o binario).

Como en Python el cliente necesita el código ejecutable para correrlo en el intérprete, existen **cuatro estrategias principales**, desde la vía técnica hasta la vía legal:

### 1. El modelo moderno: Convertir tu proyecto en SaaS (Software as a Service)

Es la solución más utilizada hoy en día para proteger la propiedad intelectual al 100%.

- **Cómo funciona:** El código Python se ejecuta en un servidor bajo tu control (en la nube) y el cliente solo interactúa con el programa a través de un navegador web o una API.
    
- **Ventaja:** El cliente jamás llega a tocar ni ver una sola línea de tu código fuente.
    

### 2. Compilar el código a C o Binarios Ejecutables

Si necesitas entregar el programa para que se ejecute **físicamente en el ordenador o servidor del cliente**, no entregues los archivos `.py` en texto plano.

- **Cython:** Transforma tus archivos `.py` a código fuente en C y luego los compila en archivos de biblioteca binaria (`.so` en Linux/Mac o `.pyd` en Windows). El cliente puede importar y usar las funciones, pero no puede leer el código original.
    
- **PyArmor:** Es una herramienta diseñada específicamente para empaquetar y ofuscar scripts de Python. Ofusca el código de bytecode y permite añadir **licencias con fecha de caducidad** o restringir la ejecución a la dirección MAC del ordenador del cliente.
    
- **Nuitka:** Un compilador de Python a C++ que genera directamente un archivo binario ejecutable único, dificultando la ingeniería inversa.
    

### 3. Ofuscación de código (_Code Obfuscation_)

Consiste en pasar tu código fuente por una herramienta que transforma los nombres de variables, clases y funciones en cadenas ilegibles, elimina comentarios y reestructura la lógica para que sea incomprensible para un humano, aunque el programa siga funcionando exactamente igual.

Python

```
# Tu código original
def calcular_impuesto(monto):
    return monto * 0.21

# Código ofuscado (ejemplo conceptual)
def _0x1a(a): return a * 0.21
```

### 4. La protección legal: Licencia y Contrato de Software

En el mundo profesional, la tecnología se combina siempre con la capa legal:

- **Contrato de Propiedad Intelectual / EULA:** En el contrato de venta se especifica claramente que el cliente adquiere una **licencia de uso**, no la propiedad del código fuente, prohibiendo explícitamente la redistribución, reventa o ingeniería inversa.
    
- **Acuerdos de confidencialidad (NDA):** Firmados antes de la entrega del software.
    

### Resumen de estrategia recomendada

| **Caso de uso**                                    | **Solución recomendada**                                                                                                         |
| -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| **Aplicación web o herramienta con base de datos** | Modelo **SaaS** (servidor propio).                                                                                               |
| **Herramienta local instalable en cliente**        | Compilar/Proteger con **PyArmor** o **Cython**.                                                                                  |
| **Proyecto a medida para un cliente corporativo**  | Entregar el código `.py` bajo **Contrato de Licencia estricto** (muchas empresas exigen el código para auditorías de seguridad). |


Exacto, ¡has dado en el clavo! La flexibilidad de Python no es una limitación, sino una decisión de diseño: prioriza la velocidad de desarrollo, y cuando necesitas rendimiento o protección, la industria ya ha creado soluciones como **Cython** o **PyArmor**.

Sobre tu duda respecto a si un archivo **`.so`** (o `.pyd` en Windows) es muy grande: **no, el tamaño no suele ser un problema en absoluto.**

### ¿De qué tamaño estamos hablando?

Para un proyecto típico en Python:

- Un script normal de Python (`.py`) pesa unos pocos **kilobytes** (KB), porque es solo texto.
    
- La versión compilada a `.so` mediante Cython suele pesar entre unos **cientos de KB hasta un par de Megabytes (MB)** por módulo.
    

A no ser que estés programando para un microcontrolador con memoria ultra reducida (como un reloj inteligente o un sensor IoT), **2 o 5 MB de tamaño es algo insignificante** en cualquier ordenador o servidor moderno.

### ¿Por qué el `.so` pesa un poco más que el código fuente?

Cuando Cython traduce tu archivo de Python a C y luego lo compila a binario `.so`:

1. **Añade código de compatibilidad:** Incluye las llamadas internas a la API de CPython para que el intérprete sepa cómo manejar los objetos.
    
2. **Optimiza la ejecución:** Convierte bucles y variables a instrucciones C directas.
    
3. **Ofusca el código:** Tu lógica queda convertida en instrucciones de código máquina (ensamblador/binario), lo que oculta el texto original pero añade una pequeña sobrecarga de estructura al archivo.
    

### La gran ventaja del `.so`

Lo mejor de compilar un módulo a `.so` es la **comodidad de uso**:

Python

```
# En tu script principal de Python importas el módulo .so
# EXACTAMENTE IGUAL que si fuera un archivo .py normal:

import mi_modulo_protegido

mi_modulo_protegido.ejecutar_logica_secreta()
```

Para la persona o cliente que ejecuta el código, el archivo `.so` es totalmente transparente: funciona de forma nativa en Python, corre mucho más rápido y **nadie puede abrirlo con un editor de texto** para copiar tu código.



**¡Exacto! Lo has entendido a la perfección.** Eso es literalmente lo que hace por dentro.

Un `.exe` generado por PyInstaller es en realidad un **archivo comprimido auto-extraíble superinteligente**.

### ¿Qué pasa cuando el usuario hace doble clic en tu `mi_prog.exe`?

En cuestión de milisegundos y de forma **totalmente invisible** para el cliente, ocurren estos 3 pasos:

```
┌────────────────────────────────────────────────────────────────────────┐
│                             mi_prog.exe                                │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │ (Doble Clic)
                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│ 1. Crea una carpeta temporal en el sistema (%TEMP% en Windows)         │
│ 2. Extrae ahí dentro:                                                 │
│    ├── python.exe (el entorno de ejecución)                            │
│    ├── pandas, numpy, etc. (todas las librerías)                      │
│    └── tus archivos (.py, .so / .pyd)                                  │
│ 3. Arranca el programa en silencio y elimina la carpeta al cerrar     │
└────────────────────────────────────────────────────────────────────────┘
```

1. **Crea un espacio privado:** Abre una carpeta temporal oculta en el sistema operativo (en Windows suele ser `C:\Users\Usuario\AppData\Local\Temp\_MEIXXXXXX`).
    
2. **Desempaqueta todo la estructura:** Vuelca en esa carpeta el motor de Python, las carpetas con las librerías (`pandas`, `numpy`, etc.) y tus archivos compilados o scripts.
    
3. **Ejecuta y limpia:** Arranca tu aplicación leyendo todo desde esa carpeta temporal. En cuanto el usuario cierra tu programa, PyInstaller elimina automáticamente esa carpeta sin dejar rastro en su disco.
    

### El "Efecto Profesional"

Para el cliente final, todo este proceso es un **misterio transparente**. Él solo ve lo siguiente:

- No tuvo que instalar Python.
    
- No tuvo que abrir una terminal ni ejecutar comandos `pip install`.
    
- Hizo doble clic en un icono de escritorio (`mi_prog.exe`), la aplicación se abrió y funcionó al instante.
    

Es la forma perfecta de mantener tu forma clásica de distribuir software (_Old School_) usando la potencia moderna de Python.


