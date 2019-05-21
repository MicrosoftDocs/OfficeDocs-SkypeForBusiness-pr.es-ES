---
title: Administrar la configuración de la reunión en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumen: Obtenga información sobre cómo administrar la configuración de la reunión en Skype empresarial Server.'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283742"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="69ee1-103">Administrar la configuración de la reunión en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="69ee1-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="69ee1-104">**Resumen:** Obtenga información sobre cómo administrar la configuración de la reunión en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="69ee1-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="69ee1-105">This topic describes how to manage meeting configuration settings.</span><span class="sxs-lookup"><span data-stu-id="69ee1-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="69ee1-106">Para obtener más información sobre cómo planear e implementar conferencias, consulte [planear la Conferencia en Skype empresarial Server](../../plan-your-deployment/conferencing/conferencing.md) e [implementar conferencias en Skype empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="69ee1-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="69ee1-107">Las opciones de configuración de reunión definen el tipo de reuniones que pueden crear los usuarios, además de controlar cómo (o, incluso, si) los usuarios de conferencias anónimos o de acceso telefónico local pueden participar en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="69ee1-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="69ee1-108">Tenga en cuenta que esta configuración solo afecta a las reuniones programadas; no afectan a las reuniones ad-hoc creadas al hacer clic en la opción reunirse ahora en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="69ee1-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="69ee1-109">Las opciones de configuración de reuniones definen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69ee1-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="69ee1-110">Si los usuarios que realizan la llamada desde una red telefónica conmutada (RTC) pasan al salón de espera.</span><span class="sxs-lookup"><span data-stu-id="69ee1-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="69ee1-111">Quién puede ser moderador.</span><span class="sxs-lookup"><span data-stu-id="69ee1-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="69ee1-112">Si el tipo de conferencia está asignado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="69ee1-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="69ee1-113">Si los usuarios anónimos (sin autenticar) se admiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="69ee1-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="69ee1-114">Puede definir las características de las reuniones con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="69ee1-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="69ee1-115">Puede especificar la configuración de la reunión en el nivel global (creado de forma predeterminada), en el nivel de sitio o en el nivel de grupo.</span><span class="sxs-lookup"><span data-stu-id="69ee1-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="69ee1-116">De forma predeterminada, la configuración global define la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="69ee1-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="69ee1-117">Si crea una configuración a nivel de grupo, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda.</span><span class="sxs-lookup"><span data-stu-id="69ee1-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="69ee1-118">Si no crea ninguna configuración a nivel de grupo, se aplicará la configuración a nivel de sitio, si existe.</span><span class="sxs-lookup"><span data-stu-id="69ee1-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="69ee1-119">Si no define la configuración a nivel de sitio, se aplicará la configuración global a todas las reuniones.</span><span class="sxs-lookup"><span data-stu-id="69ee1-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="69ee1-120">Administrar la configuración de la reunión con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="69ee1-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="69ee1-121">Para administrar la configuración de la reunión con el panel de control de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="69ee1-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="69ee1-122">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="69ee1-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="69ee1-123">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="69ee1-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="69ee1-124">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="69ee1-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="69ee1-125">Administrar la configuración de la reunión con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="69ee1-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="69ee1-126">Para administrar las reuniones con el shell de administración de Skype empresarial Server, use los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="69ee1-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="69ee1-127">**Opciones de configuración de reuniones**</span><span class="sxs-lookup"><span data-stu-id="69ee1-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="69ee1-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="69ee1-128">**Cmdlet**</span></span>|<span data-ttu-id="69ee1-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="69ee1-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="69ee1-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="69ee1-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="69ee1-131">Devuelve información sobre las opciones de configuración de reuniones que se usan actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="69ee1-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="69ee1-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="69ee1-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="69ee1-133">Crea una recopilación de opciones de configuración de reunión en el ámbito del sitio o del servicio.</span><span class="sxs-lookup"><span data-stu-id="69ee1-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="69ee1-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="69ee1-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="69ee1-135">Elimina una colección existente de opciones de configuración de reunión.</span><span class="sxs-lookup"><span data-stu-id="69ee1-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="69ee1-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="69ee1-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="69ee1-137">Modifica las opciones de configuración de reuniones que se usan actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="69ee1-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

