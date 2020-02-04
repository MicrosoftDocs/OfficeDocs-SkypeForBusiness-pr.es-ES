---
title: Configuración de archivado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'Las configuraciones de archivado se usan para controlar las opciones de archivado de la implementación de Skype empresarial Server, incluida la activación y desactivación de las siguientes opciones:'
ms.openlocfilehash: 1222e5e4c848f7ce0f3ca05943aa5b5acf4d365a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41704705"
---
# <a name="archiving-configuration"></a><span data-ttu-id="9fc6a-103">Configuración de archivado</span><span class="sxs-lookup"><span data-stu-id="9fc6a-103">Archiving Configuration</span></span>
 
<span data-ttu-id="9fc6a-104">Las configuraciones de archivado se usan para controlar las opciones de archivado de la implementación de Skype empresarial Server, incluida la activación y desactivación de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9fc6a-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="9fc6a-105">Bloquear sesiones de mensajería instantánea o conferencias si no se pueden archivar</span><span class="sxs-lookup"><span data-stu-id="9fc6a-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="9fc6a-106">Integración con almacenamiento de Exchange, para usuarios alojados en Exchange</span><span class="sxs-lookup"><span data-stu-id="9fc6a-106">Integration with Exchange storage, for users homed on Exchange</span></span>
    
- <span data-ttu-id="9fc6a-107">Purgar datos archivados</span><span class="sxs-lookup"><span data-stu-id="9fc6a-107">Purging of archived data</span></span>
    
<span data-ttu-id="9fc6a-108">Las configuraciones de archivado están formadas por la configuración global y, de forma opcional, por una o varias configuraciones de archivado de sitio y grupo:</span><span class="sxs-lookup"><span data-stu-id="9fc6a-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="9fc6a-109">**Configuración global** La configuración global se crea de forma predeterminada en todas las implementaciones de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="9fc6a-110">La configuración global se puede editar, pero no eliminar.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="9fc6a-111">Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="9fc6a-112">**Configuración del sitio (opcional)** Puede especificar una o más configuraciones de archivado de sitio, cada una de las cuales puede configurar para controlar las opciones de archivado de un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="9fc6a-113">Una configuración de sitio reemplaza a la configuración global, pero solo en los sitios especificados en las configuraciones de sitio de archivado.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="9fc6a-114">Las configuraciones de sitio se pueden editar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="9fc6a-115">**Configuración del grupo (opcional)** Puede especificar una o más configuraciones de archivado de grupo para controlar las opciones de archivado de un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="9fc6a-116">Una configuración de grupo reemplaza a la configuración global y la configuración del sitio, pero solo en los grupos especificados en las configuraciones de grupo de archivado.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="9fc6a-117">Las configuraciones de grupo se pueden editar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9fc6a-118">Las configuraciones de archivado se aplican a los usuarios alojados en Skype empresarial Server y, si usa Exchange para almacenar los datos de archivado en Microsoft Exchange, para los usuarios alojados en Exchange, pero que se implementan de manera ligeramente diferente para los usuarios alojados en Exchange.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange but are implemented slightly differently for users homed on Exchange.</span></span> <span data-ttu-id="9fc6a-119">En la siguiente sección se describen estas diferencias.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="9fc6a-p105">La página **Configuración de archivado** muestra cada directiva de archivado configurada en la implementación. También muestra el nombre de la directiva, el ámbito (global, sitio o usuario) y qué opciones de archivado están habilitadas para cada configuración de archivado. En la página **Configuración de archivado** dispone de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9fc6a-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="9fc6a-123">**Nuevo** Puede Agregar una o más de las siguientes configuraciones de archivo opcionales.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="9fc6a-124">Configuración de sitio</span><span class="sxs-lookup"><span data-stu-id="9fc6a-124">Site configuration</span></span>
    
  - <span data-ttu-id="9fc6a-125">Configuración del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="9fc6a-125">Pool configuration</span></span>
    
- <span data-ttu-id="9fc6a-126">**Editar** Puede cambiar las opciones de cualquiera de las configuraciones de archivado que aparecen en la página.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="9fc6a-127">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9fc6a-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="9fc6a-128">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de archivado para la configuración de archivado seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="9fc6a-129">Solo puede mostrar detalles para una configuración de archivado cada vez.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="9fc6a-130">**Seleccionar todo** Esta opción selecciona todas las configuraciones de archivado de la lista.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="9fc6a-131">**Eliminar** Esta opción elimina todas las configuraciones de archivado seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="9fc6a-132">**Acción** Puede usar esta opción para habilitar o deshabilitar rápidamente el archivado de sesiones de mensajería instantánea o de conferencias web en cualquier configuración que aparezca en la página, en lugar de editar la configuración.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="9fc6a-133">Las opciones disponibles en **Acción** dependen de qué opción esté especificada actualmente en la configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="9fc6a-134">Todas las opciones están disponibles, excepto la opción en vigor actualmente para la configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="9fc6a-135">Las opciones son estas:</span><span class="sxs-lookup"><span data-stu-id="9fc6a-135">Options include the following:</span></span>
    
  - <span data-ttu-id="9fc6a-136">**Archivar sesiones de mensajería instantánea**</span><span class="sxs-lookup"><span data-stu-id="9fc6a-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="9fc6a-137">**Archivar sesiones de mensajería instantánea y conferencias web**</span><span class="sxs-lookup"><span data-stu-id="9fc6a-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="9fc6a-138">**Deshabilitar archivado**</span><span class="sxs-lookup"><span data-stu-id="9fc6a-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="9fc6a-139">**Actualizar** Puede actualizar la página **configuración de archivado** para comprobar el estado de las opciones de todas las configuraciones de archivado.</span><span class="sxs-lookup"><span data-stu-id="9fc6a-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="9fc6a-140">Para obtener información sobre la característica y capacidades de archivado, incluyendo la integración de Exchange, consulte [planear el archivado en Skype empresarial Server](../../../plan-your-deployment/archiving/archiving.md), [implementar el archivado para Skype empresarial Server](../../../deploy/deploy-archiving/deploy-archiving.md)y [administrar el archivado en Skype empresarial Server](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="9fc6a-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

