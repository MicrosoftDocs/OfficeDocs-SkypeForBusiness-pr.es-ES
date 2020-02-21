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
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Página de aterrizaje para enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: d643c137145649c0843296300a909c520ba653a6
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157908"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="b8863-103">Enrutamiento directo del Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="b8863-103">Phone System Direct Routing</span></span>

<span data-ttu-id="b8863-104">Ha completado la [Introducción](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="b8863-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="b8863-105">Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="b8863-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="b8863-106">Es posible que haya implementado [reuniones & conferencias](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="b8863-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="b8863-107">Ahora está listo para agregar cargas de trabajo de voz de nube y ha decidido usar su propio operador de telefonía para conectividad de red telefónica conmutada (RTC) con enrutamiento directo de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="b8863-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="b8863-108">Con el enrutamiento directo, puede usar el sistema telefónico con prácticamente cualquier operador de telefonía.</span><span class="sxs-lookup"><span data-stu-id="b8863-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="b8863-109">En este artículo se describen las decisiones básicas de implementación para el enrutamiento directo, así como otras consideraciones adicionales, según las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="b8863-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="b8863-110">También debe leer [la voz de nube en Microsoft Teams](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b8863-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="b8863-111">Más información sobre el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="b8863-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="b8863-112">Los artículos siguientes proporcionan más información sobre cómo configurar y usar el enrutamiento directo del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="b8863-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="b8863-113">La configuración del enrutamiento directo requiere comprender el diseño de enrutamiento de RTC.</span><span class="sxs-lookup"><span data-stu-id="b8863-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="b8863-114">Debe leer todos estos artículos para comprender cómo planificar y configurar el enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="b8863-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="b8863-115">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="b8863-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="b8863-116">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="b8863-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="b8863-117">Lista de controladores de borde de sesión certificados para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="b8863-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="b8863-118">Supervisar y solucionar problemas de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="b8863-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="b8863-119">Además, es posible que desee leer los artículos siguientes según sus necesidades:</span><span class="sxs-lookup"><span data-stu-id="b8863-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="b8863-120">Configurar un controlador de borde de sesión para varios inquilinos</span><span class="sxs-lookup"><span data-stu-id="b8863-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="b8863-121">Migrar a enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="b8863-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="b8863-122">Cuentas de usuario en un entorno híbrido con conectividad RTC</span><span class="sxs-lookup"><span data-stu-id="b8863-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="b8863-123">Vea la siguiente sesión para obtener más información sobre el enrutamiento directo: [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="b8863-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="b8863-124">Decisiones de implementación principales</span><span class="sxs-lookup"><span data-stu-id="b8863-124">Core deployment decisions</span></span>

<span data-ttu-id="b8863-125">Estas son las decisiones básicas para considerar el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="b8863-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="b8863-126">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8863-126">Ask yourself</span></span>|<span data-ttu-id="b8863-127">Acción</span><span class="sxs-lookup"><span data-stu-id="b8863-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="b8863-128">¿Para qué usuarios habilitaría el enrutamiento directo?</span><span class="sxs-lookup"><span data-stu-id="b8863-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="b8863-129">Para obtener más información, vea [Habilitar usuarios para el servicio de enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="b8863-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="b8863-130">¿Tengo las licencias necesarias para el enrutamiento directo?</span><span class="sxs-lookup"><span data-stu-id="b8863-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="b8863-131">Para obtener más información, consulte [licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="b8863-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="b8863-132">Consideraciones del controlador de borde de sesión (SBC)</span><span class="sxs-lookup"><span data-stu-id="b8863-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="b8863-133">Con el enrutamiento directo, conecta su propio controlador de borde de sesión (SBC) directamente al sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="b8863-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="b8863-134">Para obtener una lista de SBCs certificado, consulte [controladores de borde de sesión admitidos](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="b8863-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="b8863-135">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8863-135">Ask yourself</span></span>|<span data-ttu-id="b8863-136">Acción</span><span class="sxs-lookup"><span data-stu-id="b8863-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="b8863-137">¿Dónde y cómo implementar SBCs?</span><span class="sxs-lookup"><span data-stu-id="b8863-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="b8863-138">Para obtener más información, consulte [configurar el enrutamiento directo](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="b8863-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="b8863-139">¿Tengo varios inquilinos?</span><span class="sxs-lookup"><span data-stu-id="b8863-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="b8863-140">Para obtener más información, vea [configurar un controlador de borde de sesión para varios inquilinos](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="b8863-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="b8863-141">Consideraciones de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="b8863-141">Voice routing considerations</span></span>

<span data-ttu-id="b8863-142">Tendrá que configurar el sistema telefónico para enrutar las llamadas al SBCs específico.</span><span class="sxs-lookup"><span data-stu-id="b8863-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="b8863-143">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8863-143">Ask yourself</span></span>|<span data-ttu-id="b8863-144">Acción</span><span class="sxs-lookup"><span data-stu-id="b8863-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="b8863-145">¿Qué directivas de enrutamiento de voz, uso de RTC y rutas de voz necesito crear?</span><span class="sxs-lookup"><span data-stu-id="b8863-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="b8863-146">Para obtener información sobre el enrutamiento de voz, vea [configurar el enrutamiento de voz](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="b8863-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="b8863-147">¿Qué usuarios se asignarán a la Directiva de enrutamiento de voz que definio?</span><span class="sxs-lookup"><span data-stu-id="b8863-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="b8863-148">Consulte los ejemplos de [configurar el enrutamiento de voz](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="b8863-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="b8863-149">Asegurarse de que las llamadas entrantes estén en el cliente de Teams mediante TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="b8863-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="b8863-150">El enrutamiento directo solo es compatible con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b8863-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="b8863-151">Para recibir llamadas RTC mediante enrutamiento directo, debe configurar TeamsUpgradePolicy para asegurarse de que las llamadas entrantes se reciban en Teams.</span><span class="sxs-lookup"><span data-stu-id="b8863-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="b8863-152">Los usuarios deben estar en el modo solo de equipos, que puede hacer asignando la instancia "UpgradeToTeams" de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="b8863-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="b8863-153">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8863-153">Ask yourself</span></span>|<span data-ttu-id="b8863-154">Acción</span><span class="sxs-lookup"><span data-stu-id="b8863-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="b8863-155">¿Qué significa el modo solo de Teams?</span><span class="sxs-lookup"><span data-stu-id="b8863-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="b8863-156">Para obtener más información, consulte [Guía de migración e interoperabilidad para las organizaciones que usan Teams conjuntamente con Skype empresarial](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="b8863-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="b8863-157">Consideraciones de implementación adicionales</span><span class="sxs-lookup"><span data-stu-id="b8863-157">Additional deployment considerations</span></span>

<span data-ttu-id="b8863-158">Es posible que desee tener en cuenta lo siguiente, en función de las necesidades y la configuración de su organización:</span><span class="sxs-lookup"><span data-stu-id="b8863-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="b8863-159">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8863-159">Ask yourself</span></span>| <span data-ttu-id="b8863-160">Acción</span><span class="sxs-lookup"><span data-stu-id="b8863-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="b8863-161">¿Tiene una implementación existente de Skype empresarial Server con una conectividad híbrida configurada?</span><span class="sxs-lookup"><span data-stu-id="b8863-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="b8863-162">Para comprender cómo se suministran y administran las cuentas de usuario en un entorno híbrido, consulte [cuentas de usuario en un entorno híbrido con conectividad RTC](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b8863-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="b8863-163">¿Va a migrar el enrutamiento directo desde el plan de llamadas o desde un entorno local de Skype empresarial?</span><span class="sxs-lookup"><span data-stu-id="b8863-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="b8863-164">Para obtener más información sobre cómo migrar para dirigir el enrutamiento desde un entorno existente, consulte [migrar a enrutamiento directo](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="b8863-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
