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
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424640"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="4ad19-103">Introducción a las plantillas de Teams para el comercio minorista</span><span class="sxs-lookup"><span data-stu-id="4ad19-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="4ad19-104">Las plantillas de Teams le permiten crear equipos de forma rápida y sencilla al proporcionar una plantilla de configuración predefinida, canales y aplicaciones preinstaladas.</span><span class="sxs-lookup"><span data-stu-id="4ad19-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="4ad19-105">Las plantillas de Teams tienen definiciones predefinidas de estructuras de equipo diseñadas en función de las necesidades del comercio minorista.</span><span class="sxs-lookup"><span data-stu-id="4ad19-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="4ad19-106">Puede usar plantillas de Teams para crear rápidamente los tipos de equipos que funcionan bien para el comercio minorista e implementarlos en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="4ad19-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="4ad19-107">También puede ampliar las plantillas de Teams para crear equipos que se adapten a las necesidades específicas de su organización.</span><span class="sxs-lookup"><span data-stu-id="4ad19-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="4ad19-108">En este artículo, le mostraremos cada una de las plantillas de Teams y le recomendaremos cómo usarlas.</span><span class="sxs-lookup"><span data-stu-id="4ad19-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="4ad19-109">Este artículo le ayudará si es responsable de planear, implementar y administrar varios equipos en toda su organización minorista.</span><span class="sxs-lookup"><span data-stu-id="4ad19-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="4ad19-110">Ya ha implementado el servicio de Teams en su organización.</span><span class="sxs-lookup"><span data-stu-id="4ad19-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="4ad19-111">Si todavía no ha implementado Teams, empiece por leer [Cómo implementar Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4ad19-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="4ad19-112">Para obtener más información sobre las plantillas de equipo en general, consulte [Introducción a las plantillas de Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="4ad19-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="4ad19-113">Plantilla de tienda</span><span class="sxs-lookup"><span data-stu-id="4ad19-113">Store template</span></span>

<span data-ttu-id="4ad19-114">La plantilla de tienda es ideal para crear un equipo que represente la ubicación de una tienda.</span><span class="sxs-lookup"><span data-stu-id="4ad19-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="4ad19-115">Con la plantilla de tienda, puede crear un equipo para cada ubicación de las tiendas de su organización.</span><span class="sxs-lookup"><span data-stu-id="4ad19-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="4ad19-116">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="4ad19-116">Base template type</span></span> | <span data-ttu-id="4ad19-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4ad19-117">baseTemplateId</span></span> | <span data-ttu-id="4ad19-118">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="4ad19-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="4ad19-119">Comercio minorista:</span><span class="sxs-lookup"><span data-stu-id="4ad19-119">Retail -</span></span> <br><span data-ttu-id="4ad19-120">Tienda</span><span class="sxs-lookup"><span data-stu-id="4ad19-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="4ad19-121">Canales</span><span class="sxs-lookup"><span data-stu-id="4ad19-121">Channels</span></span> <ul><li><span data-ttu-id="4ad19-122">Cambio de turno\*</span><span class="sxs-lookup"><span data-stu-id="4ad19-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="4ad19-123">Aprendizaje\*</span><span class="sxs-lookup"><span data-stu-id="4ad19-123">Learning\*</span></span></li></ul><span data-ttu-id="4ad19-124">\*Canales marcados como favoritos automáticamente</span><span class="sxs-lookup"><span data-stu-id="4ad19-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="4ad19-125">Propiedades del equipo</span><span class="sxs-lookup"><span data-stu-id="4ad19-125">Team properties</span></span> <ul><li><span data-ttu-id="4ad19-126">Visibilidad de equipo establecida en Público</span><span class="sxs-lookup"><span data-stu-id="4ad19-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="4ad19-127">Permisos de miembro</span><span class="sxs-lookup"><span data-stu-id="4ad19-127">Member permissions</span></span> <ul><li><span data-ttu-id="4ad19-128">No se pueden crear, actualizar ni eliminar canales</span><span class="sxs-lookup"><span data-stu-id="4ad19-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="4ad19-129">No se pueden agregar ni quitar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4ad19-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="4ad19-130">No se pueden crear, actualizar ni quitar pestañas</span><span class="sxs-lookup"><span data-stu-id="4ad19-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="4ad19-131">No se pueden crear, actualizar ni quitar conectores</span><span class="sxs-lookup"><span data-stu-id="4ad19-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="4ad19-132">Formas recomendadas para personalizar la plantilla de tienda para su organización:</span><span class="sxs-lookup"><span data-stu-id="4ad19-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="4ad19-133">Si la organización tiene departamentos en cada tienda, agregue un canal para cada departamento.</span><span class="sxs-lookup"><span data-stu-id="4ad19-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="4ad19-134">Agregar un canal facilita la comunicación y la colaboración dentro del departamento.</span><span class="sxs-lookup"><span data-stu-id="4ad19-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="4ad19-135">Si su organización tiene sitios web internos (por ejemplo, un sitio de SharePoint), considere la posibilidad de anclarlos como pestañas en el canal de equipo relevante.</span><span class="sxs-lookup"><span data-stu-id="4ad19-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="4ad19-136">Consulte la [Introducción a las plantillas de Teams](get-started-with-teams-templates.md) para obtener más instrucciones.</span><span class="sxs-lookup"><span data-stu-id="4ad19-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="4ad19-137">Plantilla de colaboración de encargados</span><span class="sxs-lookup"><span data-stu-id="4ad19-137">Manager Collaboration template</span></span>

<span data-ttu-id="4ad19-138">La plantilla de colaboración de encargados es otra de las plantillas de Teams diseñadas para las necesidades del comercio minorista.</span><span class="sxs-lookup"><span data-stu-id="4ad19-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="4ad19-139">La plantilla de colaboración de encargados es ideal para crear un equipo para un conjunto de encargados con el que poder colaborar en tiendas o zonas, y mucho más.</span><span class="sxs-lookup"><span data-stu-id="4ad19-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="4ad19-140">Por ejemplo, si su organización se encuentra en varias zonas, puede crear un equipo de colaboración de encargados de California e incluir todos los encargados de las tiendas de esa zona, así como el encargado regional de la misma.</span><span class="sxs-lookup"><span data-stu-id="4ad19-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="4ad19-141">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="4ad19-141">Base template type</span></span> | <span data-ttu-id="4ad19-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4ad19-142">baseTemplateId</span></span> | <span data-ttu-id="4ad19-143">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="4ad19-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="4ad19-144">Comercio minorista:</span><span class="sxs-lookup"><span data-stu-id="4ad19-144">Retail -</span></span> <br><span data-ttu-id="4ad19-145">Tienda</span><span class="sxs-lookup"><span data-stu-id="4ad19-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="4ad19-146">Canales</span><span class="sxs-lookup"><span data-stu-id="4ad19-146">Channels</span></span> <ul><li><span data-ttu-id="4ad19-147">Operaciones\*</span><span class="sxs-lookup"><span data-stu-id="4ad19-147">Operations\*</span></span></li><li><span data-ttu-id="4ad19-148">Aprendizaje\*</span><span class="sxs-lookup"><span data-stu-id="4ad19-148">Learning\*</span></span></li></ul><span data-ttu-id="4ad19-149">\*Canales marcados como favoritos automáticamente</span><span class="sxs-lookup"><span data-stu-id="4ad19-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="4ad19-150">Propiedades del equipo</span><span class="sxs-lookup"><span data-stu-id="4ad19-150">Team properties</span></span> <ul><li><span data-ttu-id="4ad19-151">Visibilidad de equipo establecida en Privado</span><span class="sxs-lookup"><span data-stu-id="4ad19-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="4ad19-152">Permisos de miembro</span><span class="sxs-lookup"><span data-stu-id="4ad19-152">Member permissions</span></span> <ul><li><span data-ttu-id="4ad19-153">Puede crear, actualizar y eliminar canales</span><span class="sxs-lookup"><span data-stu-id="4ad19-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="4ad19-154">Puede agregar y eliminar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4ad19-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="4ad19-155">Puede crear, actualizar y quitar pestañas</span><span class="sxs-lookup"><span data-stu-id="4ad19-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="4ad19-156">Puede crear, actualizar y quitar conectores</span><span class="sxs-lookup"><span data-stu-id="4ad19-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="4ad19-157">Formas recomendadas de personalizar la plantilla de colaboración de encargados para su organización:</span><span class="sxs-lookup"><span data-stu-id="4ad19-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="4ad19-158">Si la organización tiene sitios web internos, como un sitio de SharePoint, que sean relevantes para los encargados, considere la posibilidad de anclarlos como pestañas en un canal de equipo relevante.</span><span class="sxs-lookup"><span data-stu-id="4ad19-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="4ad19-159">Puede consultar la [documentación de la plantilla de Microsoft Teams](get-started-with-teams-templates.md) para obtener más instrucciones.</span><span class="sxs-lookup"><span data-stu-id="4ad19-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="4ad19-160">Cómo usar plantillas propias</span><span class="sxs-lookup"><span data-stu-id="4ad19-160">How to use first party templates</span></span>

<span data-ttu-id="4ad19-161">Para usar estas plantillas, cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "estándar" a los TemplateID anteriores.</span><span class="sxs-lookup"><span data-stu-id="4ad19-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="4ad19-162">Para obtener más información sobre cómo implementar plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="4ad19-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="4ad19-163">Los canales de la plantilla se crearán automáticamente en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="4ad19-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="4ad19-164">Ejemplo: script de extensiones para plantilla de tienda</span><span class="sxs-lookup"><span data-stu-id="4ad19-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="4ad19-165">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="4ad19-165">Relate topic</span></span>

[<span data-ttu-id="4ad19-166">Introducción a las plantillas de Teams en el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="4ad19-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
