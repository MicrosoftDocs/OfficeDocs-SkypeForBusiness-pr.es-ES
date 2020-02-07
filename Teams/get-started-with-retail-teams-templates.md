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
ms.openlocfilehash: 31c6b04531b21996f897b3d668fdb6515f1e953f
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836820"
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
| Anuales <br>Guarde | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canales <ul><li>Desplaza la entrega\*</li><li>Aprendiendo\*</li></ul>\*Canales favoritos automáticos<br><br>Propiedades del equipo <ul><li>Visibilidad de equipo establecida como pública</li></ul> <br>Permisos de miembro <ul><li>No se pueden crear, actualizar o eliminar canales </li><li>No se pueden agregar o quitar aplicaciones </li><li>No se pueden crear/actualizar o quitar fichas</li><li>No se pueden crear, actualizar o quitar conectores</li><ul>|
||||

Recomendaciones para personalizar la plantilla de tienda de su organización:

- Si su organización tiene departamentos dentro de cada tienda, agregue un canal para cada departamento. Esto facilitará la comunicación y la colaboración dentro del Departamento.

- Si su organización tiene sitios Web internos (por ejemplo, un sitio de SharePoint), considere anclarlos como pestañas en el canal de equipo correspondiente. Para obtener más información, consulte [Introducción a las plantillas de Teams](get-started-with-teams-templates.md) .

## <a name="manager-collaboration-template"></a>Plantilla de colaboración de administrador

La plantilla de colaboración de administradores es otra de las plantillas de Teams diseñadas para las necesidades de las tiendas minoristas. La plantilla de colaboración de administrador es ideal para crear un equipo para un grupo de administradores que colaboren en tiendas/regiones, etc. Por ejemplo, si su organización tiene regiones, puede crear un equipo de colaboración de administradores para la región de California e incluir a todos los administradores de la tienda de esa región, así como al administrador regional de esa región.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Anuales <br>Guarde | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canales <ul><li>Operations\*</li><li>Aprendiendo\*</li></ul>\*Canales favoritos automáticos<br><br>Propiedades del equipo <ul><li>Visibilidad del equipo establecida en privado</li></ul> <br>Permisos de miembro <ul><li>Permite crear, actualizar o eliminar canales </li><li>Puede Agregar o quitar aplicaciones </li><li>Puede crear, actualizar o quitar fichas</li><li>Puede crear, actualizar o quitar conectores</li><ul>|
||||

Recomendaciones para personalizar la plantilla de colaboración de administrador de su organización:

- Si su organización tiene sitios Web internos (por ejemplo, un sitio de SharePoint) relevantes para los directores, considere la posibilidad de anclarlos como pestañas en un canal de equipo relevante (consulte la documentación [aquí](get-started-with-teams-templates.md) para obtener instrucciones).
