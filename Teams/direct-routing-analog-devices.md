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
description: Lea este artículo para obtener información sobre cómo usar dispositivos analógicos con Teléfono Microsoft system direct routing.
ms.openlocfilehash: dc49c22dceffda6905d1f57652fd14d584d02cf6
ms.sourcegitcommit: 9d446485aa842abbdcd34d946b247166c2bf1610
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "52642100"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="12571-103">Cómo usar dispositivos analógicos con Sistema telefónico enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="12571-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="12571-104">En este artículo se describe cómo usar dispositivos analógicos con Sistema telefónico enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="12571-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="12571-105">Para conectar dispositivos analógicos al enrutamiento directo, debe usar un adaptador de telefonía analógica (ATA) y este adaptador debe ser compatible con el proveedor certificado del controlador de borde de sesión (SBC).</span><span class="sxs-lookup"><span data-stu-id="12571-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="12571-106">Cuando un usuario realiza una llamada desde un dispositivo analógico, la señalización y los medios fluyen a través del adaptador de telefonía analógica (ATA) al SBC.</span><span class="sxs-lookup"><span data-stu-id="12571-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="12571-107">El SBC envía la llamada a un punto de conexión Microsoft Teams o a la red telefónica conmutada (RTC) en función de la tabla de enrutamiento interno.</span><span class="sxs-lookup"><span data-stu-id="12571-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="12571-108">Cuando un dispositivo realiza una llamada, la ruta que toma depende de las directivas de enrutamiento creadas para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="12571-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="12571-109">En el siguiente diagrama, enrutamiento directo está configurado de modo que cualquier llamada Teams a y desde los números entre +1425 4XX XX XX y +1425 5XX XX XX debe tomar la ruta roja (línea de puntos), y cualquier llamada RTC a y desde números entre +1425 4XX XX XX y cualquier otro número excepto el rango de números +1425 5XX XX XX debe tomar la ruta azul (línea sólida).</span><span class="sxs-lookup"><span data-stu-id="12571-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="12571-110">![Diagrama que muestra la configuración de enrutamiento directo](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="12571-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="12571-111">Ejemplo: Cómo configurar el uso de dispositivos analógicos con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="12571-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="12571-112">Para configurar el uso de dispositivos analógicos con enrutamiento directo, debe conectar el adaptador de telefonía analógica al SBC y configurar el SBC para que funcione con enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="12571-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="12571-113">Este ejemplo le guiará por los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="12571-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="12571-114">Conectar el SBC a Enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="12571-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="12571-115">Crear el uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="12571-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="12571-116">Crear una ruta de voz y asociarla con el uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="12571-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="12571-117">Asigne la ruta de voz al uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="12571-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="12571-118">Habilite el usuario en línea.</span><span class="sxs-lookup"><span data-stu-id="12571-118">Enable the online user.</span></span>
6. <span data-ttu-id="12571-119">Asigne la directiva de ruta de voz al usuario.</span><span class="sxs-lookup"><span data-stu-id="12571-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="12571-120">Cree una ruta de voz para un dispositivo analógico.</span><span class="sxs-lookup"><span data-stu-id="12571-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="12571-121">Para obtener información sobre cómo conectar un ATA a un SBC y configurar el SBC, consulte la guía de configuración del fabricante de SBC:</span><span class="sxs-lookup"><span data-stu-id="12571-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="12571-122">Documentación de configuración de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="12571-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="12571-123">Documentación de configuración de la cinta de opciones</span><span class="sxs-lookup"><span data-stu-id="12571-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [<span data-ttu-id="12571-124">Documentación de configuración de Oracle</span><span class="sxs-lookup"><span data-stu-id="12571-124">Oracle configuration documentation</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="12571-125">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="12571-125">Step 1.</span></span>  <span data-ttu-id="12571-126">Conectar el SBC a enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="12571-126">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="12571-127">El siguiente comando configura la conexión SBC de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="12571-127">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="12571-128">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12571-128">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="12571-129">Puerto de señalización 5068</span><span class="sxs-lookup"><span data-stu-id="12571-129">Signaling port 5068</span></span>
- <span data-ttu-id="12571-130">Modo de omisión multimedia</span><span class="sxs-lookup"><span data-stu-id="12571-130">Media bypass mode</span></span>
- <span data-ttu-id="12571-131">Información del historial de llamadas reenviada al SBC-</span><span class="sxs-lookup"><span data-stu-id="12571-131">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="12571-132">Encabezado P-Asserted-Identity (PAI) reenviado junto con la llamada</span><span class="sxs-lookup"><span data-stu-id="12571-132">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="12571-133">Paso 2: Crear el uso de RTC</span><span class="sxs-lookup"><span data-stu-id="12571-133">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="12571-134">El comando siguiente crea un uso de RTC vacío.</span><span class="sxs-lookup"><span data-stu-id="12571-134">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="12571-135">Los usos de RTC en línea son valores de cadena que se usan para la autorización de llamadas.</span><span class="sxs-lookup"><span data-stu-id="12571-135">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="12571-136">Un uso de RTC en línea vincula una directiva de voz en línea a una ruta.</span><span class="sxs-lookup"><span data-stu-id="12571-136">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="12571-137">En este ejemplo se agrega la cadena "Interop" a la lista actual de usos de RTC disponibles.</span><span class="sxs-lookup"><span data-stu-id="12571-137">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="12571-138">Paso 3: Crear una ruta de voz y asociarla con el uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="12571-138">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="12571-139">Este comando crea una nueva ruta de voz en línea con la identidad "interoperabilidad analógica" para el rango de números +1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="12571-139">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="12571-140">La ruta de voz se aplica a una lista de puertas de enlace en línea sbc.contoso.com y asocia la ruta con el uso de RTC en línea "Interoperabilidad".</span><span class="sxs-lookup"><span data-stu-id="12571-140">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="12571-141">Una ruta de voz incluye una expresión regular que identifica qué números de teléfono se enrutarán a través de una ruta de voz determinada:</span><span class="sxs-lookup"><span data-stu-id="12571-141">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="12571-142">Paso 4: Asignar la ruta de voz al uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="12571-142">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="12571-143">Este comando crea una nueva directiva de enrutamiento de voz por usuario en línea con la identidad "AnalogInteropPolicy".</span><span class="sxs-lookup"><span data-stu-id="12571-143">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="12571-144">A esta directiva se le asigna un único uso de RTC en línea: "Interoperabilidad".</span><span class="sxs-lookup"><span data-stu-id="12571-144">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="12571-145">Paso 5: Habilitar el usuario en línea</span><span class="sxs-lookup"><span data-stu-id="12571-145">Step 5: Enable the online user</span></span>

<span data-ttu-id="12571-146">Este comando modifica la cuenta de usuario con la exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="12571-146">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="12571-147">En este caso, la cuenta se modifica para habilitar Telefonía IP empresarial, la implementación de VoIP de Microsoft, con correo de voz habilitado y asigna el número +1425500000 a este usuario.</span><span class="sxs-lookup"><span data-stu-id="12571-147">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="12571-148">Este comando debe ejecutarse para cada usuario Teams (excluyendo los usuarios de dispositivos ATA) en el espacio empresarial de la empresa.</span><span class="sxs-lookup"><span data-stu-id="12571-148">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="12571-149">Paso 6: Asignar la directiva de ruta de voz a un usuario</span><span class="sxs-lookup"><span data-stu-id="12571-149">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="12571-150">Este comando asigna la directiva de enrutamiento de voz en línea por usuario AnalogInteropPolicy al usuario con la identidad exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="12571-150">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="12571-151">Este comando debe ejecutarse para cada usuario Teams (excluyendo los usuarios de dispositivos ATA) en el espacio empresarial de la empresa.</span><span class="sxs-lookup"><span data-stu-id="12571-151">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="12571-152">Paso 7: Crear una ruta de voz para un dispositivo analógico</span><span class="sxs-lookup"><span data-stu-id="12571-152">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="12571-153">Este comando crea una ruta de voz en línea con la identidad "interoperabilidad analógica" para el rango de números +1425 4XX XX XX aplicable a una lista de puertas de enlace en línea sbc.contoso.com y la asocia con el uso de RTC en línea "Interop".</span><span class="sxs-lookup"><span data-stu-id="12571-153">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="12571-154">Este comando debe ejecutarse para cada dispositivo analógico con el patrón de número de teléfono adecuado.</span><span class="sxs-lookup"><span data-stu-id="12571-154">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="12571-155">Como alternativa, se puede usar un patrón de número adecuado para dispositivos analógicos al configurar la ruta de voz en línea durante uno de los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="12571-155">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="12571-156">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="12571-156">Considerations</span></span>

- <span data-ttu-id="12571-157">A menos que tenga en cuenta lo contrario, un dispositivo analógico es cualquier dispositivo que puede enviar dígitos DTMF para realizar una llamada.</span><span class="sxs-lookup"><span data-stu-id="12571-157">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="12571-158">Por ejemplo, teléfonos analógicos, faxes y paginadores generales.</span><span class="sxs-lookup"><span data-stu-id="12571-158">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="12571-159">Los teléfonos analógicos conectados a un ATA no se pueden buscar desde Teams.</span><span class="sxs-lookup"><span data-stu-id="12571-159">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="12571-160">Teams usuarios deben escribir manualmente el número de teléfono asociado al dispositivo para llamar a ese dispositivo.</span><span class="sxs-lookup"><span data-stu-id="12571-160">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="12571-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="12571-161">See also</span></span>

[<span data-ttu-id="12571-162">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="12571-162">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="12571-163">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="12571-163">Configure Direct Routing</span></span>](direct-routing-configure.md)
