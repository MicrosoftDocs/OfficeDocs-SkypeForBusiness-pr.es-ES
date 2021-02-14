---
title: Introducción a las plantillas comerciales de Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar plantillas de Teams para crear estructuras de equipo diseñadas para las necesidades del distribuidor proporcionando configuraciones predefinidas, canales y aplicaciones preinstaladas.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424640"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Introducción a las plantillas comerciales de Teams

Las plantillas de Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.

Las plantillas de Teams tienen definiciones predefinidas de estructuras de equipo diseñadas para satisfacer las necesidades de los distribuidores. Puede usar plantillas de Teams para crear rápidamente los tipos de equipos que funcionan bien para los distribuidores e implementarlos en toda la organización. También puede ampliar las plantillas de Teams para crear equipos que se adapten a sus necesidades organizativas específicas.

En este artículo, presentaremos cada una de las plantillas de Teams y le recomendamos que las use.

Este artículo es para usted si es responsable de planear, implementar y administrar varios equipos en toda su organización comercial. Ya ha implementado el servicio Teams en su organización. Si aún no ha lanzado Teams, empiece leyendo cómo [se lanza Microsoft Teams.](How-to-roll-out-teams.md)

Para obtener más información sobre las plantillas de equipo en general, consulte Introducción [a las plantillas de Teams.](get-started-with-teams-templates.md)

## <a name="store-template"></a>Plantilla de Store

La plantilla de Store es ideal para crear un equipo que represente una ubicación individual de la tienda minorista. Con la plantilla de Store, puede crear un equipo para cada ubicación de la tienda minorista de su organización.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Venta al por menor: <br>Almacén | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canales <ul><li>Entrega de turnos\*</li><li>Aprendizaje\*</li></ul>\*Canales auto favoritos<br><br>Propiedades del equipo <ul><li>Visibilidad del equipo establecida en Público</li></ul> <br>Permisos de miembros <ul><li>No se pueden crear, actualizar o eliminar canales </li><li>No se pueden agregar ni quitar aplicaciones </li><li>No se pueden crear, actualizar o quitar pestañas</li><li>No se pueden crear, actualizar o quitar conectores</li><ul>|
||||

Formas recomendadas de personalizar la plantilla de Store para su organización:

- Si su organización tiene departamentos dentro de cada tienda, agregue un canal para cada departamento. Agregar un canal facilita la comunicación y la colaboración dentro del departamento.

- Si su organización tiene sitios web internos (por ejemplo, un sitio de SharePoint), considere anclarlos como pestañas en el canal de equipo correspondiente. Consulte Introducción [a las plantillas de Teams](get-started-with-teams-templates.md) para obtener instrucciones.

## <a name="manager-collaboration-template"></a>Plantilla de colaboración del administrador

La plantilla colaboración de administradores es otra de las plantillas de Teams diseñadas para satisfacer las necesidades de los distribuidores. La plantilla colaboración de administradores es ideal para crear un equipo para que un conjunto de administradores colabore entre tiendas o regiones, y mucho más. Por ejemplo, si su organización tiene regiones, puede crear un equipo de colaboración de administrador para la región de California e incluir todos los administradores de almacén de esa región, así como el administrador regional de esa región.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Venta al por menor: <br>Almacén | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canales <ul><li>Operations\*</li><li>Aprendizaje\*</li></ul>\*Canales auto favoritos<br><br>Propiedades del equipo <ul><li>Visibilidad del equipo establecida en Privado</li></ul> <br>Permisos de miembros <ul><li>Puede crear, actualizar o eliminar canales </li><li>Puede agregar o quitar aplicaciones </li><li>Puede crear, actualizar o quitar pestañas</li><li>Puede crear, actualizar o quitar conectores</li><ul>|
||||

Formas recomendadas de personalizar la plantilla colaboración de administrador para su organización:

- Si su organización tiene sitios web internos, como un sitio de SharePoint, que sean relevantes para los administradores, considere anclarlos como pestañas en un canal de equipo relevante. Puede consultar la documentación de la plantilla [de Microsoft Teams para](get-started-with-teams-templates.md) obtener instrucciones.

## <a name="how-to-use-first-party-templates"></a>Cómo usar plantillas de terceros

Para usar estas plantillas, cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "estándar" a los templateIDs anteriores.  Para obtener más información sobre cómo implementar plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Los canales de la plantilla se crearán automáticamente en la pestaña General.

### <a name="example-store-template-extension-script"></a>Ejemplo: Script de extensión de plantilla de Store

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
## <a name="relate-topic"></a>Relacionar tema

[Introducción a las plantillas de Teams en el Centro de administración](get-started-with-teams-templates-in-the-admin-console.md)
