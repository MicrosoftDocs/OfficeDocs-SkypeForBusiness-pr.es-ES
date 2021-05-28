---
title: Introducción a una plantilla de equipo en retail
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
description: Obtenga información sobre cómo usar plantillas de equipo para crear estructuras de equipo diseñadas para las necesidades del distribuidor proporcionando configuraciones predefinidas, canales y aplicaciones preinstaladas.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edc3b646af4577199b13a5803837625b8a9ea354
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684558"
---
# <a name="create-a-team-using-retail-team-templates"></a>Crear un equipo con plantillas de equipo minoristas

Las plantillas de equipo de Microsoft le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.

Las plantillas de equipo tienen definiciones predefinidas de estructuras de equipo diseñadas en función de las necesidades del distribuidor. Puede usar plantillas de equipo para crear rápidamente los tipos de equipos que funcionan bien para los minoristas e implementarlos en toda la organización. También puede ampliar las plantillas de equipo para crear equipos que se adapten a sus necesidades organizativas específicas.

En este artículo, presentaremos cada una de las plantillas de equipo y le recomendamos cómo usarlas.

Este artículo le ayudará si es responsable de planear, implementar y administrar varios equipos en toda su organización minorista. Ya ha implementado el servicio de Teams en su organización. Si todavía no ha implementado Teams, empiece por leer [Cómo implementar Microsoft Teams](./deploy-overview.md).

Para obtener más información sobre las plantillas de equipo en general, consulte Introducción [a las plantillas de equipo.](get-started-with-teams-templates.md)

| Quién | Método de uso: |
| ---- | --------- |
| Administradores y profesionales de TI | [Use el Teams de administración para](#use-the-team-templates-in-the-teams-admin-center) crear equipos basados en las plantillas de equipo de ventas minoristas.|
| Desarrolladores e integradores de sistemas | [Use microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) para crear equipos basados en las plantillas de equipo de ventas minoristas. |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a>Usar las plantillas de equipo en el centro Teams administración

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

## <a name="use-the-team-templates-with-the-microsoft-graph"></a>Use las plantillas de equipo con microsoft Graph

### <a name="store-template"></a>Plantilla de tienda

La plantilla de tienda es ideal para crear un equipo que represente la ubicación de una tienda. Con la plantilla de tienda, puede crear un equipo para cada ubicación de las tiendas de su organización.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Comercio minorista: <br>Tienda | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canales <ul><li>Cambio de turno\*</li><li>Aprendizaje\*</li></ul>\*Canales marcados como favoritos automáticamente<br><br>Propiedades del equipo <ul><li>Visibilidad de equipo establecida en Público</li></ul> <br>Permisos de miembro <ul><li>No se pueden crear, actualizar ni eliminar canales </li><li>No se pueden agregar ni quitar aplicaciones </li><li>No se pueden crear, actualizar ni quitar pestañas</li><li>No se pueden crear, actualizar ni quitar conectores</li><ul>|
||||

Formas recomendadas para personalizar la plantilla de tienda para su organización:

- Si la organización tiene departamentos en cada tienda, agregue un canal para cada departamento. Agregar un canal facilita la comunicación y la colaboración dentro del departamento.

- Si su organización tiene sitios web internos (por ejemplo, un sitio de SharePoint), considere la posibilidad de anclarlos como pestañas en el canal de equipo relevante. Consulte Introducción [a las plantillas de equipo](get-started-with-teams-templates.md) para obtener instrucciones.

### <a name="manager-collaboration-template"></a>Plantilla de colaboración de encargados

La plantilla Colaboración de administrador es otra de las plantillas de equipo diseñadas en función de las necesidades del distribuidor. La plantilla de colaboración de encargados es ideal para crear un equipo para un conjunto de encargados con el que poder colaborar en tiendas o zonas, y mucho más. Por ejemplo, si su organización se encuentra en varias zonas, puede crear un equipo de colaboración de encargados de California e incluir todos los encargados de las tiendas de esa zona, así como el encargado regional de la misma.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Comercio minorista: <br>Tienda | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canales <ul><li>Operaciones\*</li><li>Aprendizaje\*</li></ul>\*Canales marcados como favoritos automáticamente<br><br>Propiedades del equipo <ul><li>Visibilidad de equipo establecida en Privado</li></ul> <br>Permisos de miembro <ul><li>Puede crear, actualizar y eliminar canales </li><li>Puede agregar y eliminar aplicaciones </li><li>Puede crear, actualizar y quitar pestañas</li><li>Puede crear, actualizar y quitar conectores</li><ul>|
||||

Formas recomendadas de personalizar la plantilla de colaboración de encargados para su organización:

- Si la organización tiene sitios web internos, como un sitio de SharePoint, que sean relevantes para los encargados, considere la posibilidad de anclarlos como pestañas en un canal de equipo relevante. Puede echar un vistazo a la documentación de plantilla del equipo [de Microsoft para](get-started-with-teams-templates.md) obtener instrucciones.

## <a name="how-to-use-first-party-templates"></a>Cómo usar plantillas de terceros

Para usar estas plantillas, cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "estándar" a los TemplateID anteriores.  Para obtener más información sobre cómo implementar plantillas de equipo, vea el artículo de Microsoft Graph sobre cómo [crear un equipo.](/graph/api/team-post?view=graph-rest-beta)

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
