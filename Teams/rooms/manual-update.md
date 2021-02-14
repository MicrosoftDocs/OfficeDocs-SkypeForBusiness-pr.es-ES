---
title: Actualizar manualmente un dispositivo de Salas de Microsoft Teams
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
description: Obtenga información sobre cómo actualizar manualmente el dispositivo de salas de Microsoft Teams a una versión específica.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731402"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Actualizar manualmente un dispositivo de Salas de Microsoft Teams

La aplicación Salas de Microsoft Teams se distribuye a través de Microsoft Store. Las actualizaciones de la aplicación se instalan automáticamente desde Microsoft Store durante el mantenimiento nocturno; este es el método recomendado para obtener actualizaciones. Sin embargo, hay algunas situaciones en las que un dispositivo de Salas de Teams no puede recibir actualizaciones de Microsoft Store. Por ejemplo, es posible que las directivas de seguridad no permitan que los dispositivos se conecten a Internet o que no permitan que las aplicaciones se descarguen de Microsoft Store. O bien, es posible que quieras actualizar un dispositivo antes de realizar la configuración, durante el cual Microsoft Store no está disponible.

Si no puede obtener actualizaciones de Microsoft Store, puede usar un script de PowerShell de actualización de aplicaciones sin conexión para actualizar manualmente los dispositivos de salas de Teams a una versión más reciente de la aplicación Salas de Teams. Siga los pasos de este artículo para actualizar manualmente los dispositivos de salas de Teams.

> [!NOTE]
> Este proceso solo puede actualizar un dispositivo de Salas de Teams con la aplicación Salas de Teams ya instalada. No se puede usar para realizar una nueva instalación. Tampoco se puede usar para degradar la aplicación a una versión anterior. Para realizar una nueva instalación de la aplicación Teams Rooms, póngase en contacto con el fabricante del dispositivo para obtener contenido multimedia específico para él o vea [Preparar el medio de instalación.](console.md#prepare-the-installation-media)

## <a name="step-1-download-the-offline-app-update-script"></a>Paso 1: Descargar el script de actualización de aplicaciones sin conexión

Primero, descargue la última versión del script de actualización de aplicaciones sin conexión. Para descargar el script, haga clic <https://go.microsoft.com/fwlink/?linkid=2151817> en . El script se descargará en la carpeta de descargas predeterminada del dispositivo.

Los archivos descargados pueden estar marcados como bloqueados por Windows. Si necesita ejecutar el script sin ninguna interacción, tendrá que desbloquear el script. Para desbloquear el script, haga lo siguiente:

1. Haga clic con el botón derecho en el archivo en el Explorador de archivos
2. Haga clic **en Propiedades**
3. Seleccione **Desbloquear**
4. Haga clic **en Aceptar**

Para desbloquear el script con PowerShell, vea [Desbloquear archivo.](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)

Después de descargar el script de actualización de aplicaciones sin conexión, transfiera el archivo al dispositivo de Salas de Teams. Puede transferir un archivo al dispositivo mediante una unidad USB o accediendo al archivo desde un recurso compartido de archivos de red mientras está en modo de administración en el dispositivo. Asegúrese de anote dónde guarda el archivo en el dispositivo.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Paso 2: Ejecutar el script para actualizar la aplicación Salas de Teams

El script de actualización de aplicaciones sin conexión debe ejecutarse desde un símbolo del sistema con privilegios elevados mientras el usuario de Skype (el usuario en el que se ejecuta la aplicación) sigue conectado. Para obtener más información sobre cómo iniciar sesión en una cuenta de administrador para usar el símbolo del sistema con privilegios elevados mientras el usuario de Skype todavía está conectado, consulte Cambiar al modo de administración y volver cuando se está ejecutando la aplicación [Microsoft Teams Rooms.](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

Haga lo siguiente para ejecutar el script desde un símbolo del sistema con privilegios elevados:

1. Cambiar al modo de administración
2. Haga clic en el icono Inicio, escriba **Símbolo del sistema** y, después, seleccione Ejecutar como **administrador.**
3. Ejecute el comando siguiente, `<path to script>` donde se incluye la ruta de acceso completa al script y el nombre del archivo de script:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Por ejemplo, si el archivo de script se encuentra en y el nombre del archivo de `C:\Users\Admin\Downloads` script `MTR-Update-4.5.6.7.ps1` es, ejecute el siguiente comando:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Permita que se ejecute el script. Cuando termine, el script reiniciará el dispositivo de Salas de Teams.

También puede ejecutar el script mediante El PowerShell remoto. Para obtener más información sobre el uso de PowerShell remoto con dispositivos de salas de Teams, consulte Administración remota [con PowerShell.](rooms-operations.md#remote-management-using-powershell)

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Paso 3: Comprobar que la aplicación se ha actualizado correctamente

Si el script se ejecuta correctamente, el dispositivo se reiniciará en la aplicación Teams Rooms.

Si el script encuentra un problema, indicará cuál es el problema en la línea de comandos y registrará su salida en un archivo. Siga las instrucciones que proporciona el script. Si necesita ponerse en contacto con el soporte técnico de Microsoft, asegúrese de incluir el archivo de registro junto con la solicitud de soporte técnico. El script le proporcionará la ruta de acceso al archivo de registro.
