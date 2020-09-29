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
description: Obtenga información sobre cómo usar las plantillas de Teams para crear estructuras de equipo diseñadas para las necesidades de los minoristas al proporcionar una configuración predefinida, canales y aplicaciones preinstaladas.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33be31797833152aea9dd477698be56884a5aa0b
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294636"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="73058-103">Introducción a las plantillas comerciales de Teams</span><span class="sxs-lookup"><span data-stu-id="73058-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="73058-104">Las plantillas de Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.</span><span class="sxs-lookup"><span data-stu-id="73058-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="73058-105">Las plantillas de Teams tienen definiciones preconstruidas de estructuras de equipo diseñadas según las necesidades de los minoristas.</span><span class="sxs-lookup"><span data-stu-id="73058-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="73058-106">Puede usar las plantillas de Teams para crear rápidamente los tipos de equipos que funcionan bien en tiendas minoristas e implementarlos en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="73058-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="73058-107">También puede ampliar las plantillas de Teams para crear equipos que estén adaptados a las necesidades específicas de su organización.</span><span class="sxs-lookup"><span data-stu-id="73058-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="73058-108">En este artículo, presentaremos cada una de las plantillas de Teams y le recomendamos que las use.</span><span class="sxs-lookup"><span data-stu-id="73058-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="73058-109">Este artículo le interesa si es responsable de planear, implementar y administrar varios equipos en la organización minorista.</span><span class="sxs-lookup"><span data-stu-id="73058-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="73058-110">Ya ha implementado el servicio de Teams en su organización.</span><span class="sxs-lookup"><span data-stu-id="73058-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="73058-111">Si aún no ha implementado Teams, empiece por leer [cómo implementar Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="73058-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="73058-112">Para obtener más información sobre las plantillas de equipo en general, consulte Introducción a [las plantillas](get-started-with-teams-templates.md)de Teams.</span><span class="sxs-lookup"><span data-stu-id="73058-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="73058-113">Plantilla de tienda</span><span class="sxs-lookup"><span data-stu-id="73058-113">Store template</span></span>

<span data-ttu-id="73058-114">La plantilla de tienda es ideal para crear un equipo que represente una ubicación individual de la tienda minorista.</span><span class="sxs-lookup"><span data-stu-id="73058-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="73058-115">Con la plantilla de la tienda, puede crear un equipo para cada ubicación de la tienda minorista de su organización.</span><span class="sxs-lookup"><span data-stu-id="73058-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="73058-116">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="73058-116">Base template type</span></span> | <span data-ttu-id="73058-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="73058-117">baseTemplateId</span></span> | <span data-ttu-id="73058-118">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="73058-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="73058-119">Anuales</span><span class="sxs-lookup"><span data-stu-id="73058-119">Retail -</span></span> <br><span data-ttu-id="73058-120">Tienda</span><span class="sxs-lookup"><span data-stu-id="73058-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="73058-121">Canales</span><span class="sxs-lookup"><span data-stu-id="73058-121">Channels</span></span> <ul><li><span data-ttu-id="73058-122">Desplaza la entrega\*</span><span class="sxs-lookup"><span data-stu-id="73058-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="73058-123">Aprendiendo\*</span><span class="sxs-lookup"><span data-stu-id="73058-123">Learning\*</span></span></li></ul><span data-ttu-id="73058-124">\*Canales favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="73058-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="73058-125">Propiedades del equipo</span><span class="sxs-lookup"><span data-stu-id="73058-125">Team properties</span></span> <ul><li><span data-ttu-id="73058-126">Visibilidad de equipo establecida como pública</span><span class="sxs-lookup"><span data-stu-id="73058-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="73058-127">Permisos de miembro</span><span class="sxs-lookup"><span data-stu-id="73058-127">Member permissions</span></span> <ul><li><span data-ttu-id="73058-128">No se pueden crear, actualizar o eliminar canales</span><span class="sxs-lookup"><span data-stu-id="73058-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="73058-129">No se pueden agregar o quitar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="73058-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="73058-130">No se pueden crear, actualizar o quitar fichas</span><span class="sxs-lookup"><span data-stu-id="73058-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="73058-131">No se pueden crear, actualizar o quitar conectores</span><span class="sxs-lookup"><span data-stu-id="73058-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="73058-132">Recomendaciones para personalizar la plantilla de tienda de su organización:</span><span class="sxs-lookup"><span data-stu-id="73058-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="73058-133">Si su organización tiene departamentos dentro de cada tienda, agregue un canal para cada departamento.</span><span class="sxs-lookup"><span data-stu-id="73058-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="73058-134">Agregar un canal facilita la comunicación y la colaboración dentro del Departamento.</span><span class="sxs-lookup"><span data-stu-id="73058-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="73058-135">Si su organización tiene sitios Web internos (por ejemplo, un sitio de SharePoint), considere anclarlos como pestañas en el canal de equipo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="73058-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="73058-136">Para obtener más información, consulte [Introducción a las plantillas de Teams](get-started-with-teams-templates.md) .</span><span class="sxs-lookup"><span data-stu-id="73058-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="73058-137">Plantilla de colaboración de administrador</span><span class="sxs-lookup"><span data-stu-id="73058-137">Manager Collaboration template</span></span>

<span data-ttu-id="73058-138">La plantilla de colaboración de administradores es otra de las plantillas de Teams diseñadas para las necesidades de las tiendas minoristas.</span><span class="sxs-lookup"><span data-stu-id="73058-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="73058-139">La plantilla de colaboración de administrador es ideal para crear un equipo para un conjunto de administradores que colaboran en todos los almacenes/regiones, y mucho más.</span><span class="sxs-lookup"><span data-stu-id="73058-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="73058-140">Por ejemplo, si su organización tiene regiones, puede crear un equipo de colaboración de administradores para la región de California e incluir a todos los administradores de la tienda de esa región, así como al administrador regional de esa región.</span><span class="sxs-lookup"><span data-stu-id="73058-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="73058-141">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="73058-141">Base template type</span></span> | <span data-ttu-id="73058-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="73058-142">baseTemplateId</span></span> | <span data-ttu-id="73058-143">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="73058-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="73058-144">Anuales</span><span class="sxs-lookup"><span data-stu-id="73058-144">Retail -</span></span> <br><span data-ttu-id="73058-145">Tienda</span><span class="sxs-lookup"><span data-stu-id="73058-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="73058-146">Canales</span><span class="sxs-lookup"><span data-stu-id="73058-146">Channels</span></span> <ul><li><span data-ttu-id="73058-147">Operations\*</span><span class="sxs-lookup"><span data-stu-id="73058-147">Operations\*</span></span></li><li><span data-ttu-id="73058-148">Aprendiendo\*</span><span class="sxs-lookup"><span data-stu-id="73058-148">Learning\*</span></span></li></ul><span data-ttu-id="73058-149">\*Canales favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="73058-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="73058-150">Propiedades del equipo</span><span class="sxs-lookup"><span data-stu-id="73058-150">Team properties</span></span> <ul><li><span data-ttu-id="73058-151">Visibilidad del equipo establecida en privado</span><span class="sxs-lookup"><span data-stu-id="73058-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="73058-152">Permisos de miembro</span><span class="sxs-lookup"><span data-stu-id="73058-152">Member permissions</span></span> <ul><li><span data-ttu-id="73058-153">Permite crear, actualizar o eliminar canales</span><span class="sxs-lookup"><span data-stu-id="73058-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="73058-154">Puede Agregar o quitar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="73058-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="73058-155">Puede crear, actualizar o quitar fichas</span><span class="sxs-lookup"><span data-stu-id="73058-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="73058-156">Puede crear, actualizar o quitar conectores</span><span class="sxs-lookup"><span data-stu-id="73058-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="73058-157">Recomendaciones para personalizar la plantilla de colaboración de administrador de su organización:</span><span class="sxs-lookup"><span data-stu-id="73058-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="73058-158">Si su organización tiene sitios Web internos, como un sitio de SharePoint, que sean relevantes para los directores, considere la posibilidad de anclarlos como pestañas en un canal de equipo relevante.</span><span class="sxs-lookup"><span data-stu-id="73058-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="73058-159">Puede consultar la documentación de la [plantilla Microsoft Teams](get-started-with-teams-templates.md) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="73058-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="73058-160">Cómo usar las plantillas de primera fiesta</span><span class="sxs-lookup"><span data-stu-id="73058-160">How to use first party templates</span></span>

<span data-ttu-id="73058-161">Para usar estas plantillas, cambie la propiedad ' template@odata. bind ' en el cuerpo de la solicitud de ' Standard ' a la TemplateIDs anterior.</span><span class="sxs-lookup"><span data-stu-id="73058-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="73058-162">Para obtener más información sobre cómo implementar las plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="73058-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="73058-163">Los canales de la plantilla se crearán automáticamente en la ficha General.</span><span class="sxs-lookup"><span data-stu-id="73058-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="73058-164">Ejemplo: script de extensión de plantilla de tienda</span><span class="sxs-lookup"><span data-stu-id="73058-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="73058-165">Relacionar tema</span><span class="sxs-lookup"><span data-stu-id="73058-165">Relate topic</span></span>

[<span data-ttu-id="73058-166">Introducción a las plantillas de Teams en la consola de administración</span><span class="sxs-lookup"><span data-stu-id="73058-166">Get started with Teams templates in the Admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
