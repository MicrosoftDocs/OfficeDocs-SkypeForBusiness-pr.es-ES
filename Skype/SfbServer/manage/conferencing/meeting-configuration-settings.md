---
title: Administrar opciones de configuración de reuniones en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumen: Conozca cómo administrar los valores de configuración de Skype para Business Server 2015 de reunión.'
ms.openlocfilehash: 30b19eee5e298bfaa5eefe1eee50c9ea615b5682
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="e0cb1-103">Administrar opciones de configuración de reuniones en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0cb1-103">Manage meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e0cb1-104">**Resumen:** Aprenda a administrar valores de configuración de Skype para Business Server 2015 de reunión.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e0cb1-105">This topic describes how to manage meeting configuration settings.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="e0cb1-106">Para obtener más información acerca de cómo planear e implementar la conferencia, consulte [Plan de conferencia en Skype para Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) y [conferencias de implementar en Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="e0cb1-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="e0cb1-107">Las opciones de configuración de reunión definen el tipo de reuniones que pueden crear los usuarios, además de controlar cómo (o, incluso, si) los usuarios de conferencias anónimos o de acceso telefónico local pueden participar en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="e0cb1-108">Tenga en cuenta que esta configuración sólo afecta a las reuniones programadas; no afectan a reuniones ad hoc creadas haciendo clic en la opción Reunirse ahora en Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="e0cb1-109">Las opciones de configuración de reuniones definen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0cb1-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="e0cb1-110">Si los usuarios que realizan la llamada desde una red telefónica conmutada (RTC) pasan al salón de espera.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="e0cb1-111">Quién puede ser moderador.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="e0cb1-112">Si el tipo de conferencia está asignado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="e0cb1-113">Si los usuarios anónimos (sin autenticar) se admiten de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="e0cb1-114">Puede definir las características de reuniones utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="e0cb1-115">Puede especificar configuración en el nivel global (que se crea de manera predeterminada) de la reunión, a nivel de sitio o grupo de nivel.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="e0cb1-116">De forma predeterminada, la configuración global define la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="e0cb1-117">Si crea una configuración a nivel de grupo, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="e0cb1-118">Si no crea ninguna configuración a nivel de grupo, se aplicará la configuración a nivel de sitio, si existe.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="e0cb1-119">Si no define la configuración a nivel de sitio, se aplicará la configuración global a todas las reuniones.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e0cb1-120">Administrar opciones de reunión mediante Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="e0cb1-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="e0cb1-121">Para administrar la configuración de reunión utilizando Skype para Panel de Control de servidor de negocios:</span><span class="sxs-lookup"><span data-stu-id="e0cb1-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="e0cb1-122">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="e0cb1-123">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e0cb1-124">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e0cb1-125">Administrar opciones de reunión mediante Skype para el Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="e0cb1-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="e0cb1-126">Para administrar las reuniones mediante Skype para el Shell de administración de servidor de negocio, use los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e0cb1-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="e0cb1-127">**Opciones de configuración de la reunión**</span><span class="sxs-lookup"><span data-stu-id="e0cb1-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="e0cb1-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="e0cb1-128">**Cmdlet**</span></span>|<span data-ttu-id="e0cb1-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e0cb1-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e0cb1-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0cb1-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="e0cb1-131">Devuelve información sobre las opciones de configuración de reunión en uso en la organización.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="e0cb1-132">Nueva CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0cb1-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="e0cb1-133">Crea una colección de opciones de configuración de reunión en el ámbito de sitio o de servicio.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="e0cb1-134">Quitar CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0cb1-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="e0cb1-135">Elimina una colección existente de opciones de configuración de reunión.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="e0cb1-136">Conjunto de CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0cb1-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="e0cb1-137">Modifica las opciones de configuración de reuniones que se usan actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="e0cb1-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

