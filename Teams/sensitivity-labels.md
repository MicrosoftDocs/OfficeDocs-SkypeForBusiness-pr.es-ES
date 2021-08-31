---
title: Etiquetas de confidencialidad para Microsoft Teams
ms.author: mikeplum
author: cabailey
manager: laurawi
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo usar etiquetas de confidencialidad para proteger los equipos en Microsoft Teams.
ms.openlocfilehash: e4f6f3b790bb84b4d628760548b6ab1115f6326d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729599"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Etiquetas de confidencialidad para Microsoft Teams

[Las etiquetas](/microsoft-365/compliance/sensitivity-labels) de confidencialidad Teams los administradores pueden proteger y regular el acceso al contenido organizativo confidencial creado durante la colaboración en equipos. Después de configurar etiquetas de confidencialidad con sus directivas asociadas en el Centro de cumplimiento de [Microsoft,](/microsoft-365/compliance/go-to-the-securitycompliance-center)estas etiquetas se pueden aplicar a los equipos de su organización.

Actualmente, las etiquetas de confidencialidad no son compatibles en los equipos de clase para los clientes que usan Teams SKU de educación. Para obtener más información sobre las licencias, [vea Microsoft Teams descripción del servicio](/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>¿Cuál es la diferencia entre las etiquetas de confidencialidad Teams etiquetas de clasificación?

Las etiquetas de confidencialidad son diferentes de las etiquetas de clasificación, también conocidas como clasificación de grupo de Azure AD. Las etiquetas de clasificación son cadenas de texto que se pueden asociar a un grupo Microsoft 365 pero que no tienen ninguna directiva real asociada. Use etiquetas de clasificación como metadatos y, a continuación, debe usar otros métodos, como herramientas internas y scripts, para aplicar directivas.

La ventaja de usar etiquetas de confidencialidad es que sus directivas se aplican automáticamente de un extremo a otro a través de una combinación de la plataforma grupos de Microsoft 365, el centro de cumplimiento y Teams servicios. Las etiquetas de confidencialidad proporcionan un soporte de infraestructura eficaz para proteger los datos confidenciales de su organización y garantizar el cumplimiento de sus directivas internas o normativas.

Si actualmente usa etiquetas de clasificación, consulte la documentación siguiente para obtener más información e instrucciones sobre cómo migrarlas a etiquetas de confidencialidad: clasificación de grupo clásica [de Azure AD.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)

## <a name="example-scenarios-for-sensitivity-labels"></a>Escenarios de ejemplo para etiquetas de confidencialidad

Escenarios de ejemplo para usar etiquetas de confidencialidad con Teams en su organización:

- [Establecer el nivel de privacidad (público o privado) de los equipos](#set-the-privacy-level-for-teams)
- [Controlar el acceso de invitado a los equipos](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Establecer el nivel de privacidad de los equipos

Puede crear y configurar una etiqueta de confidencialidad que, cuando se aplica durante la creación de equipos, permite a los usuarios crear equipos con una configuración de privacidad específica (pública o privada).

Por ejemplo, crea y publica una etiqueta de confidencialidad denominada "Confidencial" que tiene la opción de privacidad de etiqueta configurada como **Privado.** Como resultado, cualquier equipo que se cree con esta etiqueta debe ser un equipo privado. 

Cuando un usuario crea un equipo  y selecciona la etiqueta Confidencial, la única opción de privacidad disponible para el usuario es **Privado.** Otras opciones de privacidad como Público y Toda la organización no están disponibles para que el usuario seleccione:

![Captura de pantalla de etiqueta confidencialidad.](media/sensitivity-labels-confidential-example.png)

De forma similar, cree y publique una etiqueta de confidencialidad denominada "General" que tenga la opción de privacidad de etiqueta configurada como **Público.** Cuando un usuario crea un equipo nuevo, solo puede crear equipos públicos o de toda la organización al seleccionar esta etiqueta:

![Captura de pantalla de etiqueta de confidencialidad general.](media/sensitivity-labels-general-example.png)

Cuando se crea el equipo, la etiqueta de confidencialidad está visible en la esquina superior derecha de los canales del equipo. 

> [!NOTE]
> Si usa etiquetas jerárquicas de elementos primarios y secundarios como "Confidencial\Finanzas", solo se mostrará la etiqueta principal en el encabezado del canal.

![Captura de pantalla de la etiqueta de confidencialidad en el canal de grupo.](media/sensitivity-labels-channel.png)

El propietario de un equipo puede cambiar la etiqueta de confidencialidad y la configuración de privacidad del equipo en cualquier momento yendo al equipo y, a continuación, haga clic **en Editar equipo.**

![Captura de pantalla de etiqueta de confidencialidad en las propiedades del equipo.](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Controlar el acceso de invitado a los equipos

Puede usar etiquetas de confidencialidad para controlar el acceso de invitado a sus equipos. Teams creados con una etiqueta que no permite el acceso de invitado solo están disponibles para los usuarios de su organización. Las personas de fuera de su organización no se pueden agregar al equipo.

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams de administración

Puede aplicar etiquetas de confidencialidad al crear o editar un equipo en el centro Microsoft Teams administración. 

Las etiquetas de confidencialidad también  están visibles en las propiedades del equipo y en la columna Clasificación de la página Administrar equipos del centro Microsoft Teams administración. 

## <a name="limitations"></a>Limitaciones

Antes de usar etiquetas de Teams, tenga en cuenta las siguientes limitaciones:

- **Los nombres de etiquetas primarias no se muestran para etiquetas subatiquetas**
    
    Teams admite subetiquetas, pero no muestra el nombre de la etiqueta principal. Por ejemplo, **Confidencial** \\ **Todos los empleados** se muestra **como Todos los empleados.**

- **Las etiquetas de confidencialidad no son compatibles Teams Graph API, cmdlets de PowerShell y plantillas**
    
    Los usuarios no podrán especificar etiquetas de confidencialidad al crear equipos directamente a través de Teams Graph API, Teams cmdlets de PowerShell y Teams plantillas. Sin embargo, los grupos Graph API y cmdlets de PowerShell permiten la creación de grupos con etiquetas. Para que los usuarios primero puedan crear grupos con etiquetas con grupos Graph API o cmdlets de PowerShell y, después, convertir estos grupos en Teams.

- **Compatibilidad con canales privados**
    
    Los canales privados que se crean en un equipo heredan la etiqueta de confidencialidad que se aplicó en un equipo. La misma etiqueta se aplica automáticamente en la SharePoint de sitios del canal privado.
    
    Sin embargo, si un usuario cambia directamente la etiqueta de confidencialidad en un sitio de SharePoint para un canal privado, ese cambio de etiqueta no se refleja en el Teams cliente. En este escenario, los usuarios siguen ven la etiqueta de confidencialidad original aplicada en el equipo en el encabezado del canal privado.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Cómo crear y configurar etiquetas de confidencialidad para Teams

Use las instrucciones de la documentación Microsoft 365 para crear y configurar etiquetas de confidencialidad para Teams: 

- [Use etiquetas de confidencialidad para](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)proteger el contenido Microsoft Teams, Microsoft 365 grupos y SharePoint sitios .
