---
title: Configurar el enrutamiento de voz para el enrutamiento directo
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
description: Obtenga información sobre cómo configurar el enrutamiento de voz con el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530997"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="2cf44-103">Configurar el enrutamiento de voz para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="2cf44-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="2cf44-104">En este artículo se describe cómo configurar el enrutamiento de voz para el enrutamiento directo de un sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="2cf44-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="2cf44-105">Este es el paso 3 de los pasos siguientes para configurar el enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="2cf44-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="2cf44-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="2cf44-106">Step 1.</span></span> [<span data-ttu-id="2cf44-107">Conectar el SBC con Microsoft Phone System y validar la conexión</span><span class="sxs-lookup"><span data-stu-id="2cf44-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="2cf44-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="2cf44-108">Step 2.</span></span> [<span data-ttu-id="2cf44-109">Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz</span><span class="sxs-lookup"><span data-stu-id="2cf44-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="2cf44-110">**Paso 3. Configurar el enrutamiento de voz** (este artículo)</span><span class="sxs-lookup"><span data-stu-id="2cf44-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="2cf44-111">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="2cf44-111">Step 4.</span></span> [<span data-ttu-id="2cf44-112">Traducir números a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="2cf44-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="2cf44-113">Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, consulte [configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="2cf44-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="2cf44-114">Introducción al enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="2cf44-114">Voice routing overview</span></span>

<span data-ttu-id="2cf44-115">Microsoft Phone System tiene un mecanismo de enrutamiento que permite que se envíe una llamada a un controlador de borde de sesión (SBC) específico en función de:</span><span class="sxs-lookup"><span data-stu-id="2cf44-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="2cf44-116">El patrón de número al que se llama</span><span class="sxs-lookup"><span data-stu-id="2cf44-116">The called number pattern</span></span> 
- <span data-ttu-id="2cf44-117">El patrón de número al que se llama y el usuario específico que realiza la llamada</span><span class="sxs-lookup"><span data-stu-id="2cf44-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="2cf44-118">SBCs puede designarse como activo y como backup.</span><span class="sxs-lookup"><span data-stu-id="2cf44-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="2cf44-119">Cuando el SBC configurado como activo no está disponible para una ruta de llamada específica, la llamada se redirigirá a un SBC de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2cf44-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="2cf44-120">El enrutamiento de voz consta de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="2cf44-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="2cf44-121">**Directiva de enrutamiento de voz** : contenedor de uso de RTC, que se puede asignar a un usuario o a varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="2cf44-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="2cf44-122">**Usos de RTC** : un contenedor de rutas de voz y usos de RTC, que se pueden compartir en diferentes directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="2cf44-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="2cf44-123">**Rutas de voz** : un patrón de número y un conjunto de puertas de enlace RTC en línea para usarlas en las llamadas en las que el número de llamada coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="2cf44-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="2cf44-124">**Puerta de enlace RTC en línea** : puntero a un SBC que también almacena la configuración que se aplica cuando una llamada se coloca a través de SBC, como la identidad de aserción de P (PAI) o los códecs preferidos. se puede Agregar a las rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="2cf44-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="2cf44-125">Consideraciones de directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="2cf44-125">Voice routing policy considerations</span></span>

<span data-ttu-id="2cf44-126">Si un usuario tiene una licencia de plan de llamadas, las llamadas salientes de ese usuario se enrutan automáticamente a través de la infraestructura RTC del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cf44-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="2cf44-127">Si configura y asigna una directiva de enrutamiento de voz en línea a un usuario del plan de llamadas, se comprobarán las llamadas salientes de ese usuario para determinar si el número marcado coincide con un patrón de número definido en la Directiva de enrutamiento de voz en línea.</span><span class="sxs-lookup"><span data-stu-id="2cf44-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="2cf44-128">Si hay una coincidencia, la llamada se dirige a través del tronco de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="2cf44-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="2cf44-129">Si no hay ninguna coincidencia, la llamada se dirige a través de la infraestructura RTC del plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2cf44-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="2cf44-130">Si configura y aplica la Directiva de enrutamiento de voz en línea global (predeterminada para toda la organización), todos los usuarios habilitados para voz de la organización heredarán esa Directiva, lo que puede provocar que las llamadas RTC se dirijan de forma inadvertida a un tronco de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="2cf44-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="2cf44-131">Si no desea que todos los usuarios usen la Directiva de enrutamiento de voz en línea global, configure una directiva de enrutamiento de voz en línea personalizada y asígnela a usuarios habilitados para voz.</span><span class="sxs-lookup"><span data-stu-id="2cf44-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="2cf44-132">Ejemplo 1: enrutamiento de voz con un uso de RTC</span><span class="sxs-lookup"><span data-stu-id="2cf44-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="2cf44-133">En el siguiente diagrama se muestran dos ejemplos de directivas de enrutamiento de voz en un flujo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2cf44-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="2cf44-134">**Flujo de llamadas 1 (a la izquierda):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se dirige a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2cf44-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="2cf44-135">Si ni sbc1.contoso.biz ni sbc2.contoso.biz están disponibles, la llamada se interrumpe.</span><span class="sxs-lookup"><span data-stu-id="2cf44-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="2cf44-136">**Flujo de llamadas 2 (a la derecha):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2cf44-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="2cf44-137">Si no hay ninguna SBC disponible, se intentará la ruta con prioridad más baja (sbc3.contoso.biz y sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="2cf44-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="2cf44-138">Si ninguno de los SBCs está disponible, la llamada se corta.</span><span class="sxs-lookup"><span data-stu-id="2cf44-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Muestra ejemplos de directiva de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="2cf44-140">En ambos ejemplos, mientras se asignan prioridades a la ruta de voz, se prueba el SBCs en las rutas en orden aleatorio.</span><span class="sxs-lookup"><span data-stu-id="2cf44-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span> <span data-ttu-id="2cf44-141">Cuando se configuran dos SBC en una ruta, el tráfico de red debe ser enrutable entre los dos de SBC o los medios no se establecerán en las transferencias, ya que es posible que la nueva invitación para la transferencia se envíe a un SBC diferente en la ruta.</span><span class="sxs-lookup"><span data-stu-id="2cf44-141">When two SBC's are configured in one route, network traffic must be routable between both SBC's or media will fail to be established on transfers as it is possible that the new invite for the transfer will be sent to a different SBC in the route.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2cf44-142">A menos que el usuario también tenga una licencia de plan de llamadas de Microsoft, las llamadas a cualquier número excepto los números que coincidan con los patrones + 1 425 XXX XX XX o + 1 206 XXX XX XX en la configuración de ejemplo se eliminan.</span><span class="sxs-lookup"><span data-stu-id="2cf44-142">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="2cf44-143">Si el usuario tiene una licencia de plan de llamadas, la llamada se redirige automáticamente según las directivas del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cf44-143">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="2cf44-144">El plan de llamadas de Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de plan de llamadas de Microsoft y no requiere configuración de enrutamiento de llamadas adicional.</span><span class="sxs-lookup"><span data-stu-id="2cf44-144">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="2cf44-145">En el ejemplo que se muestra en el siguiente diagrama, se agrega una ruta de voz para enviar llamadas a todos los demás números canadienses y de Estados Unidos (llamadas que van al patrón de números llamado + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="2cf44-145">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Muestra la Directiva de enrutamiento de voz con una tercera ruta](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="2cf44-147">Para todas las demás llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="2cf44-147">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="2cf44-148">Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, la llamada se dirige a través del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cf44-148">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="2cf44-149">Si el usuario solo tiene Microsoft Phone System, la llamada se descarta porque no hay disponibles reglas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="2cf44-149">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2cf44-150">El valor de prioridad para la ruta "otros + 1" no importa en este caso porque hay una sola ruta que coincide con el patrón + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="2cf44-150">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="2cf44-151">Si un usuario llama a + 1 324 567 89 89 y tanto sbc5.contoso.biz como sbc6.contoso.biz no están disponibles, la llamada se cancela.</span><span class="sxs-lookup"><span data-stu-id="2cf44-151">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="2cf44-152">En la tabla siguiente se resume la configuración mediante tres rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="2cf44-152">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="2cf44-153">En este ejemplo, las tres rutas forman parte del mismo uso de la RTC, "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="2cf44-153">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="2cf44-154">Todas las rutas se asocian con el uso de RTC "Estados Unidos y Canadá" y el uso de RTC está asociado a la Directiva de enrutamiento de voz "solo para Estados Unidos".</span><span class="sxs-lookup"><span data-stu-id="2cf44-154">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="2cf44-155">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="2cf44-155">**PSTN usage**</span></span>|<span data-ttu-id="2cf44-156">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="2cf44-156">**Voice route**</span></span>|<span data-ttu-id="2cf44-157">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="2cf44-157">**Number pattern**</span></span>|<span data-ttu-id="2cf44-158">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="2cf44-158">**Priority**</span></span>|<span data-ttu-id="2cf44-159">**SBC**</span><span class="sxs-lookup"><span data-stu-id="2cf44-159">**SBC**</span></span>|<span data-ttu-id="2cf44-160">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2cf44-160">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2cf44-161">Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="2cf44-161">US and Canada</span></span>|<span data-ttu-id="2cf44-162">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="2cf44-162">"Redmond 1"</span></span>|<span data-ttu-id="2cf44-163">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="2cf44-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2cf44-164">1</span><span class="sxs-lookup"><span data-stu-id="2cf44-164">1</span></span>|<span data-ttu-id="2cf44-165">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-165">sbc1.contoso.biz</span></span><br/><span data-ttu-id="2cf44-166">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-166">sbc2.contoso.biz</span></span>|<span data-ttu-id="2cf44-167">Ruta activa para números llamados + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2cf44-167">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2cf44-168">Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="2cf44-168">US and Canada</span></span>|<span data-ttu-id="2cf44-169">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="2cf44-169">"Redmond 2"</span></span>|<span data-ttu-id="2cf44-170">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="2cf44-170">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2cf44-171">2</span><span class="sxs-lookup"><span data-stu-id="2cf44-171">2</span></span>|<span data-ttu-id="2cf44-172">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-172">sbc3.contoso.biz</span></span><br/><span data-ttu-id="2cf44-173">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-173">sbc4.contoso.biz</span></span>|<span data-ttu-id="2cf44-174">Ruta de copia de seguridad para los números + 1 425 XXX XX XX ó + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2cf44-174">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2cf44-175">Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="2cf44-175">US and Canada</span></span>|<span data-ttu-id="2cf44-176">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="2cf44-176">"Other +1"</span></span>|<span data-ttu-id="2cf44-177">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="2cf44-177">^\\+1(\d{10})$</span></span>|<span data-ttu-id="2cf44-178">3</span><span class="sxs-lookup"><span data-stu-id="2cf44-178">3</span></span>|<span data-ttu-id="2cf44-179">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-179">sbc5.contoso.biz</span></span><br/><span data-ttu-id="2cf44-180">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-180">sbc6.contoso.biz</span></span>|<span data-ttu-id="2cf44-181">Ruta de números llamados + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="2cf44-181">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="2cf44-182">Ejemplo 1: pasos de configuración</span><span class="sxs-lookup"><span data-stu-id="2cf44-182">Example 1: Configuration steps</span></span>

<span data-ttu-id="2cf44-183">En el ejemplo siguiente se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="2cf44-183">The following example shows how to:</span></span>

1. <span data-ttu-id="2cf44-184">Crear un único uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="2cf44-184">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="2cf44-185">Configurar tres rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="2cf44-185">Configure three voice routes.</span></span>
3. <span data-ttu-id="2cf44-186">Crear una directiva de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="2cf44-186">Create a voice routing policy.</span></span>
4. <span data-ttu-id="2cf44-187">Asigne la Directiva a un usuario denominado Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="2cf44-187">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="2cf44-188">Puede usar el [centro de administración de Microsoft Teams](#admincenterexample1) o [PowerShell](#powershellexample1) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2cf44-188">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2cf44-189">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2cf44-189">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="2cf44-190">Paso 1: crear el uso de la RTC "Estados Unidos y Canadá"</span><span class="sxs-lookup"><span data-stu-id="2cf44-190">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="2cf44-191">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a enrutamiento de **voz**  >  **directo** y, a continuación, en la esquina superior derecha, seleccione **administrar registros de uso de RTC**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-191">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="2cf44-192">Haga clic en **Agregar**, escriba **Estados Unidos y Canadá** y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-192">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="2cf44-193">Paso 2: crear tres rutas de voz (Redmond 1, Redmond 2 y otros + 1)</span><span class="sxs-lookup"><span data-stu-id="2cf44-193">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="2cf44-194">Los pasos siguientes describen cómo crear una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="2cf44-194">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="2cf44-195">Siga estos pasos para crear las tres rutas de voz llamada Redmond 1, Redmond 2 y otro + 1 para este ejemplo con la configuración descrita en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="2cf44-195">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="2cf44-196">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a enrutamiento de **voz**  >  **directo** y, a continuación, seleccione la pestaña **rutas de voz** .</span><span class="sxs-lookup"><span data-stu-id="2cf44-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="2cf44-197">Haga clic en **Agregar** y, a continuación, escriba un nombre y una descripción para la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="2cf44-197">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="2cf44-198">Establezca la prioridad y especifique el patrón de número marcado.</span><span class="sxs-lookup"><span data-stu-id="2cf44-198">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="2cf44-199">Para inscribir un SBC con la ruta de voz, en **SBCS inscrito (opcional)**, haga clic en **Agregar SBCS**, seleccione el SBCS que desea inscribir y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-199">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="2cf44-200">Para agregar registros de uso de RTC, en **registros de uso de RTC (opcional)**, haga clic en **Agregar uso de RTC**, seleccione los registros RTC que desea agregar y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-200">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="2cf44-201">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-201">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="2cf44-202">Paso 3: crear una directiva de enrutamiento de voz denominada "solo para EE. UU." y agregar el uso de RTC "Estados Unidos y Canadá" a la Directiva</span><span class="sxs-lookup"><span data-stu-id="2cf44-202">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="2cf44-203">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de enrutamiento de voz de **voz**  >  **Voice routing policies** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-203">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="2cf44-204">Escriba **solo** el nombre del contacto y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="2cf44-204">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="2cf44-205">En **registros de uso de RTC**, haga clic en **Agregar uso de RTC**, seleccione el registro de uso de RTC "Estados Unidos y Canadá" y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-205">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="2cf44-206">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-206">Click **Save**.</span></span>

<span data-ttu-id="2cf44-207">Para obtener más información, consulte [Administrar directivas de enrutamiento de voz](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2cf44-207">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="2cf44-208">Paso 4: asignar la Directiva de enrutamiento de voz a un usuario denominado Spencer Low</span><span class="sxs-lookup"><span data-stu-id="2cf44-208">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="2cf44-209">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="2cf44-209">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="2cf44-210">Haga clic en **directivas** y, junto a **directivas asignadas**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-210">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="2cf44-211">En **Directiva de enrutamiento de voz**, seleccione la Directiva "solo para Estados Unidos" y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-211">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="2cf44-212">Para obtener más información, consulte [Administrar directivas de enrutamiento de voz](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2cf44-212">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2cf44-213">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cf44-213">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="2cf44-214">Paso 1: crear el uso de la RTC "Estados Unidos y Canadá"</span><span class="sxs-lookup"><span data-stu-id="2cf44-214">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="2cf44-215">En una sesión de PowerShell remoto en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="2cf44-215">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="2cf44-216">Para comprobar que el uso se ha creado, escriba:</span><span class="sxs-lookup"><span data-stu-id="2cf44-216">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="2cf44-217">Que devuelve una lista de los nombres que se pueden truncar:</span><span class="sxs-lookup"><span data-stu-id="2cf44-217">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="2cf44-218">En el siguiente ejemplo se muestra el resultado de ejecutar el `(Get-CSOnlinePSTNUsage).usage` comando PowerShell para mostrar nombres completos (no truncado):</span><span class="sxs-lookup"><span data-stu-id="2cf44-218">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="2cf44-219">Paso 2: crear tres rutas de voz (Redmond 1, Redmond 2 y otros + 1)</span><span class="sxs-lookup"><span data-stu-id="2cf44-219">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="2cf44-220">Para crear la ruta de "Redmond 1", en una sesión de PowerShell en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="2cf44-220">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="2cf44-221">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="2cf44-221">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="2cf44-222">Para crear la ruta de Redmond 2, escriba:</span><span class="sxs-lookup"><span data-stu-id="2cf44-222">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="2cf44-223">Para crear la ruta otra + 1, escriba:</span><span class="sxs-lookup"><span data-stu-id="2cf44-223">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="2cf44-224">Asegúrese de que la expresión regular en el atributo NumberPattern es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="2cf44-224">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="2cf44-225">Puede probarla con este sitio web: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="2cf44-225">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="2cf44-226">En algunos casos, es necesario enrutar todas las llamadas a la misma SBC; Use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="2cf44-226">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="2cf44-227">Enrutar todas las llamadas al mismo SBC.</span><span class="sxs-lookup"><span data-stu-id="2cf44-227">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="2cf44-228">Compruebe que ha configurado correctamente la ruta ejecutando el `Get-CSOnlineVoiceRoute` comando PowerShell con las opciones que se muestran:</span><span class="sxs-lookup"><span data-stu-id="2cf44-228">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="2cf44-229">Que debería devolver:</span><span class="sxs-lookup"><span data-stu-id="2cf44-229">Which should return:</span></span>
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

<span data-ttu-id="2cf44-230">En el ejemplo, se asignó automáticamente la prioridad 4 a la ruta "otros + 1".</span><span class="sxs-lookup"><span data-stu-id="2cf44-230">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="2cf44-231">Paso 3: crear una directiva de enrutamiento de voz denominada "solo para EE. UU." y agregar el uso de RTC "Estados Unidos y Canadá" a la Directiva</span><span class="sxs-lookup"><span data-stu-id="2cf44-231">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="2cf44-232">En una sesión de PowerShell en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="2cf44-232">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="2cf44-233">El resultado se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2cf44-233">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="2cf44-234">Paso 4: asignar la Directiva de enrutamiento de voz a un usuario denominado Spencer Low</span><span class="sxs-lookup"><span data-stu-id="2cf44-234">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="2cf44-235">En una sesión de PowerShell en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="2cf44-235">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="2cf44-236">Valide la asignación de directiva escribiendo este comando:</span><span class="sxs-lookup"><span data-stu-id="2cf44-236">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="2cf44-237">El comando devuelve lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2cf44-237">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="2cf44-238">Ejemplo 2: enrutamiento de voz con varios usos de RTC</span><span class="sxs-lookup"><span data-stu-id="2cf44-238">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="2cf44-239">La Directiva de enrutamiento de voz creada en el ejemplo 1 solo permite llamadas a números de teléfono en Estados Unidos y Canadá, a menos que la licencia del plan de llamadas de Microsoft también esté asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="2cf44-239">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="2cf44-240">En el ejemplo siguiente, puede crear la Directiva de enrutamiento de voz "sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="2cf44-240">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="2cf44-241">La Directiva reutiliza el uso de RTC "Estados Unidos y Canadá" creado en el ejemplo 1, así como el nuevo uso de RTC "internacional".</span><span class="sxs-lookup"><span data-stu-id="2cf44-241">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="2cf44-242">Esta directiva dirige todas las demás llamadas a los sbc2.contoso.biz y sbc5.contoso.biz de SBCs.</span><span class="sxs-lookup"><span data-stu-id="2cf44-242">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="2cf44-243">Los ejemplos que se muestran asignan la Directiva solo de Estados Unidos a User Spencer Low y la Directiva sin restricciones para el usuario John Woods, de modo que el enrutamiento se produce de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2cf44-243">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="2cf44-244">Spencer solamente política de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="2cf44-244">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="2cf44-245">Las llamadas solo se permiten a números de Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="2cf44-245">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="2cf44-246">Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBCs.</span><span class="sxs-lookup"><span data-stu-id="2cf44-246">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="2cf44-247">Los números que no son de Estados Unidos no se enrutan a menos que la licencia del plan de llamadas se asigne al usuario.</span><span class="sxs-lookup"><span data-stu-id="2cf44-247">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="2cf44-248">John Woods: política internacional.</span><span class="sxs-lookup"><span data-stu-id="2cf44-248">John Woods – International policy.</span></span>  <span data-ttu-id="2cf44-249">Las llamadas pueden realizarse a cualquier número.</span><span class="sxs-lookup"><span data-stu-id="2cf44-249">Calls are allowed to any number.</span></span> <span data-ttu-id="2cf44-250">Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBCs.</span><span class="sxs-lookup"><span data-stu-id="2cf44-250">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="2cf44-251">Los números que no sean de Estados Unidos se enrutarán mediante sbc2.contoso.biz y sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2cf44-251">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Muestra la Directiva de enrutamiento de voz asignada al usuario Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="2cf44-253">Para todas las demás llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="2cf44-253">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="2cf44-254">Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, la llamada se redirige a través del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cf44-254">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="2cf44-255">Si el usuario solo tiene Microsoft Phone System, la llamada se elimina porque no hay disponibles reglas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="2cf44-255">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Muestra la Directiva de enrutamiento de voz asignada al usuario John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="2cf44-257">En la siguiente tabla se resumen las denominaciones de uso y las rutas de voz de directivas de enrutamiento "sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="2cf44-257">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="2cf44-258">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="2cf44-258">**PSTN usage**</span></span>|<span data-ttu-id="2cf44-259">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="2cf44-259">**Voice route**</span></span>|<span data-ttu-id="2cf44-260">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="2cf44-260">**Number pattern**</span></span>|<span data-ttu-id="2cf44-261">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="2cf44-261">**Priority**</span></span>|<span data-ttu-id="2cf44-262">**SBC**</span><span class="sxs-lookup"><span data-stu-id="2cf44-262">**SBC**</span></span>|<span data-ttu-id="2cf44-263">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2cf44-263">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2cf44-264">Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="2cf44-264">US and Canada</span></span>|<span data-ttu-id="2cf44-265">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="2cf44-265">"Redmond 1"</span></span>|<span data-ttu-id="2cf44-266">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="2cf44-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2cf44-267">1</span><span class="sxs-lookup"><span data-stu-id="2cf44-267">1</span></span>|<span data-ttu-id="2cf44-268">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-268">sbc1.contoso.biz</span></span><br/><span data-ttu-id="2cf44-269">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-269">sbc2.contoso.biz</span></span>|<span data-ttu-id="2cf44-270">Ruta activa para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2cf44-270">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2cf44-271">Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="2cf44-271">US and Canada</span></span>|<span data-ttu-id="2cf44-272">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="2cf44-272">"Redmond 2"</span></span>|<span data-ttu-id="2cf44-273">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="2cf44-273">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2cf44-274">2</span><span class="sxs-lookup"><span data-stu-id="2cf44-274">2</span></span>|<span data-ttu-id="2cf44-275">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-275">sbc3.contoso.biz</span></span><br/><span data-ttu-id="2cf44-276">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-276">sbc4.contoso.biz</span></span>|<span data-ttu-id="2cf44-277">Ruta de reserva para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2cf44-277">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2cf44-278">Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="2cf44-278">US and Canada</span></span>|<span data-ttu-id="2cf44-279">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="2cf44-279">"Other +1"</span></span>|<span data-ttu-id="2cf44-280">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="2cf44-280">^\\+1(\d{10})$</span></span>|<span data-ttu-id="2cf44-281">3</span><span class="sxs-lookup"><span data-stu-id="2cf44-281">3</span></span>|<span data-ttu-id="2cf44-282">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-282">sbc5.contoso.biz</span></span><br/><span data-ttu-id="2cf44-283">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-283">sbc6.contoso.biz</span></span>|<span data-ttu-id="2cf44-284">Ruta para números de la llamada + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="2cf44-284">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="2cf44-285">International</span><span class="sxs-lookup"><span data-stu-id="2cf44-285">International</span></span>|<span data-ttu-id="2cf44-286">International</span><span class="sxs-lookup"><span data-stu-id="2cf44-286">International</span></span>|<span data-ttu-id="2cf44-287">\d +</span><span class="sxs-lookup"><span data-stu-id="2cf44-287">\d+</span></span>|<span data-ttu-id="2cf44-288">4</span><span class="sxs-lookup"><span data-stu-id="2cf44-288">4</span></span>|<span data-ttu-id="2cf44-289">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-289">sbc2.contoso.biz</span></span><br/><span data-ttu-id="2cf44-290">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cf44-290">sbc5.contoso.biz</span></span>|<span data-ttu-id="2cf44-291">Ruta para cualquier patrón de números</span><span class="sxs-lookup"><span data-stu-id="2cf44-291">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="2cf44-292">El orden de los usos de RTC en las directivas de enrutamiento de voz es fundamental.</span><span class="sxs-lookup"><span data-stu-id="2cf44-292">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="2cf44-293">Los usos se aplican en orden y, si se encuentra una coincidencia en el primer uso, no se evalúan otros usos.</span><span class="sxs-lookup"><span data-stu-id="2cf44-293">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="2cf44-294">El uso de RTC "internacional" debe colocarse después del uso de RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="2cf44-294">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="2cf44-295">Para cambiar el orden de los usos de RTC, ejecute el `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="2cf44-295">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="2cf44-296">Por ejemplo, para cambiar el orden de "Estados Unidos y Canadá" primero por "internacional" y el segundo al orden invertido:</span><span class="sxs-lookup"><span data-stu-id="2cf44-296">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="2cf44-297">La prioridad de las rutas de voz "otras + 1" y "internacionales" se asigna automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2cf44-297">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="2cf44-298">No importa siempre que tengan prioridades más bajas que "Redmond 1" y "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="2cf44-298">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="2cf44-299">Ejemplo 2: pasos de configuración</span><span class="sxs-lookup"><span data-stu-id="2cf44-299">Example 2: Configuration steps</span></span>

<span data-ttu-id="2cf44-300">En el ejemplo siguiente se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="2cf44-300">The following example shows how to:</span></span>

1. <span data-ttu-id="2cf44-301">Cree un nuevo uso de RTC denominado internacional.</span><span class="sxs-lookup"><span data-stu-id="2cf44-301">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="2cf44-302">Cree una nueva ruta de voz denominada internacional.</span><span class="sxs-lookup"><span data-stu-id="2cf44-302">Create a new voice route called International.</span></span>
3. <span data-ttu-id="2cf44-303">Crear una directiva de enrutamiento de voz llamada sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="2cf44-303">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="2cf44-304">Asigne la Directiva al usuario John Woods.</span><span class="sxs-lookup"><span data-stu-id="2cf44-304">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="2cf44-305">Puede usar el [centro de administración de Microsoft Teams](#admincenterexample2) o [PowerShell](#powershellexample2) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2cf44-305">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2cf44-306">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2cf44-306">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="2cf44-307">Paso 1: crear el uso de RTC "internacional"</span><span class="sxs-lookup"><span data-stu-id="2cf44-307">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="2cf44-308">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a enrutamiento de **voz**  >  **directo** y, a continuación, en la esquina superior derecha, seleccione **administrar registros de uso de RTC**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-308">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="2cf44-309">Haga clic en **Agregar**, escriba **internacional** y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-309">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="2cf44-310">Paso 2: crear la ruta de voz "internacional"</span><span class="sxs-lookup"><span data-stu-id="2cf44-310">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="2cf44-311">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a enrutamiento de **voz**  >  **directo** y, a continuación, seleccione la pestaña **rutas de voz** .</span><span class="sxs-lookup"><span data-stu-id="2cf44-311">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="2cf44-312">Haga clic en **Agregar**, escriba "internacional" como nombre y, a continuación, agregue la descripción.</span><span class="sxs-lookup"><span data-stu-id="2cf44-312">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="2cf44-313">Establezca la prioridad en 4 y, a continuación, establezca el patrón de número marcado como \d +.</span><span class="sxs-lookup"><span data-stu-id="2cf44-313">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="2cf44-314">En **SBCS inscrito (opcional)**, haga clic en **Agregar SBCs**, seleccione sbc2.contoso.BIZ y sbc5.contoso.BIZ y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-314">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="2cf44-315">En **registros de uso de RTC (opcional)**, haga clic en **Agregar uso de RTC**, seleccione el registro de uso de RTC "internacional" y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-315">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="2cf44-316">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-316">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="2cf44-317">Paso 3: crear una directiva de enrutamiento de voz denominada "sin restricciones" y agregar los usos de "Estados Unidos y Canadá" y "internacional" a la Directiva</span><span class="sxs-lookup"><span data-stu-id="2cf44-317">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="2cf44-318">El uso de la RTC "Estados Unidos y Canadá" se reutiliza en esta directiva de enrutamiento de voz para mantener el control especial de las llamadas al número "+ 1 425 XXX XX XX" y "+ 1 206 XXX XX XX" como llamadas locales o locales.</span><span class="sxs-lookup"><span data-stu-id="2cf44-318">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="2cf44-319">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de enrutamiento de voz de **voz**  >  **Voice routing policies** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-319">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="2cf44-320">Escriba **ninguna restricción** como nombre y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="2cf44-320">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="2cf44-321">En **registros de uso de RTC**, haga clic en **Agregar uso de RTC**, seleccione el registro de uso de RTC "Estados Unidos y Canadá" y, a continuación, seleccione el registro de uso de RTC "internacional".</span><span class="sxs-lookup"><span data-stu-id="2cf44-321">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="2cf44-322">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-322">Click **Apply**.</span></span>

    <span data-ttu-id="2cf44-323">Tome nota del orden de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="2cf44-323">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="2cf44-324">Si una llamada se realiza en el número "+ 1 425 XXX XX XX" con los usos configurados, como en este ejemplo, la llamada sigue la ruta establecida en el uso de "Estados Unidos y Canadá" y se aplica la lógica de enrutamiento especial.</span><span class="sxs-lookup"><span data-stu-id="2cf44-324">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="2cf44-325">Es decir, la llamada se enruta usando sbc1.contoso.biz y sbc2.contoso.biz en primer lugar y, a continuación, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2cf44-325">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="2cf44-326">Si el uso de RTC "internacional" es anterior a "Estados Unidos y Canadá", las llamadas a + 1 425 XXX XX XX se enrutan a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="2cf44-326">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="2cf44-327">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-327">Click **Save**.</span></span>

<span data-ttu-id="2cf44-328">Para obtener más información, consulte [Administrar directivas de enrutamiento de voz](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2cf44-328">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="2cf44-329">Paso 4: asignar la Directiva de enrutamiento de voz a un usuario denominado John Woods</span><span class="sxs-lookup"><span data-stu-id="2cf44-329">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="2cf44-330">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="2cf44-330">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="2cf44-331">Haga clic en **directivas** y, junto a **directivas asignadas**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-331">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="2cf44-332">En **Directiva de enrutamiento de voz**, seleccione la Directiva "sin restricciones" y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2cf44-332">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="2cf44-333">El resultado es que la política de voz aplicada a las llamadas de John Woods no tiene restricciones y seguirá la lógica del enrutamiento de llamadas disponible para las llamadas de Estados Unidos, Canadá e internacionales.</span><span class="sxs-lookup"><span data-stu-id="2cf44-333">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2cf44-334">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cf44-334">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="2cf44-335">Paso 1: crear el uso de RTC "internacional"</span><span class="sxs-lookup"><span data-stu-id="2cf44-335">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="2cf44-336">En una sesión de PowerShell remoto en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="2cf44-336">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="2cf44-337">Paso 2: crear una nueva ruta de voz denominada "internacional"</span><span class="sxs-lookup"><span data-stu-id="2cf44-337">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="2cf44-338">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="2cf44-338">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="2cf44-339">Paso 3: crear una directiva de enrutamiento de voz denominada "sin restricciones"</span><span class="sxs-lookup"><span data-stu-id="2cf44-339">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="2cf44-340">El uso de RTC "Redmond 1" y "Redmond" se reutiliza en esta directiva de enrutamiento de voz para mantener un control especial de las llamadas al número "+ 1 425 XXX XX XX" y "+ 1 206 XXX XX XX" como llamadas locales o locales.</span><span class="sxs-lookup"><span data-stu-id="2cf44-340">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="2cf44-341">Tome nota del orden de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="2cf44-341">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="2cf44-342">Si una llamada se realiza en el número "+ 1 425 XXX XX XX" con los usos configurados como en el ejemplo siguiente, la llamada sigue el conjunto de rutas en "Estados Unidos y Canadá" y se aplica la lógica de enrutamiento especial.</span><span class="sxs-lookup"><span data-stu-id="2cf44-342">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="2cf44-343">Es decir, la llamada se enruta usando sbc1.contoso.biz y sbc2.contoso.biz en primer lugar y, a continuación, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2cf44-343">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="2cf44-344">Si el uso de RTC "internacional" es anterior a "Estados Unidos y Canadá", las llamadas a + 1 425 XXX XX XX se enrutan a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="2cf44-344">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="2cf44-345">Escribe el comando:</span><span class="sxs-lookup"><span data-stu-id="2cf44-345">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="2cf44-346">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="2cf44-346">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="2cf44-347">Paso 4: asignar la Directiva de enrutamiento de voz al usuario denominado John Woods</span><span class="sxs-lookup"><span data-stu-id="2cf44-347">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="2cf44-348">A continuación, verifique la asignación con el comando:</span><span class="sxs-lookup"><span data-stu-id="2cf44-348">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="2cf44-349">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="2cf44-349">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="2cf44-350">El resultado es que la política de voz aplicada a las llamadas de John Woods no tiene restricciones, y seguirá la lógica de enrutamiento de llamadas disponible para las llamadas de Estados Unidos, Canadá e internacionales.</span><span class="sxs-lookup"><span data-stu-id="2cf44-350">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="2cf44-351">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2cf44-351">See also</span></span>

[<span data-ttu-id="2cf44-352">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="2cf44-352">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="2cf44-353">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="2cf44-353">Configure Direct Routing</span></span>](direct-routing-configure.md)
