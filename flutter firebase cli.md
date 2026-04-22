Para integrar Firebase en tu proyecto de Flutter de manera profesional, es fundamental contar con las herramientas de línea de comandos (CLI). Aquí tienes la guía completa paso a paso para preparar tu entorno en Windows.

---

## 1. Verificación de Node.js y npm
Antes de instalar nada, verifica si ya tienes las herramientas instaladas (muchas veces vienen con otros entornos de desarrollo).

* Abre una terminal (PowerShell o CMD).
* Escribe los siguientes comandos:
    * `node -v`
    * `npm -v`

> **¿Qué versión utilizar?** Para el año 2026, lo ideal es utilizar la versión **LTS (Long Term Support)** de Node.js (actualmente la **v20.x** o superior). Firebase CLI requiere como mínimo la **v18.0.0**.

---

## 2. Instalación de Node.js (Si no lo tienes)
Si los comandos anteriores fallaron, sigue estos pasos:

1.  **Descarga:** Ve al sitio oficial [nodejs.org](https://nodejs.org/) y descarga el instalador **.msi** de la versión **LTS**.
2.  **Ejecución:** Abre el archivo descargado.
3.  **Configuración:** Sigue el asistente de instalación. **Importante:** Asegúrate de que la opción *"Add to PATH"* esté seleccionada (viene marcada por defecto).
4.  **Herramientas adicionales:** El instalador te preguntará si deseas instalar "Tools for Native Modules"; puedes marcarlo si planeas hacer desarrollo avanzado, pero no es estrictamente necesario para Firebase.
5.  **Finalizar:** Reinicia tu terminal para que reconozca los cambios.

---

## 3. Instalación Global de Firebase CLI
Una vez que `npm` funciona, instalaremos las herramientas de Firebase para que estén disponibles en todo tu sistema.

1.  Abre la terminal como **Administrador** (clic derecho en el botón de Inicio -> Terminal/PowerShell (Administrador)).
2.  Ejecuta el siguiente comando:
    ```bash
    npm install -g firebase-tools
    ```
    * El parámetro `-g` significa **Global**, permitiéndote usar el comando `firebase` en cualquier carpeta de tu PC.

---

## 4. Comandos de Firebase y Flutter

### Acceder a Firebase con Google
Para vincular tu terminal con tu consola de Firebase:
1.  En la terminal, escribe:
    ```bash
    firebase login
    ```
2.  Se abrirá una ventana en tu navegador. Selecciona tu cuenta de Google y otorga los permisos.
3.  Si tienes éxito, la terminal mostrará: `Success! Logged in as [tu-correo]`.

### Vincular tu App de Flutter
Para Flutter específicamente, hoy en día se utiliza el **FlutterFire CLI**, que automatiza la configuración de archivos como `google-services.json`.

1.  **Instala el CLI de FlutterFire:**
    ```bash
    dart pub global activate flutterfire_cli
    ```
2.  **Configura tu proyecto:** (Dentro de la carpeta de tu app de Flutter):
    ```bash
    flutterfire configure
    ```
    * Este comando te permitirá seleccionar tu proyecto de Firebase y creará automáticamente el archivo `firebase_options.dart` en tu carpeta `lib/`.

### Comandos útiles de `firebase-tools`
| Comando | Propósito |
| :--- | :--- |
| `firebase projects:list` | Muestra todos tus proyectos de Firebase. |
| `firebase init` | Inicia la configuración de servicios (Hosting, Firestore, etc.) en tu carpeta local. |
| `firebase deploy` | Sube tus cambios o reglas a la nube de Firebase. |
| `firebase logout` | Cierra la sesión de tu cuenta actual. |

¿Deseas que te ayude con el código necesario para inicializar Firebase dentro del archivo `main.dart` de tu aplicación?
