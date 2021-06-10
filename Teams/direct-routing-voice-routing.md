---
title: Configurar el enrutamiento de voz para enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar el enrutamiento de voz con Teléfono Microsoft System Direct Routing.
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383984"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="a8159-103">Configurar el enrutamiento de voz para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="a8159-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="a8159-104">En este artículo se describe cómo configurar el enrutamiento de voz para Sistema telefónico enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="a8159-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="a8159-105">Este es el paso 3 de los pasos siguientes para configurar enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="a8159-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="a8159-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="a8159-106">Step 1.</span></span> [<span data-ttu-id="a8159-107">Conectar el SBC con Teléfono Microsoft y validar la conexión</span><span class="sxs-lookup"><span data-stu-id="a8159-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="a8159-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="a8159-108">Step 2.</span></span> [<span data-ttu-id="a8159-109">Habilitar usuarios para enrutamiento directo, voz y correo de voz</span><span class="sxs-lookup"><span data-stu-id="a8159-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="a8159-110">**Paso 3. Configurar el enrutamiento de** voz (este artículo)</span><span class="sxs-lookup"><span data-stu-id="a8159-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="a8159-111">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="a8159-111">Step 4.</span></span> [<span data-ttu-id="a8159-112">Traducir números a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="a8159-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="a8159-113">Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="a8159-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="a8159-114">Información general sobre enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="a8159-114">Voice routing overview</span></span>

<span data-ttu-id="a8159-115">Teléfono Microsoft El sistema tiene un mecanismo de enrutamiento que permite enviar una llamada a un controlador de borde de sesión (SBC) específico en función de:</span><span class="sxs-lookup"><span data-stu-id="a8159-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="a8159-116">El patrón de número llamado</span><span class="sxs-lookup"><span data-stu-id="a8159-116">The called number pattern</span></span> 
- <span data-ttu-id="a8159-117">El patrón de número llamado más el usuario específico que realiza la llamada</span><span class="sxs-lookup"><span data-stu-id="a8159-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="a8159-118">Los SBC se pueden designar como activos y de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a8159-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="a8159-119">Cuando el SBC configurado como activo no está disponible para una ruta de llamada específica, la llamada se enruta a un SBC de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a8159-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="a8159-120">El enrutamiento de voz está hecho de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="a8159-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="a8159-121">**Directiva de enrutamiento de** voz: un contenedor para usos RTC, que se puede asignar a un usuario o a varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="a8159-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="a8159-122">**Usos rtc:** un contenedor para rutas de voz y usos rtc, que se pueden compartir en distintas directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="a8159-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="a8159-123">**Rutas de voz:** un patrón de números y un conjunto de puertas de enlace RTC en línea que se usan para llamadas en las que el número de llamada coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a8159-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="a8159-124">**Puerta** de enlace RTC en línea: un puntero a un SBC que también almacena la configuración que se aplica cuando se coloca una llamada a través del SBC, como los códecs preferidos o P-Asserted-Identity (PAI) reenviados; se puede agregar a las rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="a8159-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="a8159-125">Consideraciones de directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="a8159-125">Voice routing policy considerations</span></span>

<span data-ttu-id="a8159-126">Si un usuario tiene una licencia de Plan de llamadas, las llamadas salientes de ese usuario se enruta automáticamente a través de la infraestructura RTC del Plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8159-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="a8159-127">Si configura y asigna una directiva de enrutamiento de voz en línea a un usuario del Plan de llamadas, las llamadas salientes de ese usuario se comprueban para determinar si el número marcado coincide con un patrón de número definido en la directiva de enrutamiento de voz en línea.</span><span class="sxs-lookup"><span data-stu-id="a8159-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="a8159-128">Si hay una coincidencia, la llamada se enruta a través del tronco de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="a8159-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="a8159-129">Si no hay ninguna coincidencia, la llamada se enruta a través de la infraestructura RTC del Plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a8159-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="a8159-130">Si configura y aplica la directiva de enrutamiento de voz en línea global (predeterminada para toda la organización), todos los usuarios habilitados para voz de su organización heredarán esa directiva, lo que puede provocar que las llamadas RTC de los usuarios del Plan de llamadas se enruten sin darse cuenta a un tronco de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="a8159-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="a8159-131">Si no desea que todos los usuarios usen la directiva global de enrutamiento de voz en línea, configure una directiva de enrutamiento de voz en línea personalizada y asígnela a usuarios habilitados para voz individuales.</span><span class="sxs-lookup"><span data-stu-id="a8159-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="a8159-132">Ejemplo 1: Enrutamiento de voz con un uso de RTC</span><span class="sxs-lookup"><span data-stu-id="a8159-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="a8159-133">En el siguiente diagrama se muestran dos ejemplos de directivas de enrutamiento de voz en un flujo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a8159-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="a8159-134">**Llamar Flow 1 (a la izquierda):** Si un usuario realiza una llamada a +1 425 XXX XX XX o +1 206 XXX XX XX, la llamada se enruta a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="a8159-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="a8159-135">Si no sbc1.contoso.biz ni sbc2.contoso.biz disponibles, la llamada se descarta.</span><span class="sxs-lookup"><span data-stu-id="a8159-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="a8159-136">**Llamar Flow 2 (a la derecha):** Si un usuario realiza una llamada a +1 425 XXX XX XX o +1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="a8159-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="a8159-137">Si no hay ninguna SBC disponible, se probará la ruta con menor prioridad (sbc3.contoso.biz y sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="a8159-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="a8159-138">Si ninguno de los SBC está disponible, la llamada se descarta.</span><span class="sxs-lookup"><span data-stu-id="a8159-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Muestra ejemplos de directivas de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="a8159-140">En ambos ejemplos, mientras se asignan prioridades a la ruta de voz, los SBC de las rutas se prueban en orden aleatorio.</span><span class="sxs-lookup"><span data-stu-id="a8159-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a8159-141">A menos que el usuario también tenga una licencia de Microsoft Calling Plan, las llamadas a cualquier número excepto los números que coincidan con los patrones +1 425 XXX XX XX o +1 206 XXX XX XX en la configuración de ejemplo se descartan.</span><span class="sxs-lookup"><span data-stu-id="a8159-141">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="a8159-142">Si el usuario tiene una licencia del Plan de llamadas, la llamada se enruta automáticamente según las directivas del Plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8159-142">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="a8159-143">El Plan de llamadas de Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de Microsoft Calling Plan y no requiere configuración de enrutamiento de llamadas adicional.</span><span class="sxs-lookup"><span data-stu-id="a8159-143">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="a8159-144">En el ejemplo que se muestra en el siguiente diagrama, se agrega una ruta de voz para enviar llamadas a todos los demás números de EE. UU. y Canadá (llamadas que van a patrón de número llamado +1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="a8159-144">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Muestra la directiva de enrutamiento de voz con una tercera ruta](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="a8159-146">Para todas las demás llamadas, si un usuario tiene ambas licencias (Teléfono Microsoft System y Microsoft Calling Plan), se usa la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="a8159-146">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="a8159-147">Si nada coincide con los patrones de número en las rutas de voz en línea creadas por el administrador, la llamada se enruta a través del Plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8159-147">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="a8159-148">Si el usuario solo tiene Teléfono Microsoft sistema, la llamada se descarta porque no hay reglas que coincidan.</span><span class="sxs-lookup"><span data-stu-id="a8159-148">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a8159-149">El valor prioridad de la ruta "Otros +1" no importa en este caso porque solo hay una ruta que coincida con el patrón +1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="a8159-149">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="a8159-150">Si un usuario realiza una llamada a +1 324 567 89 89 y sbc5.contoso.biz y sbc6.contoso.biz no están disponibles, la llamada se descarta.</span><span class="sxs-lookup"><span data-stu-id="a8159-150">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="a8159-151">En la tabla siguiente se resume la configuración con tres rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="a8159-151">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="a8159-152">En este ejemplo, las tres rutas forman parte del mismo uso de RTC, "EE. UU. y Canadá".</span><span class="sxs-lookup"><span data-stu-id="a8159-152">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="a8159-153">Todas las rutas están asociadas con el uso de RTC "EE. UU. y Canadá" y el uso de RTC está asociado con la directiva de enrutamiento de voz "SOLO EE. UU.".</span><span class="sxs-lookup"><span data-stu-id="a8159-153">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="a8159-154">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="a8159-154">**PSTN usage**</span></span>|<span data-ttu-id="a8159-155">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="a8159-155">**Voice route**</span></span>|<span data-ttu-id="a8159-156">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="a8159-156">**Number pattern**</span></span>|<span data-ttu-id="a8159-157">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="a8159-157">**Priority**</span></span>|<span data-ttu-id="a8159-158">**SBC**</span><span class="sxs-lookup"><span data-stu-id="a8159-158">**SBC**</span></span>|<span data-ttu-id="a8159-159">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a8159-159">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8159-160">EE. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="a8159-160">US and Canada</span></span>|<span data-ttu-id="a8159-161">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="a8159-161">"Redmond 1"</span></span>|<span data-ttu-id="a8159-162">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="a8159-162">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a8159-163">1</span><span class="sxs-lookup"><span data-stu-id="a8159-163">1</span></span>|<span data-ttu-id="a8159-164">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-164">sbc1.contoso.biz</span></span><br/><span data-ttu-id="a8159-165">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-165">sbc2.contoso.biz</span></span>|<span data-ttu-id="a8159-166">Ruta activa para los números llamados +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a8159-166">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a8159-167">EE. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="a8159-167">US and Canada</span></span>|<span data-ttu-id="a8159-168">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="a8159-168">"Redmond 2"</span></span>|<span data-ttu-id="a8159-169">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="a8159-169">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a8159-170">2</span><span class="sxs-lookup"><span data-stu-id="a8159-170">2</span></span>|<span data-ttu-id="a8159-171">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-171">sbc3.contoso.biz</span></span><br/><span data-ttu-id="a8159-172">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-172">sbc4.contoso.biz</span></span>|<span data-ttu-id="a8159-173">Ruta de copia de seguridad para números llamados +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a8159-173">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a8159-174">EE. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="a8159-174">US and Canada</span></span>|<span data-ttu-id="a8159-175">"Otros +1"</span><span class="sxs-lookup"><span data-stu-id="a8159-175">"Other +1"</span></span>|<span data-ttu-id="a8159-176">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="a8159-176">^\\+1(\d{10})$</span></span>|<span data-ttu-id="a8159-177">3</span><span class="sxs-lookup"><span data-stu-id="a8159-177">3</span></span>|<span data-ttu-id="a8159-178">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-178">sbc5.contoso.biz</span></span><br/><span data-ttu-id="a8159-179">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-179">sbc6.contoso.biz</span></span>|<span data-ttu-id="a8159-180">Ruta para números llamados +1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="a8159-180">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="a8159-181">Ejemplo 1: Pasos de configuración</span><span class="sxs-lookup"><span data-stu-id="a8159-181">Example 1: Configuration steps</span></span>

<span data-ttu-id="a8159-182">En el ejemplo siguiente se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="a8159-182">The following example shows how to:</span></span>

1. <span data-ttu-id="a8159-183">Crear un único uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="a8159-183">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="a8159-184">Configure tres rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="a8159-184">Configure three voice routes.</span></span>
3. <span data-ttu-id="a8159-185">Crear una directiva de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="a8159-185">Create a voice routing policy.</span></span>
4. <span data-ttu-id="a8159-186">Asigne la directiva a un usuario llamado Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="a8159-186">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="a8159-187">Puede usar el centro [Microsoft Teams de administración](#admincenterexample1) o [PowerShell](#powershellexample1) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a8159-187">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a8159-188">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8159-188">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="a8159-189">Paso 1: Crear el uso de RTC "EE. UU. y Canadá"</span><span class="sxs-lookup"><span data-stu-id="a8159-189">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="a8159-190">En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a Enrutamiento directo de voz y, a continuación, en la esquina superior derecha, seleccione Administrar registros de  >  uso **de RTC.**</span><span class="sxs-lookup"><span data-stu-id="a8159-190">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="a8159-191">Haga **clic en Agregar,** escriba **EE. UU. y Canadá** y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-191">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="a8159-192">Paso 2: Crear tres rutas de voz (Redmond 1, Redmond 2 y Otros +1)</span><span class="sxs-lookup"><span data-stu-id="a8159-192">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="a8159-193">En los pasos siguientes se describe cómo crear una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="a8159-193">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="a8159-194">Siga estos pasos para crear las tres rutas de voz denominadas Redmond 1, Redmond 2 y Otros +1 para este ejemplo mediante la configuración descrita en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="a8159-194">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="a8159-195">En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Enrutamiento directo de voz y, a continuación, seleccione la pestaña  >   **Rutas de** voz.</span><span class="sxs-lookup"><span data-stu-id="a8159-195">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="a8159-196">Haga **clic en** Agregar y, a continuación, escriba un nombre y una descripción para la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="a8159-196">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="a8159-197">Establezca la prioridad y especifique el patrón de número marcado.</span><span class="sxs-lookup"><span data-stu-id="a8159-197">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="a8159-198">Para inscribir un SBC con la ruta de voz, en SBC inscrito **(opcional),** haga clic en Agregar SBC, seleccione los SBC que desea inscribir y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-198">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="a8159-199">Para agregar registros de uso rtc, en Registros de uso rtc **(opcional),** haga clic en Agregar uso de **RTC,** seleccione los registros RTC que desea agregar y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-199">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="a8159-200">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8159-200">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="a8159-201">Paso 3: Crear una directiva de enrutamiento de voz denominada "SOLO ESTADOS UNIDOS" y agregar el uso de RTC "EE. UU. y Canadá" a la directiva</span><span class="sxs-lookup"><span data-stu-id="a8159-201">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="a8159-202">En el panel de navegación izquierdo del centro Microsoft Teams de administración, vaya a Directivas de enrutamiento de voz y, a continuación,  >  haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-202">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="a8159-203">Escriba **SOLO EE. UU.** como nombre y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="a8159-203">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="a8159-204">En **Registros de uso rtc,** haga clic en Agregar uso de **RTC,** seleccione el registro de uso rtc "EE. UU. y Canadá" y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-204">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="a8159-205">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8159-205">Click **Save**.</span></span>

<span data-ttu-id="a8159-206">Para obtener más información, vea [Administrar directivas de enrutamiento de voz.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a8159-206">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="a8159-207">Paso 4: Asignar la directiva de enrutamiento de voz a un usuario llamado Spencer Low</span><span class="sxs-lookup"><span data-stu-id="a8159-207">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="a8159-208">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="a8159-208">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="a8159-209">Haga **clic en** Directivas y, a continuación, junto a Directivas **asignadas,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-209">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="a8159-210">En **Directiva de enrutamiento de voz,** seleccione la directiva "Solo EE. UU." y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-210">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="a8159-211">Para obtener más información, vea [Administrar directivas de enrutamiento de voz.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a8159-211">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a8159-212">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8159-212">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="a8159-213">Paso 1: Crear el uso de RTC "EE. UU. y Canadá"</span><span class="sxs-lookup"><span data-stu-id="a8159-213">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="a8159-214">En una sesión remota de PowerShell en Skype Empresarial Online, escriba:</span><span class="sxs-lookup"><span data-stu-id="a8159-214">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="a8159-215">Compruebe que el uso se creó especificando:</span><span class="sxs-lookup"><span data-stu-id="a8159-215">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="a8159-216">Lo que devuelve una lista de nombres que se pueden truncar:</span><span class="sxs-lookup"><span data-stu-id="a8159-216">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="a8159-217">En el ejemplo siguiente se muestra el resultado de ejecutar el comando de PowerShell para mostrar nombres completos `(Get-CSOnlinePSTNUsage).usage` (no truncados):</span><span class="sxs-lookup"><span data-stu-id="a8159-217">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` PowerShell command to display full names (not truncated):</span></span>

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="a8159-218">Paso 2: Crear tres rutas de voz (Redmond 1, Redmond 2 y Otros +1)</span><span class="sxs-lookup"><span data-stu-id="a8159-218">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="a8159-219">Para crear la ruta "Redmond 1", en una sesión de PowerShell en Skype Empresarial Online, escriba:</span><span class="sxs-lookup"><span data-stu-id="a8159-219">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a8159-220">Lo que devuelve:</span><span class="sxs-lookup"><span data-stu-id="a8159-220">Which returns:</span></span>

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

<span data-ttu-id="a8159-221">Para crear la ruta de Redmond 2, escriba:</span><span class="sxs-lookup"><span data-stu-id="a8159-221">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a8159-222">Para crear la ruta Otros +1, escriba:</span><span class="sxs-lookup"><span data-stu-id="a8159-222">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="a8159-223">Asegúrese de que la expresión regular en el atributo NumberPattern es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="a8159-223">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="a8159-224">Puede probarlo con este sitio web: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="a8159-224">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="a8159-225">En algunos casos, es necesario enrutar todas las llamadas al mismo SBC; usar -NumberPattern ".\*"</span><span class="sxs-lookup"><span data-stu-id="a8159-225">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="a8159-226">Enruta todas las llamadas al mismo SBC.</span><span class="sxs-lookup"><span data-stu-id="a8159-226">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="a8159-227">Compruebe que ha configurado correctamente la ruta ejecutando el comando `Get-CSOnlineVoiceRoute` de PowerShell con opciones como se muestra:</span><span class="sxs-lookup"><span data-stu-id="a8159-227">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="a8159-228">Lo que debería devolver:</span><span class="sxs-lookup"><span data-stu-id="a8159-228">Which should return:</span></span>

```console
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
```

<span data-ttu-id="a8159-229">En el ejemplo, se asignó automáticamente la prioridad 4 a la ruta "Otros +1".</span><span class="sxs-lookup"><span data-stu-id="a8159-229">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="a8159-230">Paso 3: Crear una directiva de enrutamiento de voz denominada "SOLO ESTADOS UNIDOS" y agregar el uso de RTC "EE. UU. y Canadá" a la directiva</span><span class="sxs-lookup"><span data-stu-id="a8159-230">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="a8159-231">En una sesión de PowerShell en Skype Empresarial Online, escriba:</span><span class="sxs-lookup"><span data-stu-id="a8159-231">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a8159-232">El resultado se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a8159-232">The result is shown in this example:</span></span>

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="a8159-233">Paso 4: Asignar la directiva de enrutamiento de voz a un usuario llamado Spencer Low</span><span class="sxs-lookup"><span data-stu-id="a8159-233">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="a8159-234">En una sesión de PowerShell en Skype Empresarial Online, escriba:</span><span class="sxs-lookup"><span data-stu-id="a8159-234">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="a8159-235">Para validar la asignación de directivas, escriba este comando:</span><span class="sxs-lookup"><span data-stu-id="a8159-235">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="a8159-236">El comando devuelve lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8159-236">The command returns the following:</span></span>

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="a8159-237">Ejemplo 2: Enrutamiento de voz con varios usos de RTC</span><span class="sxs-lookup"><span data-stu-id="a8159-237">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="a8159-238">La directiva de enrutamiento de voz creada en el ejemplo 1 solo permite las llamadas a números de teléfono en Ee. UU. y Canadá, a menos que la licencia del Plan de llamadas de Microsoft también se asigne al usuario.</span><span class="sxs-lookup"><span data-stu-id="a8159-238">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="a8159-239">En el ejemplo siguiente, puede crear la directiva de enrutamiento de voz "Sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="a8159-239">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="a8159-240">La directiva reutiliza el uso de RTC "EE. UU. y Canadá" creado en el ejemplo 1, así como el nuevo uso de RTC "Internacional".</span><span class="sxs-lookup"><span data-stu-id="a8159-240">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="a8159-241">Esta directiva enruta todas las demás llamadas a los SBC sbc2.contoso.biz y sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="a8159-241">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="a8159-242">Los ejemplos que se muestran asignan la directiva Solo ee. UU. al usuario Spencer Low y la directiva Sin restricciones al usuario John Woods para que el enrutamiento se realice de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a8159-242">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="a8159-243">Spencer Low: directiva solo para EE. UU.</span><span class="sxs-lookup"><span data-stu-id="a8159-243">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="a8159-244">Las llamadas solo se permiten a números de EE. UU. y Canadá.</span><span class="sxs-lookup"><span data-stu-id="a8159-244">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="a8159-245">Al llamar al rango de números de Redmond, debe usarse el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="a8159-245">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="a8159-246">Los números que no sean de EE. UU. no se enrutarán a menos que la licencia del Plan de llamadas esté asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="a8159-246">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="a8159-247">John Woods: política internacional.</span><span class="sxs-lookup"><span data-stu-id="a8159-247">John Woods – International policy.</span></span>  <span data-ttu-id="a8159-248">Las llamadas se permiten a cualquier número.</span><span class="sxs-lookup"><span data-stu-id="a8159-248">Calls are allowed to any number.</span></span> <span data-ttu-id="a8159-249">Al llamar al rango de números de Redmond, debe usarse el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="a8159-249">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="a8159-250">Los números que no sean de EE. UU. se enrutarán con sbc2.contoso.biz y sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="a8159-250">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Muestra la directiva de enrutamiento de voz asignada al usuario Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="a8159-252">Para todas las demás llamadas, si un usuario tiene ambas licencias (Teléfono Microsoft System y Microsoft Calling Plan), se usa la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="a8159-252">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="a8159-253">Si nada coincide con los patrones de número en las rutas de voz en línea creadas por el administrador, la llamada se enruta con Microsoft Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="a8159-253">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="a8159-254">Si el usuario solo tiene Teléfono Microsoft sistema, la llamada se descarta porque no hay reglas que coincidan.</span><span class="sxs-lookup"><span data-stu-id="a8159-254">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Muestra la directiva de enrutamiento de voz asignada al usuario John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="a8159-256">En la tabla siguiente se resumen las designaciones de uso y las rutas de voz de la directiva de enrutamiento "Sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="a8159-256">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

| <span data-ttu-id="a8159-257">Uso de RTC</span><span class="sxs-lookup"><span data-stu-id="a8159-257">PSTN usage</span></span> | <span data-ttu-id="a8159-258">Ruta de voz</span><span class="sxs-lookup"><span data-stu-id="a8159-258">Voice route</span></span> | <span data-ttu-id="a8159-259">Patrón de números</span><span class="sxs-lookup"><span data-stu-id="a8159-259">Number pattern</span></span> | <span data-ttu-id="a8159-260">Prioridad</span><span class="sxs-lookup"><span data-stu-id="a8159-260">Priority</span></span> | <span data-ttu-id="a8159-261">SBC</span><span class="sxs-lookup"><span data-stu-id="a8159-261">SBC</span></span> | <span data-ttu-id="a8159-262">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8159-262">Description</span></span> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8159-263">EE. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="a8159-263">US and Canada</span></span>|<span data-ttu-id="a8159-264">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="a8159-264">"Redmond 1"</span></span>|<span data-ttu-id="a8159-265">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="a8159-265">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a8159-266">1</span><span class="sxs-lookup"><span data-stu-id="a8159-266">1</span></span>|<span data-ttu-id="a8159-267">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-267">sbc1.contoso.biz</span></span><br/><span data-ttu-id="a8159-268">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-268">sbc2.contoso.biz</span></span>|<span data-ttu-id="a8159-269">Ruta activa para números de calle +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a8159-269">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a8159-270">EE. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="a8159-270">US and Canada</span></span>|<span data-ttu-id="a8159-271">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="a8159-271">"Redmond 2"</span></span>|<span data-ttu-id="a8159-272">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="a8159-272">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a8159-273">2</span><span class="sxs-lookup"><span data-stu-id="a8159-273">2</span></span>|<span data-ttu-id="a8159-274">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-274">sbc3.contoso.biz</span></span><br/><span data-ttu-id="a8159-275">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-275">sbc4.contoso.biz</span></span>|<span data-ttu-id="a8159-276">Ruta de copia de seguridad para números de callee +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a8159-276">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a8159-277">EE. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="a8159-277">US and Canada</span></span>|<span data-ttu-id="a8159-278">"Otros +1"</span><span class="sxs-lookup"><span data-stu-id="a8159-278">"Other +1"</span></span>|<span data-ttu-id="a8159-279">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="a8159-279">^\\+1(\d{10})$</span></span>|<span data-ttu-id="a8159-280">3</span><span class="sxs-lookup"><span data-stu-id="a8159-280">3</span></span>|<span data-ttu-id="a8159-281">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-281">sbc5.contoso.biz</span></span><br/><span data-ttu-id="a8159-282">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-282">sbc6.contoso.biz</span></span>|<span data-ttu-id="a8159-283">Ruta para números de callee +1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="a8159-283">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="a8159-284">International</span><span class="sxs-lookup"><span data-stu-id="a8159-284">International</span></span>|<span data-ttu-id="a8159-285">International</span><span class="sxs-lookup"><span data-stu-id="a8159-285">International</span></span>|<span data-ttu-id="a8159-286">\d+</span><span class="sxs-lookup"><span data-stu-id="a8159-286">\d+</span></span>|<span data-ttu-id="a8159-287">4</span><span class="sxs-lookup"><span data-stu-id="a8159-287">4</span></span>|<span data-ttu-id="a8159-288">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-288">sbc2.contoso.biz</span></span><br/><span data-ttu-id="a8159-289">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a8159-289">sbc5.contoso.biz</span></span>|<span data-ttu-id="a8159-290">Ruta para cualquier patrón de número</span><span class="sxs-lookup"><span data-stu-id="a8159-290">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="a8159-291">El orden de los usos rtc en las directivas de enrutamiento de voz es fundamental.</span><span class="sxs-lookup"><span data-stu-id="a8159-291">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="a8159-292">Los usos se aplican en orden y, si se encuentra una coincidencia en el primer uso, nunca se evalúan otros usos.</span><span class="sxs-lookup"><span data-stu-id="a8159-292">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="a8159-293">El uso de RTC "Internacional" debe colocarse después del uso de RTC "EE. UU. y Canadá".</span><span class="sxs-lookup"><span data-stu-id="a8159-293">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="a8159-294">Para cambiar el orden de los usos de RTC, ejecute el `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="a8159-294">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="a8159-295">Por ejemplo, para cambiar el orden de "EE. UU. y Canadá" en primer lugar y "Internacional" en segundo lugar a la ejecución de orden inverso:</span><span class="sxs-lookup"><span data-stu-id="a8159-295">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="a8159-296">La prioridad de las rutas de voz "Otras +1" e "Internacional" se asigna automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a8159-296">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="a8159-297">No importan siempre que tengan prioridades más bajas que "Redmond 1" y "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="a8159-297">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="a8159-298">Ejemplo 2: Pasos de configuración</span><span class="sxs-lookup"><span data-stu-id="a8159-298">Example 2: Configuration steps</span></span>

<span data-ttu-id="a8159-299">En el ejemplo siguiente se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="a8159-299">The following example shows how to:</span></span>

1. <span data-ttu-id="a8159-300">Cree un nuevo uso de RTC llamado Internacional.</span><span class="sxs-lookup"><span data-stu-id="a8159-300">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="a8159-301">Cree una nueva ruta de voz llamada Internacional.</span><span class="sxs-lookup"><span data-stu-id="a8159-301">Create a new voice route called International.</span></span>
3. <span data-ttu-id="a8159-302">Cree una directiva de enrutamiento de voz denominada Sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="a8159-302">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="a8159-303">Asigne la directiva al usuario John Woods.</span><span class="sxs-lookup"><span data-stu-id="a8159-303">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="a8159-304">Puede usar el centro [Microsoft Teams de administración](#admincenterexample2) o [PowerShell](#powershellexample2) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a8159-304">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a8159-305">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8159-305">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="a8159-306">Paso 1: Crear el uso de RTC "Internacional"</span><span class="sxs-lookup"><span data-stu-id="a8159-306">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="a8159-307">En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a Enrutamiento directo de voz y, a continuación, en la esquina superior derecha, seleccione Administrar registros de  >  uso **de RTC.**</span><span class="sxs-lookup"><span data-stu-id="a8159-307">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="a8159-308">Haga **clic en Agregar**, escriba **Internacional** y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-308">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="a8159-309">Paso 2: Crear la ruta de voz "Internacional"</span><span class="sxs-lookup"><span data-stu-id="a8159-309">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="a8159-310">En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Enrutamiento directo de voz y, a continuación, seleccione la pestaña  >   **Rutas de** voz.</span><span class="sxs-lookup"><span data-stu-id="a8159-310">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="a8159-311">Haga **clic en** Agregar, escriba "Internacional" como nombre y, a continuación, agregue la descripción.</span><span class="sxs-lookup"><span data-stu-id="a8159-311">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="a8159-312">Establezca la prioridad en 4 y, después, establezca el patrón de número marcado en \d+.</span><span class="sxs-lookup"><span data-stu-id="a8159-312">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="a8159-313">En **SBC inscritos (opcional),** haga clic en Agregar **SBC,** seleccione sbc2.contoso.biz y sbc5.contoso.biz y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a8159-313">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="a8159-314">En Registros de uso rtc **(opcional),** haga clic en Agregar uso de **RTC,** seleccione el registro de uso RTC "Internacional" y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-314">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="a8159-315">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8159-315">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="a8159-316">Paso 3: Crear una directiva de enrutamiento de voz denominada "Sin restricciones" y agregar los usos RTC "EE. UU. y Canadá" e "Internacional" a la directiva</span><span class="sxs-lookup"><span data-stu-id="a8159-316">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="a8159-317">El uso de RTC "EE. UU. y Canadá" se reutiliza en esta directiva de enrutamiento de voz para conservar el tratamiento especial para llamadas a los números "+1 425 XXX XX XX" y "+1 206 XXX XX XX" como llamadas locales o locales.</span><span class="sxs-lookup"><span data-stu-id="a8159-317">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="a8159-318">En el panel de navegación izquierdo del centro Microsoft Teams de administración, vaya a Directivas de enrutamiento de voz y, a continuación,  >  haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-318">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="a8159-319">Escriba **Sin restricciones** como nombre y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="a8159-319">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="a8159-320">En **Registros de** uso de RTC, haga clic en Agregar uso de RTC, seleccione el registro de uso rtc "EE. UU. y Canadá" y, después, seleccione el registro de uso RTC "Internacional". </span><span class="sxs-lookup"><span data-stu-id="a8159-320">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="a8159-321">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a8159-321">Click **Apply**.</span></span>

    <span data-ttu-id="a8159-322">Tome nota del orden de los usos de RTC:</span><span class="sxs-lookup"><span data-stu-id="a8159-322">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="a8159-323">Si una llamada realizada al número "+1 425 XXX XX XX" con los usos configurados como en este ejemplo, la llamada sigue la ruta establecida en el uso "EE. UU. y Canadá" y se aplica la lógica de enrutamiento especial.</span><span class="sxs-lookup"><span data-stu-id="a8159-323">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="a8159-324">Es decir, la llamada se enruta sbc1.contoso.biz y sbc2.contoso.biz y, después, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a8159-324">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="a8159-325">Si el uso de RTC "Internacional" es anterior a "EE. UU. y Canadá", las llamadas a +1 425 XXX XX XX se enruta a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a8159-325">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="a8159-326">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8159-326">Click **Save**.</span></span>

<span data-ttu-id="a8159-327">Para obtener más información, vea [Administrar directivas de enrutamiento de voz.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a8159-327">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="a8159-328">Paso 4: Asignar la directiva de enrutamiento de voz a un usuario llamado John Woods</span><span class="sxs-lookup"><span data-stu-id="a8159-328">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="a8159-329">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="a8159-329">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="a8159-330">Haga **clic en** Directivas y, a continuación, junto a Directivas **asignadas,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-330">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="a8159-331">En **Directiva de enrutamiento de voz,** seleccione la directiva "Sin restricciones" y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="a8159-331">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="a8159-332">El resultado es que la directiva de voz aplicada a las llamadas de John Woods no está restringida y seguirá la lógica de enrutamiento de llamadas disponible para llamadas de EE. UU., Canadá e Internacionales.</span><span class="sxs-lookup"><span data-stu-id="a8159-332">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a8159-333">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8159-333">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="a8159-334">Paso 1: Crear el uso de RTC "Internacional"</span><span class="sxs-lookup"><span data-stu-id="a8159-334">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="a8159-335">En una sesión remota de PowerShell en Skype Empresarial Online, escriba:</span><span class="sxs-lookup"><span data-stu-id="a8159-335">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="a8159-336">Paso 2: Crear una nueva ruta de voz denominada "Internacional"</span><span class="sxs-lookup"><span data-stu-id="a8159-336">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

<span data-ttu-id="a8159-337">Lo que devuelve:</span><span class="sxs-lookup"><span data-stu-id="a8159-337">Which returns:</span></span>

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="a8159-338">Paso 3: Crear una directiva de enrutamiento de voz denominada "Sin restricciones"</span><span class="sxs-lookup"><span data-stu-id="a8159-338">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="a8159-339">El uso de RTC "Redmond 1" y "Redmond" se reutilizan en esta directiva de enrutamiento de voz para conservar el tratamiento especial para las llamadas a los números "+1 425 XXX XX XX" y "+1 206 XXX XX XX" como llamadas locales o locales.</span><span class="sxs-lookup"><span data-stu-id="a8159-339">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="a8159-340">Tome nota del orden de los usos de RTC:</span><span class="sxs-lookup"><span data-stu-id="a8159-340">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="a8159-341">Si una llamada realizada al número "+1 425 XXX XX XX" con los usos configurados como en el ejemplo siguiente, la llamada sigue la ruta establecida en el uso de "EE. UU. y Canadá" y se aplica la lógica de enrutamiento especial.</span><span class="sxs-lookup"><span data-stu-id="a8159-341">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="a8159-342">Es decir, la llamada se enruta sbc1.contoso.biz y sbc2.contoso.biz y, después, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a8159-342">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="a8159-343">Si el uso de RTC "Internacional" es anterior a "EE. UU. y Canadá", las llamadas a +1 425 XXX XX XX se enruta a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a8159-343">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="a8159-344">Escriba el comando:</span><span class="sxs-lookup"><span data-stu-id="a8159-344">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="a8159-345">Lo que devuelve:</span><span class="sxs-lookup"><span data-stu-id="a8159-345">Which returns:</span></span>

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="a8159-346">Paso 4: Asignar la directiva de enrutamiento de voz al usuario llamado John Woods</span><span class="sxs-lookup"><span data-stu-id="a8159-346">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="a8159-347">A continuación, compruebe la tarea con el comando:</span><span class="sxs-lookup"><span data-stu-id="a8159-347">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="a8159-348">Lo que devuelve:</span><span class="sxs-lookup"><span data-stu-id="a8159-348">Which returns:</span></span>

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

<span data-ttu-id="a8159-349">El resultado es que la directiva de voz aplicada a las llamadas de John Woods no está restringida y seguirá la lógica de enrutamiento de llamadas disponible para las llamadas de Estados Unidos, Canadá e Internacionales.</span><span class="sxs-lookup"><span data-stu-id="a8159-349">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8159-350">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8159-350">See also</span></span>

[<span data-ttu-id="a8159-351">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="a8159-351">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="a8159-352">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="a8159-352">Configure Direct Routing</span></span>](direct-routing-configure.md)
