# UTPL | Documentación del Trabajo de Titulación (TT)

Tema: Implementación de la capa de Seguridad en el Ciclo de Vida del Desarrollo de Aplicaciones Móviles

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

```bash
.
│
├───Despliegue
│   │   BookStore               # Backend
│   │   App                     # Cliente
│   │   Manager                 # Administrador
├───Prototipo
│   │   Backend
│   │   Client
│   │   Admin
├───Seguridad                   # SAST/DAST (incluyen tutorial README)
│   │   MobSF (SAST)            # Pruebas mediante MobSF del archivo APK
│   │   Rooting (DAST)          # Pruebas en dispositivos móviles mediante Rooting
│   ├───    0 Unbrick             # Proceso para revivir un móvil si este se Brickea (Migrado a Google Drive)
│
```

<br/>
<br/>

## Replicación Local para ejecutar Aplicaciones

📌 NOTA: El desarrollo de estas aplicaciones se lo realizó utilizando Ubuntu (Linux) por lo que a continuación se indican los pasos para replicar su ejecución en este sistema operativo.

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

## Resultados

De la versión de Despliegue se publicó en Internet tanto el Backend como la aplicación móvil del cliente (App) en los siguientes enlaces:

📌 NOTA: El backend está desplegado a través de un servidor gratuito por lo que debe inicializarse y después de 2 a 5 minutos aproximadamente se pueden realizar peticiones.

- [BookStore API](https://utpl-tt-bookstore.azurewebsites.net/api/books)
- [BookStore (Demo)](https://play.google.com/store/apps/details?id=com.daochoa6.bookstoreapp)

Adicionalmente, si se desean realizar modificaciones a los libros publicados o agregar más se debe crear una build tipo APK del proyecto de la aplicación de administrador (Manager).