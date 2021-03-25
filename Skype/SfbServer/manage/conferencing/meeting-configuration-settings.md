---
title: Administrar las opciones de configuración de reuniones en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumen: obtenga información sobre cómo administrar las opciones de configuración de reuniones en Skype Empresarial Server.'
ms.openlocfilehash: 1e6ef11992a547456d2a971c2f8de6f3097b166e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119439"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="a8d0e-103">Administrar las opciones de configuración de reuniones en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a8d0e-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="a8d0e-104">**Resumen:** Obtenga información sobre cómo administrar las opciones de configuración de reuniones en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="a8d0e-105">En este tema se describe cómo administrar las opciones de configuración de reuniones.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="a8d0e-106">Para obtener más información sobre cómo planear e implementar conferencias, vea [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="a8d0e-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="a8d0e-107">Las opciones de configuración de reunión determinan el tipo de reuniones que los usuarios pueden crear, además de controlar cómo (o incluso si) los usuarios anónimos y los usuarios de conferencias de acceso telefónico local pueden unirse a estas reuniones.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="a8d0e-108">Tenga en cuenta que esta configuración solo afecta a las reuniones programadas; no afectan a las reuniones ad hoc creadas haciendo clic en la opción Reunirse ahora en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="a8d0e-109">Las opciones de configuración de reunión definen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8d0e-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="a8d0e-110">Si los usuarios que realizan la llamada desde una red telefónica conmutada (RTC) pasan a la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="a8d0e-111">Quién puede ser moderador.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="a8d0e-112">Si el tipo de conferencia está asignado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="a8d0e-113">Si los usuarios anónimos (sin autenticar) se admiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="a8d0e-114">Puede definir las características de las reuniones mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="a8d0e-115">Puede especificar la configuración de reunión en el nivel global (creado de forma predeterminada), el nivel de sitio o el nivel de grupo.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="a8d0e-116">De forma predeterminada, la configuración global define la experiencia de reunión.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="a8d0e-117">Si crea una configuración en el nivel de grupo de servidores, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="a8d0e-118">Si no crea ninguna configuración en el nivel de grupo de servidores, se aplicará la configuración del nivel de sitio, si existe.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="a8d0e-119">Si no define la configuración en el nivel de sitio, se aplicará la configuración global a todas las reuniones.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a8d0e-120">Administrar la configuración de la reunión mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a8d0e-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="a8d0e-121">Para administrar la configuración de reuniones mediante el Panel de control de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="a8d0e-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="a8d0e-122">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="a8d0e-123">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a8d0e-124">En la barra de navegación izquierda, haga clic **en Conferencia y,** a continuación, haga clic en **Configuración de reunión.**</span><span class="sxs-lookup"><span data-stu-id="a8d0e-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a8d0e-125">Administrar la configuración de reuniones mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a8d0e-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a8d0e-126">Para administrar reuniones mediante el Shell de administración de Skype Empresarial Server, use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8d0e-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="a8d0e-127">**Opciones de configuración de reuniones**</span><span class="sxs-lookup"><span data-stu-id="a8d0e-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="a8d0e-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="a8d0e-128">**Cmdlet**</span></span>|<span data-ttu-id="a8d0e-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a8d0e-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a8d0e-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8d0e-130">Get-CsMeetingConfiguration</span></span>](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a8d0e-131">Devuelve información sobre las opciones de configuración de reunión que se usan actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="a8d0e-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8d0e-132">New-CsMeetingConfiguration</span></span>](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a8d0e-133">Crea una recopilación de opciones de configuración de reunión en el ámbito de sitio o de servicio.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="a8d0e-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8d0e-134">Remove-CsMeetingConfiguration</span></span>](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a8d0e-135">Elimina una colección existente de opciones de configuración de reunión.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="a8d0e-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8d0e-136">Set-CsMeetingConfiguration</span></span>](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a8d0e-137">Modifica las opciones de configuración de reunión que se usan actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="a8d0e-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
