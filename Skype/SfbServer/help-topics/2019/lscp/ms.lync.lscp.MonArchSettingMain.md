---
title: Configuración de archivado
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Utilice las configuraciones de archivado para controlar las opciones para su Skype para la implementación de servidor empresarial, incluidas la habilitación y deshabilitación de las siguientes opciones de archivado:'
ms.openlocfilehash: e32c42d5ef945b360ce4992ea9a33658bcc4068a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="archiving-configuration"></a><span data-ttu-id="6acb3-103">Configuración de archivado</span><span class="sxs-lookup"><span data-stu-id="6acb3-103">Archiving Configuration</span></span>
 
<span data-ttu-id="6acb3-104">Utilice las configuraciones de archivado para controlar las opciones para su Skype para la implementación de servidor empresarial, incluidas la habilitación y deshabilitación de las siguientes opciones de archivado:</span><span class="sxs-lookup"><span data-stu-id="6acb3-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="6acb3-105">Bloquear sesiones de mensajería instantánea o conferencias si no se pueden archivar</span><span class="sxs-lookup"><span data-stu-id="6acb3-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="6acb3-106">Integración con el almacenamiento de Exchange 2013, para los usuarios alojados en Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="6acb3-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="6acb3-107">Purgar datos archivados</span><span class="sxs-lookup"><span data-stu-id="6acb3-107">Purging of archived data</span></span>
    
<span data-ttu-id="6acb3-108">Las configuraciones de archivado están formadas por la configuración global y, de forma opcional, por una o varias configuraciones de archivado de sitio y grupo:</span><span class="sxs-lookup"><span data-stu-id="6acb3-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="6acb3-109">**Configuración global** La configuración global se crea de forma predeterminada en todos los Skype para las implementaciones de servidores empresariales.</span><span class="sxs-lookup"><span data-stu-id="6acb3-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="6acb3-110">La configuración global se puede editar, pero no eliminar.</span><span class="sxs-lookup"><span data-stu-id="6acb3-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="6acb3-111">Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="6acb3-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="6acb3-112">**Configuración de sitio (opcional)** Puede especificar uno o varios sitios las configuraciones de archivado, que cada uno de los cuales puede configurar para controlar las opciones de un sitio específico de archivado.</span><span class="sxs-lookup"><span data-stu-id="6acb3-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="6acb3-113">Una configuración de sitio reemplaza a la configuración global, pero solo en los sitios especificados en las configuraciones de sitio de archivado.</span><span class="sxs-lookup"><span data-stu-id="6acb3-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="6acb3-114">Las configuraciones de sitio se pueden editar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="6acb3-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="6acb3-115">**Configuración de grupo de servidores (opcional)** Puede especificar uno o más del grupo Configuración de archivado, al control de las opciones para un grupo específico de archivado.</span><span class="sxs-lookup"><span data-stu-id="6acb3-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="6acb3-116">Una configuración de grupo reemplaza a la configuración global y la configuración del sitio, pero solo en los grupos especificados en las configuraciones de grupo de archivado.</span><span class="sxs-lookup"><span data-stu-id="6acb3-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="6acb3-117">Las configuraciones de grupo se pueden editar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="6acb3-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6acb3-118">Las configuraciones de archivado se aplican a los usuarios hospedados en Skype para Business Server y, si se utiliza Exchange para almacenar datos de archivado en Microsoft Exchange, para los usuarios alojados en Exchange 2013, pero se implementan de forma ligeramente diferente para los usuarios alojados en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="6acb3-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="6acb3-119">En la siguiente sección se describen estas diferencias.</span><span class="sxs-lookup"><span data-stu-id="6acb3-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="6acb3-p105">La página **Configuración de archivado** muestra cada directiva de archivado configurada en la implementación. También muestra el nombre de la directiva, el ámbito (global, sitio o usuario) y qué opciones de archivado están habilitadas para cada configuración de archivado. En la página **Configuración de archivado** dispone de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6acb3-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="6acb3-123">**Nuevo** Puede agregar uno o varios de cada una de las siguientes configuraciones de archivado opcionales.</span><span class="sxs-lookup"><span data-stu-id="6acb3-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="6acb3-124">Configuración de sitio</span><span class="sxs-lookup"><span data-stu-id="6acb3-124">Site configuration</span></span>
    
  - <span data-ttu-id="6acb3-125">Configuración del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6acb3-125">Pool configuration</span></span>
    
- <span data-ttu-id="6acb3-126">**Editar** Puede cambiar las opciones de cualquiera de las configuraciones de archivado que aparecen en la página.</span><span class="sxs-lookup"><span data-stu-id="6acb3-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="6acb3-127">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6acb3-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="6acb3-128">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de archivado para la configuración de archivado seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6acb3-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="6acb3-129">Solo puede mostrar detalles para una configuración de archivado cada vez.</span><span class="sxs-lookup"><span data-stu-id="6acb3-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="6acb3-130">**Seleccionar todo** Esta opción selecciona todas las configuraciones de archivado en la lista.</span><span class="sxs-lookup"><span data-stu-id="6acb3-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="6acb3-131">**Eliminar** Esta opción elimina todas las configuraciones de archivado seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="6acb3-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="6acb3-132">**Acción** Puede usar esta opción para habilitar o deshabilitar el archivado de sesiones de mensajería instantánea o sesiones de conferencia web en cualquier configuración que aparecen en la página, en lugar de modificar la configuración de rápidamente.</span><span class="sxs-lookup"><span data-stu-id="6acb3-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="6acb3-133">Las opciones disponibles en **Acción** dependen de qué opción esté especificada actualmente en la configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="6acb3-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="6acb3-134">Todas las opciones están disponibles, excepto la opción en vigor actualmente para la configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="6acb3-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="6acb3-135">Las opciones son estas:</span><span class="sxs-lookup"><span data-stu-id="6acb3-135">Options include the following:</span></span>
    
  - <span data-ttu-id="6acb3-136">**Archivar sesiones de mensajería instantánea**</span><span class="sxs-lookup"><span data-stu-id="6acb3-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="6acb3-137">**Archivar sesiones de mensajería instantánea y conferencias web**</span><span class="sxs-lookup"><span data-stu-id="6acb3-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="6acb3-138">**Deshabilitar archivado**</span><span class="sxs-lookup"><span data-stu-id="6acb3-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="6acb3-139">**Actualizar** Puede actualizar la página de **Configuración de archivado** para comprobar el estado de las opciones de todas las configuraciones de archivado.</span><span class="sxs-lookup"><span data-stu-id="6acb3-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="6acb3-140">Para obtener información detallada acerca de la característica de archivado y capacidades, que incluye la integración de Exchange, vea [Planear el archivado en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [implementar el archivado de Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)y [administrar el archivado en Skype para 2015 empresariales de servidor](../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="6acb3-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

