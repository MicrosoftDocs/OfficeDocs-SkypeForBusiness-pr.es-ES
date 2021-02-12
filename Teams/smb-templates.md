---
title: Plantillas de Teams para pequeñas y medianas empresas creadas con Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Use plantillas predefinidas de Microsoft Teams creadas en Microsoft Graph para crear de forma rápida y sencilla equipos para pequeñas y medianas empresas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7196dd93fc1245102a333c150715c4b4570986c7
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294556"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Plantillas de Teams creadas en Microsoft Graph para pequeñas y medianas empresas

Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.

Para las empresas pequeñas y medianas, las plantillas pueden ser especialmente eficaces, ya que ayudan a los administradores a implementar teams rápidamente en toda la organización. Las plantillas también ayudan a orientar a los usuarios y comenzar a usar Teams de forma eficaz. Este artículo es para usted si es responsable de planear, implementar y administrar varios equipos en toda su organización.

Actualmente, ofrecemos tres plantillas de SMB de terceros que puede aprovechar para una variedad de situaciones. Todas las plantillas crearán *equipos* privados. Una vez que haya creado Teams y esté listo para su  implementación en su organización, puede establecer la privacidad en Público o Para toda la *organización,* según corresponda. Para obtener más información sobre las plantillas de equipo en general, vea [Introducción a las plantillas de Teams.](get-started-with-teams-templates.md)

## <a name="company-wide-template"></a>Company-Wide plantilla
La Company-Wide profesional está pensada para la comunicación y la colaboración, que son relevantes para toda la empresa. Puede usar el canal General para anuncios de toda la empresa, noticias del sector o publicaciones de ejecutivos. El canal de Recursos Humanos es un buen lugar para consolidar todas las actividades relacionadas con los recursos humanos, como las publicaciones de trabajo, la incorporación, la formación y el desarrollo de nuevos empleados. El canal Cosas divertidas proporciona una plataforma social para todas las publicaciones aleatorias y divertidas.

| Tipo de plantilla base  | baseTemplateId | Propiedades que vienen con esta plantilla base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Toda la empresa | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canales <ul><li>General\*</li><li>Recursos humanos\*</li><li>Cosas divertidas\*</li></ul><br> Aplicaciones<ul><li>Portal de empresa (sitio web anclado al **canal de Recursos** Humanos) </li> </UL><br>Propiedades del equipo <ul><li>Visibilidad del equipo establecida en Privado</li></ul> |

*Canales auto favoritos 

Para crear el Company-Wide de grupo con los valores predeterminados de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud. Para obtener más información sobre cómo implementar plantillas de Teams, vea el artículo de Microsoft Graph [sobre cómo crear un equipo.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

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

La plantilla equipo ejecutivo es ideal para crear un equipo para que los ejecutivos de la compañía se comuniquen y colaboren en iniciativas de la empresa como prioridades anuales, presupuestos fiscales, iniciativas estratégicas y clientes principales. Esta plantilla incluye un canal *privado para* invitar a usuarios seleccionados a temas específicos.

| Tipo de plantilla base  | baseTemplateId | Propiedades que vienen con esta plantilla base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Equipo de ejecutivos | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canales <ul><li>General\*</li><li>Privado \*</li></ul> Aplicaciones<ul><li>OneNote (anclado al **canal** privado)</li> <li>Planner (anclado al **canal** privado) </li></ul><br>Propiedades del equipo <ul><li>Visibilidad del equipo establecida en Privado</li></ul> | 

*Canales auto favoritos<br>

Para crear el equipo de ejecutivos con los valores predeterminados de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud. Para obtener más información sobre cómo implementar plantillas de Teams, vea el artículo de Microsoft Graph [sobre cómo crear un equipo.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

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

## <a name="departmental-team-template"></a>Plantilla Equipo de departamento

La plantilla de equipo de departamento se puede usar para crear un equipo para departamentos individuales o para proyectos. La plantilla del equipo de finanzas es ideal para todas las publicaciones, anuncios y colaboración y comunicación diarias dentro del equipo de Finanzas y los miembros del equipo ejecutivo según corresponda. La plantilla incluye un canal *privado para* invitar a usuarios seleccionados a temas específicos. También proporcionamos el script siguiente para el equipo de finanzas que se puede usar para extender la plantilla a departamentos adicionales o proyectos específicos agregando, eliminando o editando a su gusto. Por ejemplo, si tiene un departamento de *marketing,* el script se  puede adaptar si cambia el nombre del equipo de Finanzas a *Marketing* para crear un nuevo equipo de marketing

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Finanzas  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canales <ul><li>General\*</li><li>Privado \*</li></ul><br> Aplicaciones<ul><li>OneNote (anclado al **canal** privado)</li> <li>Planner (anclado al **canal** privado) </li> </ul><br>Propiedades del equipo <ul><li>Visibilidad del equipo establecida en Privado</li></ul> | 

*Canales auto favoritos

Para crear el equipo de finanzas con los valores predeterminados de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud. Para obtener más información sobre cómo implementar plantillas de Teams, vea el artículo de Microsoft Graph [sobre cómo crear un equipo.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

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

- [Introducción a las plantillas de Teams en la consola de administración](get-started-with-teams-templates-in-the-admin-console.md)
- [Introducción a las plantillas de Teams](get-started-with-teams-templates.md)
- [Crear un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en versión preliminar)

