
¡Perfecto! Ya con la bóveda correcta abierta en Obsidian, pasamos a conectar Git desde la terminal para que todo quede enlazado con GitHub.

Sigue estos pasos en tu computadora:

1. **Abre tu terminal** (CMD, PowerShell o Git Bash).
    
2. **Navega hasta la carpeta** de tu bóveda escribiendo el comando `cd` seguido de la ruta de tu carpeta:
    
    Bash
    
    ```
    cd ruta/a/tu/carpeta/knowledge-base-md
    ```
    
    _(Sustituye `ruta/a/tu/carpeta/` por la ubicación real donde se encuentra `knowledge-base-md` en tu ordenador)._
    
3. Una vez dentro de la carpeta en la terminal, **ejecuta estos comandos uno por uno**:
    
    - Inicializa el repositorio localmente:
        
        Bash
        
        ```
        git init
        ```
        
    - Prepara todos los archivos actuales para el primer guardado:
        
        Bash
        
        ```
        git add .
        ```
        
    - Guarda los cambios con un mensaje inicial:
        
        Bash
        
        ```
        git commit -m "Primer respaldo inicial de mi boveda"
        ```
        
    - Asegúrate de que la rama principal se llame `main`:
        
        Bash
        
        ```
        git branch -M main
        ```
        
    - Conéctalo con tu repositorio remoto en GitHub:
        
        Bash
        
        ```
        git remote add origin https://github.com/raulcontreraso-bit/knowledge-base-md.git
        ```
        
    - Sube tus archivos por primera vez:
        
        Bash
        
        ```
        git push -u origin main
        ```
        

Avísame en cuanto ejecutes estos comandos para dar el último paso y activar el respaldo automático dentro de Obsidian.