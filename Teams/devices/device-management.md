---
title: Administrar sus dispositivos en Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Obtenga información sobre cómo administrar dispositivos usados con equipos de su organización.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366a24706a80f6fe96cc8a3733022cc64f78ba7e
ms.sourcegitcommit: 3ed779277540589eabef745685ab6c67d8a8ff90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "44281719"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Administrar sus dispositivos en Microsoft Teams

Como administrador, puede administrar los dispositivos que se usan con los equipos de su organización desde el centro de administración de Microsoft Teams. Puede ver y administrar el inventario de dispositivos de su organización y realizar tareas como actualizar, reiniciar y supervisar los diagnósticos de los dispositivos. También puede crear y asignar perfiles de configuración a un dispositivo o a grupos de dispositivos. 

## <a name="what-devices-can-you-manage"></a>¿Qué dispositivos puede administrar?
Puede administrar cualquier dispositivo que esté certificado e inscrito en Teams. Un dispositivo se inscribe automáticamente la primera vez que un usuario inicia sesión en Teams en el dispositivo. Para obtener una lista de los dispositivos certificados que se pueden administrar, consulte:

- [Teléfonos de conferencia](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [Teléfonos de escritorio](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- Barras de colaboración

Los dispositivos se administran en el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com) , en **dispositivos** , en la barra de navegación izquierda.

> [!NOTE]
> Si tiene Microsoft Intune, los dispositivos se inscriton automáticamente en Intune. Una vez que se ha inscrito un dispositivo, se confirma el cumplimiento del dispositivo y se aplican las directivas de acceso condicional al dispositivo.

## <a name="manage-phones-and-collaboration-bars-in-teams"></a>Administrar teléfonos y barras de colaboración en Teams

Aunque los teléfonos y las barras de colaboración se administran de la misma manera en el centro de administración de Microsoft Teams, tienen sus propias secciones en el navegación de la izquierda, en **dispositivos**. Esto le permite administrar cada tipo de dispositivo por separado.

Desde aquí, puede ver y administrar teléfonos y barras de colaboración inscritos en los equipos de su organización. La información que verás para cada dispositivo incluye el nombre del dispositivo, el fabricante, el modelo, el usuario, el estado, la acción, la última vista y el historial. Puede personalizar la vista para que muestre la información que se adapte a sus necesidades.

Estos son algunos ejemplos de cómo puede administrar los dispositivos de equipos de su organización.  
    
|Para hacer esto...  |Haga lo siguiente |
|---------|---------|
|Cambiar la información del dispositivo   | Seleccione un dispositivo > **Editar**. Puede editar detalles como el nombre del dispositivo, la etiqueta de activos y agregar notas.     |
|Administrar actualizaciones de software   |Seleccione un dispositivo > **Actualizar**. Puede ver la lista de actualizaciones de software y firmware disponibles para el dispositivo y elegir las actualizaciones que desea instalar.    |
|Reiniciar un dispositivo   |Seleccione un dispositivo > **reiniciar**.          |
|Ver el historial del dispositivo  | Seleccione un dispositivo > **historial**. Puede ver el historial de actualizaciones del dispositivo.     |
|Ver diagnósticos  | Seleccione un dispositivo > **diagnósticos**.        |

## <a name="use-configuration-profiles-in-teams"></a>Usar perfiles de configuración en Teams

Use perfiles de configuración para administrar la configuración y las características de los dispositivos de equipos de su organización. Puede crear o cargar perfiles de configuración para incluir opciones y características que desee habilitar o deshabilitar y, después, asignar un perfil a un dispositivo o a grupos de dispositivos. 

### <a name="create-a-configuration-profile"></a>Crear un perfil de configuración

1. En el navegación de la izquierda, vaya a perfiles de configuración de **dispositivos**  >  **Configuration profiles**.
2. Haga clic en **Agregar**.
3. Escriba un nombre para el perfil y, si lo desea, agregue una descripción.
4. Especifique la configuración que desee para el perfil y, a continuación, haga clic en **Guardar**.

### <a name="assign-a-configuration-profile"></a>Asignar un perfil de configuración

1. En el navegación de la izquierda, vaya a perfiles de configuración de **dispositivos**  >  **Configuration profiles**.
2. Seleccione el **Perfil de configuración** que desea asignar y, a continuación, haga clic en **asignar al dispositivo**.  
3. En el panel **asignar dispositivos a un perfil de configuración** , busque y seleccione los dispositivos que desea asignar.
4. Haga clic en **Guardar **.
