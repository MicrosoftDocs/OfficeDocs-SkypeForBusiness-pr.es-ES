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
description: Obtenga información sobre cómo configurar el enrutamiento de voz con enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530997"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="69b9b-103">Configurar el enrutamiento de voz para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="69b9b-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="69b9b-104">En este artículo se describe cómo configurar el enrutamiento de voz para el enrutamiento directo de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="69b9b-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="69b9b-105">Este es el paso 3 de los siguientes pasos para configurar el enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="69b9b-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="69b9b-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="69b9b-106">Step 1.</span></span> [<span data-ttu-id="69b9b-107">Conectar el SBC con Microsoft Phone System y validar la conexión</span><span class="sxs-lookup"><span data-stu-id="69b9b-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="69b9b-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="69b9b-108">Step 2.</span></span> [<span data-ttu-id="69b9b-109">Habilitar a los usuarios el enrutamiento directo, la voz y el correo de voz</span><span class="sxs-lookup"><span data-stu-id="69b9b-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="69b9b-110">**Paso 3. Configurar el enrutamiento de** voz (en este artículo)</span><span class="sxs-lookup"><span data-stu-id="69b9b-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="69b9b-111">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="69b9b-111">Step 4.</span></span> [<span data-ttu-id="69b9b-112">Traducir números a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="69b9b-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="69b9b-113">Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="69b9b-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="69b9b-114">Información general sobre el enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="69b9b-114">Voice routing overview</span></span>

<span data-ttu-id="69b9b-115">Microsoft Phone System tiene un mecanismo de enrutamiento que permite que una llamada se envíe a un controlador de borde de sesión (SBC) específico en función de:</span><span class="sxs-lookup"><span data-stu-id="69b9b-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="69b9b-116">El patrón de número llamado</span><span class="sxs-lookup"><span data-stu-id="69b9b-116">The called number pattern</span></span> 
- <span data-ttu-id="69b9b-117">El patrón de número llamado y el usuario específico que realiza la llamada</span><span class="sxs-lookup"><span data-stu-id="69b9b-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="69b9b-118">Los SDC se pueden designar como activos y de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="69b9b-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="69b9b-119">Cuando el SBC que está configurado como activo no está disponible para una ruta de llamada específica, la llamada se enruta a una copia de seguridad SBC.</span><span class="sxs-lookup"><span data-stu-id="69b9b-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="69b9b-120">El enrutamiento de voz está basado en los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="69b9b-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="69b9b-121">**Directiva de enrutamiento de** voz: contenedor para usos de RTC, que se puede asignar a un usuario o a varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="69b9b-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="69b9b-122">**Usos de RTC:** contenedor para las rutas de voz y los usos de RTC, que se pueden compartir en diferentes directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="69b9b-123">**Rutas de voz:** un patrón de números y un conjunto de puertas de enlace RTC en línea que se pueden usar para llamadas cuando el número de llamada coincida con el patrón.</span><span class="sxs-lookup"><span data-stu-id="69b9b-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="69b9b-124"> Puerta de enlace RTC en línea: un puntero a un SBC que también almacena la configuración que se aplica cuando una llamada se hace a través del SBC, como reenvío de identidad profesional (PAI) o códecs preferidos. se pueden agregar a las rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="69b9b-125">Consideraciones de directivas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="69b9b-125">Voice routing policy considerations</span></span>

<span data-ttu-id="69b9b-126">Si un usuario tiene una licencia de plan de llamadas, las llamadas salientes de ese usuario se enruta automáticamente a través de la infraestructura RTC del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="69b9b-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="69b9b-127">Si configura y asigna una directiva de enrutamiento de voz en línea a un usuario del plan de llamadas, las llamadas salientes del usuario se comprobarán para determinar si el número marcado coincide con un patrón de número definido en la directiva de enrutamiento de voz en línea.</span><span class="sxs-lookup"><span data-stu-id="69b9b-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="69b9b-128">Si hay una coincidencia, la llamada se enruta a través del tronco de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="69b9b-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="69b9b-129">Si no hay ninguna coincidencia, la llamada se enruta a través de la infraestructura rtc del plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="69b9b-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="69b9b-130">Si configura y aplica la directiva de enrutamiento de voz en línea global (predeterminada para toda la organización), todos los usuarios habilitados para voz de su organización heredarán esa directiva, lo que puede provocar que las llamadas RTC de usuarios del plan de llamadas se enruten sin darse cuenta a un tronco de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="69b9b-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="69b9b-131">Si no desea que todos los usuarios usen la directiva global de enrutamiento de voz en línea, configure una directiva de enrutamiento de voz en línea personalizada y asígnela a usuarios individuales habilitados para voz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="69b9b-132">Ejemplo 1: Enrutamiento de voz con un uso de RTC</span><span class="sxs-lookup"><span data-stu-id="69b9b-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="69b9b-133">El siguiente diagrama muestra dos ejemplos de directivas de enrutamiento de voz en un flujo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="69b9b-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="69b9b-134">**Flujo de llamadas 1 (a la izquierda):** Si un usuario realiza una llamada a +1 425 XXX XX o +1 206 XXX XX XX, la llamada se enruta a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="69b9b-135">Si no sbc1.contoso.biz ni sbc2.contoso.biz disponibles, la llamada se descarta.</span><span class="sxs-lookup"><span data-stu-id="69b9b-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="69b9b-136">**Flujo de llamadas 2 (a la derecha):** Si un usuario realiza una llamada a +1 425 XXX XX o +1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="69b9b-137">Si no hay disponible SBC, se probará la ruta con una prioridad inferior (sbc3.contoso.biz y sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="69b9b-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="69b9b-138">Si ninguno de los SBC está disponible, la llamada se descarta.</span><span class="sxs-lookup"><span data-stu-id="69b9b-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Muestra ejemplos de directivas de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="69b9b-140">En ambos ejemplos, mientras se asignan prioridades a la ruta de voz, se prueban de forma aleatoria los SBC de las rutas.</span><span class="sxs-lookup"><span data-stu-id="69b9b-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span> <span data-ttu-id="69b9b-141">Cuando dos SBC están configurados en una ruta, el tráfico de red debe ser enrutable entre SBC o multimedia no se establecerá en las transferencias, ya que es posible que la nueva invitación para la transferencia se envíe a otro SBC en la ruta.</span><span class="sxs-lookup"><span data-stu-id="69b9b-141">When two SBC's are configured in one route, network traffic must be routable between both SBC's or media will fail to be established on transfers as it is possible that the new invite for the transfer will be sent to a different SBC in the route.</span></span>

  > [!NOTE]
  > <span data-ttu-id="69b9b-142">A menos que el usuario también tenga una licencia de Microsoft Calling Plan, las llamadas a cualquier número excepto los números que coincidan con los patrones +1 425 XXX XX XX o +1 206 XXX XX XX en la configuración de ejemplo se descartan.</span><span class="sxs-lookup"><span data-stu-id="69b9b-142">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="69b9b-143">Si el usuario tiene una licencia de plan de llamadas, la llamada se enruta automáticamente según las directivas del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="69b9b-143">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="69b9b-144">El plan de llamadas de Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de Microsoft Calling Plan y no requiere configuración adicional de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="69b9b-144">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="69b9b-145">En el ejemplo que se muestra en el siguiente diagrama, se agrega una ruta de voz para enviar llamadas a todos los demás números de EE. UU. y Canadá (llamadas que van a llamar a patrón de números +1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="69b9b-145">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Muestra la directiva de enrutamiento de voz con una tercera ruta](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="69b9b-147">En el resto de llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Calling Plan), se usará la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="69b9b-147">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="69b9b-148">Si no hay nada que coincida con los patrones de números en las rutas de voz en línea creadas por el administrador, la llamada se enruta a través de Microsoft Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="69b9b-148">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="69b9b-149">Si el usuario solo tiene Microsoft Phone System, la llamada se descarta porque no hay reglas que coincidan.</span><span class="sxs-lookup"><span data-stu-id="69b9b-149">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="69b9b-150">El valor de prioridad de la ruta "Otros +1" no importa en este caso porque solo hay una ruta que coincida con el patrón +1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="69b9b-150">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="69b9b-151">Si un usuario llama al +1 324 567 89 89 y sbc5.contoso.biz y sbc6.contoso.biz no están disponibles, la llamada se descarta.</span><span class="sxs-lookup"><span data-stu-id="69b9b-151">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="69b9b-152">En la tabla siguiente se resume la configuración mediante tres rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-152">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="69b9b-153">En este ejemplo, las tres rutas forman parte del mismo uso de RTC, "EE. UU. y Canadá".</span><span class="sxs-lookup"><span data-stu-id="69b9b-153">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="69b9b-154">Todas las rutas están asociadas con el uso de RTC de "EE. UU. y Canadá" y el uso de RTC está asociado con la directiva de enrutamiento de voz "Solo para ESTADOS UNIDOS".</span><span class="sxs-lookup"><span data-stu-id="69b9b-154">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="69b9b-155">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="69b9b-155">**PSTN usage**</span></span>|<span data-ttu-id="69b9b-156">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="69b9b-156">**Voice route**</span></span>|<span data-ttu-id="69b9b-157">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="69b9b-157">**Number pattern**</span></span>|<span data-ttu-id="69b9b-158">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="69b9b-158">**Priority**</span></span>|<span data-ttu-id="69b9b-159">**SBC**</span><span class="sxs-lookup"><span data-stu-id="69b9b-159">**SBC**</span></span>|<span data-ttu-id="69b9b-160">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="69b9b-160">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="69b9b-161">Ee. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="69b9b-161">US and Canada</span></span>|<span data-ttu-id="69b9b-162">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="69b9b-162">"Redmond 1"</span></span>|<span data-ttu-id="69b9b-163">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="69b9b-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="69b9b-164">1</span><span class="sxs-lookup"><span data-stu-id="69b9b-164">1</span></span>|<span data-ttu-id="69b9b-165">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-165">sbc1.contoso.biz</span></span><br/><span data-ttu-id="69b9b-166">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-166">sbc2.contoso.biz</span></span>|<span data-ttu-id="69b9b-167">Ruta activa para números llamados +1 425 XXX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="69b9b-167">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="69b9b-168">Ee. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="69b9b-168">US and Canada</span></span>|<span data-ttu-id="69b9b-169">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="69b9b-169">"Redmond 2"</span></span>|<span data-ttu-id="69b9b-170">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="69b9b-170">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="69b9b-171">2</span><span class="sxs-lookup"><span data-stu-id="69b9b-171">2</span></span>|<span data-ttu-id="69b9b-172">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-172">sbc3.contoso.biz</span></span><br/><span data-ttu-id="69b9b-173">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-173">sbc4.contoso.biz</span></span>|<span data-ttu-id="69b9b-174">Ruta de copia de seguridad para números llamados +1 425 XXX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="69b9b-174">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="69b9b-175">Ee. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="69b9b-175">US and Canada</span></span>|<span data-ttu-id="69b9b-176">"Otros +1"</span><span class="sxs-lookup"><span data-stu-id="69b9b-176">"Other +1"</span></span>|<span data-ttu-id="69b9b-177">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="69b9b-177">^\\+1(\d{10})$</span></span>|<span data-ttu-id="69b9b-178">3</span><span class="sxs-lookup"><span data-stu-id="69b9b-178">3</span></span>|<span data-ttu-id="69b9b-179">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-179">sbc5.contoso.biz</span></span><br/><span data-ttu-id="69b9b-180">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-180">sbc6.contoso.biz</span></span>|<span data-ttu-id="69b9b-181">Ruta para números llamados +1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="69b9b-181">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="69b9b-182">Ejemplo 1: Pasos de configuración</span><span class="sxs-lookup"><span data-stu-id="69b9b-182">Example 1: Configuration steps</span></span>

<span data-ttu-id="69b9b-183">En el ejemplo siguiente se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="69b9b-183">The following example shows how to:</span></span>

1. <span data-ttu-id="69b9b-184">Cree un único uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="69b9b-184">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="69b9b-185">Configure tres rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-185">Configure three voice routes.</span></span>
3. <span data-ttu-id="69b9b-186">Cree una directiva de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-186">Create a voice routing policy.</span></span>
4. <span data-ttu-id="69b9b-187">Asigne la directiva a un usuario llamado Low.</span><span class="sxs-lookup"><span data-stu-id="69b9b-187">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="69b9b-188">Puede usar el Centro [de administración de Microsoft Teams](#admincenterexample1) o [PowerShell](#powershellexample1) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="69b9b-188">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="69b9b-189">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69b9b-189">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="69b9b-190">Paso 1: Crear el uso de RTC "EE. UU. y Canadá"</span><span class="sxs-lookup"><span data-stu-id="69b9b-190">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="69b9b-191">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Enrutamiento directo de voz y, en la esquina superior derecha, seleccione Administrar registros  >  de uso **de RTC.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-191">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="69b9b-192">Haga **clic en Agregar,** escriba **EE. UU. y Canadá** y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-192">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="69b9b-193">Paso 2: Crear tres rutas de voz (Redmond 1, Redmond 2 y Otros +1)</span><span class="sxs-lookup"><span data-stu-id="69b9b-193">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="69b9b-194">En los pasos siguientes se describe cómo crear una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-194">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="69b9b-195">Siga estos pasos para crear las tres rutas de voz denominadas Redmond 1, Redmond 2 y Otros +1 para este ejemplo mediante la configuración descrita en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="69b9b-195">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="69b9b-196">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Enrutamiento directo de voz y, después, seleccione  >  la **pestaña Rutas de** voz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="69b9b-197">Haga **clic en** Agregar y, a continuación, escriba un nombre y una descripción para la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-197">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="69b9b-198">Establezca la prioridad y especifique el patrón de número marcado.</span><span class="sxs-lookup"><span data-stu-id="69b9b-198">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="69b9b-199">Para inscribir un SBC con la ruta de voz, en los SBC inscritos **(opcional),** haga clic en Agregar SBC, seleccione los SBC que desea inscribir y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-199">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="69b9b-200">Para agregar registros de uso de RTC, en Registros de uso de RTC **(opcional),** haga clic en Agregar uso de **RTC,** seleccione los registros RTC que desea agregar y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-200">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="69b9b-201">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="69b9b-201">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="69b9b-202">Paso 3: Crear una directiva de enrutamiento de voz denominada "Solo Estados Unidos" y agregar el uso de RTC "EE. UU. y Canadá" a la directiva</span><span class="sxs-lookup"><span data-stu-id="69b9b-202">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="69b9b-203">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las **directivas** de enrutamiento de voz y, a continuación, haga clic  >  en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-203">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="69b9b-204">Escriba **US Only** como nombre y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="69b9b-204">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="69b9b-205">En **Registros de uso de RTC,** haga clic en Agregar uso de RTC, seleccione el registro de uso de RTC "EE. UU. y Canadá" y, a continuación, haga clic en **Aplicar.** </span><span class="sxs-lookup"><span data-stu-id="69b9b-205">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="69b9b-206">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="69b9b-206">Click **Save**.</span></span>

<span data-ttu-id="69b9b-207">Para obtener más información, vea [Administrar directivas de enrutamiento de voz.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="69b9b-207">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="69b9b-208">Paso 4: Asignar la directiva de enrutamiento de voz a un usuario llamado Low</span><span class="sxs-lookup"><span data-stu-id="69b9b-208">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="69b9b-209">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="69b9b-209">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="69b9b-210">Haga clic **en Directivas** y, junto a **Directivas asignadas,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-210">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="69b9b-211">En **Directiva de enrutamiento de** voz, seleccione la directiva "Solo Estados Unidos" y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-211">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="69b9b-212">Para obtener más información, vea [Administrar directivas de enrutamiento de voz.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="69b9b-212">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="69b9b-213">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="69b9b-213">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="69b9b-214">Paso 1: Crear el uso de RTC "EE. UU. y Canadá"</span><span class="sxs-lookup"><span data-stu-id="69b9b-214">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="69b9b-215">En una sesión remota de PowerShell en Skype Empresarial Online, escriba:</span><span class="sxs-lookup"><span data-stu-id="69b9b-215">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="69b9b-216">Compruebe que el uso se creó especificando:</span><span class="sxs-lookup"><span data-stu-id="69b9b-216">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="69b9b-217">Lo que devuelve una lista de nombres que pueden truncarse:</span><span class="sxs-lookup"><span data-stu-id="69b9b-217">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="69b9b-218">En el ejemplo siguiente se muestra el resultado de ejecutar el comando PowerShell para mostrar nombres completos `(Get-CSOnlinePSTNUsage).usage` (no truncados):</span><span class="sxs-lookup"><span data-stu-id="69b9b-218">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="69b9b-219">Paso 2: Crear tres rutas de voz (Redmond 1, Redmond 2 y Otros +1)</span><span class="sxs-lookup"><span data-stu-id="69b9b-219">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="69b9b-220">Para crear la ruta de "Redmond 1", en una sesión de PowerShell en Skype Empresarial Online, escriba:</span><span class="sxs-lookup"><span data-stu-id="69b9b-220">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="69b9b-221">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="69b9b-221">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="69b9b-222">Para crear la ruta de Redmond 2, escribe:</span><span class="sxs-lookup"><span data-stu-id="69b9b-222">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="69b9b-223">Para crear la ruta Otros +1, escriba:</span><span class="sxs-lookup"><span data-stu-id="69b9b-223">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="69b9b-224">Asegúrese de que la expresión regular del atributo NumberPattern es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="69b9b-224">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="69b9b-225">Puede probarlo con este sitio web: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="69b9b-225">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="69b9b-226">En algunos casos, es necesario enrutar todas las llamadas al mismo SBC; use -NumberPattern ".\*"</span><span class="sxs-lookup"><span data-stu-id="69b9b-226">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="69b9b-227">Enrutar todas las llamadas al mismo SBC.</span><span class="sxs-lookup"><span data-stu-id="69b9b-227">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="69b9b-228">Compruebe que ha configurado correctamente la ruta ejecutando el comando `Get-CSOnlineVoiceRoute` de PowerShell con opciones como se muestra:</span><span class="sxs-lookup"><span data-stu-id="69b9b-228">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="69b9b-229">Lo que debería devolver:</span><span class="sxs-lookup"><span data-stu-id="69b9b-229">Which should return:</span></span>
<pre>
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
</pre>

<span data-ttu-id="69b9b-230">En el ejemplo, se asignó automáticamente la prioridad 4 a la ruta "Otros +1".</span><span class="sxs-lookup"><span data-stu-id="69b9b-230">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="69b9b-231">Paso 3: Crear una directiva de enrutamiento de voz denominada "Solo Estados Unidos" y agregar el uso de RTC "EE. UU. y Canadá" a la directiva</span><span class="sxs-lookup"><span data-stu-id="69b9b-231">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="69b9b-232">En una sesión de PowerShell en Skype Empresarial Online, escriba:</span><span class="sxs-lookup"><span data-stu-id="69b9b-232">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="69b9b-233">El resultado se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="69b9b-233">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="69b9b-234">Paso 4: Asignar la directiva de enrutamiento de voz a un usuario llamado Low</span><span class="sxs-lookup"><span data-stu-id="69b9b-234">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="69b9b-235">En una sesión de PowerShell en Skype Empresarial Online, escriba:</span><span class="sxs-lookup"><span data-stu-id="69b9b-235">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="69b9b-236">Valide la asignación de directiva especificando este comando:</span><span class="sxs-lookup"><span data-stu-id="69b9b-236">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="69b9b-237">El comando devuelve lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69b9b-237">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="69b9b-238">Ejemplo 2: Enrutamiento de voz con varios usos de RTC</span><span class="sxs-lookup"><span data-stu-id="69b9b-238">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="69b9b-239">La directiva de enrutamiento de voz creada en el ejemplo 1 solo permite las llamadas a números de teléfono de Estados Unidos y Canadá, a menos que la licencia del plan de llamadas de Microsoft también esté asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="69b9b-239">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="69b9b-240">En el ejemplo siguiente, puede crear la directiva de enrutamiento de voz "Sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="69b9b-240">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="69b9b-241">La directiva reutiliza el uso de RTC "EE. UU. y Canadá" creado en el ejemplo 1, así como el nuevo uso de RTC "Internacional".</span><span class="sxs-lookup"><span data-stu-id="69b9b-241">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="69b9b-242">Esta directiva desvía todas las demás llamadas a las sbc2.contoso.biz y sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-242">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="69b9b-243">En los ejemplos que se muestran se asigna la directiva US Only al usuario Low y la directiva Sin restricciones al usuario John Protocol para que el enrutamiento se realice de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="69b9b-243">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="69b9b-244">Qué bajo: directiva de EE. UU. solo.</span><span class="sxs-lookup"><span data-stu-id="69b9b-244">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="69b9b-245">Las llamadas solo se permiten a números de EE. UU. y canadienses.</span><span class="sxs-lookup"><span data-stu-id="69b9b-245">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="69b9b-246">Al llamar al rango de números de Redmond, debe usarse el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="69b9b-246">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="69b9b-247">Los números que no sean de EE. UU. no se enruta a menos que se asigne al usuario una licencia del plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="69b9b-247">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="69b9b-248">John Bosques: directiva internacional.</span><span class="sxs-lookup"><span data-stu-id="69b9b-248">John Woods – International policy.</span></span>  <span data-ttu-id="69b9b-249">Las llamadas se permiten a cualquier número.</span><span class="sxs-lookup"><span data-stu-id="69b9b-249">Calls are allowed to any number.</span></span> <span data-ttu-id="69b9b-250">Al llamar al rango de números de Redmond, debe usarse el conjunto específico de SBC.</span><span class="sxs-lookup"><span data-stu-id="69b9b-250">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="69b9b-251">Los números que no sean de EE. UU. se enruta con sbc2.contoso.biz y sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-251">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Muestra la directiva de enrutamiento de voz asignada al usuario Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="69b9b-253">En el resto de llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Calling Plan), se usa la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="69b9b-253">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="69b9b-254">Si no hay nada que coincida con los patrones de números de las rutas de voz en línea creadas por el administrador, la llamada se enruta con el plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="69b9b-254">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="69b9b-255">Si el usuario solo tiene Microsoft Phone System, la llamada se descarta porque no hay reglas que coincidan.</span><span class="sxs-lookup"><span data-stu-id="69b9b-255">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Muestra la directiva de enrutamiento de voz asignada al usuario JohnPecto](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="69b9b-257">En la tabla siguiente se resumen las designaciones de uso y las rutas de voz "Sin restricciones" de la directiva de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="69b9b-257">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="69b9b-258">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="69b9b-258">**PSTN usage**</span></span>|<span data-ttu-id="69b9b-259">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="69b9b-259">**Voice route**</span></span>|<span data-ttu-id="69b9b-260">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="69b9b-260">**Number pattern**</span></span>|<span data-ttu-id="69b9b-261">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="69b9b-261">**Priority**</span></span>|<span data-ttu-id="69b9b-262">**SBC**</span><span class="sxs-lookup"><span data-stu-id="69b9b-262">**SBC**</span></span>|<span data-ttu-id="69b9b-263">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="69b9b-263">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="69b9b-264">Ee. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="69b9b-264">US and Canada</span></span>|<span data-ttu-id="69b9b-265">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="69b9b-265">"Redmond 1"</span></span>|<span data-ttu-id="69b9b-266">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="69b9b-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="69b9b-267">1</span><span class="sxs-lookup"><span data-stu-id="69b9b-267">1</span></span>|<span data-ttu-id="69b9b-268">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-268">sbc1.contoso.biz</span></span><br/><span data-ttu-id="69b9b-269">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-269">sbc2.contoso.biz</span></span>|<span data-ttu-id="69b9b-270">Ruta activa para números del destinatario +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="69b9b-270">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="69b9b-271">Ee. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="69b9b-271">US and Canada</span></span>|<span data-ttu-id="69b9b-272">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="69b9b-272">"Redmond 2"</span></span>|<span data-ttu-id="69b9b-273">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="69b9b-273">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="69b9b-274">2</span><span class="sxs-lookup"><span data-stu-id="69b9b-274">2</span></span>|<span data-ttu-id="69b9b-275">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-275">sbc3.contoso.biz</span></span><br/><span data-ttu-id="69b9b-276">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-276">sbc4.contoso.biz</span></span>|<span data-ttu-id="69b9b-277">Ruta de copia de seguridad para números del destinatario +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="69b9b-277">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="69b9b-278">Ee. UU. y Canadá</span><span class="sxs-lookup"><span data-stu-id="69b9b-278">US and Canada</span></span>|<span data-ttu-id="69b9b-279">"Otros +1"</span><span class="sxs-lookup"><span data-stu-id="69b9b-279">"Other +1"</span></span>|<span data-ttu-id="69b9b-280">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="69b9b-280">^\\+1(\d{10})$</span></span>|<span data-ttu-id="69b9b-281">3</span><span class="sxs-lookup"><span data-stu-id="69b9b-281">3</span></span>|<span data-ttu-id="69b9b-282">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-282">sbc5.contoso.biz</span></span><br/><span data-ttu-id="69b9b-283">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-283">sbc6.contoso.biz</span></span>|<span data-ttu-id="69b9b-284">Ruta para números de destinatario +1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="69b9b-284">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="69b9b-285">International</span><span class="sxs-lookup"><span data-stu-id="69b9b-285">International</span></span>|<span data-ttu-id="69b9b-286">International</span><span class="sxs-lookup"><span data-stu-id="69b9b-286">International</span></span>|<span data-ttu-id="69b9b-287">\d+</span><span class="sxs-lookup"><span data-stu-id="69b9b-287">\d+</span></span>|<span data-ttu-id="69b9b-288">4</span><span class="sxs-lookup"><span data-stu-id="69b9b-288">4</span></span>|<span data-ttu-id="69b9b-289">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-289">sbc2.contoso.biz</span></span><br/><span data-ttu-id="69b9b-290">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="69b9b-290">sbc5.contoso.biz</span></span>|<span data-ttu-id="69b9b-291">Ruta para cualquier patrón de números</span><span class="sxs-lookup"><span data-stu-id="69b9b-291">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="69b9b-292">El orden de los usos de RTC en las directivas de enrutamiento de voz es fundamental.</span><span class="sxs-lookup"><span data-stu-id="69b9b-292">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="69b9b-293">Los usos se aplican en orden y, si se encuentra una coincidencia en el primer uso, nunca se evalúan otros usos.</span><span class="sxs-lookup"><span data-stu-id="69b9b-293">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="69b9b-294">El uso de RTC "Internacional" debe colocarse después del uso de RTC "EE. UU. y Canadá".</span><span class="sxs-lookup"><span data-stu-id="69b9b-294">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="69b9b-295">Para cambiar el orden de los usos de RTC, ejecute el `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="69b9b-295">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="69b9b-296">Por ejemplo, para cambiar el orden de "EE. UU. y Canadá" primero e "Internacional" segundo al orden inverso ejecute:</span><span class="sxs-lookup"><span data-stu-id="69b9b-296">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="69b9b-297">La prioridad de las rutas de voz "Otros +1" e "Internacional" se asigna automáticamente.</span><span class="sxs-lookup"><span data-stu-id="69b9b-297">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="69b9b-298">No importan tanto como tengan prioridades más bajas que "Redmond 1" y "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="69b9b-298">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="69b9b-299">Ejemplo 2: Pasos de configuración</span><span class="sxs-lookup"><span data-stu-id="69b9b-299">Example 2: Configuration steps</span></span>

<span data-ttu-id="69b9b-300">En el ejemplo siguiente se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="69b9b-300">The following example shows how to:</span></span>

1. <span data-ttu-id="69b9b-301">Cree un nuevo uso de RTC llamado Internacional.</span><span class="sxs-lookup"><span data-stu-id="69b9b-301">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="69b9b-302">Crea una nueva ruta de voz llamada Internacional.</span><span class="sxs-lookup"><span data-stu-id="69b9b-302">Create a new voice route called International.</span></span>
3. <span data-ttu-id="69b9b-303">Cree una directiva de enrutamiento de voz llamada Sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="69b9b-303">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="69b9b-304">Asigne la directiva al usuario John Bosques.</span><span class="sxs-lookup"><span data-stu-id="69b9b-304">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="69b9b-305">Puede usar el Centro [de administración de Microsoft Teams](#admincenterexample2) o [PowerShell](#powershellexample2) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="69b9b-305">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="69b9b-306">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69b9b-306">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="69b9b-307">Paso 1: Crear el uso de RTC "Internacional"</span><span class="sxs-lookup"><span data-stu-id="69b9b-307">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="69b9b-308">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Enrutamiento directo de voz y, en la esquina superior derecha, seleccione Administrar registros  >  de uso **de RTC.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-308">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="69b9b-309">Haga **clic en Agregar,** escriba **Internacional** y, a continuación, haga clic **en Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-309">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="69b9b-310">Paso 2: Crear la ruta de voz "Internacional"</span><span class="sxs-lookup"><span data-stu-id="69b9b-310">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="69b9b-311">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Enrutamiento directo de voz y, después, seleccione  >  la **pestaña Rutas de** voz.</span><span class="sxs-lookup"><span data-stu-id="69b9b-311">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="69b9b-312">Haga **clic en** Agregar, escriba "Internacional" como nombre y, a continuación, agregue la descripción.</span><span class="sxs-lookup"><span data-stu-id="69b9b-312">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="69b9b-313">Establezca la prioridad en 4 y, a continuación, establezca el patrón de números marcados en \d+.</span><span class="sxs-lookup"><span data-stu-id="69b9b-313">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="69b9b-314">En **CCSS inscritos (opcional),** haga clic en Agregar OSN, seleccione sbc2.contoso.biz y sbc5.contoso.biz y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-314">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="69b9b-315">En Registros de uso de RTC **(opcional),** haga clic en Agregar uso de **RTC,** seleccione el registro de uso de RTC "Internacional" y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-315">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="69b9b-316">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="69b9b-316">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="69b9b-317">Paso 3: Crear una directiva de enrutamiento de voz denominada "Sin restricciones" y agregar los usos de RTC "EE. UU. y Canadá" e "Internacional" a la directiva</span><span class="sxs-lookup"><span data-stu-id="69b9b-317">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="69b9b-318">El uso de RTC "EE. UU. y Canadá" se reutiliza en esta directiva de enrutamiento de voz para conservar la administración especial para las llamadas al número "+1 425 XXX XX XX" y "+1 206 XXX XX XX" como llamadas locales o locales.</span><span class="sxs-lookup"><span data-stu-id="69b9b-318">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="69b9b-319">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las **directivas** de enrutamiento de voz y, a continuación, haga clic  >  en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-319">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="69b9b-320">Escriba **Sin restricciones** como nombre y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="69b9b-320">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="69b9b-321">En **Registros de uso** de RTC, haga clic en Agregar uso de RTC, seleccione el registro de uso de RTC "EE. UU. y Canadá" y, a continuación, seleccione el registro de uso de RTC "Internacional". </span><span class="sxs-lookup"><span data-stu-id="69b9b-321">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="69b9b-322">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="69b9b-322">Click **Apply**.</span></span>

    <span data-ttu-id="69b9b-323">Anote el orden de los usos de RTC:</span><span class="sxs-lookup"><span data-stu-id="69b9b-323">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="69b9b-324">Si una llamada realizada al número "+1 425 XXX XX XX" con los usos configurados como en este ejemplo, la llamada sigue la ruta establecida en "EE. UU. y Canadá" uso y se aplica la lógica de enrutamiento especial.</span><span class="sxs-lookup"><span data-stu-id="69b9b-324">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="69b9b-325">Es decir, la llamada se enruta usando sbc1.contoso.biz y sbc2.contoso.biz en primer lugar y, después, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="69b9b-325">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="69b9b-326">Si el uso de RTC "Internacional" es anterior a "EE. UU. y Canadá", las llamadas a +1 425 XXX XX XX se enruta a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="69b9b-326">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="69b9b-327">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="69b9b-327">Click **Save**.</span></span>

<span data-ttu-id="69b9b-328">Para obtener más información, vea [Administrar directivas de enrutamiento de voz.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="69b9b-328">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="69b9b-329">Paso 4: Asignar la directiva de enrutamiento de voz a un usuario llamado John Noé</span><span class="sxs-lookup"><span data-stu-id="69b9b-329">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="69b9b-330">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="69b9b-330">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="69b9b-331">Haga clic **en Directivas** y, junto a **Directivas asignadas,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-331">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="69b9b-332">En **Directiva de enrutamiento de** voz, seleccione la directiva "Sin restricciones" y haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="69b9b-332">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="69b9b-333">El resultado es que la directiva de voz aplicada a las llamadas de John John Se ha restringido y seguirá la lógica del enrutamiento de llamadas disponible para llamadas estadounidenses, canadá e internacionales.</span><span class="sxs-lookup"><span data-stu-id="69b9b-333">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="69b9b-334">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="69b9b-334">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="69b9b-335">Paso 1: Crear el uso de RTC "Internacional"</span><span class="sxs-lookup"><span data-stu-id="69b9b-335">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="69b9b-336">En una sesión remota de PowerShell en Skype Empresarial Online, escriba:</span><span class="sxs-lookup"><span data-stu-id="69b9b-336">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="69b9b-337">Paso 2: Crear una nueva ruta de voz denominada "Internacional"</span><span class="sxs-lookup"><span data-stu-id="69b9b-337">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="69b9b-338">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="69b9b-338">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="69b9b-339">Paso 3: Crear una directiva de enrutamiento de voz denominada "Sin restricciones"</span><span class="sxs-lookup"><span data-stu-id="69b9b-339">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="69b9b-340">El uso de RTC "Redmond 1" y "Redmond" se reutilizan en esta directiva de enrutamiento de voz para conservar la administración especial para las llamadas al número "+1 425 XXX XX XX" y "+1 206 XXX XX XX" como llamadas locales o locales.</span><span class="sxs-lookup"><span data-stu-id="69b9b-340">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="69b9b-341">Anote el orden de los usos de RTC:</span><span class="sxs-lookup"><span data-stu-id="69b9b-341">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="69b9b-342">Si una llamada realizada al número "+1 425 XXX XX XX" con los usos configurados como en el ejemplo siguiente, la llamada sigue la ruta establecida en "EE. UU. y Canadá" uso y se aplica la lógica de enrutamiento especial.</span><span class="sxs-lookup"><span data-stu-id="69b9b-342">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="69b9b-343">Es decir, la llamada se enruta usando sbc1.contoso.biz y sbc2.contoso.biz en primer lugar y, después, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="69b9b-343">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="69b9b-344">Si el uso de RTC "Internacional" es anterior a "EE. UU. y Canadá", las llamadas a +1 425 XXX XX XX se enruta a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="69b9b-344">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="69b9b-345">Escriba el comando:</span><span class="sxs-lookup"><span data-stu-id="69b9b-345">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="69b9b-346">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="69b9b-346">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="69b9b-347">Paso 4: Asignar la directiva de enrutamiento de voz al usuario llamado John Seleán</span><span class="sxs-lookup"><span data-stu-id="69b9b-347">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="69b9b-348">Después, compruebe la tarea con el comando:</span><span class="sxs-lookup"><span data-stu-id="69b9b-348">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="69b9b-349">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="69b9b-349">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="69b9b-350">El resultado es que la directiva de voz aplicada a las llamadas de John John Se ha restringido y seguirá la lógica del enrutamiento de llamadas disponible para llamadas estadounidenses, canadá e internacionales.</span><span class="sxs-lookup"><span data-stu-id="69b9b-350">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="69b9b-351">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69b9b-351">See also</span></span>

[<span data-ttu-id="69b9b-352">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="69b9b-352">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="69b9b-353">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="69b9b-353">Configure Direct Routing</span></span>](direct-routing-configure.md)
