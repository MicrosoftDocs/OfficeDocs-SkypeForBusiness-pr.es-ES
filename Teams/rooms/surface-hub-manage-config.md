---
title: Administrar Microsoft Teams configuración en Surface Hub
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Administrar Microsoft Teams configuración en Surface Hub con Microsoft Intune y Windows Diseñador de configuración
ms.openlocfilehash: d368bed6db1d86e9c97d849d462edd1ff0a21c6d
ms.sourcegitcommit: 3704577b1424c063fd925a58a6f6d0b3ff2c8148
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53278473"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Administrar Microsoft Teams configuración en Surface Hub

Puede administrar la configuración Microsoft Teams en un Surface Hub con Windows de configuración o Microsoft Intune en Microsoft Endpoint Manager. Es necesario tener Windows de configuración o Microsoft Intune para realizar cambios en la configuración Teams configuración. Para obtener más información sobre estas opciones, vea los siguientes artículos:

- [Crear un paquete de aprovisionamiento para Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [¿Qué es Microsoft Intune de dispositivos?](/mem/intune/remote-actions/device-management)

Windows El Diseñador de configuración es una buena opción si solo tiene Surface Hub dispositivos y puede acceder a ellos fácilmente. Si tienes muchos Surface Hubs, o si están en ubicaciones remotas, usa Microsoft Intune en Microsoft Endpoint Manager si está implementado en tu organización. Independientemente del método que elija, debe crear un archivo de configuración XML para realizar cambios en la configuración Teams en Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Teams sintaxis del archivo de configuración

Teams configuración en un Surface Hub se define con un archivo XML. El archivo XML contiene todas las opciones de configuración que se pueden usar para controlar cómo Teams funciona. Tanto Windows diseñador de configuración como Microsoft Intune la misma sintaxis XML. Este es un ejemplo del archivo XML Teams configuración:

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

En la tabla siguiente se describen todas las opciones de configuración disponibles en el archivo de configuración:

| Padres                  | Elemento                                   | Atributo | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ninguna                    | `<SurfaceHubSettings>`                    |           | Contiene todos los elementos de configuración Teams configuración en un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina si Surface Hub anuncia que está disponible para Bluetooth conexiones.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina si Teams automáticamente las reuniones basadas en proximidad.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contiene todos los elementos de configuración para reuniones coordinadas.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina si Teams está configurado para participar en reuniones coordinadas con otros dispositivos.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Esta es una lista separada por comas de UPN para cada dispositivo de sala de Teams o Surface Hub desde el que el dispositivo debe aceptar las solicitudes de unirse a la reunión o a qué solicitudes de unirse a la reunión se deben enviar.<br>Valores aceptados: cadena                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contiene elementos de configuración de audio y vídeo para reuniones coordinadas                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controla la configuración de audio Teams en un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina en qué dispositivo estará activo el micrófono cuando se inicie una reunión. Solo un dispositivo (normalmente un dispositivo Salas de Teams) puede tener este campo establecido en, mientras que el resto de los dispositivos debe tener este campo configurado para evitar el eco de audio y los `true` `false` comentarios.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina si los participantes de una reunión pueden activar o desactivar el micrófono. Los dispositivos en los que **se** establece el valor predeterminado de audio deben tener esta configuración establecida en para que los participantes no puedan activar accidentalmente un micrófono y causar eco de audio o `false` `false` comentarios.<p>Si **audio predeterminado** está establecido en , esta configuración se ignora y los participantes pueden silenciar o activar el `true` micrófono.<br>Valores aceptados: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controla la configuración de vídeo Teams en un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina en qué dispositivo estará activa la cámara cuando se inicie una reunión. Para obtener la mejor experiencia, le recomendamos que solo el Salas de Teams esté establecido en mientras todos los demás dispositivos `true` están establecidos en `false` .<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina si los participantes de una reunión pueden activar o desactivar la cámara. Puede establecer esta opción en cualquier otro dispositivo del evento en el que los participantes quieran compartir diferentes perspectivas de vídeo (por ejemplo, si un participante usa la pizarra `true` Surface Hub vídeo). Si no desea que los participantes activen o desactiven una cámara en un dispositivo, establezca esta opción en `false` .<p> Si **video predeterminado** está establecido en , esta configuración se ignora y los `true` participantes pueden activar o desactivar la cámara.<br>Valores aceptados: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Aplicar Teams configuración a Surface Hub

Aplique o actualice Teams configuración de configuración en Surface Hub con Windows de configuración o Microsoft Intune en Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usar Windows de configuración

Puedes usar Windows de configuración para crear un paquete de aprovisionamiento que puedes usar para aplicar Teams configuración a tus Surface Hubs. Pegará el archivo XML que creó anteriormente en Windows de configuración para crear el paquete de aprovisionamiento.

> [!IMPORTANT]
> Si ya ha aplicado una configuración Teams a su Surface Hub un paquete de aprovisionamiento y desea cambiarlo, primero debe quitar el paquete de aprovisionamiento existente. Para obtener más información, vea [Quitar un paquete de aprovisionamiento creado por Windows Diseñador de configuración.](#remove-a-provisioning-package-created-by-windows-configuration-designer)

Haga lo siguiente para crear el paquete de aprovisionamiento en Windows Diseñador de configuración:

1. Instale Windows de configuración desde la Windows Store en su equipo local y ábralo
2. Seleccione **Aprovisionar Surface Hub dispositivos y,** a **continuación, Cambiar al editor avanzado**
3. En la siguiente pantalla, expanda **WindowsTeamSettings**  >  **Teams** y seleccione **Configuraciones**
4. En el campo junto a **Configuraciones** en el panel central, pegue la única línea de XML que creó anteriormente
5. Seleccione **Exportar paquete** de  >  **aprovisionamiento**
6. Proporcione un nombre para el paquete de aprovisionamiento **en Nombre** y seleccione **Siguiente**  >  **siguiente**
7. Especifique una ubicación para guardar el paquete de aprovisionamiento y seleccione **Siguiente**
8. Seleccione **Compilación** para crear el paquete de aprovisionamiento y, a continuación, **Finalizar**

Por último, después de crear el paquete de aprovisionamiento, haga lo siguiente para aplicar el paquete de aprovisionamiento a su Surface Hub:

1. Guardar el paquete de aprovisionamiento que creó anteriormente en una unidad USB
2. Inserte la unidad USB en su Surface Hub
3. En el Surface Hub, abra el menú Inicio, seleccione Todas las aplicaciones **y,** a continuación, **seleccione Configuración**
4. Proporcione su nombre de usuario y contraseña de administrador y, a continuación, seleccione **Sí**
5. Vaya a **Surface Hub**, **Administración de dispositivos,** Agregar o quitar un paquete de **aprovisionamiento** y, a continuación, **Agregar un paquete**
6. En **Seleccionar un paquete,** seleccione **Agregar** junto al paquete de aprovisionamiento y, a continuación, reinicie el Surface Hub

### <a name="use-microsoft-intune"></a>Use Microsoft Intune

Si los Surface Hubs se administran con Microsoft Intune en Microsoft Endpoint Management, puedes usarlo para aplicar Teams configuración a tus Surface Hubs. Creará un nuevo perfil de configuración y, a continuación, pegará en él el archivo XML que creó anteriormente.

> [!IMPORTANT]
> Los Surface Hubs deben estar en un grupo de dispositivos para que el Microsoft Intune pueda identificar a qué dispositivos aplicar el perfil de configuración. Para obtener información sobre cómo crear un grupo de dispositivos, vea [Agregar grupos para organizar usuarios y dispositivos.](/mem/intune/fundamentals/groups-add)

Haga lo siguiente para crear un perfil de configuración para aplicar Teams configuración a surface hubs:

1. Inicie sesión en Microsoft Endpoint Manager visitandohttps://endpoint.microsoft.com/
2. Vaya a **Perfiles**  >  **de configuración de dispositivos** y seleccione Crear **perfil**
3. En **Plataforma,** selecciona **Windows 10 y versiones posteriores**
4. En **Perfil,** seleccione **Personalizado** y, a continuación, haga clic en **Crear**
5. En la **pestaña Conceptos** básicos, en **Nombre,** proporcione un nombre descriptivo para su perfil de configuración y seleccione **Siguiente**
6. En la **pestaña Configuración,** seleccione **Agregar**
7. En el **panel Agregar fila,** haga lo siguiente:
    1. Proporcione un nombre descriptivo y, opcionalmente, una descripción de la Teams configuración que está agregando
    2. En **OMA-URI,** escriba `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. En **Tipo de datos**, seleccione Cadena **(archivo XML)**
    4. Abra el explorador de archivos, seleccione el archivo XML que creó anteriormente y **Abrir**
8. Seleccione **Agregar** y, a continuación, **Siguiente**
9. En la **pestaña Tareas,** asegúrese de que **Asignar a** está establecido en **Grupos seleccionados**
10. En **Grupos seleccionados,** **selecciona Seleccionar grupos para** incluir y elige el grupo que contiene tus Surface Hubs y, a continuación, selecciona **Seleccionar**
11. Seleccione **Siguiente**, **Siguiente**
12. En revisar **+ crear**, seleccione **Crear**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Quitar Teams configuración de un Surface Hub

Quite Teams configuración de Surface Hub con Windows de configuración o Microsoft Intune en Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Quitar un paquete de aprovisionamiento creado por Windows Diseñador de configuración

Si aplicó Teams configuración a un Surface Hub mediante un paquete de aprovisionamiento creado por el Diseñador de configuración de Windows, siga estos pasos para quitar el paquete y su configuración:

1. En el Surface Hub, abra el menú Inicio, seleccione Todas las aplicaciones **y,** a continuación, **seleccione Configuración**
2. Proporcione su nombre de usuario y contraseña de administrador y, a continuación, seleccione **Sí**
3. Vaya a **Surface Hub**, **Administración de dispositivos** y, a **continuación, Agregar o quitar un paquete de aprovisionamiento**
4. Junto al paquete de aprovisionamiento que quiera quitar, seleccione **Quitar**
5. Vaya a **Surface Hub** y, a continuación, **Aplicaciones & características**
6. Busque **Microsoft Teams para Surface Hub y, a** continuación, seleccione Opciones **avanzadas**
7. Seleccione **Restablecer** y, a continuación, **Restablecer de** nuevo
8. Reinicie el Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Quitar la configuración aplicada por Microsoft Intune

Si aplicó Teams configuración a un Surface Hub con Microsoft Intune en Microsoft Endpoint Management, siga estos pasos para quitar el perfil de configuración y su configuración:

1. Inicie sesión en Microsoft Endpoint Manager visitandohttps://endpoint.microsoft.com/
2. Ir a **Perfiles**  >  **de configuración de dispositivos**
3. Seleccione el perfil de configuración que contiene la configuración de reunión coordinada que desea quitar
4. En la página de detalles del perfil de configuración, **seleccione Eliminar** y, a continuación, **Aceptar**

Después de quitar el perfil de configuración que contenía la configuración de reunión coordinada para su Surface Hub, siga estos pasos para restablecer la aplicación Teams en el Surface Hub:

1. En el Surface Hub, abra el menú Inicio, seleccione Todas las aplicaciones **y,** a continuación, **seleccione Configuración**
2. Proporcione su nombre de usuario y contraseña de administrador y, a continuación, seleccione **Sí**
3. Vaya a **Surface Hub** y, a continuación, **Aplicaciones & características**
4. Busque **Microsoft Teams para Surface Hub y, a** continuación, seleccione Opciones **avanzadas**
5. Seleccione **Restablecer** y, a continuación, **Restablecer de** nuevo
6. Reinicie el Surface Hub