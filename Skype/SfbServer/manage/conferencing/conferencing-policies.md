---
title: Administrar directivas de conferencia en Skype Empresarial Server
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Resumen: obtenga información sobre cómo administrar directivas de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: 3ad59f186ccc4bebdefae1a6bfefdf04e9bf6851
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835280"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="22ca8-103">Administrar directivas de conferencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="22ca8-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="22ca8-104">**Resumen:** Obtenga información sobre cómo administrar directivas de conferencia en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="22ca8-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="22ca8-105">En este tema se describe cómo administrar directivas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="22ca8-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="22ca8-106">Para obtener más información acerca de cómo planear e implementar conferencias, vea [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="22ca8-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="22ca8-107">Las directivas de conferencia permiten definir una amplia variedad de opciones de programación y participación, desde si una reunión puede incluir audio y vídeo IP hasta el número máximo de personas que pueden asistir.</span><span class="sxs-lookup"><span data-stu-id="22ca8-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="22ca8-108">Puede usar directivas de conferencia para administrar la seguridad, el ancho de banda y los aspectos legales de las reuniones.</span><span class="sxs-lookup"><span data-stu-id="22ca8-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="22ca8-109">Puede definir la directiva de conferencias en tres niveles: ámbito global, ámbito de sitio y ámbito de usuario.</span><span class="sxs-lookup"><span data-stu-id="22ca8-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="22ca8-110">La configuración se aplica a un usuario específico del ámbito más limitado al ámbito más extenso.</span><span class="sxs-lookup"><span data-stu-id="22ca8-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="22ca8-111">Si asigna una directiva a un usuario, dicha configuración tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="22ca8-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="22ca8-112">Si no asigna una directiva de usuario, se aplicará la configuración de sitio.</span><span class="sxs-lookup"><span data-stu-id="22ca8-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="22ca8-113">Si no se aplica ni la directiva de usuario ni la de sitio, la directiva global proporcionará la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22ca8-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="22ca8-p104">Existe una directiva global predeterminada, de modo que no puede crear una nueva directiva global. Tampoco puede eliminar la directiva global existente, pero puede cambiar la directiva global para personalizar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22ca8-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="22ca8-116">Administrar directivas de conferencia con el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="22ca8-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="22ca8-117">Para administrar directivas de conferencia con el Panel de control de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="22ca8-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="22ca8-118">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="22ca8-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="22ca8-119">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="22ca8-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="22ca8-120">En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Directiva **de conferencia.**</span><span class="sxs-lookup"><span data-stu-id="22ca8-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="22ca8-121">Administrar directivas de conferencia mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="22ca8-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="22ca8-122">Para administrar reuniones mediante el Shell de administración de Skype Empresarial Server, use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="22ca8-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="22ca8-123">**Configuración de directiva de conferencia**</span><span class="sxs-lookup"><span data-stu-id="22ca8-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="22ca8-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="22ca8-124">**Cmdlet**</span></span>|<span data-ttu-id="22ca8-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="22ca8-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="22ca8-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="22ca8-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="22ca8-127">Devuelve información sobre las directivas de conferencia que se han configurado para su uso en la organización.</span><span class="sxs-lookup"><span data-stu-id="22ca8-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="22ca8-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="22ca8-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="22ca8-129">Asigna una directiva de conferencia en el ámbito por usuario.</span><span class="sxs-lookup"><span data-stu-id="22ca8-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="22ca8-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="22ca8-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="22ca8-131">Crea una directiva de conferencia para usar en la organización.</span><span class="sxs-lookup"><span data-stu-id="22ca8-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="22ca8-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="22ca8-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="22ca8-133">Quita la directiva de conferencia especificada.</span><span class="sxs-lookup"><span data-stu-id="22ca8-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="22ca8-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="22ca8-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="22ca8-135">Modifica una directiva de conferencia existente.</span><span class="sxs-lookup"><span data-stu-id="22ca8-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

