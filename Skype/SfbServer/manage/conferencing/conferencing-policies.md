---
title: Administrar las directivas de conferencia en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Resumen: Obtenga información sobre cómo administrar las directivas de conferencia en Skype para Business Server.'
ms.openlocfilehash: 96b2f5e27aa65931f5cd76499e1a3f66b817baa5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222866"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="70b19-103">Administrar las directivas de conferencia en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="70b19-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="70b19-104">**Resumen:** Obtenga información sobre cómo administrar las directivas de conferencia en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="70b19-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="70b19-105">En este tema se describe cómo administrar directivas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="70b19-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="70b19-106">Para obtener más información acerca de cómo planear e implementar una conferencia, vea [Plan para las conferencias en Skype para Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencias en Skype para Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="70b19-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="70b19-p102">Las directivas de conferencia le permiten definir una amplia variedad de opciones de programación y participación, que van desde si una reunión puede incluir audio y vídeo IP hasta la cantidad máxima de personas que pueden asistir. Puede usar directivas de conferencia para administrar la seguridad, el ancho de banda y los aspectos jurídicos de las reuniones.</span><span class="sxs-lookup"><span data-stu-id="70b19-p102">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="70b19-109">Puede definir la directiva de conferencias en tres niveles: ámbito global, ámbito de sitio y ámbito de usuario.</span><span class="sxs-lookup"><span data-stu-id="70b19-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="70b19-110">La configuración se aplica a un usuario específico del ámbito más limitado al ámbito más extenso.</span><span class="sxs-lookup"><span data-stu-id="70b19-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="70b19-111">Si asigna una directiva a un usuario, esa configuración tendrá preferencia.</span><span class="sxs-lookup"><span data-stu-id="70b19-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="70b19-112">Si no asigna una directiva de usuario, se aplicará la configuración de sitio.</span><span class="sxs-lookup"><span data-stu-id="70b19-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="70b19-113">Si no se aplica ni la directiva de usuario ni la de sitio, la directiva global proporcionará la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="70b19-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="70b19-114">Existe una directiva global predeterminada, de modo que no puede crear una nueva directiva global.</span><span class="sxs-lookup"><span data-stu-id="70b19-114">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="70b19-115">Tampoco puede eliminar la directiva global existente, pero puede cambiar la directiva global para personalizar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="70b19-115">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="70b19-116">Administrar las directivas de conferencia mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="70b19-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="70b19-117">Para administrar las directivas de conferencia mediante el uso de Skype para el Panel de Control de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="70b19-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="70b19-118">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="70b19-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="70b19-119">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="70b19-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="70b19-120">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="70b19-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="70b19-121">Administrar las directivas de conferencia mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="70b19-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="70b19-122">Para administrar las reuniones mediante el uso de Skype para Shell de administración de servidor empresarial, use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="70b19-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="70b19-123">**Configuración de la directiva de conferencia**</span><span class="sxs-lookup"><span data-stu-id="70b19-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="70b19-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="70b19-124">**Cmdlet**</span></span>|<span data-ttu-id="70b19-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="70b19-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="70b19-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="70b19-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="70b19-127">Devuelve información sobre las directivas de conferencia que se han configurado para su uso en la organización.</span><span class="sxs-lookup"><span data-stu-id="70b19-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="70b19-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="70b19-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="70b19-129">Asigna una directiva de conferencia en el ámbito por usuario.</span><span class="sxs-lookup"><span data-stu-id="70b19-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="70b19-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="70b19-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="70b19-131">Crea una directiva de conferencia para usar en la organización.</span><span class="sxs-lookup"><span data-stu-id="70b19-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="70b19-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="70b19-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="70b19-133">Quita la directiva de conferencia especificada.</span><span class="sxs-lookup"><span data-stu-id="70b19-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="70b19-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="70b19-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="70b19-135">Modifica una directiva de conferencia existente.</span><span class="sxs-lookup"><span data-stu-id="70b19-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

