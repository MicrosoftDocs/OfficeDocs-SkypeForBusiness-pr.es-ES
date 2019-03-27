---
title: Administrar opciones de configuración en Skype para Business Server de la reunión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumen: Obtenga información sobre cómo administrar los valores de configuración de Skype para Business Server de la reunión.'
ms.openlocfilehash: 90d1004101f1dd3b4737c7bfa4414438a65c54a6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883224"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="0bd94-103">Administrar opciones de configuración en Skype para Business Server de la reunión</span><span class="sxs-lookup"><span data-stu-id="0bd94-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="0bd94-104">**Resumen:** Obtenga información sobre cómo administrar los valores de configuración de Skype para Business Server de la reunión.</span><span class="sxs-lookup"><span data-stu-id="0bd94-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="0bd94-105">This topic describes how to manage meeting configuration settings.</span><span class="sxs-lookup"><span data-stu-id="0bd94-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="0bd94-106">Para obtener más información acerca de cómo planear e implementar una conferencia, vea [Plan para las conferencias en Skype para Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencias en Skype para Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="0bd94-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="0bd94-107">Las opciones de configuración de reunión definen el tipo de reuniones que pueden crear los usuarios, además de controlar cómo (o, incluso, si) los usuarios de conferencias anónimos o de acceso telefónico local pueden participar en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="0bd94-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="0bd94-108">Tenga en cuenta que esta configuración sólo afecta a las reuniones programadas; no afectan a las reuniones de ad-hoc creadas haciendo clic en la opción Reunirse ahora en Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="0bd94-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="0bd94-109">Las opciones de configuración de reuniones definen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bd94-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="0bd94-110">Si los usuarios que realizan la llamada desde una red telefónica conmutada (RTC) pasan al salón de espera.</span><span class="sxs-lookup"><span data-stu-id="0bd94-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="0bd94-111">Quién puede ser moderador.</span><span class="sxs-lookup"><span data-stu-id="0bd94-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="0bd94-112">Si el tipo de conferencia está asignado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0bd94-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="0bd94-113">Si los usuarios anónimos (sin autenticar) se admiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0bd94-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="0bd94-114">Puede definir las características de las reuniones mediante Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0bd94-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="0bd94-115">Puede especificar opciones en el nivel global (creada de manera predeterminada) de la reunión, nivel de sitio o del nivel de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="0bd94-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="0bd94-116">De forma predeterminada, la configuración global define la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="0bd94-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="0bd94-117">Si crea una configuración a nivel de grupo, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda.</span><span class="sxs-lookup"><span data-stu-id="0bd94-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="0bd94-118">Si no crea ninguna configuración a nivel de grupo, se aplicará la configuración a nivel de sitio, si existe.</span><span class="sxs-lookup"><span data-stu-id="0bd94-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="0bd94-119">Si no define la configuración a nivel de sitio, se aplicará la configuración global a todas las reuniones.</span><span class="sxs-lookup"><span data-stu-id="0bd94-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0bd94-120">Administrar la configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="0bd94-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="0bd94-121">Para administrar la configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="0bd94-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="0bd94-122">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0bd94-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="0bd94-123">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0bd94-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0bd94-124">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="0bd94-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0bd94-125">Administrar la configuración de reunión mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="0bd94-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0bd94-126">Para administrar las reuniones mediante el uso de Skype para Shell de administración de servidor empresarial, use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="0bd94-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="0bd94-127">**Opciones de configuración de reuniones**</span><span class="sxs-lookup"><span data-stu-id="0bd94-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="0bd94-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="0bd94-128">**Cmdlet**</span></span>|<span data-ttu-id="0bd94-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0bd94-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0bd94-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0bd94-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="0bd94-131">Devuelve información sobre las opciones de configuración de reuniones que se usan actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="0bd94-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="0bd94-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0bd94-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="0bd94-133">Crea una recopilación de opciones de configuración de reunión en el ámbito del sitio o del servicio.</span><span class="sxs-lookup"><span data-stu-id="0bd94-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="0bd94-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0bd94-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="0bd94-135">Elimina una colección existente de opciones de configuración de reunión.</span><span class="sxs-lookup"><span data-stu-id="0bd94-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="0bd94-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0bd94-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="0bd94-137">Modifica las opciones de configuración de reuniones que se usan actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="0bd94-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

