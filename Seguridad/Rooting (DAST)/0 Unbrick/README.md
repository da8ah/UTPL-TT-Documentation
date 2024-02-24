# UNBRICK: Restablecer un dispositivo móvil corrupto

<br/>

⚠ ADVERTENCIA: Sin garantía ninguna, este proceso se realiza para recuperar un dispositivo móvil que ha quedado inservible (brickeado) pero dado que estos problemas pueden llegar a ser específicos de cada dispositivo no se puede asegurar que el proceso funcione exactamente igual en todos los dispositivos.

<br/>

1. Descargar e instalar [Git LFS](https://git-lfs.com/) (Windows)
1. Yo tengo el repositorio de la Documentación en Ubuntu (Linux):
    
    - Ubicarse en el repositorio desde la consola y ejecutar:

    ```bash
    cd UTPL-TT-Documentation/
    ```
    ```bash
    curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | sudo bash
    ```
    ```bash
    sudo apt-get install git-lfs
    ```
    ```bash
    git lfs install
    ```

1. Clonar nuevamente este repositorio para descargar todos los recursos necesarios
1. Tener a la mano esta carpeta `0 Unbrick` con sus recursos

<br/>

## Preparación

<br/>

📌 NOTA: El UNBRICK se lo realizó utilizando Windows por lo que a continuación se indican los pasos para replicar su ejecución en este sistema operativo.

1. El Bootloader debe estar desbloqueado como se indicó en [(DAST)](https://github.com/da8ah/UTPL-TT-Documentation/tree/main/Seguridad/Rooting%20(DAST)#testing-en-dispositivos-m%C3%B3viles-dast)
1. Acceder al `Modo EDL` ([Emergency Download Mode](https://nitorijournal.org/es/android-es/que-es-el-modo-edl-como-ingresar-al-modo-edl-en-cualquier-dispositivo-308.html))
1. Instalar `Qualcomm Drivers`
1. Deshabilitar `antivirus`/`firewall` y `Driver Signature Verification` (Test Mode on/off)
1. Descargar `MSM Tool` para Unbrick
1. Abrir MSM Tool con el móvil **desconectado** de USB:
    - Dejar desmarcada opción `SHA256`
    - Cambiar `Target` a `TMO`
    - Presionar `Start` para empezar ha escuchar conexiones
1. Acceder al Modo EDL **Manualmente**:
    - El dispositivo debe estar desconectado de USB
    - Apagar el dispositivo
    - Mantener ambos botones de volumen presionados
    - Conectar por USB manteniendo los botones (`Manual EDL`)
1. Una vez finalizado desconectar el móvil y salir del Test Mode (`Driver Signature Verification`)

<br/>
