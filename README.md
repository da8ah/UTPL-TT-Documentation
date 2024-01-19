# UTPL | Documentación del Trabajo de Titulación (TT)

Tema: Implementación de la capa de seguridad en el ciclo de vida del desarrollo de aplicaciones móviles

## Escenarios de Prueba

La propuesta de seguridad elaborada en el Trabajo de Titulación se implementará en el desarrollo de dos aplicaciones móviles que se describen a continuación: una librería (BookStore) requiere agilizar las ventas por Internet, motivo por el que se propone desarrollar dos aplicaciones móviles a la medida con seguridad. Una aplicación móvil para el vendedor (administrador) y otra para el comprador (cliente). El rol administrador permite a un usuario gestionar todas las actividades relacionadas al negocio de la venta de libros pudiendo mantener y modificar un registro de los libros y revisar las transacciones realizadas en el sistema. El rol cliente puede mediante el sistema revisar todos los libros disponibles para la venta y adquirir los que desee. Este proyecto cuenta con las siguientes características: 

- Se requieren dos aplicaciones móviles: administrador (Manager) y cliente (App) para la librería “BookStore”.
- Las aplicaciones deben ser del tipo nativas para el sistema operativo de Android.
- Se empleará el lenguaje de programación Typescript y el framework React Native.
- El proyecto deberá ser gestionado con la metodología de desarrollo SCRUM.
- Se debe construir un backend (API) con Arquitectura Limpia, y se presupone que ha sido asegurado con el estándar ASVS.
- En el diseño de la arquitectura de las aplicaciones móviles se requiere utilizar el patrón arquitectónico MVVM.
- Se emplean como herramientas: VSCode para el desarrollo, y para realizar pruebas SAST y DAST se utilizan MobSF y NowSecure.

El objetivo de este proyecto es analizar la seguridad de las aplicaciones móviles. Los resultados se obtuvieron mediante la implementación de la seguridad en los escenarios de prueba especificados. Se realizaron dos implementaciones de la seguridad en los mismos escenarios de prueba para realizar una comparativa: 

- Prototipo: implementación de la seguridad de forma tardía, y
- Despliegue: implementación con la propuesta de seguridad definida en el segundo capítulo.

## Estructura del Repositorio

## Replicación Local para ejecutar Aplicaciones

⚠ NOTA: El desarrollo de estas aplicaciones se lo realizó utilizando Ubuntu (Linux) por lo que a continuación se indican los pasos para replicar su ejecución en este sistema operativo.

### Node y NPM con NVM (Ubuntu)

1. Instalar nvm

    ```bash
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
    sudo apt update -y
    ```

1. Recargar la Terminal

    ```bash
    nvm -v
    ```

1. Instalar una versión de Node y NPM

    ```bash
    nvm ls
    ```

    (Recomendado)
    ```bash
    nvm install lts/hydrogen
    ```
    (Última versión estable)
    ```bash
    nvm install --lts
    ```

1. Cambiar de versión en caso de tener otras

    (Última versión estable)
    ```bash
    nvm use --lts
    ```

1. Verificar Node y NPM

    ```bash
    node -v
    npm -v
    ```

1. Desinstalar (en caso de fallas)

    ```bash
    nvm deactivate
    nvm uninstall node
    ```

### Backend

1. Clonar el repositorio

    ```bash
    git clone <repo-url>
    ```
    ```bash
    cd <repo-name>
    ```

1. Instalar PNPM mediante NPM

    ```bash
    npm install -g pnpm
    ```

1. Instalar dependencias

    ```bash
    pnpm i
    ```

1. Ejecutar y Testear

    ```bash
    pnpm start
    pnpm test
    ```

### Aplicaciones Móviles

1. Clonar el repositorio

    ```bash
    git clone <repo-url>
    ```
    ```bash
    cd <repo-name>
    ```

1. Instalar dependencias con NPM

    ```bash
    npm i
    ```

1. Ejecutar y Testear

    ```bash
    npm start
    npm test
    ```

<br/>
<br/>

## Replicación Local para SAST/DAST de Aplicaciones Móviles

⚠ NOTA: El testing de estas aplicaciones se lo realizó utilizando Windows por lo que a continuación se indican los pasos para replicar su ejecución en este sistema operativo.

### Testing mediante MobSF (SAST)

1. [Obtener Winget desde la Microsoft Store](https://www.microsoft.com/p/app-installer/9nblggh4nns1#activetab=pivot:overviewtab)

1. Instalar dependencias desde PowerShell

    IDs:
    - `Git.Git`
    - `Python.Python.3.8`
    - `Oracle.JavaRuntimeEnvironment`
    - `Oracle.JDK.19` (o 20)
    - `Microsoft.VisualStudio.2022.BuildTools`
    - `ShiningLight.OpenSSL`
    - `wkhtmltopdf.wkhtmltox`

    <br/>

    ```bash
    winget install -i <id>
    ```

1. Agregar las siguientes Variables de Entorno

    - `Python3.8`
    - `jre1.8.0`
    - `jdk-19`
    - `wkhtmltopdf`

1. Clonar el repositorio

    ```bash
    git clone https://github.com/MobSF/Mobile-Security-Framework-MobSF.git
    ```

1. Instalar MobSF

    ```bash
    cd Mobile-Security-Framework-MobSF
    ```
    ```bash
    .\setup.bat
    ```

1. Ejecutar MobSF

    ```bash
    cd Mobile-Security-Framework-MobSF
    ```
    ```bash
    .\run.bat 127.0.0.1:8000
    ```

### Testing en Dispositivos Móviles (DAST)

⚠ ADVERTENCIA: Este proceso lo realicé con la finalidad de investigación, específicamente para este Trabajo de Titulación. No me responsabilizo por ningún daño provocado al seguir este proceso. Sin embargo, si decides continuar te recomiendo utilizar los mismos recursos que comparto para minimizar posibles pérdidas, y sin la garantía de que todo funcione de la misma manera.

1. Usar un dispositivo para pruebas, en este caso [OnePlus 7T HD1907](https://a.co/d/cJ2WtwK)
1. Hacer una Copia de seguridad de los archivos y del sistema (se formateará el dispositivo)
1. Desbloquear Bootloader (arranque) si está bloqueado (para evitar [full-brick](https://xdaforums.com/t/op7t-t-mobile-oos-11-0-1-5-hd63cb-unbrick-tool-to-restore-your-device-to-oxygenos.4004005/))
1. Extraer una imagen (boot.img) con [Oxygen Updater](https://oxygenupdater.com/) y [payload_dumper](https://github.com/vm03/payload_dumper.git)
1. Usar [Magisk](https://github.com/topjohnwu/Magisk/releases) para parchear la imagen
1. Usar la imagen parcheada para Flashear el dispositivo