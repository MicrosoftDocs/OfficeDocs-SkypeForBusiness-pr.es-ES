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
description: Obtenga información sobre cómo supervisar y solucionar problemas de configuración de enrutamiento directo, incluidos controladores de borde de sesión, componentes de enrutamiento directo y troncos de Telecom.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121408"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="efc82-103">Supervisar y solucionar problemas de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="efc82-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="efc82-104">En este artículo se describe cómo supervisar y solucionar problemas de configuración de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="efc82-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="efc82-105">La capacidad de realizar y recibir llamadas mediante enrutamiento directo implica los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="efc82-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="efc82-106">Controladores de borde de sesión (SBC)</span><span class="sxs-lookup"><span data-stu-id="efc82-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="efc82-107">Componentes de enrutamiento directo en Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="efc82-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="efc82-108">Troncos de telecomunicaciones</span><span class="sxs-lookup"><span data-stu-id="efc82-108">Telecom trunks</span></span> 

<span data-ttu-id="efc82-109">Si tiene dificultades para solucionar problemas, puede abrir un caso de soporte técnico con su proveedor de SBC o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efc82-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="efc82-110">Microsoft está trabajando en proporcionar más herramientas para la solución de problemas y la supervisión.</span><span class="sxs-lookup"><span data-stu-id="efc82-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="efc82-111">Compruebe periódicamente si hay actualizaciones en la documentación.</span><span class="sxs-lookup"><span data-stu-id="efc82-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="efc82-112">Supervisar la disponibilidad de los controladores de borde de sesión con mensajes de opciones del Protocolo de inicio de sesión (SIP)</span><span class="sxs-lookup"><span data-stu-id="efc82-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="efc82-113">Enrutamiento directo usa las opciones SIP enviadas por los controladores de borde de sesión para supervisar el estado de SBC.</span><span class="sxs-lookup"><span data-stu-id="efc82-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="efc82-114">No se requieren acciones del administrador de inquilinos para habilitar la supervisión de opciones SIP.</span><span class="sxs-lookup"><span data-stu-id="efc82-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="efc82-115">La información recopilada se tiene en cuenta al tomar decisiones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="efc82-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="efc82-116">Por ejemplo, si, para un usuario específico, hay varios SBC disponibles para enrutar una llamada, Enrutamiento directo considera la información de opciones SIP recibida de cada SBC para determinar el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="efc82-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="efc82-117">En el siguiente diagrama se muestra un ejemplo de la configuración:</span><span class="sxs-lookup"><span data-stu-id="efc82-117">The following diagram shows an example of the configuration:</span></span> 

![Ejemplo de configuración de opciones SIP](media/sip-options-config-example.png)

<span data-ttu-id="efc82-119">Cuando un usuario realiza una llamada al número +1 425, \<any seven digits> Enrutamiento directo evalúa la ruta.</span><span class="sxs-lookup"><span data-stu-id="efc82-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="efc82-120">Hay dos SBC en la ruta: sbc1.contoso.com y sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="efc82-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="efc82-121">Ambos SBC tienen la misma prioridad en la ruta.</span><span class="sxs-lookup"><span data-stu-id="efc82-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="efc82-122">Antes de elegir un SBC, el mecanismo de enrutamiento evalúa el estado de los SBC en función de cuándo el SBC envió las opciones SIP la última vez.</span><span class="sxs-lookup"><span data-stu-id="efc82-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="efc82-123">Un SBC se considera correcto si las estadísticas en el momento de enviar la llamada muestran que el SBC envía opciones cada minuto.</span><span class="sxs-lookup"><span data-stu-id="efc82-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="efc82-124">Cuando se realiza una llamada, se aplica la siguiente lógica:</span><span class="sxs-lookup"><span data-stu-id="efc82-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="efc82-125">El SBC se emparejaba a las 11:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="efc82-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="efc82-126">El SBC envía opciones a las 11:01 a.m., 11:02 a.m., y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="efc82-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="efc82-127">A las 11:15, un usuario realiza una llamada y el mecanismo de enrutamiento selecciona este SBC.</span><span class="sxs-lookup"><span data-stu-id="efc82-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="efc82-128">Enrutamiento directo toma las opciones de intervalo regular tres veces (el intervalo normal es de un minuto).</span><span class="sxs-lookup"><span data-stu-id="efc82-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="efc82-129">Si las opciones se enviaron durante los últimos tres minutos, el SBC se considera correcto.</span><span class="sxs-lookup"><span data-stu-id="efc82-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="efc82-130">Si el SBC del ejemplo envió opciones en cualquier período entre las 11:12 a.m. y las 11:15 a.m. (la hora en que se realizó la llamada), se considera que está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="efc82-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="efc82-131">Si no es así, el SBC se degradará de la ruta.</span><span class="sxs-lookup"><span data-stu-id="efc82-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="efc82-132">La degradación significa que el SBC no se probará primero.</span><span class="sxs-lookup"><span data-stu-id="efc82-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="efc82-133">Por ejemplo, hemos sbc1.contoso.com y sbc2.contoso.com con la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="efc82-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="efc82-134">Si sbc1.contoso.com no envía opciones SIP en un intervalo regular como se ha descrito anteriormente, se degrada.</span><span class="sxs-lookup"><span data-stu-id="efc82-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="efc82-135">A continuación, sbc2.contoso.com la llamada.</span><span class="sxs-lookup"><span data-stu-id="efc82-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="efc82-136">Si sbc2.contoso.con no puede realizar la llamada, el sbc1.contoso.com (degradado) se vuelve a intentar antes de que se genere un error.</span><span class="sxs-lookup"><span data-stu-id="efc82-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="efc82-137">Si dos (o más) SBC en una ruta se consideran correctos e iguales, se aplica un orden aleatorio Fisher-Yates distribuir las llamadas entre los SBC.</span><span class="sxs-lookup"><span data-stu-id="efc82-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="efc82-138">Supervisar el panel de Análisis de calidad de llamadas y los registros de SBC</span><span class="sxs-lookup"><span data-stu-id="efc82-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="efc82-139">En algunos casos, especialmente durante el emparejamiento inicial, puede haber problemas relacionados con la configuración incorrecta de los SBC o el servicio de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="efc82-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="efc82-140">Puede usar las siguientes herramientas para supervisar la configuración:</span><span class="sxs-lookup"><span data-stu-id="efc82-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="efc82-141">Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="efc82-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="efc82-142">Registros SBC</span><span class="sxs-lookup"><span data-stu-id="efc82-142">SBC logs</span></span> 

<span data-ttu-id="efc82-143">El servicio de enrutamiento directo tiene códigos de error muy descriptivos notificados a Análisis de llamadas o a los registros de SBC.</span><span class="sxs-lookup"><span data-stu-id="efc82-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="efc82-144">El Panel de calidad de llamadas proporciona información sobre la calidad y la confiabilidad de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="efc82-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="efc82-145">Para obtener más información sobre cómo solucionar problemas con Análisis de llamadas, vea Activar y usar el panel de calidad de llamadas para Microsoft Teams y [Skype Empresarial Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) y Usar Análisis de llamadas para solucionar problemas de mala calidad de [llamada.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="efc82-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="efc82-146">En caso de errores de llamada, Análisis de llamadas proporciona códigos SIP estándar para ayudarle con la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="efc82-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Código SIP de ejemplo para errores de llamada](media/failed-response-code.png)

<span data-ttu-id="efc82-148">Sin embargo, Análisis de llamadas solo puede ayudar cuando las llamadas llegan a los componentes internos de Enrutamiento directo y fallan.</span><span class="sxs-lookup"><span data-stu-id="efc82-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="efc82-149">En caso de problemas con el emparejamiento SBC o problemas en los que se rechazó la opción "Invitar" sip (por ejemplo, el nombre del FQDN del tronco está mal configurado), Análisis de llamadas no le ayudará.</span><span class="sxs-lookup"><span data-stu-id="efc82-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="efc82-150">En este caso, consulte los registros de SBC.</span><span class="sxs-lookup"><span data-stu-id="efc82-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="efc82-151">Enrutamiento directo envía una descripción detallada de los problemas a los SBC; estos problemas se pueden leer en los registros de SBC.</span><span class="sxs-lookup"><span data-stu-id="efc82-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span>