---
title: Enrutamiento directo del Sistema telefónico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1keywords: ms.teamsadmincenter.directrouting.overview
description: Página de aterrizaje para enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: 965fb26aee3d83550740e2ae7f855559fd9cdb79
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484064"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="bfe42-103">Enrutamiento directo del Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="bfe42-103">Phone System Direct Routing</span></span>

<span data-ttu-id="bfe42-104">Ha completado la [Introducción](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="bfe42-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="bfe42-105">Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="bfe42-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="bfe42-106">Es posible que haya implementado [reuniones & conferencias](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="bfe42-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="bfe42-107">Ahora está listo para agregar cargas de trabajo de voz de nube y ha decidido usar su propio operador de telefonía para conectividad de red telefónica conmutada (RTC) con enrutamiento directo de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="bfe42-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="bfe42-108">Con el enrutamiento directo, puede usar el sistema telefónico con prácticamente cualquier operador de telefonía.</span><span class="sxs-lookup"><span data-stu-id="bfe42-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="bfe42-109">En este artículo se describen las decisiones básicas de implementación para el enrutamiento directo, así como otras consideraciones adicionales, según las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="bfe42-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="bfe42-110">También debe leer [la voz de nube en Microsoft Teams](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bfe42-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="bfe42-111">Más información sobre el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="bfe42-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="bfe42-112">Los artículos siguientes proporcionan más información sobre cómo configurar y usar el enrutamiento directo del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="bfe42-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="bfe42-113">La configuración del enrutamiento directo requiere comprender el diseño de enrutamiento de RTC.</span><span class="sxs-lookup"><span data-stu-id="bfe42-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="bfe42-114">Debe leer todos estos artículos para comprender cómo planificar y configurar el enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="bfe42-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="bfe42-115">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="bfe42-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="bfe42-116">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="bfe42-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="bfe42-117">Lista de controladores de borde de sesión certificados para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="bfe42-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="bfe42-118">Supervisar y solucionar problemas de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="bfe42-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="bfe42-119">Además, es posible que desee leer los artículos siguientes según sus necesidades:</span><span class="sxs-lookup"><span data-stu-id="bfe42-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="bfe42-120">Configurar un controlador de borde de sesión para varios inquilinos</span><span class="sxs-lookup"><span data-stu-id="bfe42-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="bfe42-121">Migrar a enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="bfe42-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="bfe42-122">Cuentas de usuario en un entorno híbrido con conectividad RTC</span><span class="sxs-lookup"><span data-stu-id="bfe42-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="bfe42-123">Vea la siguiente sesión para obtener más información sobre el enrutamiento directo: [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="bfe42-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="bfe42-124">Decisiones de implementación principales</span><span class="sxs-lookup"><span data-stu-id="bfe42-124">Core deployment decisions</span></span>

<span data-ttu-id="bfe42-125">Estas son las decisiones básicas para considerar el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="bfe42-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="bfe42-126">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfe42-126">Ask yourself</span></span>|<span data-ttu-id="bfe42-127">Acción</span><span class="sxs-lookup"><span data-stu-id="bfe42-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="bfe42-128">¿Para qué usuarios habilitaría el enrutamiento directo?</span><span class="sxs-lookup"><span data-stu-id="bfe42-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="bfe42-129">Para obtener más información, vea [Habilitar usuarios para el servicio de enrutamiento directo](direct-routing-configure.md#enable-users-for-direct-routing-service).</span><span class="sxs-lookup"><span data-stu-id="bfe42-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="bfe42-130">¿Tengo las licencias necesarias para el enrutamiento directo?</span><span class="sxs-lookup"><span data-stu-id="bfe42-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="bfe42-131">Para obtener más información, consulte [licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="bfe42-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="bfe42-132">Consideraciones del controlador de borde de sesión (SBC)</span><span class="sxs-lookup"><span data-stu-id="bfe42-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="bfe42-133">Con el enrutamiento directo, conecta su propio controlador de borde de sesión (SBC) directamente al sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="bfe42-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="bfe42-134">Para obtener una lista de SBCs certificado, consulte [controladores de borde de sesión admitidos](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="bfe42-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="bfe42-135">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfe42-135">Ask yourself</span></span>|<span data-ttu-id="bfe42-136">Acción</span><span class="sxs-lookup"><span data-stu-id="bfe42-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bfe42-137">¿Dónde y cómo implementar SBCs?</span><span class="sxs-lookup"><span data-stu-id="bfe42-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="bfe42-138">Para obtener más información, consulte [configurar el enrutamiento directo](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="bfe42-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="bfe42-139">¿Tengo varios inquilinos?</span><span class="sxs-lookup"><span data-stu-id="bfe42-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="bfe42-140">Para obtener más información, vea [configurar un controlador de borde de sesión para varios inquilinos](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="bfe42-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="bfe42-141">Consideraciones de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="bfe42-141">Voice routing considerations</span></span>

<span data-ttu-id="bfe42-142">Tendrá que configurar el sistema telefónico para enrutar las llamadas al SBCs específico.</span><span class="sxs-lookup"><span data-stu-id="bfe42-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="bfe42-143">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfe42-143">Ask yourself</span></span>|<span data-ttu-id="bfe42-144">Acción</span><span class="sxs-lookup"><span data-stu-id="bfe42-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bfe42-145">¿Qué directivas de enrutamiento de voz, uso de RTC y rutas de voz necesito crear?</span><span class="sxs-lookup"><span data-stu-id="bfe42-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="bfe42-146">Para obtener información sobre el enrutamiento de voz, vea [configurar el enrutamiento de voz](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="bfe42-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="bfe42-147">¿Qué usuarios se asignarán a la Directiva de enrutamiento de voz que definio?</span><span class="sxs-lookup"><span data-stu-id="bfe42-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="bfe42-148">Consulte los ejemplos de [configurar el enrutamiento de voz](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="bfe42-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="calling-and-interop-policies"></a><span data-ttu-id="bfe42-149">Directivas de llamadas y interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="bfe42-149">Calling and interop policies</span></span>

<span data-ttu-id="bfe42-150">El enrutamiento directo solo es compatible con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bfe42-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="bfe42-151">Para realizar o recibir llamadas RTC mediante enrutamiento directo, debe configurar las directivas necesarias para asegurarse de que las llamadas entrantes se reciban en Teams.</span><span class="sxs-lookup"><span data-stu-id="bfe42-151">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="bfe42-152">Puede configurar los usuarios para que establezcan equipos como su cliente preferido para las llamadas, ya sea configurando el usuario para el modo solo de Teams o configurando Teams como el cliente de llamadas preferido asignando el TeamsCallingPolicy y TeamsInteropPolicy.</span><span class="sxs-lookup"><span data-stu-id="bfe42-152">You can configure users to set Teams as their preferred client for calls by either configuring the user for Teams Only mode or configuring Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

|<span data-ttu-id="bfe42-153">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfe42-153">Ask yourself</span></span>|<span data-ttu-id="bfe42-154">Acción</span><span class="sxs-lookup"><span data-stu-id="bfe42-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="bfe42-155">¿Cómo establezco Teams como el cliente preferido para las llamadas?</span><span class="sxs-lookup"><span data-stu-id="bfe42-155">How will I set Teams as the preferred client for calls?</span></span> | <span data-ttu-id="bfe42-156">Para obtener más información, vea [establecer Microsoft Teams como el cliente de llamadas preferido para los usuarios](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span><span class="sxs-lookup"><span data-stu-id="bfe42-156">For more information, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="bfe42-157">Consideraciones de implementación adicionales</span><span class="sxs-lookup"><span data-stu-id="bfe42-157">Additional deployment considerations</span></span>

<span data-ttu-id="bfe42-158">Es posible que desee tener en cuenta lo siguiente, en función de las necesidades y la configuración de su organización:</span><span class="sxs-lookup"><span data-stu-id="bfe42-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="bfe42-159">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfe42-159">Ask yourself</span></span>| <span data-ttu-id="bfe42-160">Acción</span><span class="sxs-lookup"><span data-stu-id="bfe42-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="bfe42-161">¿Tiene una implementación existente de Skype empresarial Server con una conectividad híbrida configurada?</span><span class="sxs-lookup"><span data-stu-id="bfe42-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="bfe42-162">Para comprender cómo se suministran y administran las cuentas de usuario en un entorno híbrido, consulte [cuentas de usuario en un entorno híbrido con conectividad RTC](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="bfe42-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="bfe42-163">¿Va a migrar el enrutamiento directo desde el plan de llamadas o desde un entorno local de Skype empresarial?</span><span class="sxs-lookup"><span data-stu-id="bfe42-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="bfe42-164">Para obtener más información sobre cómo migrar para dirigir el enrutamiento desde un entorno existente, consulte [migrar a enrutamiento directo](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="bfe42-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
