---
title: Usar plantillas de equipo de venta minorista
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
- m365-frontline
ms.localizationpriority: high
search.appverid: MET150
description: Obtenga información sobre cómo administrar y usar las plantillas de equipos de venta minorista en el Centro de administración de Teams y con Microsoft Graph para crear equipos de forma rápida y sencilla para su organización de venta minorista.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d8c6af4cc86051c9233e06d0bf6c67abe1a4ad39
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837340"
---
# <a name="use-retail-team-templates"></a>Usar plantillas de equipo de venta minorista

## <a name="overview"></a>Información general

Las plantillas de equipo de Microsoft Teams le permiten crear equipos de forma rápida y sencilla al proporcionar una estructura predefinida de equipos de configuración, canales y aplicaciones preinstaladas.

Para los minoristas, las plantillas de equipo pueden ser especialmente eficaces, ya que le ayudan a implementar rápidamente equipos coherentes en toda la organización. Las plantillas también han ayudado al personal a orientarse con la forma de usar Teams de manera eficaz.

Teams incluye plantillas diseñadas específicamente para las necesidades de los minoristas. Use estas plantillas predefinidas para crear rápidamente equipos para que el personal pueda comunicarse y colaborar. En este artículo, le presentamos cada una de estas plantillas y le recomendamos que las use.

La forma de administrar y trabajar con plantillas de equipo depende de si es administrador o desarrollador.

|Si está: | A continuación, usted: |
| ---- | --------- |
| Un administrador o un profesional de TI |[Administrar plantillas de equipo en el centro de administración de Teams](#manage-team-templates-in-the-teams-admin-center). Vea las plantillas de equipo y aplique directivas de plantillas para controlar qué plantillas puede usar el personal para crear equipos en Teams. |
| Un desarrollador | [Use Microsoft Graph](#use-team-templates-with-microsoft-graph) para crear equipos a partir de plantillas de equipo. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Administrar plantillas de equipo en el Centro de administración de Teams

Como un administrador, puede administrar plantillas de equipo en el Centro de administración de Microsoft Teams. Aquí puede ver los detalles acerca de cada plantilla. También puede [crear y asignar directivas de plantillas](templates-policies.md) al personal para controlar qué plantillas ven en Teams para [crear equipos](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Para obtener más información sobre las plantillas de equipo en general, vea [Introducción a las plantillas de Teams en el Centro de administración](get-started-with-teams-templates-in-the-admin-console.md).

Actualmente ofrecemos las siguientes plantillas de equipo de venta directa predefinidas. Para verlos, en el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Teams** > **plantillas de Teams**.

> [!NOTE]
> Un asterisco (*) indica que la plantilla es una *plantilla conectada a Microsoft 365*. Cuando los usuarios crean un equipo con la plantilla, la plantilla de SharePoint conectada se aplica al sitio y al equipo. Los componentes de SharePoint, como páginas, listas e integraciones de Power Platform, se agregan y anclan automáticamente como pestañas al canal General del equipo. Los usuarios pueden editar estas páginas y listas directamente desde Teams.
>
> Para obtener más información sobre las plantillas de SharePoint, vea [Aplicar y personalizar plantillas de sitio de SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>Administrar una Store*

Reúna a sus empleados minoristas en una experiencia central para administrar tareas, compartir documentos y resolver problemas de los clientes. Integre aplicaciones adicionales para simplificar los procesos de inicio y finalización de turnos.

> [!div class="mx-tdBreakAll"]
>| Tipo de plantilla |TemplateId | Propiedades que vienen con esta plantilla |
>| ------------------|-- |----------------------------------------------------- |
>| Administrar una Tienda| `retailStore` |Canales: <ul><li>General<li>Desplazar la entrega</li><li>Store Readiness</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Aprobaciones</li><li>Inspección</li><li>Listas<ul><li>Lista de inventario</li></ul></li><li>Páginas de SharePoint<ul><li>Nuestra tienda</li></ul></li><li>Turnos</li><li>Tareas por Planner y To Do</li><li>Wiki</li></ul>|

### <a name="retail-for-managers"></a>Venta al por menor para administradores*

Cree un equipo para que un conjunto de administradores colabore entre tiendas o regiones. Por ejemplo, si su organización tiene regiones, puede crear un equipo para la región de California e incluir todos los administradores de almacén de esa región, junto con el administrador regional de esa región.

> [!div class="mx-tdBreakAll"]
>| Tipo de plantilla| TemplateId | Propiedades que vienen con esta plantilla |
>| ------------------|- |----------------------------------------------------- |
>| Venta al por menor para administradores| `retailManagerCollaboration` |Canales: <ul><li>General<li>Operaciones</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Aprobaciones</li><li>Inspección</li><li>Páginas de SharePoint<ul><li>Nuestra tienda</li></ul></li><li>Tareas por Planner y To Do</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Uso de plantillas de equipo con Microsoft Graph

Los desarrolladores pueden usar Microsoft Graph para crear equipos a partir de plantillas de equipo predefinidas. Para obtener más información sobre el uso de plantillas de equipo con Microsoft Graph, vea [Introducción a las plantillas de equipo mediante Microsoft Graph](get-started-with-teams-templates.md), [información general de la API de Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0) y [tipo de recurso teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Estas son las plantillas de equipo de venta directa predefinidas.

> [!NOTE]
> Un asterisco (*) indica que la plantilla es una *plantilla conectada a Microsoft 365*. Cuando los usuarios crean un equipo con la plantilla, la plantilla de SharePoint conectada se aplica al sitio y al equipo. Los componentes de SharePoint, como páginas, listas e integraciones de Power Platform, se agregan y anclan automáticamente como pestañas al canal General del equipo. Los usuarios pueden editar estas páginas y listas directamente desde Teams.
>
> Para obtener más información sobre las plantillas de SharePoint, vea [Aplicar y personalizar plantillas de sitio de SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>Administrar una Store*

Use esta plantilla para crear un equipo para cada ubicación de tienda minorista de su organización.

> [!div class="mx-tdBreakAll"]
>| Tipo de plantilla | TemplateId | Canales de plantilla |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Comercio minorista: <br>Tienda | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| Canales <ul><li>General</li><li>Desplazar la entrega</li><li>Store Readiness</li><li>Aprendizaje</li></ul>Propiedades del equipo <ul><li>Visibilidad de equipo establecida en Público</li></ul> <br>Permisos de miembro <ul><li>No se pueden crear, actualizar ni eliminar canales </li><li>No se pueden agregar ni quitar aplicaciones </li><li>No se pueden crear, actualizar o quitar pestañas</li><li>No se pueden crear, actualizar ni quitar conectores</li><ul>|

Formas recomendadas para personalizar la plantilla de tienda para su organización:

- Si la organización tiene departamentos en cada tienda, agregue un canal para cada departamento. Agregar un canal facilita la comunicación y la colaboración dentro del departamento.

- Si su organización tiene sitios web internos (por ejemplo, un sitio de SharePoint), considere la posibilidad de anclarlos como pestañas en el canal de equipo relevante.

### <a name="retail-for-managers"></a>Venta al por menor para administradores*

Use esta plantilla para crear un equipo para que un conjunto de administradores colabore entre tiendas o regiones. Por ejemplo, si su organización tiene regiones, puede crear un equipo para la región de California e incluir todos los administradores de almacén de esa región, junto con el administrador regional de esa región.

> [!div class="mx-tdBreakAll"]
>| Tipo de plantilla | TemplateId | Canales de plantilla |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Comercio minorista: <br>Colaboración del administrador | `https://graph.microsoft.com/beta/teamsTemplates('retailManagerCollaboration')`| Canales <ul><li>General</li><li>Operaciones</li><li>Aprendizaje</li></ul>Propiedades del equipo <ul><li>Visibilidad de equipo establecida en Privado</li></ul> <br>Permisos de miembro <ul><li>Puede crear, actualizar y eliminar canales </li><li>Puede agregar y quitar aplicaciones </li><li>Puede crear, actualizar y quitar pestañas</li><li>Puede crear, actualizar y quitar conectores</li><ul>|

Formas recomendadas de personalizar la plantilla de colaboración de encargados para su organización:

- Si la organización tiene sitios web internos, como un sitio de SharePoint, que sean relevantes para los encargados, considere la posibilidad de anclarlos como pestañas en un canal de equipo relevante.

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Cómo usar las plantillas de equipo con Microsoft Graph

Para usar estas plantillas, cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "standard" a TemplateIds anterior.  Para obtener más información sobre cómo implementar plantillas de equipo, vea el artículo de Microsoft Graph sobre cómo [crear un equipo](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Los canales de la plantilla se crearán automáticamente en la pestaña **General**.

### <a name="example-store-template-extension-script"></a>Ejemplo: Script de extensiones para plantilla de tienda

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

> [!NOTE]
> Si usa Microsoft Graph para crear un equipo a partir de un grupo o equipo de Microsoft 365 existente con una plantilla conectada a Microsoft 365, la plantilla de SharePoint conectada no se aplica automáticamente al sitio o al equipo. Tendrá que aplicar manualmente la plantilla de sitio de SharePoint después de crear el equipo. En Teams, vaya al equipo, seleccione **Más opciones** en la esquina superior derecha > **Abrir en SharePoint**. Después, elija **Configuración** > **Aplicar una plantilla de sitio** y seleccione la plantilla de sitio correspondiente.

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las plantillas de equipo en el centro de administración de Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Crear un equipo a partir de una plantilla](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introducción a las plantillas de equipo con Microsoft Graph](get-started-with-teams-templates.md)