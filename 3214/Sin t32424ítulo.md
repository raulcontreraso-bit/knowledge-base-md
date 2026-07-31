Hacer enlaces a carpetas de Google Drive (o incluso a carpetas y archivos locales de tu ordenador) dentro de Obsidian es muy fácil.

Aquí te muestro cómo se hace de las dos formas para que las apliques en tu nueva estructura:

### 1. Enlazar una carpeta o archivo de Google Drive

Como Google Drive vive en la nube, la forma de enlazarlo es usando su URL web:

1. Ve a tu Google Drive, haz clic derecho sobre la carpeta o archivo que quieras enlazar y selecciona **Compartir** > **Copiar enlace**.
    
2. En tu nota de Obsidian, puedes poner el enlace de dos formas muy limpias:
    
    - **Como enlace directo de texto:**
        
        Markdown
        
        ```
        [Carpeta de Libros de Programación en Drive](https://drive.google.com/drive/folders/tu-codigo-de-enlace-aqui)
        ```
        
    - **Como botón o mención limpia:** Si prefieres que se vea como un enlace clásico de Markdown, simplemente pégalo o usa `[Nombre que quieras](URL)`.
        

### 2. Enlazar carpetas o archivos de tu propio ordenador (Windows / Linux)

Si estás en una nota y quieres poner un acceso directo para abrir una carpeta local de tu disco duro (por ejemplo, el código de un proyecto), Obsidian te permite usar un enlace especial llamado **URI**:

- **Para abrir una carpeta local:**
    
    Markdown
    
    ```
    [Abrir carpeta de proyectos local](file:///C:/Users/TuUsuario/Ruta/A/Tu/Carpeta)
    ```
    
    _(Si estás en Linux, la ruta cambiaría a algo como `file:///home/tuusuario/ruta/a/tu/carpeta`)._
    

**Un truco avanzado en Obsidian:** Si quieres enlazar una nota _con otra nota_ dentro de tu misma bóveda (por ejemplo, conectar un curso con una carpeta), solo tienes que escribir doble corchete `[[` y empezar a escribir el nombre de la nota o carpeta, y Obsidian te autocompletará el enlace al instante.