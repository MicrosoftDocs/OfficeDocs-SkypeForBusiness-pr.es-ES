---
title: Introducción a las plantillas comerciales de Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar las plantillas de Teams para crear estructuras de equipo diseñadas para las necesidades de los distribuidores.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec16f919bad5ed696741664836aa3d7127837c5a
ms.sourcegitcommit: 92a278c0145798266ecbe052e645b2259bcbd62d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42892370"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Introducción a las plantillas comerciales de Teams 

Las plantillas de Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.

Las plantillas de Teams tienen definiciones preconstruidas de estructuras de equipo diseñadas según las necesidades de los minoristas. Puede usar las plantillas de Teams para crear rápidamente los tipos de equipos que funcionan bien en tiendas minoristas e implementarlos en toda la organización. También puede ampliar las plantillas de Teams para crear equipos que estén adaptados a las necesidades específicas de su organización.

En este artículo, presentaremos cada una de las plantillas de Teams y cómo le recomendamos que las use.

Este artículo le interesa si es responsable de planear, implementar y administrar varios equipos en la organización minorista. Damos por hecho que ya ha implementado el servicio de Teams en su organización. Si aún no ha implementado Teams, empiece por leer [cómo implementar Microsoft Teams](How-to-roll-out-teams.md).

Para obtener más información sobre las plantillas de equipo en general, consulte Introducción a [las plantillas](get-started-with-teams-templates.md)de Teams.

## <a name="store-template"></a>Plantilla de tienda

La plantilla de tienda es ideal para crear un equipo que represente una ubicación individual de la tienda minorista. Con la plantilla de la tienda, puede crear un equipo para cada ubicación de la tienda minorista de su organización.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Anuales <br>Tienda | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canales <ul><li>Desplaza la entrega\*</li><li>Aprendiendo\*</li></ul>\*Canales favoritos automáticos<br><br>Propiedades del equipo <ul><li>Visibilidad de equipo establecida como pública</li></ul> <br>Permisos de miembro <ul><li>No se pueden crear, actualizar o eliminar canales </li><li>No se pueden agregar o quitar aplicaciones </li><li>No se pueden crear/actualizar o quitar fichas</li><li>No se pueden crear, actualizar o quitar conectores</li><ul>|
||||

Recomendaciones para personalizar la plantilla de tienda de su organización:

- Si su organización tiene departamentos dentro de cada tienda, agregue un canal para cada departamento. Esto facilitará la comunicación y la colaboración dentro del Departamento.

- Si su organización tiene sitios Web internos (por ejemplo, un sitio de SharePoint), considere anclarlos como pestañas en el canal de equipo correspondiente. Para obtener más información, consulte [Introducción a las plantillas de Teams](get-started-with-teams-templates.md) .

## <a name="manager-collaboration-template"></a>Plantilla de colaboración de administrador

La plantilla de colaboración de administradores es otra de las plantillas de Teams diseñadas para las necesidades de las tiendas minoristas. La plantilla de colaboración de administrador es ideal para crear un equipo para un grupo de administradores que colaboren en tiendas/regiones, etc. Por ejemplo, si su organización tiene regiones, puede crear un equipo de colaboración de administradores para la región de California e incluir a todos los administradores de la tienda de esa región, así como al administrador regional de esa región.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Anuales <br>Tienda | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canales <ul><li>Operations\*</li><li>Aprendiendo\*</li></ul>\*Canales favoritos automáticos<br><br>Propiedades del equipo <ul><li>Visibilidad del equipo establecida en privado</li></ul> <br>Permisos de miembro <ul><li>Permite crear, actualizar o eliminar canales </li><li>Puede Agregar o quitar aplicaciones </li><li>Puede crear, actualizar o quitar fichas</li><li>Puede crear, actualizar o quitar conectores</li><ul>|
||||

Recomendaciones para personalizar la plantilla de colaboración de administrador de su organización:

- Si su organización tiene sitios Web internos (por ejemplo, un sitio de SharePoint) relevantes para los directores, considere la posibilidad de anclarlos como pestañas en un canal de equipo relevante (consulte la documentación [aquí](get-started-with-teams-templates.md) para obtener instrucciones).

## <a name="how-to-use-first-party-templates"></a>Cómo usar las plantillas de primera fiesta

Para usar estas plantillas, simplemente cambie la propiedad ' template@odata. bind ' en el cuerpo de la solicitud de ' Standard ' a la TemplateIDs anterior.  Para obtener más información sobre cómo implementar las plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Los canales de la plantilla se crearán automáticamente en la ficha General.

### <a name="example-store-template-extension-script"></a>Ejemplo: script de extensión de plantilla de tienda

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
