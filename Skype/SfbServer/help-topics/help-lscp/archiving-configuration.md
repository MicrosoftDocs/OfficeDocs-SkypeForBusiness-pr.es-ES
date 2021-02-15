---
title: Configuración de archivado
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Las configuraciones de archivado se usan para controlar las opciones de archivado para la implementación de Skype Empresarial Server, incluida la habilitación y deshabilitación de las siguientes opciones:'
ms.openlocfilehash: 96a01579f43833017978fc6067b5a86f9e9951aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827010"
---
# <a name="archiving-configuration"></a><span data-ttu-id="edae8-103">Configuración de archivado</span><span class="sxs-lookup"><span data-stu-id="edae8-103">Archiving Configuration</span></span>
 
<span data-ttu-id="edae8-104">Las configuraciones de archivado se usan para controlar las opciones de archivado para la implementación de Skype Empresarial Server, incluida la habilitación y deshabilitación de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="edae8-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="edae8-105">Bloquear sesiones de mensajería instantánea o conferencias si no se pueden archivar</span><span class="sxs-lookup"><span data-stu-id="edae8-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="edae8-106">Integración con el almacenamiento de Exchange 2013 para los usuarios que están en Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="edae8-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="edae8-107">Purgar datos archivados</span><span class="sxs-lookup"><span data-stu-id="edae8-107">Purging of archived data</span></span>
    
<span data-ttu-id="edae8-108">Las configuraciones de archivado incluyen la configuración global y, de forma opcional, una o varias configuraciones de archivado de sitio y grupo:</span><span class="sxs-lookup"><span data-stu-id="edae8-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="edae8-109">**Configuración global** La configuración global se crea de forma predeterminada en todas las implementaciones de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="edae8-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="edae8-110">Puede editar la configuración global, pero no puede eliminar esta configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="edae8-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="edae8-111">Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="edae8-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="edae8-112">**Configuración del sitio (opcional)** Puede especificar una o varias configuraciones de archivado de sitios, cada una de las cuales puede configurar para controlar las opciones de archivado de un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="edae8-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="edae8-113">Una configuración de sitio anula la configuración global, pero solo para los sitios especificados en las configuraciones de sitios de archivado.</span><span class="sxs-lookup"><span data-stu-id="edae8-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="edae8-114">Puede editar o eliminar las configuraciones de sitios.</span><span class="sxs-lookup"><span data-stu-id="edae8-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="edae8-115">**Configuración del grupo de servidores (opcional)** Puede especificar una o más configuraciones de archivado de grupo para controlar las opciones de archivado de un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="edae8-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="edae8-116">Una configuración de grupo anula la configuración global y la configuración del sitio, pero solo para los grupos especificados en las configuraciones de grupos de archivado.</span><span class="sxs-lookup"><span data-stu-id="edae8-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="edae8-117">Puede editar o eliminar las configuraciones de grupos.</span><span class="sxs-lookup"><span data-stu-id="edae8-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="edae8-118">Las configuraciones de archivado se aplican a los usuarios que se encuentran en Skype Empresarial Server y, si usa Exchange para almacenar datos de archivado en Microsoft Exchange, a los usuarios que están en Exchange 2013, pero se implementan de forma ligeramente diferente para los usuarios de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="edae8-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="edae8-119">Las diferencias se describen en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="edae8-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="edae8-p105">La página **Configuración de archivado** muestra cada directiva de archivado configurada para su implementación. También muestra el nombre de la directiva, el ámbito (global, sitio o usuario) y qué opciones de archivado están habilitadas para cada configuración de archivado. En la página **Configuración de archivado**, tiene las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="edae8-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="edae8-123">**Nuevo** Puede agregar una o varias de las siguientes configuraciones de archivado opcionales.</span><span class="sxs-lookup"><span data-stu-id="edae8-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="edae8-124">Configuración de sitio</span><span class="sxs-lookup"><span data-stu-id="edae8-124">Site configuration</span></span>
    
  - <span data-ttu-id="edae8-125">Configuración del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="edae8-125">Pool configuration</span></span>
    
- <span data-ttu-id="edae8-126">**Editar** Puede cambiar las opciones de cualquiera de las configuraciones de archivado que aparecen en la página.</span><span class="sxs-lookup"><span data-stu-id="edae8-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="edae8-127">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="edae8-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="edae8-128">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de archivado de la configuración de archivado seleccionada.</span><span class="sxs-lookup"><span data-stu-id="edae8-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="edae8-129">Solo puede mostrar detalles para una configuración de archivado cada vez.</span><span class="sxs-lookup"><span data-stu-id="edae8-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="edae8-130">**Seleccionar todo** Esta opción selecciona todas las configuraciones de archivado de la lista.</span><span class="sxs-lookup"><span data-stu-id="edae8-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="edae8-131">**Eliminar** Esta opción elimina todas las configuraciones de archivado seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="edae8-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="edae8-132">**Acción** Puede usar esta opción para habilitar o deshabilitar rápidamente el archivado de sesiones de mensajería instantánea o sesiones de conferencia web en cualquier configuración que aparezca en la página, en lugar de editar la configuración.</span><span class="sxs-lookup"><span data-stu-id="edae8-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="edae8-133">Las opciones disponibles en **Acción** dependen de qué opción esté especificada actualmente en la configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="edae8-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="edae8-134">Todas las opciones están disponibles, excepto la opción en efecto actualmente para la configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="edae8-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="edae8-135">Las opciones incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="edae8-135">Options include the following:</span></span>
    
  - <span data-ttu-id="edae8-136">**Archivar sesiones de mensajería instantánea**</span><span class="sxs-lookup"><span data-stu-id="edae8-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="edae8-137">**Archivar sesiones de mensajería instantánea y conferencias web**</span><span class="sxs-lookup"><span data-stu-id="edae8-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="edae8-138">**Deshabilitar archivado**</span><span class="sxs-lookup"><span data-stu-id="edae8-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="edae8-139">**Actualizar** Puede actualizar la página **Configuración de** archivado para comprobar el estado de las opciones de todas las configuraciones de archivado.</span><span class="sxs-lookup"><span data-stu-id="edae8-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="edae8-140">Para obtener más información sobre la característica y las capacidades de archivado, incluida la integración de Exchange, vea [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), Deploy archiving for Skype for Business Server [2015](../../deploy/deploy-archiving/deploy-archiving.md)y [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="edae8-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

