---
title: Actualizar manualmente un dispositivo Salas de Microsoft Teams
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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Obtén información sobre cómo actualizar manualmente tu Salas de Microsoft Teams dispositivo a una versión específica.
ms.openlocfilehash: c3128f5b909901da0eb5578f1586aaad785b49a6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267645"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Actualizar manualmente un dispositivo Salas de Microsoft Teams

La aplicación Salas de Microsoft Teams se distribuye a través de Microsoft Store. Novedades a la aplicación se instalan automáticamente desde Microsoft Store durante el mantenimiento nocturno; este es el método recomendado para obtener actualizaciones. Sin embargo, hay algunas situaciones en las que un dispositivo Salas de Teams no puede recibir actualizaciones de Microsoft Store. Por ejemplo, es posible que las directivas de seguridad no permitan que los dispositivos se conecten a Internet o que no permitan la descarga de aplicaciones desde Microsoft Store. O bien, puedes actualizar un dispositivo antes de realizar la configuración, durante el cual Microsoft Store no está disponible.

Si no puedes obtener actualizaciones de Microsoft Store, puedes usar un script de PowerShell de actualización de aplicaciones sin conexión para actualizar manualmente los dispositivos Salas de Teams a una versión más reciente de la aplicación Salas de Teams. Sigue los pasos de este artículo para actualizar manualmente los dispositivos Salas de Teams.

> [!NOTE]
> Este proceso solo puede actualizar un dispositivo Salas de Teams con la aplicación Salas de Teams ya instalada. No se puede usar para realizar una nueva instalación. Tampoco se puede usar para cambiar a una versión anterior de la aplicación. Para realizar una nueva instalación de la aplicación Salas de Teams, ponte en contacto con el fabricante del dispositivo para ver los medios específicos de la aplicación.

## <a name="step-1-download-the-offline-app-update-script"></a>Paso 1: Descargar el script de actualización de la aplicación sin conexión

En primer lugar, descargue la última versión del script de actualización de la aplicación sin conexión. Para descargar el script, haga clic en <https://go.microsoft.com/fwlink/?linkid=2151817>. El script se descargará en la carpeta de descargas predeterminada de su dispositivo.

Los archivos descargados pueden estar marcados como bloqueados por Windows. Si necesita ejecutar el script sin ninguna interacción, tendrá que desbloquear el script. Para desbloquear el script, haga lo siguiente:

1. Haga clic con el botón derecho en el archivo en Explorador de archivos
2. Haga clic en **Propiedades**
3. Seleccionar **Desbloquear**
4. Haga clic en **Aceptar**

Para desbloquear el script con PowerShell, vea [Desbloquear archivo](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Después de descargar el script de actualización de la aplicación sin conexión, transfiera el archivo al dispositivo Salas de Teams. Puedes transferir un archivo al dispositivo mediante una unidad USB o accediendo al archivo desde un recurso compartido de archivos de red mientras estás en modo Administración en el dispositivo. Asegúrese de anotar dónde guarda el archivo en el dispositivo.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Paso 2: Ejecutar el script para actualizar la aplicación de Salas de Teams

El script de actualización de la aplicación sin conexión debe ejecutarse desde un símbolo del sistema con privilegios elevados mientras el usuario de Skype (el usuario en el que se ejecuta la aplicación) aún ha iniciado sesión. Para obtener más información sobre cómo iniciar sesión en una cuenta de administrador para usar el símbolo del sistema con privilegios elevados mientras el usuario de Skype sigue conectado, consulte [Cambiar al modo Administración y volver cuando se bloquea la aplicación Salas de Microsoft Teams](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes).

Haga lo siguiente para ejecutar el script desde un símbolo del sistema con privilegios elevados:

1. Cambiar al modo Administración
2. Haz clic en el icono Inicio, escribe **Símbolo del sistema** y, a continuación, selecciona **Ejecutar como administrador**
3. Ejecute el comando siguiente, donde `<path to script>` se incluye la ruta de acceso completa al script y el nombre del archivo de script:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Por ejemplo, si el archivo de script se encuentra en `C:\Users\Admin\Downloads`y el nombre de archivo de script es `MTR-Update-4.5.6.7.ps1`, ejecute el siguiente comando:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Permita que se ejecute el script. Cuando haya terminado, el script reiniciará el dispositivo Salas de Teams.

También puede ejecutar el script mediante PowerShell remoto. Para obtener más información sobre el uso de PowerShell remoto con dispositivos Salas de Teams, vea [Administración remota con PowerShell](rooms-operations.md#remote-management-using-powershell).

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Paso 3: Comprobar que la aplicación se ha actualizado correctamente

Si el script se ejecuta correctamente, el dispositivo se reiniciará en la aplicación Salas de Teams.

Si el script encuentra un problema, indicará cuál es el problema en la línea de comandos y registrará su salida en un archivo. Siga las instrucciones que proporcione el script. Si necesitas ponerte en contacto con Soporte técnico de Microsoft, asegúrate de incluir el archivo de registro junto con la solicitud de soporte técnico. El script le proporcionará la ruta de acceso al archivo de registro.
