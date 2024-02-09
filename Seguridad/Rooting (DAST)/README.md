# Testing en Dispositivos Móviles (DAST)

<br/>

⚠ ADVERTENCIA: Este proceso lo realicé con la finalidad de investigación, específicamente para este Trabajo de Titulación. No me responsabilizo por ningún daño provocado al seguir este proceso. Sin embargo, si decides continuar te recomiendo utilizar los mismos recursos que comparto para minimizar posibles pérdidas aunque sin ninguna garantía.

<br/>

1. Usar un dispositivo para pruebas, en este caso [OnePlus 7T HD1907](https://a.co/d/cJ2WtwK)
1. Hacer una Copia de seguridad de los archivos y del sistema (se formateará el dispositivo reiteradas veces)
1. Desbloquear Bootloader (arranque) si está bloqueado (para evitar [full-brick](https://xdaforums.com/t/op7t-t-mobile-oos-11-0-1-5-hd63cb-unbrick-tool-to-restore-your-device-to-oxygenos.4004005/))
1. Extraer una imagen (boot.img) con [Oxygen Updater](https://oxygenupdater.com/) y [payload_dumper](https://github.com/vm03/payload_dumper.git)
1. Usar [Magisk](https://github.com/topjohnwu/Magisk/releases) para parchear la imagen
1. Usar la imagen parcheada para Flashear el dispositivo

<br/>
<br/>

## Preparación

📌 NOTA: El testing de estas aplicaciones se lo realizó utilizando Windows por lo que a continuación se indican los pasos para replicar su ejecución en este sistema operativo.

1. Contar con el dispositivo y haber respaldado tanto el sistema como la información

1. [Obtener Winget desde la Microsoft Store](https://www.microsoft.com/p/app-installer/9nblggh4nns1#activetab=pivot:overviewtab)

1. Instalar dependencias desde PowerShell

    IDs:
    - `Google.PlatformTools`

    <br/>

    ```bash
    winget install <id>
    ```

1. Instalar [Drivers de OnePlus](https://oneplusdriver.com/download-oneplus-driver#download)

1. Agregar las siguientes Variables de Entorno

    - `Google.PlatformTools`
    - `C:\Program Files (x86)\OnePlus USB Drivers\Android`

## Desbloquear bootloader

1. Activar el modo desarrollador en el dispositivo

<br/>

<div align="center" style="width:100%;display:flex;flex-direction:row;justify-content:space-evenly;align-items:flex-start;">
<img style="width:20%" src="./img/bootloader1.jpg" >
<img style="width:20%" src="./img/bootloader2.jpg" >
<img style="width:20%" src="./img/bootloader3.jpg" >
<img style="width:20%" src="./img/bootloader4.jpg" >
</div>

<br/>