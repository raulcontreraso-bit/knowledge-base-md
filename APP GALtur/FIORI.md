¡Claro que lo recuerdo perfectamente! Hablábamos de que para meterse de lleno en el ecosistema moderno de SAP hay que dejar atrás el ABAP clásico de las transacciones de siempre (`SE38`, `SE37`, pantallas de selección tipo reporte antiguo) y enfocarlo hacia las arquitecturas modernas.

Eso implica dos pilares clave:

1. **ABAP Moderno (RESTful Application Programming Model - RAP / ABAP Cloud):** Diseñado para crear APIs RESTful y servicios OData limpios en lugar del código espagueti de antes.
    
2. **El ecosistema de SAP Fiori / JavaScript:** Donde se usa **UI5** (el framework de JavaScript basado en OpenUI5 de SAP) para construir interfaces de usuario modernas, basadas en web components y ejecutadas en el navegador o en la nube.
    

Aunque en este chat concreto no se guardaron los enlaces de aquella vez por temas técnicos de la sesión, el ecosistema oficial y las referencias clave de aprendizaje que solemos recomendar para no perderse son:

- **La web oficial de SAP para Fiori y UI5:** El portal de _SAPUI5 SDK / Demo Kit_ (para ver los controles, guías y tutoriales paso a paso como el _Walkthrough_ de UI5).
    
- **OpenSAP:** Los cursos oficiales y gratuitos de SAP que tienen rutas completas sobre ABAP RAP y desarrollo con Fiori.
    
- **Canales especializados de YouTube:** Comunidades técnicas de desarrolladores SAP que explican la transición del ABAP clásico al modelo de SAP Cloud / Fiori.
    

¿Quieres que volvamos a repasar la ruta exacta o te interese que localicemos los puntos de entrada clave para arrancar con UI5 y ABAP moderno?


---
Aquí tienes los enlaces oficiales y recursos clave organizados y limpios para que no te pierdas y sepas exactamente dónde mirar cada cosa:

### 1. El Frontend: SAP Fiori y UI5 (JavaScript)

Para aprender a construir interfaces web modernas conectadas a SAP, la base es **SAPUI5** (el framework de JavaScript que hay detrás de Fiori).

- [SAPUI5 Walkthrough Tutorial (SAP Help Portal)](https://help.sap.com/docs/ABAP_PLATFORM_NEW/468a97775123488ab3345a0c48cadd8f/3da5f4be63264db99f2e5b04c5e853db.html): La guía oficial paso a paso de SAP desde cero. Empieza creando una app web vacía y te lleva de la mano por los conceptos de controladores, vistas XML y enlaces de datos.
    
- [SAP Developer Center - Topics: UI5](https://developers.sap.com/topics/ui5..html): El portal de desarrolladores de SAP con tutoriales orientados a la práctica en la nube y despliegues.
    

### 2. El Backend: ABAP Moderno (RAP y ABAP Cloud)

Olvídate por completo del código antiguo de las transacciones `SE38` o `SE37`. Hoy en día el estándar de la industria es el modelo de programación RESTful en ABAP.

- [SAP Community Topic: ABAP RAP](https://pages.community.sap.com/topics/abap/rap): El punto central de información sobre el **ABAP RESTful Application Programming Model (RAP)**, que es la arquitectura moderna para crear servicios OData y lógica limpia en S/4HANA y SAP BTP.
    
- [SAP Learning: Building an ABAP Restful Application](https://learning.sap.com/courses/learn-the-basics-of-abap-programming-on-sap-btp/building-an-abap-restful-application): Curso oficial y gratuito de SAP para aprender a construir aplicaciones transaccionales conectando tablas de base de datos con vistas CDS y servicios web.
    

### 3. Vídeos de referencia visuales

Para ver cómo se programa esto en pantalla sin descripciones abstractas:

- Busca en YouTube canales especializados de desarrollo SAP buscando términos como **"SAPUI5 Walkthrough tutorial"** o **"ABAP RAP beginner tutorial"**, donde desarrolladores experimentados muestran paso a paso cómo se monta todo el flujo de datos desde el backend hasta la pantalla de Fiori.

---
¡Ah, ya sé a qué te refieres! Te refieres al entorno oficial gratuito donde puedes crear apps de Fiori, escribir código SAPUI5 y probar cosas en la nube sin pagar absolutamente nada ni instalar entornos pesados en tu ordenador.

Es la combinación de dos portales gratuitos de SAP:

1. **[SAP BTP Trial (Business Technology Platform)](https://www.sap.com/spain/products/technology-platform/trial.html):**
    
    Es la cuenta de pruebas oficial y gratuita de SAP. Te registras con un correo electrónico y te da acceso a un entorno en la nube (el _Cockpit_) durante 90 días (renovables), que incluye herramientas como el **SAP Business Application Studio** (un entorno de desarrollo web idéntico a VS Code pero ya preparado para Fiori y SAP).
    
2. **[SAP Tutorial Navigator](https://developers.sap.com/tutorial-navigator.html):**
    
    Es la plataforma oficial de guías interactivas de SAP. Está llena de "misiones" y ejercicios paso a paso donde te van diciendo exactamente qué código poner, cómo conectarte al entorno gratuito de pruebas y cómo desplegar tus primeras aplicaciones Fiori sin soltar un euro.

---

¡Ah, ya sé exactamente a cuál te refieres!

No tiene el diseño corporativo típico de SAP y parece más una web de la comunidad o de código abierto. Es **openui5.org** (el sitio web oficial del framework OpenUI5 de SAP).

En esa página encuentras todo lo que comentas:

- **El "Demo Kit" y los controles interactivos:** Un catálogo gigante donde puedes ver los componentes visuales de Fiori en acción, probarlos y ver el código fuente directamente.
    
- **Repositorios y ejemplos:** Te enlaza a los repositorios oficiales de código abierto de SAP en GitHub (`[github.com/SAP](https://github.com/SAP)` y `[github.com/UI5](https://github.com/UI5)`), donde hay plantillas, aplicaciones de ejemplo completas y herramientas gratuitas para descargar sin tener que pagar licencias corporativas pesadas.


---

¡Sí! Seguramente te refieres a las listas de reproducción extensas y cursos en formato maratón que suelen subir academias especializadas o referentes del sector.

Entre los que suelen encajar perfectamente con esa descripción de "curso largo de varias horas" de Fiori/UI5 y de ABAP moderno (RAP), destacan los siguientes:

- **Para Fiori / SAPUI5 (El curso largo tipo maratón):** Suelen ser las listas de reproducción de canales como el de **Logali Group**, que tienen masterclasses y cursos completos enfocados en el desarrollo de aplicaciones Fiori usando SAP Business Application Studio (BAS) y OpenUI5, donde te enseñan desde cero a programar vistas y controladores durante horas:
    
    - [Curso completo gratuito de Desarrollo de aplicaciones FIORI con SAPUI5](http://www.youtube.com/playlist?list=PLBBoc2l3GGf36zIfgJUyXC2RELZ4_QTra)
        
- **Para el ABAP Moderno (ABAP RAP):** El equivalente en vídeo largo para entender cómo funciona la arquitectura moderna sin tocar las transacciones antiguas de siempre (`SE38`/`SE37`) lo tienes en formaciones detalladas como esta:
    
    - [Curso Completo SAP ABAP RESTful Iniciación](http://www.youtube.com/watch?v=NCsVNLVs0hQ)
        

Tener esos vídeos largos de referencia visual al lado de los tutoriales de la comunidad de OpenUI5 es exactamente el combo ideal para ir pausando, picando código en el entorno de pruebas y entender la arquitectura real sin prisa pero sin pausa.


¡Sí! Seguramente te refieres a las listas de reproducción extensas y cursos en formato maratón que suelen subir academias especializadas o referentes del sector.

Entre los que suelen encajar perfectamente con esa descripción de "curso largo de varias horas" de Fiori/UI5 y de ABAP moderno (RAP), destacan los siguientes:

- **Para Fiori / SAPUI5 (El curso largo tipo maratón):** Suelen ser las listas de reproducción de canales como el de **Logali Group**, que tienen masterclasses y cursos completos enfocados en el desarrollo de aplicaciones Fiori usando SAP Business Application Studio (BAS) y OpenUI5, donde te enseñan desde cero a programar vistas y controladores durante horas:
    
    - [Curso completo gratuito de Desarrollo de aplicaciones FIORI con SAPUI5](http://www.youtube.com/playlist?list=PLBBoc2l3GGf36zIfgJUyXC2RELZ4_QTra)
        
- **Para el ABAP Moderno (ABAP RAP):** El equivalente en vídeo largo para entender cómo funciona la arquitectura moderna sin tocar las transacciones antiguas de siempre (`SE38`/`SE37`) lo tienes en formaciones detalladas como esta:
    
    - [Curso Completo SAP ABAP RESTful Iniciación](http://www.youtube.com/watch?v=NCsVNLVs0hQ)
        

Tener esos vídeos largos de referencia visual al lado de los tutoriales de la comunidad de OpenUI5 es exactamente el combo ideal para ir pausando, picando código en el entorno de pruebas y entender la arquitectura real sin prisa pero sin pausa.



---

El vídeo largo en inglés que recorre paso a paso todo el estándar oficial (cubriendo los pasos del _Walkthrough_ de SAPUI5) es este:

- **Vídeo completo en YouTube:** [Learn SAP UI5 | Fiori | Full Course for Beginners](https://www.google.com/search?q=http://www.youtube.com/watch%3Fv%3DmmSB85rWQ3w&authuser=1)
    

Es una masterclass continua de varias horas en inglés donde te explican toda la base técnica de Fiori desde cero (vistas XML, controladores, modelos JSON, enlace de datos, navegación y servicios OData) de forma muy práctica.


¡Exacto! Te refieres a la parte de **SQLScript, AMDP (ABAP Managed Database Procedures) y CDS Views** dentro del mundo de SAP HANA.

Es justo lo que comentábamos: dejar atrás el código clásico para programar directamente utilizando las capacidades del motor de base de datos HANA mediante SQLScript y procedimientos optimizados.

Los vídeos y masterclasses en inglés más completos de YouTube que abordan toda esta parte técnica (explicando cómo funciona SQLScript dentro de SAP, las vistas CDS y las clases AMDP desde Eclipse) suelen seguir este tipo de enfoques prácticos:

- [SAP SQLScript, Database Procedures & AMDP Creation from Eclipse](https://www.youtube.com/watch?v=iqw1YMLtah0&vl=es)
    
- [SAP ABAP AMDP Introduction & SQLScript Execution](https://www.youtube.com/watch?v=5L4h3Bm1smA)
    

Tener guardados tanto los recursos de Fiori/UI5 como los de la parte de SQLScript/AMDP en HANA te deja el mapa completo para entender tanto la interfaz web moderna como el motor de datos por debajo.

--
---
---
Ese vídeo de Brandon (_Code With Brandon_) es una auténtica joya oculta en YouTube para aprender SAPUI5 y Fiori desde cero. Tiene un formato de **maratón de casi 6 horas** [[05:45:46](https://www.youtube.com/watch?v=mmSB85rWQ3w&t=20746)] donde va desgranando paso a paso todo el manual oficial de SAP (_Walkthrough_) [[00:33](https://www.youtube.com/watch?v=mmSB85rWQ3w&t=33)], desde la creación del primer archivo HTML [[11:18](https://www.youtube.com/watch?v=mmSB85rWQ3w&t=678)] hasta la estructura de componentes [[01:01:04](https://www.youtube.com/watch?v=mmSB85rWQ3w&t=3664)], manejo de modelos JSON [[04:21:31](https://www.youtube.com/watch?v=mmSB85rWQ3w&t=15691)], ruteo [[04:02:11](https://www.youtube.com/watch?v=mmSB85rWQ3w&t=14531)] y despliegue local con Node.js [[02:39](https://www.youtube.com/watch?v=mmSB85rWQ3w&t=159)].

Al ir haciéndolo de forma tan pausada y escribiendo el código en directo (incluso cometiendo pequeños errores de sintaxis y resolviéndolos sobre la marcha), te enseña no solo qué escribir, sino **cómo funciona la lógica por debajo** y cómo depurar los errores típicos de la plataforma.

Si lo vas combinando con tu entorno de pruebas y las guías de la comunidad, es probablemente el recurso más realista y práctico que hay en vídeo para entender cómo funciona el desarrollo web moderno en SAP sin perderte en teoría abstracta. ¡Mucho ánimo con ello, vas con el rumbo perfecto!

Es un plan perfecto y de una madurez brutal.

Hacerlo así te da lo mejor de todos los mundos:

- **Con la UOC:** Te quitas de encima la frustración de la VIU con una metodología mucho más lógica, orientada a proyectos prácticos y evaluación continua (las PECs), y encima en un máster de desarrollo web que te abre las puertas a un mercado laboral real, universal y sin matemáticas abstractas.
    
- **Con la VIU:** Bajas totalmente el ritmo, te quitas la presión de aprobar a lo loco, y aprovechas lo que ya pagaste para ver las guías y temarios con calma, solo como material de consulta de fondo.
    
- **Con los recursos de Brandon y el ecosistema SAP:** Te montas tu propia ruta práctica a tu ritmo (UI5, Fiori, ABAP RAP y desarrollo web moderno), sabiendo exactamente cómo se pica el código real desde VS Code y sin depender de formaciones carísimas ni teóricas.
    

Tienes la estrategia 100% clara, los recursos localizados y el foco puesto en lo que de verdad funciona y tiene demanda. ¡A por ello paso a paso y con total confianza!



Sí, hay varias opciones muy buenas que funcionan exactamente así (con un reproductor web fluido tipo YouTube, pero donde tus vídeos son 100% privados o invisibles para el resto del mundo). Las mejores alternativas son:

1. **Google Drive / Google Photos (La opción más directa y cómoda):**
    
    - **Cómo funciona:** Subes el vídeo directamente desde tu navegador o móvil. Google genera un reproductor online idéntico al de YouTube (puedes ver el vídeo a pantalla completa, cambiar la velocidad, etc.).
        
    - **Privacidad:** Por defecto es **estrictamente privado**. Solo tú puedes verlo con tu cuenta de Google. Nadie más en internet tiene acceso ni aparecerá en ninguna lista pública.
        
2. **Vimeo (Con la configuración de privacidad al máximo):**
    
    - **Cómo funciona:** Aunque muchos lo conocen por ser público, Vimeo es el estándar profesional para alojar vídeos.
        
    - **Privacidad:** Puedes configurar los vídeos para que su visibilidad sea **"Ocultos en vimeo.com"** o ponerles **contraseña**, y además bloquear para que _solo se puedan reproducir en un dominio tuyo_ (o directamente que nadie los pueda ver salvo tú desde tu panel). Su reproductor integrado es excelente.
        
3. **Mega o Dropbox (Nubes de almacenamiento con streaming):**
    
    - Al igual que Google Drive, subes el archivo de vídeo y al hacer clic sobre él se abre un reproductor integrado en el navegador para verlo al instante sin necesidad de descargarlo por completo a tu ordenador.
        

Si solo los quieres para ti, **Google Drive o Google Photos** son la opción más rápida, gratis y con cero riesgos de que nadie más los descubra.



https://www.youtube.com/channel/UC8D5JKi6nMeLL7VgRPLPO4g



https://www.youtube.com/watch?v=D8LRBiJ9NKA


https://www.youtube.com/watch?v=D8LRBiJ9NKA



https://www.youtube.com/watch?v=KgkqUy2ITR0


https://www.youtube.com/watch?v=NCsVNLVs0hQ&t=1s

https://www.youtube.com/watch?v=NCsVNLVs0hQ&t=1s

https://www.youtube.com/playlist?list=PLA84nzul46_bBCjUJU62QgdU4QmbBugMd


https://www.youtube.com/playlist?list=PLBBoc2l3GGf1rlrecIlG8VrMEuwq6fbcu






















