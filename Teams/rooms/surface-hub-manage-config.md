---
title: Administrar la configuración de Microsoft Teams en Surface Hub
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
description: Administrar la configuración de Microsoft Teams en Surface Hub con Microsoft Intune y el Diseñador de configuración de Windows
ms.openlocfilehash: 9c16fa4875febd3c9e0a8457626db5e09bf90545
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117388"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Administrar la configuración de Microsoft Teams en Surface Hub

Puede administrar la configuración de Microsoft Teams en Surface Hub con el Diseñador de configuración de Windows o Microsoft Intune en Microsoft Endpoint Manager. Es necesario tener conocimientos sobre el Diseñador de configuración de Windows o Microsoft Intune para realizar cambios en la configuración de Teams. Para obtener más información sobre estas opciones, vea los siguientes artículos:

- [Crear un paquete de aprovisionamiento para Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [¿Qué es la administración de dispositivos de Microsoft Intune?](/mem/intune/remote-actions/device-management)

El Diseñador de configuración de Windows es una buena opción si solo tienes algunos dispositivos Surface Hub y puedes acceder a ellos fácilmente. Si tienes muchos Surface Hubs o si están en ubicaciones remotas, usa Microsoft Intune en Microsoft Endpoint Manager si está implementado en tu organización. Independientemente del método que elija, debe crear un archivo de configuración XML para realizar cambios en la configuración de Teams en Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Sintaxis del archivo de configuración de Teams

La configuración de Teams en Surface Hub se define con un archivo XML. El archivo XML contiene todas las opciones de configuración que se pueden usar para controlar el funcionamiento de Teams. Tanto el Diseñador de configuración de Windows como Microsoft Intune usan la misma sintaxis XML. Este es un ejemplo del archivo XML de configuración de Teams:

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
| Ninguna                    | `<SurfaceHubSettings>`                    |           | Contiene todos los elementos de configuración para la configuración de Teams en un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina si Surface Hub anuncia que está disponible para Bluetooth conexiones.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina si Teams aceptará automáticamente reuniones basadas en proximidad.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contiene todos los elementos de configuración para reuniones coordinadas.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina si Teams está configurado para participar en reuniones coordinadas con otros dispositivos.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Esta es una lista separada por comas de UPN para cada dispositivo de sala de Teams o Surface Hub desde el que el dispositivo debe aceptar las solicitudes de unirse a la reunión o a qué solicitudes de unirse a la reunión se deben enviar.<br>Valores aceptados: cadena                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contiene elementos de configuración de audio y vídeo para reuniones coordinadas                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controla la configuración de audio de Teams en Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina en qué dispositivo estará activo el micrófono cuando se inicie una reunión. Solo un dispositivo (normalmente un dispositivo salas de Teams) puede tener este campo establecido en, mientras que el resto de los dispositivos debe tener este campo configurado para evitar el eco de audio y los `true` `false` comentarios.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina si los participantes de una reunión pueden activar o desactivar el micrófono. Los dispositivos en los que **se** establece el valor predeterminado de audio deben tener esta configuración establecida en para que los participantes no puedan activar accidentalmente un micrófono y causar eco de audio o `false` `false` comentarios.<p>Si **audio predeterminado** está establecido en , esta configuración se ignora y los participantes pueden silenciar o activar el `true` micrófono.<br>Valores aceptados: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controla la configuración de vídeo de Teams en Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina en qué dispositivo estará activa la cámara cuando se inicie una reunión. Para obtener la mejor experiencia, le recomendamos que solo el dispositivo Salas de Teams esté establecido en mientras todos los demás dispositivos `true` están establecidos en `false` .<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina si los participantes de una reunión pueden activar o desactivar la cámara. Puedes establecer esta opción en cualquier otro dispositivo del evento en el que los participantes quieran compartir diferentes perspectivas de vídeo (por ejemplo, si un participante usa la pizarra de `true` Surface Hub). Si no desea que los participantes activen o desactiven una cámara en un dispositivo, establezca esta opción en `false` .<p> Si **video predeterminado** está establecido en , esta configuración se ignora y los `true` participantes pueden activar o desactivar la cámara.<br>Valores aceptados: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Aplicar la configuración de Teams a Surface Hub

Aplique o actualice la configuración de Teams en Surface Hub con el Diseñador de configuración de Windows o Microsoft Intune en Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usar el Diseñador de configuración de Windows

Puedes usar el Diseñador de configuración de Windows para crear un paquete de aprovisionamiento que puedes usar para aplicar la configuración de Teams a tus Surface Hubs. Pegará el archivo XML que creó anteriormente en el Diseñador de configuración de Windows para crear el paquete de aprovisionamiento.

> [!IMPORTANT]
> Si ya ha aplicado la configuración de Teams a Surface Hub con un paquete de aprovisionamiento y desea cambiarlo, primero debe quitar el paquete de aprovisionamiento existente. Para obtener más información, vea [Quitar un paquete de aprovisionamiento creado por el Diseñador de configuración de Windows.](#remove-a-provisioning-package-created-by-windows-configuration-designer)

Haga lo siguiente para crear el paquete de aprovisionamiento en el Diseñador de configuración de Windows:

1. Instalar el Diseñador de configuración de Windows desde la Tienda Windows en el equipo local y abrirlo
2. Selecciona **Aprovisionar dispositivos Surface Hub** **y, a continuación, Cambiar al editor avanzado**
3. En la siguiente pantalla, expanda **WindowsTeamSettings**  >  **Teams** y seleccione **Configuraciones**
4. En el campo junto a **Configuraciones** en el panel central, pegue la única línea de XML que creó anteriormente
5. Seleccione **Exportar paquete** de  >  **aprovisionamiento**
6. Proporcione un nombre para el paquete de aprovisionamiento **en Nombre** y seleccione **Siguiente**  >  **siguiente**
7. Especifique una ubicación para guardar el paquete de aprovisionamiento y seleccione **Siguiente**
8. Seleccione **Compilación** para crear el paquete de aprovisionamiento y, a continuación, **Finalizar**

Por último, después de crear el paquete de aprovisionamiento, haga lo siguiente para aplicar el paquete de aprovisionamiento a Surface Hub:

1. Guardar el paquete de aprovisionamiento que creó anteriormente en una unidad USB
2. Insertar la unidad USB en Surface Hub
3. En Surface Hub, abre el menú Inicio, selecciona Todas las **aplicaciones** y, a continuación, selecciona **Configuración**
4. Proporcione su nombre de usuario y contraseña de administrador y, a continuación, seleccione **Sí**
5. Ve a **Surface Hub,** **Administración de dispositivos,** **Agregar o quitar un paquete de aprovisionamiento** y, a **continuación, Agregar un paquete**
6. En **Seleccionar un paquete,** selecciona **Agregar** junto al paquete de aprovisionamiento y, a continuación, reinicia tu Surface Hub

### <a name="use-microsoft-intune"></a>Usar Microsoft Intune

Si los Surface Hubs se administran con Microsoft Intune en Microsoft Endpoint Management, puedes usarlo para aplicar la configuración de Teams a tus Surface Hubs. Creará un nuevo perfil de configuración y, a continuación, pegará en él el archivo XML que creó anteriormente.

> [!IMPORTANT]
> Los Surface Hub deben estar en un grupo de dispositivos para que Microsoft Intune pueda identificar a qué dispositivos aplicar el perfil de configuración. Para obtener información sobre cómo crear un grupo de dispositivos, vea [Agregar grupos para organizar usuarios y dispositivos.](/mem/intune/fundamentals/groups-add)

Haga lo siguiente para crear un perfil de configuración para aplicar la configuración de Teams a surface hubs:

1. Inicie sesión en Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Vaya a **Perfiles**  >  **de configuración de dispositivos** y seleccione Crear **perfil**
3. En **Plataforma,** selecciona **Windows 10 y versiones posteriores**
4. En **Perfil,** seleccione **Personalizado** y, a continuación, haga clic en **Crear**
5. En la **pestaña Conceptos** básicos, en **Nombre,** proporcione un nombre descriptivo para su perfil de configuración y seleccione **Siguiente**
6. En la **pestaña Configuración,** seleccione **Agregar**
7. En el **panel Agregar fila,** haga lo siguiente:
    1. Proporcione un nombre descriptivo y, opcionalmente, una descripción de la configuración de Teams que está agregando
    2. En **OMA-URI,** escriba `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. En **Tipo de datos**, seleccione Cadena **(archivo XML)**
    4. Abra el explorador de archivos, seleccione el archivo XML que creó anteriormente y **Abrir**
8. Seleccione **Agregar** y, a continuación, **Siguiente**
9. En la **pestaña Tareas,** asegúrese de que **Asignar a** está establecido en **Grupos seleccionados**
10. En **Grupos seleccionados,** **selecciona Seleccionar grupos para** incluir y elige el grupo que contiene tus Surface Hubs y, a continuación, selecciona **Seleccionar**
11. Seleccione **Siguiente**, **Siguiente**
12. En revisar **+ crear**, seleccione **Crear**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Quitar la configuración de Teams de un Surface Hub

Quite la configuración de Teams en Surface Hub con el Diseñador de configuración de Windows o Microsoft Intune en Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Quitar un paquete de aprovisionamiento creado por el Diseñador de configuración de Windows

Si aplicó la configuración de Teams a Surface Hub con un paquete de aprovisionamiento creado por el Diseñador de configuración de Windows, siga estos pasos para quitar el paquete y su configuración:

1. En Surface Hub, abre el menú Inicio, selecciona Todas las **aplicaciones** y, a continuación, selecciona **Configuración**
2. Proporcione su nombre de usuario y contraseña de administrador y, a continuación, seleccione **Sí**
3. Ve a **Surface Hub,** **Administración de dispositivos** y, **a continuación, Agrega o quita un paquete de aprovisionamiento**
4. Junto al paquete de aprovisionamiento que quiera quitar, seleccione **Quitar**
5. Ve a **Surface Hub** y, a continuación, Aplicaciones **& características**
6. Buscar **Microsoft Teams para Surface Hub** y, a continuación, seleccionar Opciones **avanzadas**
7. Seleccione **Restablecer** y, a continuación, **Restablecer de** nuevo
8. Reiniciar Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Quitar la configuración aplicada por Microsoft Intune

Si aplicó la configuración de Teams a Surface Hub con Microsoft Intune en Microsoft Endpoint Management, siga estos pasos para quitar el perfil de configuración y su configuración:

1. Inicie sesión en Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Ir a **Perfiles**  >  **de configuración de dispositivos**
3. Seleccione el perfil de configuración que contiene la configuración de reunión coordinada que desea quitar
4. En la página de detalles del perfil de configuración, **seleccione Eliminar** y, a continuación, **Aceptar**

Después de quitar el perfil de configuración que contenía la configuración de reunión coordinada de Surface Hub, siga estos pasos para restablecer la aplicación Teams en Surface Hub:

1. En Surface Hub, abre el menú Inicio, selecciona Todas las **aplicaciones** y, a continuación, selecciona **Configuración**
2. Proporcione su nombre de usuario y contraseña de administrador y, a continuación, seleccione **Sí**
3. Ve a **Surface Hub** y, a continuación, Aplicaciones **& características**
4. Buscar **Microsoft Teams para Surface Hub** y, a continuación, seleccionar Opciones **avanzadas**
5. Seleccione **Restablecer** y, a continuación, **Restablecer de** nuevo
6. Reiniciar Surface Hub