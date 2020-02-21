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
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42158022"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="a5647-103">Configurar el enrutamiento de voz para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="a5647-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="a5647-104">En este artículo se describe cómo configurar el enrutamiento de voz para el enrutamiento directo de un sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="a5647-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="a5647-105">Este es el paso 3 de los pasos siguientes para configurar el enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="a5647-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="a5647-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="a5647-106">Step 1.</span></span> [<span data-ttu-id="a5647-107">Conectar el SBC con Microsoft Phone System y validar la conexión</span><span class="sxs-lookup"><span data-stu-id="a5647-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="a5647-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="a5647-108">Step 2.</span></span> [<span data-ttu-id="a5647-109">Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz</span><span class="sxs-lookup"><span data-stu-id="a5647-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)    
- <span data-ttu-id="a5647-110">**Paso 3. Configurar el enrutamiento de voz** (este artículo)</span><span class="sxs-lookup"><span data-stu-id="a5647-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="a5647-111">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="a5647-111">Step 4.</span></span> [<span data-ttu-id="a5647-112">Traducir números a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="a5647-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="a5647-113">Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, consulte [configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="a5647-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="a5647-114">Introducción al enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="a5647-114">Voice routing overview</span></span>

<span data-ttu-id="a5647-115">Microsoft Phone System tiene un mecanismo de enrutamiento que permite que se envíe una llamada a un controlador de borde de sesión (SBC) específico en función de:</span><span class="sxs-lookup"><span data-stu-id="a5647-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="a5647-116">El patrón de número al que se llama</span><span class="sxs-lookup"><span data-stu-id="a5647-116">The called number pattern</span></span> 
- <span data-ttu-id="a5647-117">El patrón de número al que se llama y el usuario específico que realiza la llamada</span><span class="sxs-lookup"><span data-stu-id="a5647-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="a5647-118">SBCs puede designarse como activo y como backup.</span><span class="sxs-lookup"><span data-stu-id="a5647-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="a5647-119">Cuando el SBC configurado como activo no está disponible para una ruta de llamada específica, la llamada se redirigirá a un SBC de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a5647-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="a5647-120">El enrutamiento de voz consta de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="a5647-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="a5647-121">**Directiva de enrutamiento de voz** : contenedor de uso de RTC, que se puede asignar a un usuario o a varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="a5647-121">**Voice routing policy** – A container for PSTN Usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="a5647-122">**Usos de RTC** : un contenedor de rutas de voz y usos de RTC, que se pueden compartir en diferentes directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="a5647-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="a5647-123">**Rutas de voz** : un patrón de número y un conjunto de puertas de enlace RTC en línea para usarlas en las llamadas en las que el número de llamada coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="a5647-123">**Voice Routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="a5647-124">**Puerta de enlace RTC en línea** : puntero a un SBC que también almacena la configuración que se aplica cuando una llamada se coloca a través de SBC, como la identidad de aserción de P (PAI) o los códecs preferidos. se puede Agregar a las rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="a5647-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="a5647-125">Ejemplo 1: enrutamiento de voz con un uso de RTC</span><span class="sxs-lookup"><span data-stu-id="a5647-125">Example 1: Voice routing with one PSTN Usage</span></span>

<span data-ttu-id="a5647-126">En el siguiente diagrama se muestran dos ejemplos de directivas de enrutamiento de voz en un flujo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a5647-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="a5647-127">**Flujo de llamadas 1 (a la izquierda):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se dirige a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="a5647-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="a5647-128">Si ni sbc1.contoso.biz ni sbc2.contoso.biz están disponibles, la llamada se interrumpe.</span><span class="sxs-lookup"><span data-stu-id="a5647-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="a5647-129">**Flujo de llamadas 2 (a la derecha):** Si un usuario hace una llamada a + 1 425 XXX XX XX ó + 1 206 XXX XX XX, la llamada se enruta primero a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="a5647-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="a5647-130">Si no hay ninguna SBC disponible, se intentará la ruta con prioridad más baja (sbc3.contoso.biz y sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="a5647-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="a5647-131">Si ninguno de los SBCs está disponible, la llamada se corta.</span><span class="sxs-lookup"><span data-stu-id="a5647-131">If none of the SBCs are available, the call is dropped.</span></span> 

![Muestra ejemplos de directiva de enrutamiento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="a5647-133">En ambos ejemplos, mientras se asignan prioridades a la ruta de voz, se prueba el SBCs en las rutas en orden aleatorio.</span><span class="sxs-lookup"><span data-stu-id="a5647-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a5647-134">A menos que el usuario también tenga una licencia de plan de llamadas de Microsoft, las llamadas a cualquier número excepto los números que coincidan con los patrones + 1 425 XXX XX XX o + 1 206 XXX XX XX en la configuración de ejemplo se eliminan.</span><span class="sxs-lookup"><span data-stu-id="a5647-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="a5647-135">Si el usuario tiene una licencia de plan de llamadas, la llamada se redirige automáticamente según las directivas del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a5647-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="a5647-136">El plan de llamadas de Microsoft se aplica automáticamente como la última ruta a todos los usuarios con la licencia de plan de llamadas de Microsoft y no requiere configuración de enrutamiento de llamadas adicional.</span><span class="sxs-lookup"><span data-stu-id="a5647-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="a5647-137">En el ejemplo que se muestra en el siguiente diagrama, se agrega una ruta de voz para enviar llamadas a todos los demás números canadienses y de Estados Unidos (llamadas que van al patrón de números llamado + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="a5647-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Muestra la Directiva de enrutamiento de voz con una tercera ruta](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="a5647-139">Para todas las demás llamadas:</span><span class="sxs-lookup"><span data-stu-id="a5647-139">For all other calls:</span></span>

- <span data-ttu-id="a5647-140">Si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="a5647-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="a5647-141">Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, la llamada se dirige a través del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a5647-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="a5647-142">Si el usuario solo tiene Microsoft Phone System, la llamada se descarta porque no hay disponibles reglas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="a5647-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a5647-143">El valor de prioridad para la ruta "otros + 1" no importa en este caso porque hay una sola ruta que coincide con el patrón + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="a5647-143">The Priority value for route "Other +1" doesn’t matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="a5647-144">Si un usuario llama a + 1 324 567 89 89 y tanto sbc5.contoso.biz como sbc6.contoso.biz no están disponibles, la llamada se cancela.</span><span class="sxs-lookup"><span data-stu-id="a5647-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="a5647-145">En la tabla siguiente se resume la configuración mediante tres rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="a5647-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="a5647-146">En este ejemplo, las tres rutas forman parte del mismo uso de la RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="a5647-146">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>  <span data-ttu-id="a5647-147">Todas las rutas se asocian con el uso de la RTC "Estados Unidos y Canadá" y el uso de RTC está asociado a la Directiva de enrutamiento de voz "solo para EE. UU.".</span><span class="sxs-lookup"><span data-stu-id="a5647-147">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> 

|<span data-ttu-id="a5647-148">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="a5647-148">**PSTN usage**</span></span>|<span data-ttu-id="a5647-149">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="a5647-149">**Voice route**</span></span>|<span data-ttu-id="a5647-150">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="a5647-150">**Number pattern**</span></span>|<span data-ttu-id="a5647-151">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="a5647-151">**Priority**</span></span>|<span data-ttu-id="a5647-152">**SBC**</span><span class="sxs-lookup"><span data-stu-id="a5647-152">**SBC**</span></span>|<span data-ttu-id="a5647-153">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a5647-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5647-154">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="a5647-154">US only</span></span>|<span data-ttu-id="a5647-155">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="a5647-155">"Redmond 1"</span></span>|<span data-ttu-id="a5647-156">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="a5647-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a5647-157">1</span><span class="sxs-lookup"><span data-stu-id="a5647-157">1</span></span>|<span data-ttu-id="a5647-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="a5647-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="a5647-160">Ruta activa para números llamados + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a5647-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a5647-161">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="a5647-161">US only</span></span>|<span data-ttu-id="a5647-162">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="a5647-162">"Redmond 2"</span></span>|<span data-ttu-id="a5647-163">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="a5647-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a5647-164">2</span><span class="sxs-lookup"><span data-stu-id="a5647-164">2</span></span>|<span data-ttu-id="a5647-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="a5647-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="a5647-167">Ruta de copia de seguridad para los números + 1 425 XXX XX XX ó + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a5647-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a5647-168">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="a5647-168">US only</span></span>|<span data-ttu-id="a5647-169">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="a5647-169">"Other +1"</span></span>|<span data-ttu-id="a5647-170">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="a5647-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="a5647-171">3</span><span class="sxs-lookup"><span data-stu-id="a5647-171">3</span></span>|<span data-ttu-id="a5647-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="a5647-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="a5647-174">Ruta de números llamados + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="a5647-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||


### <a name="example-1-configuration-steps"></a><span data-ttu-id="a5647-175">Ejemplo 1: pasos de configuración</span><span class="sxs-lookup"><span data-stu-id="a5647-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="a5647-176">En el ejemplo siguiente se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="a5647-176">The following example shows how to:</span></span>

- <span data-ttu-id="a5647-177">Crear un único uso de RTC</span><span class="sxs-lookup"><span data-stu-id="a5647-177">Create a single PSTN Usage</span></span> 
- <span data-ttu-id="a5647-178">Configurar tres rutas de voz</span><span class="sxs-lookup"><span data-stu-id="a5647-178">Configure three voice routes</span></span>
- <span data-ttu-id="a5647-179">Crear una directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="a5647-179">Create a voice routing policy</span></span>
- <span data-ttu-id="a5647-180">Asignar la política a User Spencer Low</span><span class="sxs-lookup"><span data-stu-id="a5647-180">Assign the policy to user Spencer Low</span></span>

<span data-ttu-id="a5647-181">**Paso 1:** Crear el uso de RTC "Estados Unidos y Canadá"</span><span class="sxs-lookup"><span data-stu-id="a5647-181">**Step 1:** Create the PSTN Usage "US and Canada"</span></span>

<span data-ttu-id="a5647-182">En una sesión de PowerShell remoto de Skype empresarial, escriba:</span><span class="sxs-lookup"><span data-stu-id="a5647-182">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="a5647-183">Valide que el uso se haya creado especificando:</span><span class="sxs-lookup"><span data-stu-id="a5647-183">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="a5647-184">Que devuelve una lista de los nombres que se pueden truncar:</span><span class="sxs-lookup"><span data-stu-id="a5647-184">Which returns a list of names that may be truncated:</span></span>
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="a5647-185">En el ejemplo siguiente se muestra el resultado de ejecutar el `(Get-CSOnlinePSTNUsage).usage` comando PowerShell para mostrar nombres completos (no truncado):</span><span class="sxs-lookup"><span data-stu-id="a5647-185">The example below shows the result of  running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated):</span></span>

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

<span data-ttu-id="a5647-186">**Paso 2:** En una sesión de PowerShell de Skype empresarial online, cree tres rutas: Redmond 1, Redmond 2 y otros + 1, tal y como se muestra en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="a5647-186">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as shown in the previous table</span></span>

<span data-ttu-id="a5647-187">Para crear la ruta de "Redmond 1", escriba:</span><span class="sxs-lookup"><span data-stu-id="a5647-187">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a5647-188">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="a5647-188">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="a5647-189">Para crear la ruta de Redmond 2, escriba:</span><span class="sxs-lookup"><span data-stu-id="a5647-189">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a5647-190">Para crear la ruta otra + 1, escriba:</span><span class="sxs-lookup"><span data-stu-id="a5647-190">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="a5647-191">Asegúrese de que la expresión regular en el atributo NumberPattern es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="a5647-191">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="a5647-192">Puede probarla con este sitio web:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="a5647-192">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="a5647-193">En algunos casos, es necesario enrutar todas las llamadas a la misma SBC; Use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="a5647-193">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="a5647-194">Enrutar todas las llamadas al mismo SBC.</span><span class="sxs-lookup"><span data-stu-id="a5647-194">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="a5647-195">Confirme que ha configurado correctamente la ruta ejecutando el `Get-CSOnlineVoiceRoute` comando PowerShell con las opciones que se muestran:</span><span class="sxs-lookup"><span data-stu-id="a5647-195">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="a5647-196">Que debería devolver:</span><span class="sxs-lookup"><span data-stu-id="a5647-196">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="a5647-197">En el ejemplo, se asignó automáticamente la prioridad 4 a la ruta "otros + 1".</span><span class="sxs-lookup"><span data-stu-id="a5647-197">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="a5647-198">**Paso 3:** Crear una directiva de enrutamiento de voz "solo para EE. UU." y agregar a la directiva el uso de la RTC "Estados Unidos y Canadá".</span><span class="sxs-lookup"><span data-stu-id="a5647-198">**Step 3:** Create a voice routing policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="a5647-199">En una sesión de PowerShell en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="a5647-199">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a5647-200">El resultado se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a5647-200">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="a5647-201">**Paso 4:** Con PowerShell, conceda la Directiva de enrutamiento de voz al usuario Spencer Low:</span><span class="sxs-lookup"><span data-stu-id="a5647-201">**Step 4:** By using PowerShell, grant the voice routing policy to the user Spencer Low:</span></span>

<span data-ttu-id="a5647-202">En una sesión de PowerShell en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="a5647-202">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="a5647-203">Valide la asignación de directiva escribiendo este comando:</span><span class="sxs-lookup"><span data-stu-id="a5647-203">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="a5647-204">El comando devuelve lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5647-204">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="a5647-205">Ejemplo 2: enrutamiento de voz con varios usos de RTC</span><span class="sxs-lookup"><span data-stu-id="a5647-205">Example 2: Voice routing with multiple PSTN Usages</span></span>

<span data-ttu-id="a5647-206">La Directiva de enrutamiento de voz creada en el ejemplo 1 solo permite llamadas a números de teléfono en Estados Unidos y Canadá, a menos que la licencia del plan de llamadas de Microsoft también esté asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="a5647-206">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="a5647-207">En el ejemplo siguiente, puede crear la Directiva de enrutamiento de voz "sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="a5647-207">In the example that follows, you can create the voice routing policy "No Restrictions."</span></span> <span data-ttu-id="a5647-208">La Directiva reutiliza el uso de la RTC "Estados Unidos y Canadá" creado en el ejemplo 1, así como el nuevo uso de RTC "internacional".</span><span class="sxs-lookup"><span data-stu-id="a5647-208">The policy reuses the PSTN Usage "US and Canada" created in Example 1, as well as the new PSTN Usage "International."</span></span>  <span data-ttu-id="a5647-209">Esta directiva dirige todas las demás llamadas a los sbc2.contoso.biz y sbc5.contoso.biz de SBCs.</span><span class="sxs-lookup"><span data-stu-id="a5647-209">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> 

<span data-ttu-id="a5647-210">Los ejemplos que se muestran asignan la Directiva solo de Estados Unidos a User Spencer Low y la Directiva sin restricciones para el usuario John Woods, de modo que el enrutamiento se produce de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a5647-210">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="a5647-211">Spencer solamente política de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="a5647-211">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="a5647-212">Las llamadas solo se permiten a números de Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="a5647-212">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="a5647-213">Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBCs.</span><span class="sxs-lookup"><span data-stu-id="a5647-213">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="a5647-214">Los números que no son de Estados Unidos no se enrutan a menos que la licencia del plan de llamadas se asigne al usuario.</span><span class="sxs-lookup"><span data-stu-id="a5647-214">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="a5647-215">John Woods: política internacional.</span><span class="sxs-lookup"><span data-stu-id="a5647-215">John Woods – International policy.</span></span>  <span data-ttu-id="a5647-216">Las llamadas pueden realizarse a cualquier número.</span><span class="sxs-lookup"><span data-stu-id="a5647-216">Calls are allowed to any number.</span></span> <span data-ttu-id="a5647-217">Al llamar al intervalo de números de Redmond, debe usarse el conjunto específico de SBCs.</span><span class="sxs-lookup"><span data-stu-id="a5647-217">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="a5647-218">Los números que no sean de Estados Unidos se enrutarán mediante sbc2.contoso.biz y sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="a5647-218">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Muestra la Directiva de enrutamiento de voz asignada al usuario Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="a5647-220">Para todas las demás llamadas, si un usuario tiene ambas licencias (Microsoft Phone System y Microsoft Call plan), se usa la ruta automática.</span><span class="sxs-lookup"><span data-stu-id="a5647-220">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="a5647-221">Si nada coincide con los patrones de número de las rutas de voz en línea creadas por el administrador, la llamada se redirige a través del plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a5647-221">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="a5647-222">Si el usuario solo tiene Microsoft Phone System, la llamada se elimina porque no hay disponibles reglas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="a5647-222">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Muestra la Directiva de enrutamiento de voz asignada al usuario John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="a5647-224">En la siguiente tabla se resumen las denominaciones de uso y las rutas de voz de directivas de enrutamiento "sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="a5647-224">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="a5647-225">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="a5647-225">**PSTN usage**</span></span>|<span data-ttu-id="a5647-226">**Ruta de voz**</span><span class="sxs-lookup"><span data-stu-id="a5647-226">**Voice route**</span></span>|<span data-ttu-id="a5647-227">**Patrón de números**</span><span class="sxs-lookup"><span data-stu-id="a5647-227">**Number pattern**</span></span>|<span data-ttu-id="a5647-228">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="a5647-228">**Priority**</span></span>|<span data-ttu-id="a5647-229">**SBC**</span><span class="sxs-lookup"><span data-stu-id="a5647-229">**SBC**</span></span>|<span data-ttu-id="a5647-230">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a5647-230">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5647-231">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="a5647-231">US Only</span></span>|<span data-ttu-id="a5647-232">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="a5647-232">"Redmond 1"</span></span>|<span data-ttu-id="a5647-233">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="a5647-233">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a5647-234">1</span><span class="sxs-lookup"><span data-stu-id="a5647-234">1</span></span>|<span data-ttu-id="a5647-235">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-235">sbc1.contoso.biz</span></span><br/><span data-ttu-id="a5647-236">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-236">sbc2.contoso.biz</span></span>|<span data-ttu-id="a5647-237">Ruta activa para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a5647-237">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a5647-238">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="a5647-238">US Only</span></span>|<span data-ttu-id="a5647-239">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="a5647-239">"Redmond 2"</span></span>|<span data-ttu-id="a5647-240">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="a5647-240">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a5647-241">2</span><span class="sxs-lookup"><span data-stu-id="a5647-241">2</span></span>|<span data-ttu-id="a5647-242">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-242">sbc3.contoso.biz</span></span><br/><span data-ttu-id="a5647-243">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-243">sbc4.contoso.biz</span></span>|<span data-ttu-id="a5647-244">Ruta de reserva para números de destinatarios + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a5647-244">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a5647-245">Solo para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="a5647-245">US Only</span></span>|<span data-ttu-id="a5647-246">"Otros + 1"</span><span class="sxs-lookup"><span data-stu-id="a5647-246">"Other +1"</span></span>|<span data-ttu-id="a5647-247">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="a5647-247">^\\+1(\d{10})$</span></span>|<span data-ttu-id="a5647-248">3</span><span class="sxs-lookup"><span data-stu-id="a5647-248">3</span></span>|<span data-ttu-id="a5647-249">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-249">sbc5.contoso.biz</span></span><br/><span data-ttu-id="a5647-250">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-250">sbc6>.contoso.biz</span></span>|<span data-ttu-id="a5647-251">Ruta para números de la llamada + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="a5647-251">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="a5647-252">International</span><span class="sxs-lookup"><span data-stu-id="a5647-252">International</span></span>|<span data-ttu-id="a5647-253">International</span><span class="sxs-lookup"><span data-stu-id="a5647-253">International</span></span>|<span data-ttu-id="a5647-254">\d +</span><span class="sxs-lookup"><span data-stu-id="a5647-254">\d+</span></span>|<span data-ttu-id="a5647-255">4</span><span class="sxs-lookup"><span data-stu-id="a5647-255">4</span></span>|<span data-ttu-id="a5647-256">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-256">sbc2.contoso.biz</span></span><br/><span data-ttu-id="a5647-257">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a5647-257">sbc5.contoso.biz</span></span>|<span data-ttu-id="a5647-258">Ruta para cualquier patrón de números</span><span class="sxs-lookup"><span data-stu-id="a5647-258">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="a5647-259">El orden de los usos de RTC en las directivas de enrutamiento de voz es fundamental.</span><span class="sxs-lookup"><span data-stu-id="a5647-259">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="a5647-260">Los usos se aplican en orden y, si se encuentra una coincidencia en el primer uso, no se evalúan otros usos.</span><span class="sxs-lookup"><span data-stu-id="a5647-260">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="a5647-261">El uso de RTC "internacional" debe situarse después del uso de RTC "solo para EE. UU.".</span><span class="sxs-lookup"><span data-stu-id="a5647-261">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="a5647-262">Para cambiar el orden de los usos de RTC, ejecute el `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="a5647-262">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="a5647-263">Por ejemplo, para cambiar el orden de "Estados Unidos y Canadá" primero por "internacional" y el segundo al orden invertido:</span><span class="sxs-lookup"><span data-stu-id="a5647-263">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="a5647-264">La prioridad de las rutas de voz "otras + 1" y "internacionales" se asigna automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a5647-264">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="a5647-265">No importa siempre que tengan prioridades más bajas que "Redmond 1" y "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="a5647-265">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>


### <a name="example-2-configuration-steps"></a><span data-ttu-id="a5647-266">Ejemplo 2: pasos de configuración</span><span class="sxs-lookup"><span data-stu-id="a5647-266">Example 2: Configuration steps</span></span>

<span data-ttu-id="a5647-267">En el ejemplo siguiente se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="a5647-267">The following example shows how to:</span></span>

- <span data-ttu-id="a5647-268">Crear un nuevo uso de RTC denominado internacional</span><span class="sxs-lookup"><span data-stu-id="a5647-268">Create a new PSTN Usage called International</span></span>
- <span data-ttu-id="a5647-269">Crear una nueva ruta de voz denominada internacional</span><span class="sxs-lookup"><span data-stu-id="a5647-269">Create a new voice route called International</span></span>
- <span data-ttu-id="a5647-270">Crear una directiva de enrutamiento de voz llamada sin restricciones</span><span class="sxs-lookup"><span data-stu-id="a5647-270">Create a voice routing policy called No Restrictions</span></span>
- <span data-ttu-id="a5647-271">Asignar la Directiva al usuario John Woods</span><span class="sxs-lookup"><span data-stu-id="a5647-271">Assign the policy to user John Woods</span></span>


<span data-ttu-id="a5647-272">**Paso 1**: crear el uso de RTC "internacional".</span><span class="sxs-lookup"><span data-stu-id="a5647-272">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="a5647-273">En una sesión de PowerShell remoto en Skype empresarial online, escriba:</span><span class="sxs-lookup"><span data-stu-id="a5647-273">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="a5647-274">**Paso 2**: crear la nueva ruta de voz "internacional".</span><span class="sxs-lookup"><span data-stu-id="a5647-274">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="a5647-275">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="a5647-275">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="a5647-276">**Paso 3**: crear una directiva de enrutamiento de voz "sin restricciones".</span><span class="sxs-lookup"><span data-stu-id="a5647-276">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="a5647-277">El uso de RTC "Redmond 1" y "Redmond" se reutiliza en esta directiva de enrutamiento de voz para mantener un control especial de las llamadas al número "+ 1 425 XXX XX XX" y "+ 1 206 XXX XX XX" como llamadas locales o locales.</span><span class="sxs-lookup"><span data-stu-id="a5647-277">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="a5647-278">Tome nota del orden de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="a5647-278">Take note of the order of PSTN Usages:</span></span>

  <span data-ttu-id="a5647-279">a.</span><span class="sxs-lookup"><span data-stu-id="a5647-279">a.</span></span> <span data-ttu-id="a5647-280">Si una llamada se realiza en el número "+ 1 425 XXX XX XX" con los usos configurados como en el ejemplo siguiente, la llamada sigue el conjunto de rutas en "Estados Unidos y Canadá" y se aplica la lógica de enrutamiento especial.</span><span class="sxs-lookup"><span data-stu-id="a5647-280">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="a5647-281">Es decir, la llamada se enruta usando sbc1.contoso.biz y sbc2.contoso.biz en primer lugar y, a continuación, sbc3.contoso.biz y sbc4.contoso.biz como rutas de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a5647-281">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  <span data-ttu-id="a5647-282">b.</span><span class="sxs-lookup"><span data-stu-id="a5647-282">b.</span></span> <span data-ttu-id="a5647-283">Si el uso de RTC "internacional" es anterior a "Estados Unidos y Canadá", las llamadas a + 1 425 XXX XX XX se enrutan a sbc2.contoso.biz y sbc5.contoso.biz como parte de la lógica de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a5647-283">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="a5647-284">Escribe el comando:</span><span class="sxs-lookup"><span data-stu-id="a5647-284">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="a5647-285">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="a5647-285">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

<span data-ttu-id="a5647-286">**Paso 4**: asignar la Directiva de enrutamiento de voz al usuario "John Woods" con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a5647-286">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="a5647-287">A continuación, verifique la asignación con el comando:</span><span class="sxs-lookup"><span data-stu-id="a5647-287">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="a5647-288">Que devuelve:</span><span class="sxs-lookup"><span data-stu-id="a5647-288">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="a5647-289">El resultado es que la política de voz aplicada a las llamadas de John Woods no tiene restricciones, y seguirá la lógica de enrutamiento de llamadas disponible para las llamadas de Estados Unidos, Canadá e internacionales.</span><span class="sxs-lookup"><span data-stu-id="a5647-289">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>



## <a name="see-also"></a><span data-ttu-id="a5647-290">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5647-290">See also</span></span>

[<span data-ttu-id="a5647-291">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="a5647-291">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="a5647-292">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="a5647-292">Configure Direct Routing</span></span>](direct-routing-configure.md)
