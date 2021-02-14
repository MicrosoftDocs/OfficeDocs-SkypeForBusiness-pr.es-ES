---
title: Supervisar y solucionar problemas de enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo supervisar y solucionar problemas de configuración de enrutamiento directo, incluidos los controladores de borde de sesión, los componentes de enrutamiento directo y los troncos de telecomunicaciones.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52ab594b901606ccf7c3b43fc8484d989c248fcd
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901915"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="0e442-103">Supervisar y solucionar problemas de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="0e442-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="0e442-104">En este artículo se describe cómo supervisar y solucionar problemas de configuración de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="0e442-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="0e442-105">La capacidad para realizar y recibir llamadas mediante enrutamiento directo implica los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="0e442-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="0e442-106">Controlador de borde de sesión (SBCs)</span><span class="sxs-lookup"><span data-stu-id="0e442-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="0e442-107">Componentes de enrutamiento directo en Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="0e442-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="0e442-108">Telecom trunks</span><span class="sxs-lookup"><span data-stu-id="0e442-108">Telecom trunks</span></span> 

<span data-ttu-id="0e442-109">Si tiene dificultades para solucionar problemas, puede abrir un caso de soporte con su proveedor de SBC o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e442-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="0e442-110">Microsoft está trabajando en proporcionar más herramientas para la solución de problemas y la supervisión.</span><span class="sxs-lookup"><span data-stu-id="0e442-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="0e442-111">Compruebe la documentación periódicamente para ver si hay actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0e442-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="0e442-112">Supervisar la disponibilidad de los controladores de borde de sesión mediante los mensajes de opciones del Protocolo de inicio de sesión (SIP)</span><span class="sxs-lookup"><span data-stu-id="0e442-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="0e442-113">El enrutamiento directo usa opciones SIP enviadas por los controladores de borde de sesión para supervisar el estado de SBC.</span><span class="sxs-lookup"><span data-stu-id="0e442-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="0e442-114">No es necesario realizar ninguna acción por parte del administrador de inquilinos para habilitar la supervisión de opciones SIP.</span><span class="sxs-lookup"><span data-stu-id="0e442-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="0e442-115">La información recopilada se tiene en cuenta al tomar decisiones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0e442-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="0e442-116">Por ejemplo, si hay varios SBC disponibles para enrutar una llamada para un usuario específico, enrutamiento directo tiene en cuenta la información de opciones SIP que se recibe de cada SBC para determinar el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0e442-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="0e442-117">El siguiente diagrama muestra un ejemplo de la configuración:</span><span class="sxs-lookup"><span data-stu-id="0e442-117">The following diagram shows an example of the configuration:</span></span> 

![Ejemplo de configuración de opciones SIP](media/sip-options-config-example.png)

<span data-ttu-id="0e442-119">Cuando un usuario realiza una llamada al número +1 425 cualquiera de los siete dígitos>, enrutamiento directo \< evalúa la ruta.</span><span class="sxs-lookup"><span data-stu-id="0e442-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="0e442-120">Hay dos sbcs en la ruta: sbc1.contoso.com y sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0e442-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="0e442-121">Ambos SDC tienen la misma prioridad en la ruta.</span><span class="sxs-lookup"><span data-stu-id="0e442-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="0e442-122">Antes de elegir un SBC, el mecanismo de enrutamiento evalúa el estado de los SBC en función de cuándo la SBC envió las opciones SIP por última vez.</span><span class="sxs-lookup"><span data-stu-id="0e442-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="0e442-123">Un SBC se considera correcto si las estadísticas en el momento de enviar la llamada muestran que la SBC envía opciones cada minuto.</span><span class="sxs-lookup"><span data-stu-id="0e442-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="0e442-124">Cuando se realiza una llamada, se aplica la siguiente lógica:</span><span class="sxs-lookup"><span data-stu-id="0e442-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="0e442-125">La cadena SBC se emparejaba a las 11:00.</span><span class="sxs-lookup"><span data-stu-id="0e442-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="0e442-126">La SBC envía opciones a las 11:01, a las 11:02 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="0e442-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="0e442-127">A las 11:15, un usuario realiza una llamada y el mecanismo de enrutamiento selecciona este SBC.</span><span class="sxs-lookup"><span data-stu-id="0e442-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="0e442-128">El enrutamiento directo toma tres veces las opciones de intervalo normal (el intervalo normal es de un minuto).</span><span class="sxs-lookup"><span data-stu-id="0e442-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="0e442-129">Si las opciones se enviaron durante los últimos tres minutos, la SBC se considera que está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="0e442-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="0e442-130">Si la SBC del ejemplo de opciones enviadas en un período entre las 11:12 y las 11:15 (hora en que se realizó la llamada), se considera que está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="0e442-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="0e442-131">Si no es así, la SBC se degradará de la ruta.</span><span class="sxs-lookup"><span data-stu-id="0e442-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="0e442-132">Democión significa que no se probará la SBC primero.</span><span class="sxs-lookup"><span data-stu-id="0e442-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="0e442-133">Por ejemplo, tenemos sbc1.contoso.com y sbc2.contoso.com tienen la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="0e442-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="0e442-134">Si sbc1.contoso.com no envía opciones SIP en un intervalo regular como se describió anteriormente, se degrada.</span><span class="sxs-lookup"><span data-stu-id="0e442-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="0e442-135">A continuación, sbc2.contoso.com durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e442-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="0e442-136">Si sbc2.contoso.con no puede entregar la llamada, se vuelve a intentar el sbc1.contoso.com (degradado) antes de que se genere un error.</span><span class="sxs-lookup"><span data-stu-id="0e442-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="0e442-137">Si dos (o más) SBC de una ruta se consideran correctos e iguales, Fisher-Yates orden aleatorio se aplica para distribuir las llamadas entre las sbcs.</span><span class="sxs-lookup"><span data-stu-id="0e442-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="0e442-138">Supervisar los registros SBC y el panel de análisis de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="0e442-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="0e442-139">En algunos casos, especialmente durante el emparejamiento inicial, puede haber problemas relacionados con la configuración incorrecta de los SBC o el servicio de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="0e442-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="0e442-140">Puede usar las siguientes herramientas para supervisar la configuración:</span><span class="sxs-lookup"><span data-stu-id="0e442-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="0e442-141">Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="0e442-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="0e442-142">Registros SBC</span><span class="sxs-lookup"><span data-stu-id="0e442-142">SBC logs</span></span> 

<span data-ttu-id="0e442-143">El servicio de enrutamiento directo tiene códigos de error muy descriptivos que se han notificado a Call Analytics o a los registros SBC.</span><span class="sxs-lookup"><span data-stu-id="0e442-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="0e442-144">El panel de calidad de llamadas proporciona información sobre la calidad y la confiabilidad de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="0e442-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="0e442-145">Para obtener más información sobre cómo solucionar problemas con Análisis de llamadas, vea Activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype Empresarial [Online,](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) y use El análisis de llamadas para solucionar problemas de calidad de [llamadas deficiente.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="0e442-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="0e442-146">En caso de fallos en la llamada, Análisis de llamadas proporciona códigos SIP estándar para ayudarle a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="0e442-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Ejemplo de código SIP para un error de llamada](media/failed-response-code.png)

<span data-ttu-id="0e442-148">Sin embargo, el análisis de llamadas solo puede ayudarle cuando las llamadas llegan a los componentes internos de Enrutamiento directo y fallan.</span><span class="sxs-lookup"><span data-stu-id="0e442-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="0e442-149">En caso de problemas con el emparejamiento SBC o problemas en los que se rechazó la "Invitación" SIP (por ejemplo, el nombre del FQDN del tronco está mal configurado), Análisis de llamadas no ayudará.</span><span class="sxs-lookup"><span data-stu-id="0e442-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="0e442-150">En este caso, consulte los registros SBC.</span><span class="sxs-lookup"><span data-stu-id="0e442-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="0e442-151">El enrutamiento directo envía una descripción detallada de los problemas a los SBC; estos problemas se pueden leer en los registros de SBC.</span><span class="sxs-lookup"><span data-stu-id="0e442-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
