---
title: Administrar sus dispositivos en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: kelsawi
f1keywords: ms.teamsadmincenter.devicemanagement.overview
description: Obtenga información sobre cómo administrar dispositivos utilizados con los equipos de la organización.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb306930b4adca9c50e46ad1515324bbac2a2e2d
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754198"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Administrar sus dispositivos en Microsoft Teams

 Como administrador, puede administrar todos los dispositivos utilizados con los equipos de la organización desde el centro de administración de Microsoft Teams. Puede ver y administrar el inventario de los dispositivos para su organización y realizar tareas como la actualización, reiniciar y diagnósticos de monitor para dispositivos. También puede crear y asignar perfiles de configuración a un dispositivo o grupos de dispositivos. 

## <a name="what-devices-can-you-manage"></a>¿Qué dispositivos pueden administrar?
Dispositivos deben ser certificados para los equipos e inscritos en los equipos. Un dispositivo está inscrito automáticamente la primera vez que un usuario inicia sesión en los equipos en el dispositivo. Para obtener una lista de los dispositivos certificados que se pueden administrar, consulte [teléfonos de conferencia](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) y [teléfonos de escritorio](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).

> [!NOTE]
> Si tiene Microsoft Intune, los dispositivos se inscriben automáticamente en Intune. Después de que un dispositivo está inscrito, se confirme el cumplimiento del dispositivo y se aplican las directivas de acceso condicional para el dispositivo. 

## <a name="manage-devices-in-teams"></a>Administrar dispositivos en los equipos

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

1. En el panel de navegación izquierdo, vaya a **dispositivos** > **Administrar dispositivos**.
2. Seleccione **todos los dispositivos**.  

 Desde aquí, puede ver y administrar todos los dispositivos que se inscriben en los equipos de la organización. La información que aparece para cada dispositivo incluye historial, fabricante, modelo, usuario, estado, acción, último visto y nombre del dispositivo. Puede personalizar la vista para mostrar la información que se ajuste a sus necesidades.

 Aquí tiene algunos ejemplos de cómo se pueden administrar dispositivos de los equipos de la organización.  
    
|Para hacer esto...  |En este caso |
|---------|---------|
|Cambiar la información de dispositivo   | Seleccione un > dispositivo **Editar**. Puede editar detalles como el nombre del dispositivo, la información de usuario, la etiqueta de activos y agregar notas.     |
|Administrar las actualizaciones de software   |Seleccione una **actualización**de dispositivo >. Puede ver la lista de actualizaciones de software y firmware disponibles para el dispositivo y elija las actualizaciones para instalar.    |
|Reiniciar un dispositivo   |Seleccione un > de dispositivo que se **reinicie**.          |
|Ver el historial de dispositivo  | Seleccione un **historial**de dispositivo >. Puede ver el historial de actualización para el dispositivo.     |
|Ver diagnósticos  | Seleccione un > dispositivo **Diagnósticos**.        |

## <a name="use-configuration-profiles-in-teams"></a>Usar los perfiles de configuración en los equipos

Use los perfiles de configuración para administrar la configuración y las características de dispositivos de los equipos de la organización. Puede crear o cargar los perfiles de configuración para incluir la configuración y las características que desea habilitar o deshabilitar y, a continuación, asignar un perfil a un dispositivo o grupos de dispositivos. 

### <a name="create-a-configuration-profile"></a>Crear un perfil de configuración

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

1. En el panel de navegación izquierdo, vaya a **dispositivos** > **Administrar dispositivos**.
2. Seleccione **los perfiles de configuración**y, a continuación, seleccione **nuevo perfil de configuración**.
3. Escriba un nombre para el perfil y si lo desea, agregue una descripción simplificada.
4. Especificar la configuración que desee para el perfil y, a continuación, haga clic en **Guardar**.

### <a name="assign-a-configuration-profile"></a>Asignar un perfil de configuración

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

1. En el panel de navegación izquierdo, vaya a **dispositivos** > **Administrar dispositivos**.
2. Seleccione el **perfil de configuración**y, a continuación, en **asignado a** en el perfil que desea asignar, haga clic en el vínculo.  
3. En el panel **asignar dispositivos a un perfil de configuración** , busque y seleccione los dispositivos que desee asignar.
4. Haga clic en **Guardar**.
