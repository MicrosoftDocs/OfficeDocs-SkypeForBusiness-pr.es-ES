---
title: Introducción a las plantillas de Teams para pequeñas y medianas empresas
author: kenwith
ms.author: kenwith
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
description: Introducción a las plantillas de Teams para pequeñas y medianas empresas
ms.openlocfilehash: be42728387189f2281f892e5cc608f9e6f557b02
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837940"
---
# <a name="get-started-with-teams-templates-for-small-and-medium-businesses"></a>Introducción a las plantillas de Teams para pequeñas y medianas empresas

Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.

Para las pequeñas y medianas empresas, las plantillas pueden ser especialmente eficaces, ya que ayudan a los administradores a implementar rápidamente Teams en toda la organización. Las plantillas también ayudan a orientar a los usuarios y a comenzar a usar Teams de manera eficaz. Este artículo le interesa si es responsable de planear, implementar y administrar varios equipos en la organización.

Actualmente ofrecemos tres plantillas de SMB de primera parte que puede aprovechar para diversas situaciones. Todas las plantillas crearán equipos *privados* . Una vez que haya creado los equipos y estén listos para su organización, puede establecer la privacidad en *toda* la organización o *pública*, según corresponda. Para obtener más información sobre las plantillas de equipo en general, consulte [Introducción a las plantillas](get-started-with-teams-templates.md)de Teams.

## <a name="company-wide-template"></a>Plantilla de toda la empresa
La plantilla para toda la empresa está destinada a la comunicación y la colaboración que son relevantes para toda la empresa. Puede usar el canal general para anuncios de toda la empresa, noticias de la industria o publicaciones ejecutivas. El canal de recursos humanos es un buen lugar para consolidar todas las actividades relacionadas con recursos humanos, como las publicaciones de trabajo, la incorporación de nuevos empleados, la formación y el desarrollo. El canal de material variado proporciona una plataforma social para todas las publicaciones de forma aleatoria y divertida.

| Tipo de plantilla base  | baseTemplateId | Propiedades que vienen con esta plantilla base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| Pequeñas <br>Toda la empresa | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canales <ul><li>General\*</li><li>Recursos humanos\*</li><li>Cosas divertidas\*</li></ul><br> Aplicaciones<ul><li>Portal de empresa (sitio web anclado al canal de **recursos humanos** ) </li> </UL><br>Propiedades del equipo <ul><li>Visibilidad del equipo establecida en privado</li></ul> |

* Canales favoritos automáticos 

Para crear el equipo de toda la empresa mediante la toma de valores predeterminados de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud. Para obtener más información sobre cómo implementar las plantillas de Teams, vea el [artículo de Microsoft Graph sobre la creación de un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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

La plantilla del equipo ejecutivo es ideal para crear un equipo para que los ejecutivos de la empresa puedan comunicarse y colaborar en iniciativas de la empresa, como prioridades anuales, presupuestos fiscales, iniciativas estratégicas, clientes principales, etc. Esta plantilla viene con un canal *privado* para invitar a determinados usuarios a determinados temas.

| Tipo de plantilla base  | baseTemplateId | Propiedades que vienen con esta plantilla base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| Pequeñas <br>Equipo ejecutivos | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canales <ul><li>General\*</li><li>Empresa\*</li></ul> Aplicaciones<ul><li>OneNote (anclado al canal **privado** )</li> <li>Planner (anclado al canal **privado** ) </li></ul><br>Propiedades del equipo <ul><li>Visibilidad del equipo establecida en privado</li></ul> | 

* Canales favoritos automáticos<br>

Para crear el equipo de ejecutivos adoptando de forma predeterminada las plantillas predefinidas, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud. Para obtener más información sobre cómo implementar las plantillas de Teams, vea el [artículo de Microsoft Graph sobre la creación de un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Solicitud 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company’s leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>Plantilla de equipo departamental

La plantilla de equipo departamental se puede usar para crear un equipo para departamentos individuales o para proyectos. La plantilla del equipo de finanzas es ideal para todas las publicaciones, anuncios y colaboración y comunicación diaria dentro de los miembros del equipo de Finanzas (y miembros del equipo ejecutivo según corresponda). La plantilla viene con un canal *privado* para invitar a determinados usuarios a determinados temas. También proporcionamos la siguiente secuencia de comandos para el equipo de finanzas, que se puede usar para ampliar la plantilla a otros departamentos o proyectos específicos agregando, eliminando o editando a su gusto. Por ejemplo, si tiene un departamento de *marketing* , el script puede adaptarse cambiando el nombre del equipo de *Finance* a *marketing* para crear un nuevo equipo de marketing

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| Pequeñas <br>Finanzas  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canales <ul><li>General\*</li><li>Empresa\*</li></ul><br> Aplicaciones<ul><li>OneNote (anclado al canal **privado** )</li> <li>Planner (anclado al canal **privado** ) </li> </ul><br>Propiedades del equipo <ul><li>Visibilidad del equipo establecida en privado</li></ul> | 

* Canales favoritos automáticos

Para crear el equipo de finanzas adoptando los valores predeterminados de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud. Para obtener más información sobre cómo implementar las plantillas de Teams, vea el [artículo de Microsoft Graph sobre la creación de un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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

### <a name="example-finance-team-template-extension-script"></a>Ejemplo: script de extensión de plantilla de equipo finanzas

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

- [Introducción a las plantillas de Teams](get-started-with-teams-templates.md)
- [Crear equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en versión preliminar)

