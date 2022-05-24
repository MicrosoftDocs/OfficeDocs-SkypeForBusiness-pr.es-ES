---
title: Plantillas de equipo para pequeñas y medianas empresas creadas con Microsoft Graph
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Use Microsoft Teams plantillas predefinidas creadas en Microsoft Graph para crear equipos de forma rápida y sencilla para pequeñas y medianas empresas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5317b989bd7fe77f34743b6554cd356c226c2fa8
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646309"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Plantillas de equipo creadas en Microsoft Graph para pequeñas y medianas empresas

Las plantillas de equipo de Microsoft Teams le permiten crear equipos de forma rápida y sencilla al proporcionar una estructura predefinida de equipos de configuración, canales y aplicaciones preinstaladas.

Para pequeñas y medianas empresas, las plantillas pueden ser especialmente eficaces, ya que le ayudan a implementar rápidamente Teams en toda la organización. Las plantillas también ayudan a los usuarios a orientarse sobre cómo usar de forma eficaz Teams. Este artículo es para usted si es responsable de planear, implementar y administrar varios equipos en toda la organización.

Actualmente ofrecemos tres plantillas predefinidas para pequeñas y medianas empresas que puede usar para varias situaciones. Todas las plantillas crean equipos *privados* . Después de crear los equipos y de estar listo para su implementación en su organización, puede establecer la privacidad en *Toda* la organización o *En público*, según corresponda.

Para obtener más información sobre las plantillas de equipo en general, consulte [Comenzar con plantillas de equipo con Microsoft Graph](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>plantilla de Company-Wide

La plantilla de Company-Wide está pensada para la comunicación y la colaboración de toda la empresa. Puede usar el canal General para anuncios de toda la empresa, noticias del sector o publicaciones de ejecutivos. El canal de Recursos Humanos es un buen lugar para consolidar todas las actividades relacionadas con recursos humanos, como puestos de trabajo, incorporación de nuevos empleados, formación y desarrollo. El canal Fun Stuff proporciona una plataforma social para todas las publicaciones aleatorias y divertidas.

| Tipo de plantilla  | TemplateId | Propiedades que vienen con esta plantilla |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB: <br>Toda la empresa | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canales <ul><li>General\*</li><li>Recursos humanos\*</li><li>Cosas divertidas\*</li></ul><br> Aplicaciones<ul><li>Portal de empresa (Sitio web anclado al canal **Recursos humanos**) </li> </UL><br>Propiedades del equipo <ul><li>Visibilidad de equipo establecida en Privado</li></ul> |

*Canales favoritos automáticos 

Para crear el equipo Company-Wide tomando la configuración predeterminada de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud. Para obtener más información sobre cómo implementar plantillas de equipo, consulte el artículo de Microsoft Graph [sobre cómo crear un equipo](/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Solicitud 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a>Plantilla de equipo ejecutivo

La plantilla de equipo ejecutivo es ideal para crear un equipo para que los ejecutivos de la compañía se comuniquen y colaboren en iniciativas de la empresa, como prioridades anuales, presupuestos fiscales, iniciativas estratégicas y clientes principales. Esta plantilla incluye un canal *privado* para invitar a usuarios seleccionados para temas específicos.

| Tipo de plantilla  | TemplateId | Propiedades que vienen con esta plantilla |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB: <br>Equipo de ejecutivos | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canales <ul><li>General\*</li><li>Privado \*</li></ul> Aplicaciones<ul><li>OneNote (anclados al canal **Privado**)</li> <li>Planner (anclado al canal **Privado** ) </li></ul><br>Propiedades del equipo <ul><li>Visibilidad de equipo establecida en Privado</li></ul> | 

*Canales favoritos automáticos<br>

Para crear el equipo de ejecutivos tomando la configuración predeterminada de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud. Para obtener más información sobre cómo implementar plantillas de equipo, consulte el artículo de Microsoft Graph [sobre cómo crear un equipo](/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Solicitud 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>Plantilla de equipo departamental

La plantilla de equipo departamental se puede usar para crear un equipo para departamentos individuales o para proyectos. La plantilla del equipo de finanzas es ideal para todas las publicaciones, anuncios y colaboración diaria y comunicación dentro de los miembros del equipo de finanzas y los miembros del equipo ejecutivo según corresponda. La plantilla incluye un canal *privado* para invitar a usuarios seleccionados para temas específicos.

También proporcionamos el script siguiente para el equipo de finanzas que se puede usar para extender la plantilla a departamentos adicionales o proyectos específicos agregando, eliminando o editando a su gusto. Por ejemplo, si tiene un departamento de *marketing* , el script se puede adaptar cambiando el nombre del equipo de *Finanzas* a *Marketing* para crear un nuevo equipo de Marketing

| Tipo de plantilla | TemplateId | Propiedades que vienen con esta plantilla |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB: <br>Finanzas  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canales <ul><li>General\*</li><li>Privado \*</li></ul><br> Aplicaciones<ul><li>OneNote (anclados al canal **Privado**)</li> <li>Planner (anclado al canal **Privado** ) </li> </ul><br>Propiedades del equipo <ul><li>Visibilidad de equipo establecida en Privado</li></ul> | 

*Canales favoritos automáticos

Para crear el equipo de finanzas tomando la configuración predeterminada de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud. Para obtener más información sobre cómo implementar plantillas de equipo, consulte el artículo de Microsoft Graph [sobre cómo crear un equipo](/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Solicitud 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a>Ejemplo: Script de extensión de plantilla del equipo de finanzas

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a>Temas relacionados

- [Introducción a las plantillas de equipo en el centro de administración de Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Introducción a las plantillas de equipo con Microsoft Graph](get-started-with-teams-templates.md)
- [Crear equipo](/graph/api/team-post?view=graph-rest-beta) (en versión preliminar)
