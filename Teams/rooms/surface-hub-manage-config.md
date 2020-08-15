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
description: Administrar la configuración de Microsoft Teams en Surface Hub con Microsoft Intune y el diseñador de configuración de Windows
ms.openlocfilehash: 3e254d7f7afbd918e8279d2dc7b100ebbfdc3daf
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761460"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Administrar la configuración de Microsoft Teams en Surface Hub

Puede administrar la configuración de Microsoft Teams en un Surface Hub con el diseñador de configuración de Windows o Microsoft Intune en Microsoft Endpoint Manager. El conocimiento del diseñador de configuración de Windows o Microsoft Intune es necesario para realizar cambios en la configuración de Teams. Para obtener más información sobre estas opciones, vea los artículos siguientes:

- [Crear un paquete de aprovisionamiento para Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)
- [¿Qué es la administración de dispositivos de Microsoft Intune?](https://docs.microsoft.com/mem/intune/remote-actions/device-management)

El diseñador de configuración de Windows es una buena opción si solo tiene algunos dispositivos Surface Hub y puede acceder a ellos fácilmente. Si tiene muchos centros de superficie, o si están en ubicaciones remotas, use Microsoft Intune en Microsoft Endpoint Manager si se ha implementado en su organización. Independientemente del método que elija, necesita crear un archivo de configuración XML para realizar cambios en la configuración de Teams en Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Sintaxis del archivo de configuración de Teams

La configuración de Teams en Surface Hub se define con un archivo XML. El archivo XML contiene toda la configuración que se puede usar para controlar el funcionamiento de Teams. Tanto el diseñador de configuración de Windows como Microsoft Intune usan la misma sintaxis XML. Este es un ejemplo del archivo XML de configuración de Teams:

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

| Matriz                  | Elemento                                   | Atributo | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ninguna                    | `<SurfaceHubSettings>`                    |           | Contiene todos los elementos de configuración de la configuración de Teams en Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina si Surface Hub anuncia que está disponible para las conexiones Bluetooth.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina si Teams aceptará automáticamente reuniones basadas en proximidad.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contiene todos los elementos de configuración de reuniones coordinadas.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina si Teams está configurado para participar en reuniones coordinadas con otros dispositivos.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Esta es una lista separada por comas de UPN para cada dispositivo de la sala de equipos o Surface Hub en el que el dispositivo debe aceptar solicitudes de participación en la reunión de, o a las que se deben enviar solicitudes de unirse a la reunión.<br>Valores aceptados: cadena                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contiene elementos de configuración de audio y vídeo de configuración para reuniones coordinadas                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controla la configuración de audio de Teams en Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina en qué dispositivo estará activo el micrófono cuando se inicie una reunión. Solo un dispositivo (generalmente un dispositivo de salas de equipos) puede tener este campo establecido en `true` mientras que el resto de los dispositivos debe tener este campo establecido en `false` para evitar el eco y la retroalimentación de audio.<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina si los participantes de una reunión pueden activar o desactivar el micrófono. Los dispositivos en los que se establece el **valor predeterminado de audio** `false` deben tener esta configuración establecida en para `false` que los participantes no puedan activar accidentalmente un micrófono y causar eco o comentarios de audio.<p>Si se establece el **valor predeterminado de audio** `true` , se omite esta configuración y los participantes pueden desactivar o reactivar el micrófono.<br>Valores aceptados: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controla la configuración de video de Teams en Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina el dispositivo en el que la cámara estará activa cuando se inicie una reunión. Para obtener la mejor experiencia, le recomendamos que solo se establezca el dispositivo salas de equipos `true` mientras todos los demás dispositivos están configurados en `false` .<br>Valores aceptados: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina si los participantes de una reunión pueden activar o desactivar la cámara. Puede establecer esta configuración en `true` en cualquier otro dispositivo de los participantes del evento que deseen compartir diferentes perspectivas de vídeo (como si un participante usa la pizarra de Surface hub). Si no desea que los participantes enciendan o apaguen una cámara en un dispositivo, establezca este valor en `false` .<p> Si el **valor predeterminado de vídeo** se establece en `true` , esta configuración se omite y los participantes pueden activar o desactivar la cámara.<br>Valores aceptados: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Aplicar la configuración de Teams a Surface Hub

Aplique o actualice las opciones de configuración de Teams en Surface Hub con el diseñador de configuración de Windows o Microsoft Intune en Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usar el diseñador de configuración de Windows

Puede usar el diseñador de configuración de Windows para crear un paquete de aprovisionamiento que puede usar para aplicar la configuración de Teams a Surface Hub. Pegará el archivo XML que ha creado anteriormente en el diseñador de configuración de Windows para crear el paquete de aprovisionamiento.

> [!IMPORTANT]
> Si ya ha aplicado la configuración de Teams a su Surface Hub con un paquete de aprovisionamiento y desea cambiarla, tendrá que quitar el paquete de aprovisionamiento existente en primer lugar. Para obtener más información, vea [quitar un paquete de aprovisionamiento creado por el diseñador de configuración de Windows](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Siga este procedimiento para crear el paquete de aprovisionamiento en el diseñador de configuración de Windows:

1. Instalar el diseñador de configuración de Windows desde la tienda Windows en el equipo local y abrirlo
2. Seleccione **aprovisionar dispositivos Surface Hub** y, a continuación, **cambie al editor avanzado**
3. En la siguiente pantalla, expanda **WindowsTeamSettings**  >  **Teams** y seleccione **configuraciones**
4. En el campo que se encuentra junto a **configuraciones** en el panel central, pegue la línea única de XML que creó anteriormente.
5. Seleccionar **Export**el  >  **paquete de aprovisionamiento** de exportación
6. Escriba un nombre para el paquete de aprovisionamiento en **nombre** y seleccione **siguiente**  >  **Next**
7. Especifique una ubicación para guardar el paquete de aprovisionamiento y seleccione **siguiente**
8. Seleccione **compilación** para crear el paquete de aprovisionamiento y, a continuación, **finalice**

Por último, después de crear el paquete de aprovisionamiento, siga este procedimiento para aplicar el paquete de aprovisionamiento a su Surface Hub:

1. Guardar el paquete de aprovisionamiento que ha creado anteriormente en una unidad USB
2. Insertar la unidad USB en el Surface Hub
3. En su Surface Hub, abra el menú Inicio, seleccione **todas las aplicaciones**y, después, seleccione **configuración** .
4. Proporcione el nombre de usuario y la contraseña del administrador y, después, seleccione **sí**
5. Ir a **Surface Hub**, **Administración de dispositivos**, **Agregar o quitar un paquete de aprovisionamiento**y, a continuación, **Agregar un paquete**
6. En **seleccionar un paquete**, seleccione **Agregar** junto al paquete de aprovisionamiento y, a continuación, reinicie Surface Hub.

### <a name="use-microsoft-intune"></a>Usar Microsoft Intune

Si sus Surface Hub se administran con Microsoft Intune en Microsoft Endpoint Management, puede usarlo para aplicar la configuración de Teams a Surface Hub. Creará un nuevo perfil de configuración y, a continuación, pegará en él el archivo XML que creó anteriormente.

> [!IMPORTANT]
> Los concentradores de Surface tienen que estar en un grupo de dispositivos para que Microsoft Intune pueda identificar a qué dispositivos se debe aplicar el perfil de configuración. Para obtener más información sobre cómo crear un grupo de dispositivos, vea [agregar grupos para organizar usuarios y dispositivos](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).

Siga este procedimiento para crear un perfil de configuración que aplique la configuración de Teams a Surface Hub:

1. Para iniciar sesión en Microsoft Endpoint Manager, visite https://endpoint.microsoft.com/
2. Vaya a **Devices**  >  **perfiles de configuración** de dispositivos y seleccione **crear perfil** .
3. En **plataforma**, seleccione **Windows 10 y versiones posteriores** .
4. En **perfil**, seleccione **personalizado**y, a continuación, haga clic en **crear** .
5. En la pestaña **conceptos básicos** , en **nombre**, escriba un nombre descriptivo para el perfil de configuración y seleccione **siguiente**
6. En la pestaña **Opciones de configuración** , seleccione **Agregar** .
7. En el panel **Agregar fila** , haga lo siguiente:
    1. Proporcione un nombre descriptivo y, opcionalmente, una descripción de la configuración de teams que está agregando
    2. En **OMA-URI**, escriba `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. En **tipo de datos**, seleccione **cadena (archivo XML)** .
    4. Abra el explorador de archivos, seleccione el archivo XML que ha creado anteriormente y **abra**
8. Seleccione **Agregar** y, a continuación, **siguiente**
9. En la pestaña **tareas** , asegúrese de que **asignar a** está establecido en **grupos seleccionados** .
10. En **grupos seleccionados**, seleccione **seleccionar grupos para incluir** y elija el grupo que contiene los Surface Hub y, a continuación, seleccione **seleccionar**
11. Seleccione **siguiente**, **junto**
12. En el **repaso + crear**, seleccione **crear** .

## <a name="remove-teams-settings-from-a-surface-hub"></a>Quitar la configuración de Teams de un Surface Hub

Quite la configuración de configuración de Teams en Surface Hub con el diseñador de configuración de Windows o Microsoft Intune en Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Quitar un paquete de aprovisionamiento creado por el diseñador de configuración de Windows

Si ha aplicado la configuración de Teams a un Surface Hub con un paquete de aprovisionamiento creado por el diseñador de configuración de Windows, siga estos pasos para quitar el paquete y su configuración:

1. En su Surface Hub, abra el menú Inicio, seleccione **todas las aplicaciones**y, después, seleccione **configuración** .
2. Proporcione el nombre de usuario y la contraseña del administrador y, después, seleccione **sí**
3. Ir a **Surface Hub**, **Administración de dispositivos** y, a continuación, **Agregar o quitar un paquete de aprovisionamiento**
4. Junto al paquete de aprovisionamiento que desea quitar, seleccione **quitar** .
5. Ir a **Surface Hub** y, a continuación, **aplicaciones & características**
6. Busque **Microsoft Teams para Surface Hub** y, a continuación, seleccione **Opciones avanzadas** .
7. Seleccione **restablecer**y, a continuación, **restablecer**
8. Reiniciar Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Quitar la configuración aplicada por Microsoft Intune

Si ha aplicado la configuración de Teams a un Surface Hub con Microsoft Intune en administración de extremos de Microsoft, siga estos pasos para quitar el perfil de configuración y su configuración:

1. Para iniciar sesión en Microsoft Endpoint Manager, visite https://endpoint.microsoft.com/
2. Navegar a **Devices**  >  **perfiles de configuración** de dispositivos
3. Seleccione el perfil de configuración que contiene la configuración de reunión coordinada que desea quitar.
4. En la página Detalles del perfil de configuración, seleccione **eliminar** y, a continuación, **Aceptar**

Después de quitar el perfil de configuración que contenía la configuración de reunión coordinada de su Surface Hub, realice los siguientes pasos para restablecer la aplicación de Teams en Surface Hub:

1. En su Surface Hub, abra el menú Inicio, seleccione **todas las aplicaciones**y, después, seleccione **configuración** .
2. Proporcione el nombre de usuario y la contraseña del administrador y, después, seleccione **sí**
3. Ir a **Surface Hub** y, a continuación, **aplicaciones & características**
4. Busque **Microsoft Teams para Surface Hub** y, a continuación, seleccione **Opciones avanzadas** .
5. Seleccione **restablecer**y, a continuación, **restablecer**
6. Reiniciar Surface Hub