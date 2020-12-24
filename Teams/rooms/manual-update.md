---
title: Actualizar manualmente un dispositivo de salas de Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo actualizar manualmente el dispositivo de las salas de Microsoft Teams a una versión específica.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731402"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Actualizar manualmente un dispositivo de salas de Microsoft Teams

La aplicación salas de Microsoft Teams se distribuye a través de Microsoft Store. Las actualizaciones de la aplicación se instalan automáticamente desde Microsoft Store durante el mantenimiento nocturno; Este es el método recomendado para obtener actualizaciones. Sin embargo, hay algunas situaciones en las que un dispositivo de salas de equipos no puede recibir actualizaciones de Microsoft Store. Por ejemplo, es posible que las directivas de seguridad no permitan que los dispositivos se conecten a Internet o que no permitan la descarga de aplicaciones de Microsoft Store. O bien, es posible que desee actualizar un dispositivo antes de realizar la instalación, durante el cual Microsoft Store no está disponible.

Si no puede obtener actualizaciones de Microsoft Store, puede usar un script de PowerShell de actualización de aplicaciones sin conexión para actualizar manualmente los dispositivos de las salas de equipos a una versión más reciente de la aplicación salas de equipos. Siga los pasos que se indican en este artículo para actualizar manualmente los dispositivos de salas de equipos.

> [!NOTE]
> Este proceso solo puede actualizar un dispositivo de salas de equipos con la aplicación salas de equipos ya instalada. No se puede usar para realizar una instalación nueva. Tampoco se puede usar para degradar la aplicación a una versión anterior. Para realizar una nueva instalación de la aplicación salas de equipos, póngase en contacto con el fabricante del dispositivo para obtener medios específicos o vea [preparar los medios de instalación](console.md#prepare-the-installation-media).

## <a name="step-1-download-the-offline-app-update-script"></a>Paso 1: descargar el script de actualización de la aplicación sin conexión

En primer lugar, descargue la última versión del script de actualización de aplicaciones sin conexión. Para descargar el script, haga clic en <https://go.microsoft.com/fwlink/?linkid=2151817> . El script se descargará en la carpeta de descargas predeterminada de su dispositivo.

Los archivos descargados pueden estar marcados como bloqueados por Windows. Si necesita ejecutar el script sin ninguna interacción, tendrá que desbloquear el script. Para desbloquear el script, haga lo siguiente:

1. Haga clic con el botón derecho en el archivo en el explorador de archivos
2. Haga clic en **propiedades**
3. Seleccionar **desbloquear**
4. Haga clic en **Aceptar**

Para desbloquear el script con PowerShell, consulte [unblock-File](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Una vez descargado el script de actualización de la aplicación sin conexión, transfiera el archivo al dispositivo salas de equipos. Puede transferir un archivo al dispositivo mediante una unidad USB o accediendo al archivo desde un recurso compartido de archivos de red mientras está en el modo de administrador del dispositivo. Asegúrese de anotar dónde guarda el archivo en el dispositivo.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Paso 2: ejecutar el script para actualizar la aplicación salas de equipos

El script de actualización de la aplicación sin conexión debe ejecutarse desde un símbolo del sistema con privilegios elevados mientras el usuario de Skype (el usuario en el que se ejecuta la aplicación) aún ha iniciado sesión. Para obtener más información sobre cómo iniciar sesión en una cuenta de administrador para usar el símbolo del sistema con privilegios elevados mientras el usuario de Skype aún ha iniciado sesión, consulte [cambiar al modo de administración y volver cuando se está ejecutando la aplicación salas de Microsoft Teams](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).

Siga este procedimiento para ejecutar el script desde un símbolo del sistema con privilegios elevados:

1. Cambiar al modo de administración
2. Haga clic en el icono Inicio, escriba **símbolo del sistema** y, a continuación, seleccione **Ejecutar como administrador** .
3. Ejecute el siguiente comando `<path to script>` , donde incluye la ruta de acceso completa del script y el nombre del archivo de script:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Por ejemplo, si el archivo de script se encuentra en `C:\Users\Admin\Downloads` y el nombre de archivo de script es `MTR-Update-4.5.6.7.ps1` , ejecute el siguiente comando:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Permita que se ejecute el script. Cuando termine, el script reiniciará el dispositivo de salas de equipos.

También puede ejecutar el script mediante PowerShell remoto. Para obtener más información sobre el uso de PowerShell remoto con dispositivos de salas de equipos, vea [administración remota con PowerShell](rooms-operations.md#remote-management-using-powershell).

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Paso 3: comprobar que la aplicación se ha actualizado correctamente

Si el script se ejecuta correctamente, el dispositivo se reiniciará en la aplicación salas de equipos.

Si la secuencia de comandos encuentra un problema, indicará el problema en la línea de comandos y grabará el resultado en un archivo. Siga las instrucciones proporcionadas por el script. Si necesita ponerse en contacto con el soporte técnico de Microsoft, asegúrese de incluir el archivo de registro junto con la solicitud de asistencia. El script le proporcionará la ruta de acceso al archivo de registro.
