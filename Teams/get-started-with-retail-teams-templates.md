---
title: Introducción a las plantillas de Teams para el comercio minorista
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
description: Obtenga información sobre cómo usar plantillas de Teams para crear estructuras de equipo diseñadas para las necesidades de los minoristas, proporcionando una configuración predefinida, canales y aplicaciones preinstaladas.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d72f88bb33dca16254ec09a2ea89ac90a0e7aca
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995148"
---
# <a name="create-a-team-using-teams-retail-templates"></a>Crear un equipo con plantillas de venta al por menor de Teams

Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla al proporcionar una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.

Las plantillas de Teams tienen definiciones predefinidas de estructuras de equipo diseñadas en función de las necesidades del comercio minorista. Puede usar plantillas de Teams para crear rápidamente los tipos de equipos que funcionan bien para el comercio minorista e implementarlos en toda la organización. También puede ampliar las plantillas de Teams para crear equipos que se adapten a las necesidades específicas de su organización.

En este artículo, le mostraremos cada una de las plantillas de Teams y le recomendaremos cómo usarlas.

Este artículo le ayudará si es responsable de planear, implementar y administrar varios equipos en toda su organización minorista. Ya ha implementado el servicio de Teams en su organización. Si todavía no ha implementado Teams, empiece por leer [Cómo implementar Microsoft Teams](./deploy-overview.md).

Para obtener más información sobre las plantillas de equipo en general, consulte [Introducción a las plantillas de Teams](get-started-with-teams-templates.md).

| Quién | Método de uso: |
| ---- | --------- |
| Administradores y profesionales de TI | [Use el Centro de administración de Teams](#use-the-teams-templates-in-the-teams-admin-center) para crear equipos basados en las plantillas minoristas de Teams.|
| Desarrolladores e integradores de sistemas | [Use Microsoft Graph para](#use-the-teams-templates-with-the-microsoft-graph) crear equipos basados en las plantillas minoristas de Teams. |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Usar las plantillas de Teams en el Centro de administración de Teams

### <a name="organize-a-store"></a>Organizar una tienda

Reúna a sus empleados en una experiencia centralizada para administrar tareas, compartir documentos y resolver problemas de clientes. Integre aplicaciones adicionales para simplificar los procesos de inicio y finalización de turnos.

| Tipo de plantilla base |baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------|-- |----------------------------------------------------- |
|Organizar una tienda|`retailStore`|Canales: <ul><li>General<li>Cambio de turno</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li></ul>|
||||

### <a name="manager-collaboration"></a>Colaboración del administrador

La plantilla Colaboración de administradores es ideal para crear un equipo para que un conjunto de administradores colabore entre tiendas o regiones, etc. Por ejemplo, si su organización tiene regiones, puede crear un equipo de colaboración de administradores para la región de California e incluir todos los administradores de tienda de esa región, junto con el administrador regional de esa región.

| Tipo de plantilla base| baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------|- |----------------------------------------------------- |
|Comercio al por menor: colaboración de administradores|`retailManagerCollaboration` |Canales: <ul><li>General<li>Operaciones</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li></ul>|
||||

## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Usar las plantillas de Teams con Microsoft Graph

### <a name="store-template"></a>Plantilla de tienda

La plantilla de tienda es ideal para crear un equipo que represente la ubicación de una tienda. Con la plantilla de tienda, puede crear un equipo para cada ubicación de las tiendas de su organización.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Comercio minorista: <br>Tienda | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canales <ul><li>Cambio de turno\*</li><li>Aprendizaje\*</li></ul>\*Canales marcados como favoritos automáticamente<br><br>Propiedades del equipo <ul><li>Visibilidad de equipo establecida en Público</li></ul> <br>Permisos de miembro <ul><li>No se pueden crear, actualizar ni eliminar canales </li><li>No se pueden agregar ni quitar aplicaciones </li><li>No se pueden crear, actualizar ni quitar pestañas</li><li>No se pueden crear, actualizar ni quitar conectores</li><ul>|
||||

Formas recomendadas para personalizar la plantilla de tienda para su organización:

- Si la organización tiene departamentos en cada tienda, agregue un canal para cada departamento. Agregar un canal facilita la comunicación y la colaboración dentro del departamento.

- Si su organización tiene sitios web internos (por ejemplo, un sitio de SharePoint), considere la posibilidad de anclarlos como pestañas en el canal de equipo relevante. Consulte la [Introducción a las plantillas de Teams](get-started-with-teams-templates.md) para obtener más instrucciones.

### <a name="manager-collaboration-template"></a>Plantilla de colaboración de encargados

La plantilla de colaboración de encargados es otra de las plantillas de Teams diseñadas para las necesidades del comercio minorista. La plantilla de colaboración de encargados es ideal para crear un equipo para un conjunto de encargados con el que poder colaborar en tiendas o zonas, y mucho más. Por ejemplo, si su organización se encuentra en varias zonas, puede crear un equipo de colaboración de encargados de California e incluir todos los encargados de las tiendas de esa zona, así como el encargado regional de la misma.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Comercio minorista: <br>Tienda | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canales <ul><li>Operaciones\*</li><li>Aprendizaje\*</li></ul>\*Canales marcados como favoritos automáticamente<br><br>Propiedades del equipo <ul><li>Visibilidad de equipo establecida en Privado</li></ul> <br>Permisos de miembro <ul><li>Puede crear, actualizar y eliminar canales </li><li>Puede agregar y eliminar aplicaciones </li><li>Puede crear, actualizar y quitar pestañas</li><li>Puede crear, actualizar y quitar conectores</li><ul>|
||||

Formas recomendadas de personalizar la plantilla de colaboración de encargados para su organización:

- Si la organización tiene sitios web internos, como un sitio de SharePoint, que sean relevantes para los encargados, considere la posibilidad de anclarlos como pestañas en un canal de equipo relevante. Puede consultar la [documentación de la plantilla de Microsoft Teams](get-started-with-teams-templates.md) para obtener más instrucciones.

## <a name="how-to-use-first-party-templates"></a>Cómo usar plantillas propias

Para usar estas plantillas, cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "estándar" a los TemplateID anteriores.  Para obtener más información sobre cómo implementar plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Los canales de la plantilla se crearán automáticamente en la pestaña General.

### <a name="example-store-template-extension-script"></a>Ejemplo: script de extensiones para plantilla de tienda

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
