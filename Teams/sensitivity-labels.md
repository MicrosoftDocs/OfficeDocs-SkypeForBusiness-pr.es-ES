---
title: Etiquetas de confidencialidad para Microsoft Teams
ms.author: cabailey
author: cabailey
manager: laurawi
ms.reviewer: shubjain
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- tier1
- purview-compliance
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Aprenda a usar etiquetas de confidencialidad para proteger sus equipos en Microsoft Teams.
ms.openlocfilehash: 59bd67ea59787a1f73b2a0c808bfa3464c3bc31b
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046880"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Etiquetas de confidencialidad para Microsoft Teams

[Las etiquetas de confidencialidad](/microsoft-365/compliance/sensitivity-labels) permiten a los administradores de Teams proteger y regular el acceso al contenido confidencial de la organización creado durante la colaboración dentro de los equipos. Después de configurar las etiquetas de confidencialidad con sus directivas asociadas en el [portal de cumplimiento Microsoft Purview](/microsoft-365/compliance/go-to-the-securitycompliance-center), estas etiquetas se pueden aplicar a los equipos de su organización.

Las etiquetas de confidencialidad no son compatibles actualmente en los equipos de clase para los clientes que usan SKU de Teams para el ámbito educativo. Para obtener más información sobre las licencias, consulte [Descripción del servicio de Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>¿Cuál es la diferencia entre las etiquetas de confidencialidad y la clasificación de Teams?

Las etiquetas de confidencialidad son diferentes de la clasificación de Teams, también conocida como clasificación de grupo de Azure AD. Las clasificaciones son cadenas de texto que se pueden asociar a un grupo de Microsoft 365, pero que no tienen directivas reales asociadas. Use la clasificación como metadatos y, a continuación, debe usar otros métodos, como herramientas internas y scripts, para aplicar directivas.

La ventaja de usar etiquetas de confidencialidad es que sus directivas se aplican de un extremo a otro automáticamente a través de una combinación de la plataforma Grupos de Microsoft 365, la portal de cumplimiento Microsoft Purview y los servicios de Teams. Las etiquetas de confidencialidad proporcionan un soporte de infraestructura eficaz para proteger los datos confidenciales de su organización y garantizar el cumplimiento de sus directivas o normativas internas.

Si actualmente usa la clasificación de Teams, consulte la documentación siguiente para obtener más información e instrucciones sobre cómo convertir estos valores en etiquetas de confidencialidad: [Clasificación de grupos clásica de Azure AD](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

## <a name="example-scenarios-for-sensitivity-labels"></a>Escenarios de ejemplo para etiquetas de confidencialidad

Entre los escenarios de ejemplo para usar etiquetas de confidencialidad con Teams en su organización se incluyen los siguientes:

- [Establecer el nivel de privacidad (público o privado) para los equipos](#set-the-privacy-level-for-teams)
- [Controlar el acceso de invitado a los equipos](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Establecer el nivel de privacidad de los equipos

Puede crear y configurar una etiqueta de confidencialidad que, cuando se aplique durante la creación de equipos, permita a los usuarios crear equipos con una configuración específica de privacidad (pública o privada).

Por ejemplo, puede crear y publicar una etiqueta de confidencialidad denominada "Confidencial" que tenga la opción de privacidad de etiqueta configurada como **Privada**. Como resultado, cualquier equipo que se cree con esta etiqueta debe ser un equipo privado. 

Cuando un usuario crea un equipo y selecciona la etiqueta **Confidencial** , la única opción de privacidad que está disponible para el usuario es **Privado**. Otras opciones de privacidad, como Público y Toda la organización, no están disponibles para que el usuario seleccione:

![Captura de pantalla de etiqueta Confidencialidad confidencial.](media/sensitivity-labels-confidential-example.png)

De forma similar, puede crear y publicar una etiqueta de confidencialidad denominada "General" que tenga la opción de privacidad de etiqueta configurada como **Pública**. Cuando un usuario crea un equipo, solo puede crear equipos públicos o de toda la organización al seleccionar esta etiqueta:

![Captura de pantalla de etiqueta de confidencialidad general.](media/sensitivity-labels-general-example.png)

Cuando se crea el equipo, la etiqueta de confidencialidad es visible para los usuarios en la esquina superior derecha de los canales del equipo. 

![Captura de pantalla de la etiqueta de confidencialidad en el canal de equipo.](media/sensitivity-labels-channel.png)

El propietario de un equipo puede cambiar la etiqueta de confidencialidad y la configuración de privacidad del equipo en cualquier momento, yendo al equipo y, a continuación, haciendo clic en **Editar equipo**.

![Captura de pantalla de la etiqueta de confidencialidad en las propiedades del equipo.](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Controlar el acceso de invitado a los equipos

Puede usar etiquetas de confidencialidad para controlar el acceso de invitados a sus equipos. Los equipos creados con una etiqueta que no permite el acceso de invitado solo están disponibles para los usuarios de su organización. Personas fuera de su organización no se pueden agregar al equipo.

## <a name="microsoft-teams-admin-center"></a>Centro de administración de Microsoft Teams

Puede aplicar etiquetas de confidencialidad al crear o editar un equipo en el Centro de administración de Microsoft Teams. Las etiquetas de confidencialidad también se pueden ver en las propiedades del equipo y en la columna **Clasificación** de la página **Administrar equipos** del Centro de administración de Microsoft Teams.

## <a name="limitations"></a>Limitaciones

Antes de usar etiquetas de confidencialidad para Teams, tenga en cuenta las siguientes limitaciones:

- **Las etiquetas de confidencialidad no son compatibles con las API de Teams Graph ni con los cmdlets de PowerShell**
    
    Los usuarios no podrán especificar etiquetas de confidencialidad al crear equipos directamente a través de las API de Teams Graph o los cmdlets de PowerShell de Teams. Sin embargo, las API de Graph de grupos modernos y los cmdlets de PowerShell permiten la creación de grupos con etiquetas de confidencialidad. Esto significa que puede crear grupos con etiquetas de confidencialidad mediante estos métodos y, después, convertirlos en equipos.

- **Compatibilidad con canales privados**
    
    Los canales privados que se crean en un equipo heredan la etiqueta de confidencialidad que se aplicó en un equipo. La misma etiqueta se aplica automáticamente en la colección de sitios de SharePoint para el canal privado.
    
    Sin embargo, si un usuario cambia directamente la etiqueta de confidencialidad en un sitio de SharePoint para un canal privado, ese cambio de etiqueta no se refleja en el cliente de Teams. En este escenario, los usuarios siguen viendo la etiqueta de confidencialidad original aplicada en el equipo en el encabezado del canal privado.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Cómo crear y configurar etiquetas de confidencialidad para Teams

Use las instrucciones de la documentación de Microsoft Purview para crear y configurar etiquetas de confidencialidad para Teams: 

- [Use etiquetas de confidencialidad para proteger el contenido de Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).
