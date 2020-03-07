---
title: 'Enrutamiento directo: conexión de dispositivos analógicos'
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lea este artículo para aprender a usar dispositivos analógicos con el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: 45128b8806644e4399687787bcce251ccb807d85
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558520"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="4d285-103">Cómo usar dispositivos analógicos con enrutamiento directo de sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="4d285-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="4d285-104">En este artículo se describe cómo usar dispositivos analógicos con enrutamiento directo del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="4d285-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="4d285-105">Para conectar dispositivos analógicos a enrutamiento directo, debe usar un adaptador de telefonía analógica (ATA) y este adaptador debe ser compatible con el proveedor de controlador de borde de sesión (SBC) certificado.</span><span class="sxs-lookup"><span data-stu-id="4d285-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="4d285-106">Cuando un usuario realiza una llamada desde un dispositivo analógico, la señalización y el flujo de medios a través del adaptador de telefonía analógica (ATA) a SBC.</span><span class="sxs-lookup"><span data-stu-id="4d285-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="4d285-107">El SBC envía la llamada a un punto final de Microsoft Teams o a la red de telefonía pública conmutada (RTC) en función de la tabla de enrutamiento interna.</span><span class="sxs-lookup"><span data-stu-id="4d285-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="4d285-108">Cuando un dispositivo realiza una llamada, la ruta que toma depende de las directivas de enrutamiento creadas para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4d285-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="4d285-109">En el siguiente diagrama, el enrutamiento directo está configurado de modo que cualquier equipo que llame a y desde los números entre + 1425 4XX XX XX y + 1425 5XX XX XX debe tomar la ruta roja (línea de puntos) y cualquier llamada RTC a y desde números comprendidos entre + 1425 4XX XX XX y cualquier otro número excepto  intervalo de números + 1425 5XX XX XX debe tomar la ruta azul (línea sólida).</span><span class="sxs-lookup"><span data-stu-id="4d285-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

![Diagrama que muestra la configuración de enrutamiento directo](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="4d285-111">Ejemplo: Cómo configurar el uso de dispositivos analógicos con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="4d285-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="4d285-112">Para configurar el uso de dispositivos analógicos con enrutamiento directo, debe conectar el adaptador de telefonía analógica al SBC y configurar el SBC para que funcione con el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="4d285-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="4d285-113">Este ejemplo le guía por los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="4d285-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="4d285-114">Conecte el SBC al enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="4d285-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="4d285-115">Crear el uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="4d285-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="4d285-116">Crear una ruta de voz y asociarla con el uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="4d285-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="4d285-117">Asigne la ruta de voz al uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="4d285-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="4d285-118">Habilitar el usuario en línea.</span><span class="sxs-lookup"><span data-stu-id="4d285-118">Enable the online user.</span></span>
6. <span data-ttu-id="4d285-119">Asigne la Directiva de la ruta de voz al usuario.</span><span class="sxs-lookup"><span data-stu-id="4d285-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="4d285-120">Crear una ruta de voz para un dispositivo analógico.</span><span class="sxs-lookup"><span data-stu-id="4d285-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="4d285-121">Para obtener información sobre cómo conectar un ATA a un SBC y configurar el SBC, consulte la guía de configuración del fabricante de SBC:</span><span class="sxs-lookup"><span data-stu-id="4d285-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>
- [<span data-ttu-id="4d285-122">Documentación de configuración de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="4d285-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)
- [<span data-ttu-id="4d285-123">Documentación de configuración de la cinta</span><span class="sxs-lookup"><span data-stu-id="4d285-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="4d285-124">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="4d285-124">Step 1.</span></span>  <span data-ttu-id="4d285-125">Conectar la SBC al enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="4d285-125">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="4d285-126">El siguiente comando configura la conexión de SBC de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4d285-126">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="4d285-127">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d285-127">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="4d285-128">Puerto de señalización 5068</span><span class="sxs-lookup"><span data-stu-id="4d285-128">Signaling port 5068</span></span>
- <span data-ttu-id="4d285-129">Modo de omisión de medios</span><span class="sxs-lookup"><span data-stu-id="4d285-129">Media bypass mode</span></span>
- <span data-ttu-id="4d285-130">Información del historial de llamadas desviada a la SBC-</span><span class="sxs-lookup"><span data-stu-id="4d285-130">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="4d285-131">P-encabezado de identidad afirmado (PAI) desviado junto con la llamada</span><span class="sxs-lookup"><span data-stu-id="4d285-131">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="4d285-132">Paso 2: crear el uso de RTC</span><span class="sxs-lookup"><span data-stu-id="4d285-132">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="4d285-133">El comando siguiente crea un uso de RTC vacío.</span><span class="sxs-lookup"><span data-stu-id="4d285-133">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="4d285-134">Los usos de RTC en línea son valores de cadena que se usan para la autorización de llamadas.</span><span class="sxs-lookup"><span data-stu-id="4d285-134">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="4d285-135">Un uso de RTC en línea vincula una directiva de voz en línea a una ruta.</span><span class="sxs-lookup"><span data-stu-id="4d285-135">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="4d285-136">Este ejemplo agrega la cadena "Interop" a la lista actual de usos de RTC disponibles.</span><span class="sxs-lookup"><span data-stu-id="4d285-136">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="4d285-137">Paso 3: crear una ruta de voz y asociarla con el uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="4d285-137">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="4d285-138">Este comando crea una nueva ruta de voz en línea con la identidad "interoperabilidad analógica" para el intervalo de números + 1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="4d285-138">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="4d285-139">La ruta de voz es aplicable a una lista de puertas de enlace en línea sbc.contoso.com y asocia la ruta con el uso de RTC en línea "interoperabilidad".</span><span class="sxs-lookup"><span data-stu-id="4d285-139">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="4d285-140">Una ruta de voz incluye una expresión regular que identifica qué números de teléfono se redirigirán a través de una ruta de voz determinada:</span><span class="sxs-lookup"><span data-stu-id="4d285-140">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="4d285-141">Paso 4: asignar la ruta de voz al uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="4d285-141">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="4d285-142">Este comando crea una nueva Directiva de enrutamiento de voz por usuario en línea con la identidad "AnalogInteropPolicy".</span><span class="sxs-lookup"><span data-stu-id="4d285-142">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="4d285-143">A esta Directiva se le asigna un único uso de RTC en línea: "interoperabilidad".</span><span class="sxs-lookup"><span data-stu-id="4d285-143">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="4d285-144">Paso 5: habilitar el usuario en línea</span><span class="sxs-lookup"><span data-stu-id="4d285-144">Step 5: Enable the online user</span></span>

<span data-ttu-id="4d285-145">Este comando modifica la cuenta de usuario con la identidad exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4d285-145">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="4d285-146">En este caso, la cuenta se modifica para habilitar telefonía IP empresarial, la implementación de VoIP de Microsoft, con el correo de voz habilitado y asigna el número + 14255000000 a este usuario.</span><span class="sxs-lookup"><span data-stu-id="4d285-146">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="4d285-147">Este comando debe ejecutarse para cada usuario de Teams (excepto los usuarios del dispositivo ATA) en el espacio empresarial de la empresa.</span><span class="sxs-lookup"><span data-stu-id="4d285-147">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="4d285-148">Paso 6: asignar la Directiva de la ruta de voz a un usuario</span><span class="sxs-lookup"><span data-stu-id="4d285-148">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="4d285-149">Este comando asigna la Directiva de enrutamiento de voz en línea de AnalogInteropPolicy al usuario con la identidad exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4d285-149">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="4d285-150">Este comando debe ejecutarse para cada usuario de Teams (excepto los usuarios del dispositivo ATA) en el espacio empresarial de la empresa.</span><span class="sxs-lookup"><span data-stu-id="4d285-150">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="4d285-151">Paso 7: crear una ruta de voz para un dispositivo analógico</span><span class="sxs-lookup"><span data-stu-id="4d285-151">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="4d285-152">Este comando crea una ruta de voz en línea con la identidad "red de interoperabilidad analógica" para el intervalo de números + 1425 4XX XX XX aplicable a una lista de puertas de enlace en línea sbc.contoso.com y la asocia a la "interoperabilidad" de uso de RTC en línea.</span><span class="sxs-lookup"><span data-stu-id="4d285-152">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="4d285-153">Este comando debe ejecutarse para cada dispositivo analógico con el patrón de número de teléfono adecuado.</span><span class="sxs-lookup"><span data-stu-id="4d285-153">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="4d285-154">Como alternativa, se puede usar un patrón de número adecuado para dispositivos analógicos al configurar la ruta de voz en línea durante uno de los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="4d285-154">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="4d285-155">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="4d285-155">Considerations</span></span>

- <span data-ttu-id="4d285-156">A menos que tenga nota, un dispositivo analógico es cualquier dispositivo que pueda enviar dígitos de DTMF para realizar una llamada.</span><span class="sxs-lookup"><span data-stu-id="4d285-156">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="4d285-157">Por ejemplo, teléfonos analógicos, máquinas de fax y buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="4d285-157">For example, analog phones, fax machines, and overhead pagers.</span></span>
- <span data-ttu-id="4d285-158">Los teléfonos analógicos conectados a un ATA no se pueden buscar desde Teams.</span><span class="sxs-lookup"><span data-stu-id="4d285-158">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="4d285-159">Los usuarios de Teams deben introducir manualmente el número de teléfono asociado con el dispositivo para llamar a ese dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4d285-159">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="4d285-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d285-160">See also</span></span>

[<span data-ttu-id="4d285-161">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="4d285-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="4d285-162">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="4d285-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
