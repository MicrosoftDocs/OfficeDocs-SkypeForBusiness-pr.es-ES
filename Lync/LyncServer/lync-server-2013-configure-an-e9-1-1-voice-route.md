---
title: 'Lync Server 2013: configurar una ruta de voz de E9-1-1'
description: 'Lync Server 2013: configurar una ruta de voz de E9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 869e9eaeb454943ccd877e90a21461c73065873e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546736"
---
# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="cc518-103">Configurar una ruta de voz E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc518-103">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc518-104">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="cc518-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="cc518-105">Para implementar E9-1-1, deberá configurar primero una ruta de voz para llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="cc518-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="cc518-106">Para obtener más información sobre cómo crear rutas de voz, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="cc518-106">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="cc518-107">Puede definir más de una ruta si, por ejemplo, su implementación incluye un tronco SIP principal y otro secundario.</span><span class="sxs-lookup"><span data-stu-id="cc518-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc518-108">Para incluir información de ubicación en una invitación de E9-1-1, debe configurar el tronco SIP que se conecta al proveedor de servicios E9-1-1 para enrutar las llamadas de emergencia a través de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="cc518-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="cc518-109">Para ello, establezca la marca EnablePIDFLOSupport en el cmdlet <STRONG>set-CsTrunkConfiguration</STRONG> en true.</span><span class="sxs-lookup"><span data-stu-id="cc518-109">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="cc518-110">El valor predeterminado de EnablePIDFLOSupport es false.</span><span class="sxs-lookup"><span data-stu-id="cc518-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="cc518-111">Por ejemplo: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="cc518-111">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="cc518-112">No es necesario habilitar las ubicaciones de recepción para puertas de enlace de Red telefónica conmutada (RTC) de conmutación por error o para puertas de enlace de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="cc518-112">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="cc518-113">Para obtener información detallada sobre cómo trabajar con rutas de voz, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="cc518-113">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="cc518-114">**Set-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="cc518-114">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="cc518-115">**Get-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="cc518-115">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="cc518-116">**New-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="cc518-116">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="cc518-117">**Get-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="cc518-117">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="cc518-118">**Set-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="cc518-118">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="cc518-119">**Remove-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="cc518-119">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="cc518-120">Para configurar una ruta de voz de E9-1-1</span><span class="sxs-lookup"><span data-stu-id="cc518-120">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="cc518-121">Inicie sesión en el equipo con una cuenta que sea miembro de los grupos RTCUniversalServerAdmins o del rol administrativo CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cc518-121">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="cc518-122">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cc518-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cc518-123">Ejecute el siguiente cmdlet para crear un nuevo registro de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="cc518-123">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="cc518-124">Debe ser el mismo nombre que vaya a usar para la configuración de **RTC** en la directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="cc518-124">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="cc518-125">Aunque la implementación va a tener varios registros de uso telefónico, en el siguiente ejemplo se agrega “Uso para emergencias” a la lista actual de usos de de RTC disponibles.</span><span class="sxs-lookup"><span data-stu-id="cc518-125">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="cc518-126">Para obtener más información, consulte [Configuring Voice policies and RTC Usage Records to reautorizate Calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="cc518-126">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="cc518-127">Ejecute el siguiente cmdlet para crear una nueva ruta de voz usando el registro de uso de RTC creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="cc518-127">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="cc518-128">El patrón numérico debe coincidir con el patrón numérico que se usa en la configuración de **Cadena de marcado de emergencia** en la directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="cc518-128">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="cc518-129">Se necesita un signo "+" porque Lync agrega "+" a las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="cc518-129">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="cc518-130">"Co1-pstngateway-1" es el identificador del servicio de tronco SIP del proveedor de servicios E9-11.</span><span class="sxs-lookup"><span data-stu-id="cc518-130">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="cc518-131">En el siguiente ejemplo se usa “EmergencyRoute” como nombre de la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="cc518-131">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="cc518-p105">Opcionalmente, en las conexiones de tronco SIP se recomienda ejecutar el siguiente cmdlet para crear una ruta local para llamadas que no administra el tronco SIP del proveedor de servicios E9-11. Esta ruta se usará en el caso de que la conexión con el proveedor de servicios de E9-11 no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="cc518-p105">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="cc518-134">En el siguiente ejemplo se da por hecho que el usuario tiene un uso “Local” en su directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="cc518-134">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

