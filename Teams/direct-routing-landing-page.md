---
title: Enrutamiento directo del Sistema telefónico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
F1keywords: ms.teamsadmincenter.directrouting.overview
description: Página de destino de enrutamiento directo
appliesto: Microsoft Teams
ms.openlocfilehash: b8f7840b981b67f941598638b2624de0cd512b8c
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494064"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="01c44-103">Enrutamiento directo del Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="01c44-103">Phone System Direct Routing</span></span>

<span data-ttu-id="01c44-104">Ha completado la [Introducción](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="01c44-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="01c44-105">Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="01c44-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="01c44-106">Es posible que haya implementado [conferencia & de las reuniones](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="01c44-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="01c44-107">Ahora está listo para agregar las cargas de trabajo de voz de la nube y ha decidido utilizar su propio operador de telefonía para la conectividad pública red de telefónica conmutada (RTC) mediante el uso de enrutamiento directo de teléfono del sistema.</span><span class="sxs-lookup"><span data-stu-id="01c44-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="01c44-108">Con el enrutamiento directo, puede usar el sistema telefónico con prácticamente cualquier operador de telefonía.</span><span class="sxs-lookup"><span data-stu-id="01c44-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="01c44-109">En este artículo se describe la implementación las decisiones principales para el enrutamiento directo, así como consideraciones adicionales que es posible que desea configurar, en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="01c44-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to configure, based on your organization's needs.</span></span>  <span data-ttu-id="01c44-110">También debe leer [En la nube de voz en los equipos de Microsoft](cloud-voice-landing-page.md) para obtener más información acerca de las ofertas de voz de la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01c44-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="01c44-111">Encontrará más información acerca del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="01c44-111">Learn more about Direct Routing</span></span>


<span data-ttu-id="01c44-112">Los artículos siguientes proporcionan más información sobre cómo configurar y usar enrutamiento directo de teléfono del sistema.</span><span class="sxs-lookup"><span data-stu-id="01c44-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="01c44-113">Configurar el enrutamiento directo requiere conocimientos de diseño de enrutamiento de RTC.</span><span class="sxs-lookup"><span data-stu-id="01c44-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="01c44-114">Debe leer todos estos artículos para aprender a planear y configurar el enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="01c44-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="01c44-115">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="01c44-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="01c44-116">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="01c44-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="01c44-117">Lista de controladores de borde de sesión certificados para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="01c44-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="01c44-118">Supervisar y solucionar problemas de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="01c44-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="01c44-119">Además, es posible que desee leer los artículos según los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="01c44-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="01c44-120">Configurar un controlador de borde de sesión para varios inquilinos</span><span class="sxs-lookup"><span data-stu-id="01c44-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="01c44-121">Migrar a enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="01c44-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="01c44-122">Cuentas de usuario en un entorno híbrido con conectividad RTC</span><span class="sxs-lookup"><span data-stu-id="01c44-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="01c44-123">Vea la sesión siguiente para obtener más información acerca del enrutamiento directo: [El enrutamiento directo en los equipos de Microsoft](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="01c44-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="01c44-124">Decisiones de implementación principales</span><span class="sxs-lookup"><span data-stu-id="01c44-124">Core deployment decisions</span></span>

<span data-ttu-id="01c44-125">Estos son las decisiones principales a tener en cuenta para el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="01c44-125">These are the core decisions to consider for Direct Routing.</span></span> 


|<span data-ttu-id="01c44-126">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="01c44-126">Ask yourself</span></span>|<span data-ttu-id="01c44-127">Acción</span><span class="sxs-lookup"><span data-stu-id="01c44-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="01c44-128">¿Para los usuarios que habilitará el enrutamiento directo?</span><span class="sxs-lookup"><span data-stu-id="01c44-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="01c44-129">Para obtener más información, vea [Habilitar usuarios para el servicio de enrutamiento directo](direct-routing-configure.md#enable-users-for-direct-routing-service).</span><span class="sxs-lookup"><span data-stu-id="01c44-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="01c44-130">¿Tienen las licencias necesarias para el enrutamiento directo?</span><span class="sxs-lookup"><span data-stu-id="01c44-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="01c44-131">Para obtener más información, vea [Licensing y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="01c44-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="01c44-132">Consideraciones de controlador de borde (SBC) de sesión</span><span class="sxs-lookup"><span data-stu-id="01c44-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="01c44-133">Con el enrutamiento directo, se conecta su propio controlador de borde de sesión (SBC) directamente al sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="01c44-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="01c44-134">Para obtener una lista de SBCs certificadas, vea [Admite controladores de borde de sesión](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="01c44-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="01c44-135">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="01c44-135">Ask yourself</span></span>|<span data-ttu-id="01c44-136">Acción</span><span class="sxs-lookup"><span data-stu-id="01c44-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="01c44-137">¿Dónde y cómo va a implementar SBCs?</span><span class="sxs-lookup"><span data-stu-id="01c44-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="01c44-138">Para obtener más información, vea [Configurar el enrutamiento directo](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="01c44-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="01c44-139">¿Hay varios inquilinos?</span><span class="sxs-lookup"><span data-stu-id="01c44-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="01c44-140">Para obtener más información, vea [configurar un controlador de borde de sesión para varios inquilinos](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="01c44-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="01c44-141">Consideraciones del enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="01c44-141">Voice routing considerations</span></span>

<span data-ttu-id="01c44-142">Debe configurar el sistema telefónico para enrutar las llamadas a la SBCs específicos.</span><span class="sxs-lookup"><span data-stu-id="01c44-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="01c44-143">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="01c44-143">Ask yourself</span></span>|<span data-ttu-id="01c44-144">Acción</span><span class="sxs-lookup"><span data-stu-id="01c44-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="01c44-145">¿Qué directivas de enrutamiento de voz, el uso de RTC y rutas de voz necesito para crear?</span><span class="sxs-lookup"><span data-stu-id="01c44-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="01c44-146">Para obtener información de enrutamiento de voz, vea [Configurar el enrutamiento de voz](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="01c44-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="01c44-147">¿Los usuarios que se asignará a la directiva de enrutamiento de voz que define?</span><span class="sxs-lookup"><span data-stu-id="01c44-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="01c44-148">Vea los ejemplos de [Configuración de enrutamiento de voz](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="01c44-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="calling-and-interop-policies"></a><span data-ttu-id="01c44-149">Directivas de llamada y de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="01c44-149">Calling and interop policies</span></span>

<span data-ttu-id="01c44-150">Enrutamiento directo sólo es compatible con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="01c44-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="01c44-151">Para realizar o recibir llamadas de RTC a través de enrutamiento directa, debe configurar las directivas necesarias para asegurarse de que las llamadas entrantes se reciben en los equipos.</span><span class="sxs-lookup"><span data-stu-id="01c44-151">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="01c44-152">Puede configurar usuarios para establecer los equipos como su cliente preferido para las llamadas, puede configurar el usuario para el modo de sólo los equipos o configurar los equipos como cliente preferido llamado mediante la asignación de la TeamsCallingPolicy y la TeamsInteropPolicy.</span><span class="sxs-lookup"><span data-stu-id="01c44-152">You can configure users to set Teams as their preferred client for calls by either configuring the user for Teams Only mode or configuring Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

|<span data-ttu-id="01c44-153">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="01c44-153">Ask yourself</span></span>|<span data-ttu-id="01c44-154">Acción</span><span class="sxs-lookup"><span data-stu-id="01c44-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="01c44-155">¿Cómo va a establecer los equipos como cliente preferido para las llamadas?</span><span class="sxs-lookup"><span data-stu-id="01c44-155">How will I set Teams as the preferred client for calls?</span></span> | <span data-ttu-id="01c44-156">Para obtener más información, vea [establecer los equipos de Microsoft como el preferido llamar al cliente para los usuarios](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span><span class="sxs-lookup"><span data-stu-id="01c44-156">For more information, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="01c44-157">Consideraciones de implementación adicionales</span><span class="sxs-lookup"><span data-stu-id="01c44-157">Additional deployment considerations</span></span>

<span data-ttu-id="01c44-158">Es posible que desee tener en cuenta los siguientes valores, en función de las necesidades de su organización y la configuración:</span><span class="sxs-lookup"><span data-stu-id="01c44-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="01c44-159">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="01c44-159">Ask yourself</span></span>| <span data-ttu-id="01c44-160">Acción</span><span class="sxs-lookup"><span data-stu-id="01c44-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="01c44-161">¿Tiene un Skype existente para la implementación de servidor empresarial con conectividad híbrida configurada?</span><span class="sxs-lookup"><span data-stu-id="01c44-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="01c44-162">Para comprender cómo se aprovisionan cuentas de usuario en un entorno híbrido y administrados, vea [cuentas de usuario en un entorno híbrido con conectividad RTC](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="01c44-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="01c44-163">¿Está migrando a enrutamiento directo de planeación de una llamada a o desde un Skype para entorno local de negocio?</span><span class="sxs-lookup"><span data-stu-id="01c44-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="01c44-164">Para saber más acerca de la migración para el enrutamiento directo desde un entorno existente, consulte [migración a enrutamiento directo](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="01c44-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
