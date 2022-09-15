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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Administrar la configuración de Microsoft Teams en Surface Hub con Microsoft Intune y diseñador de configuración de Windows
ms.openlocfilehash: 7296ed84cf34b47c562cb3ab5f5582fe1eec58ac
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705979"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Administrar la configuración de Microsoft Teams en Surface Hub

Puedes administrar la configuración de Microsoft Teams en Surface Hub con el Diseñador de configuración de Windows o Microsoft Intune en Microsoft Endpoint Manager. Se necesitan conocimientos del Diseñador de configuración de Windows o Microsoft Intune para realizar cambios en la configuración de Teams. Para obtener más información sobre estas opciones, vea los artículos siguientes:

- [Crear un paquete de aprovisionamiento para Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [¿Qué es la administración de dispositivos Microsoft Intune?](/mem/intune/remote-actions/device-management)

El Diseñador de configuración de Windows es una buena opción si solo tienes unos pocos dispositivos Surface Hub y puedes acceder a ellos fácilmente. Si tienes muchos Surface Hub o están en ubicaciones remotas, usa Microsoft Intune en Microsoft Endpoint Manager si se implementa en tu organización. Independientemente del método que elija, deberá crear un archivo de configuración XML para realizar cambios en la configuración de Teams en Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Sintaxis del archivo de configuración de Teams

La configuración de Teams en Surface Hub se define mediante un archivo XML. El archivo XML contiene todas las opciones de configuración que se pueden usar para controlar el funcionamiento de Teams. Tanto el Diseñador de configuración de Windows como Microsoft Intune usan la misma sintaxis XML. Este es un ejemplo del archivo XML de configuración de Teams:

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

| Padre                  | Elemento                                   | Atributo | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ninguna                    | `<SurfaceHubSettings>`                    |           | Contiene todos los elementos de configuración de la configuración de Teams en Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina si Surface Hub anuncia que está disponible para conexiones Bluetooth.<br>Valores aceptados: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina si Teams aceptará automáticamente reuniones basadas en proximidad.<br>Valores aceptados: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contiene todos los elementos de configuración de Reuniones coordinadas.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina si Teams está configurado para participar en reuniones coordinadas con otros dispositivos.<br>Valores aceptados: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Esta es una lista de UPN separados por comas para cada dispositivo Salas de Teams o Surface Hub desde el que el dispositivo debe aceptar convocatorias de unión a una reunión, o a la que se deben enviar convocatorias de unión a una reunión.<br>Valores aceptados: cadena                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contiene elementos de configuración de audio y vídeo para reuniones coordinadas                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controla la configuración de audio de Teams en Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina en qué dispositivo estará activo el micrófono cuando se inicie una reunión. Solo un dispositivo (normalmente un dispositivo de Salas de Teams) puede tener este campo establecido`true`, mientras que el resto de los dispositivos deben tener este campo configurado para `false` evitar el eco de audio y los comentarios.<br>Valores aceptados: `true`, `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina si los participantes de una reunión pueden activar o desactivar el micrófono. Los dispositivos en los que el **valor predeterminado de Audio** esté establecido `false` deberían tener esta configuración establecida para `false` que los participantes no puedan activar accidentalmente un micrófono y generar eco de audio o comentarios.<p>Si **audio predeterminado** está establecido en `true`, esta configuración se ignora y los participantes pueden silenciar o reactivar el micrófono.<br>Valores aceptados: `true`, `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controla la configuración de vídeo de Teams en Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina en qué dispositivo estará activa la cámara cuando se inicie una reunión. Para obtener la mejor experiencia, recomendamos que solo se establezca `true` el dispositivo Salas de Teams mientras que el resto de dispositivos estén establecidos en `false`.<br>Valores aceptados: `true`, `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina si los participantes de una reunión pueden activar o desactivar la cámara. Puedes establecerlo `true` en cualquier otro dispositivo del evento en el que los participantes quieran compartir diferentes perspectivas del vídeo (por ejemplo, si un participante usa la pizarra interactiva de Surface Hub). Si no desea que los participantes activen o desactiven una cámara en un dispositivo, establezca esta opción `false`en .<p> Si **el valor predeterminado del vídeo** es `true`, esta configuración se ignora y los participantes pueden activar o desactivar la cámara.<br>Valores aceptados: `true`, `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Aplicar la configuración de Teams a Surface Hub

Aplique o actualice la configuración de Teams en Surface Hub con el Diseñador de configuración de Windows o Microsoft Intune en Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usar el Diseñador de configuración de Windows

Puedes usar el Diseñador de configuración de Windows para crear un paquete de aprovisionamiento que puedes usar para aplicar la configuración de Teams a surface hubs. Pegará el archivo XML que creó anteriormente en el Diseñador de configuración de Windows para crear el paquete de aprovisionamiento.

> [!IMPORTANT]
> Si ya has aplicado la configuración de Teams a Surface Hub con un paquete de aprovisionamiento y quieres cambiarlo, primero debes quitar el paquete de aprovisionamiento existente. Para obtener más información, consulta [Quitar un paquete de aprovisionamiento creado por el Diseñador de configuración de Windows](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Haz lo siguiente para crear el paquete de aprovisionamiento en el Diseñador de configuración de Windows:

1. Instala el Diseñador de configuración de Windows desde la Tienda Windows en el equipo local y ábrelo
2. Selecciona **Aprovisionar dispositivos Surface Hub** y, a continuación, **Cambiar al editor avanzado**
3. En la siguiente pantalla, expanda **WindowsTeamSettings** > **Teams** y seleccione **Configuraciones**
4. En el campo situado junto a **Configuraciones** en el panel central, pegue la única línea de XML que creó anteriormente
5. Selecciona **Exportar** > **paquete de aprovisionamiento**
6. Proporciona un nombre para el paquete de aprovisionamiento en **Nombre** y selecciona **Siguiente** > **Siguiente**
7. Especifica una ubicación para guardar el paquete de aprovisionamiento y selecciona **Siguiente**
8. Selecciona **Compilar** para crear el paquete de aprovisionamiento y, a continuación, **Finalizar**

Por último, después de crear el paquete de aprovisionamiento, haz lo siguiente para aplicar el paquete de aprovisionamiento a Surface Hub:

1. Guarda el paquete de aprovisionamiento que creaste anteriormente en una unidad USB
2. Insertar la unidad USB en Surface Hub
3. En Surface Hub, abre el menú Inicio, selecciona **Todas las aplicaciones** y, a continuación, selecciona **Configuración**
4. Proporciona tu nombre de usuario y contraseña de administrador y, a continuación, selecciona **Sí**
5. Ve a **Surface Hub**, **Administración de dispositivos**, **Agregar o quitar un paquete de aprovisionamiento** y, a continuación, **Agregar un paquete**
6. En **Seleccionar un paquete**, selecciona **Agregar** junto al paquete de aprovisionamiento y, a continuación, reinicia Surface Hub

### <a name="use-microsoft-intune"></a>Usar Microsoft Intune

Si los Surface Hub se administran con Microsoft Intune en Administración de puntos de conexión de Microsoft, puedes usarlos para aplicar la configuración de Teams a Surface Hubs. Creará un nuevo perfil de configuración y, a continuación, pegará el archivo XML que creó anteriormente en él.

> [!IMPORTANT]
> Los Surface Hub deben estar en un grupo de dispositivos para que el Microsoft Intune pueda identificar a qué dispositivos aplicar el perfil de configuración. Para obtener información sobre cómo crear un grupo de dispositivos, vea [Agregar grupos para organizar usuarios y dispositivos](/mem/intune/fundamentals/groups-add).

Haz lo siguiente para crear un perfil de configuración para aplicar la configuración de Teams a surface hubs:

1. Inicia sesión en Microsoft Endpoint Manager visitandohttps://endpoint.microsoft.com/
2. Vaya a **Perfiles de configuración de** **dispositivos** >  y seleccione **Crear perfil**
3. En **Plataforma**, selecciona **Windows 10 y posteriores**
4. En **Perfil**, seleccione **Personalizado** y, a continuación, haga clic en **Crear**.
5. En la pestaña **Conceptos básicos** , en **Nombre**, proporcione un nombre descriptivo para el perfil de configuración y seleccione **Siguiente**
6. En la pestaña **Configuración** , seleccione **Agregar**
7. En el panel **Agregar fila** , haga lo siguiente:
    1. Proporcione un nombre descriptivo y, opcionalmente, una descripción de la configuración de Teams que va a agregar.
    2. En **OMA-URI**, escriba `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. En **Tipo de datos**, seleccione **Cadena (archivo XML)**
    4. Abre el explorador de archivos, selecciona el archivo XML que creaste anteriormente y **Abre**
8. Selecciona **Agregar** y, a continuación **, Siguiente**
9. En la pestaña **Tareas** , asegúrese de que **Asignar a** está establecido en **Grupos seleccionados**
10. En **Grupos seleccionados**, selecciona **Seleccionar grupos para incluir** y elige el grupo que contiene los Surface Hubs y, a continuación, selecciona **Seleccionar**
11. Selecciona **Siguiente**, **Siguiente**
12. En **Revisar y crear**, seleccione **Crear**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Quitar la configuración de Teams de Surface Hub

Quite la configuración de Teams en Surface Hub con el Diseñador de configuración de Windows o Microsoft Intune en Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Quitar un paquete de aprovisionamiento creado por el Diseñador de configuración de Windows

Si aplicó la configuración de Teams a Surface Hub con un paquete de aprovisionamiento creado por el Diseñador de configuración de Windows, siga estos pasos para quitar el paquete y su configuración:

1. En Surface Hub, abre el menú Inicio, selecciona **Todas las aplicaciones** y, a continuación, selecciona **Configuración**
2. Proporciona tu nombre de usuario y contraseña de administrador y, a continuación, selecciona **Sí**
3. Ve a **Surface Hub**, **Administración de dispositivos** y, a continuación, **Agregar o quitar un paquete de aprovisionamiento**
4. Junto al paquete de aprovisionamiento que quieres quitar, selecciona **Quitar**
5. Ve a **Surface Hub** y, a continuación, **Aplicaciones & características**
6. Busca **Microsoft Teams para Surface Hub** y, a continuación, selecciona **Opciones avanzadas**
7. Selecciona **Restablecer** y, a continuación, **Restablecer** de nuevo
8. Reiniciar Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Quitar la configuración aplicada por Microsoft Intune

Si aplicó la configuración de Teams a Surface Hub con Microsoft Intune en Administración de puntos de conexión de Microsoft, siga estos pasos para quitar el perfil de configuración y su configuración:

1. Inicia sesión en Microsoft Endpoint Manager visitandohttps://endpoint.microsoft.com/
2. Ir a **Perfiles****de configuración de dispositivos** > 
3. Seleccione el perfil de configuración que contiene la configuración de reunión coordinada que desea quitar
4. En la página de detalles del perfil de configuración, selecciona **Eliminar** y, a continuación **, Aceptar**

Después de quitar el perfil de configuración que contenía la configuración de reunión coordinada de Surface Hub, siga estos pasos para restablecer la aplicación Teams en Surface Hub:

1. En Surface Hub, abre el menú Inicio, selecciona **Todas las aplicaciones** y, a continuación, selecciona **Configuración**
2. Proporciona tu nombre de usuario y contraseña de administrador y, a continuación, selecciona **Sí**
3. Ve a **Surface Hub** y, a continuación, **Aplicaciones & características**
4. Busca **Microsoft Teams para Surface Hub** y, a continuación, selecciona **Opciones avanzadas**
5. Selecciona **Restablecer** y, a continuación, **Restablecer** de nuevo
6. Reiniciar Surface Hub
