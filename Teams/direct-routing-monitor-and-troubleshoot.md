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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: En este artículo se describe cómo supervisar y solucionar problemas de la configuración de enrutamiento directo.
ms.openlocfilehash: b4d53ad566cd0c31696ce688044ce1587d771a7d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290411"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="d64c7-103">Supervisar y solucionar problemas de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="d64c7-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="d64c7-104">En este artículo se describe cómo supervisar y solucionar problemas de la configuración de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="d64c7-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="d64c7-105">La capacidad de realizar y recibir llamadas mediante enrutamiento directo incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="d64c7-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="d64c7-106">Controladores de borde de sesión (SBCs)</span><span class="sxs-lookup"><span data-stu-id="d64c7-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="d64c7-107">Componentes de enrutamiento directo en la nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d64c7-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="d64c7-108">Troncos de telecomunicación</span><span class="sxs-lookup"><span data-stu-id="d64c7-108">Telecom trunks</span></span> 

<span data-ttu-id="d64c7-109">Si tiene dificultades para solucionar problemas, abra un caso de soporte técnico con su proveedor de SBC o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d64c7-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="d64c7-110">Microsoft está trabajando en proporcionar más herramientas para la solución de problemas y la supervisión.</span><span class="sxs-lookup"><span data-stu-id="d64c7-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="d64c7-111">Consulta la documentación periódicamente para obtener las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="d64c7-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="d64c7-112">Supervisión de la disponibilidad de los controladores de borde de sesión mediante mensajes de opciones de protocolo de inicio de sesión (SIP)</span><span class="sxs-lookup"><span data-stu-id="d64c7-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) Options messages</span></span>

<span data-ttu-id="d64c7-113">El enrutamiento directo usa las opciones SIP enviadas por los controladores de borde de la sesión para supervisar el estado de SBC.</span><span class="sxs-lookup"><span data-stu-id="d64c7-113">Direct Routing uses SIP Options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="d64c7-114">El administrador de inquilinos no necesita acciones para habilitar la supervisión de las opciones del SIP.</span><span class="sxs-lookup"><span data-stu-id="d64c7-114">There are no actions required from the tenant administrator to enable the SIP Options monitoring.</span></span> <span data-ttu-id="d64c7-115">La información recopilada se toma en consideración cuando se toman decisiones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d64c7-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="d64c7-116">Por ejemplo, si, para un usuario específico, hay varios SBCs disponibles para enrutar una llamada, enrutamiento directo tiene en cuenta la información de opciones SIP recibida de cada SBC para determinar el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d64c7-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP Options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="d64c7-117">En el siguiente diagrama se muestra un ejemplo de la configuración:</span><span class="sxs-lookup"><span data-stu-id="d64c7-117">The following diagram shows an example of the configuration:</span></span> 

![Ejemplo de configuración de opciones de SIP](media/sip-options-config-example.png)

<span data-ttu-id="d64c7-119">Cuando un usuario llama a Number + 1 425 \<, los siete digits>, el enrutamiento directo evalúa la ruta.</span><span class="sxs-lookup"><span data-stu-id="d64c7-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="d64c7-120">Hay dos SBCs en la ruta: sbc1.contoso.com y sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d64c7-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="d64c7-121">Tanto SBCs tienen la misma prioridad en la ruta.</span><span class="sxs-lookup"><span data-stu-id="d64c7-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="d64c7-122">Antes de elegir un SBC, el mecanismo de enrutamiento evalúa el estado de SBCs según el momento en que la SBC envió las opciones de SIP la última vez.</span><span class="sxs-lookup"><span data-stu-id="d64c7-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP Options last time.</span></span> 

<span data-ttu-id="d64c7-123">Un SBC se considera saludable si las estadísticas en el momento de enviar la llamada muestran que SBC envía opciones de forma regular.</span><span class="sxs-lookup"><span data-stu-id="d64c7-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="d64c7-124">El enrutamiento directo calcula intervalos regulares al tomar dos veces el promedio cuando el SBC envía opciones antes de hacer la llamada y agregar cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="d64c7-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends Options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="d64c7-125">Por ejemplo, supongamos lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d64c7-125">For example, assume the following:</span></span> 

- <span data-ttu-id="d64c7-126">Una SBC está configurada para enviar opciones cada minuto.</span><span class="sxs-lookup"><span data-stu-id="d64c7-126">An SBC is configured to send Options every minute.</span></span> 
- <span data-ttu-id="d64c7-127">La SBC fue emparejada a 11,00 A.M.</span><span class="sxs-lookup"><span data-stu-id="d64c7-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="d64c7-128">El SBC envía las opciones en 11,01 A.M., 11,02 A.M., etc.</span><span class="sxs-lookup"><span data-stu-id="d64c7-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="d64c7-129">En 11,15, un usuario realiza una llamada y el mecanismo de enrutamiento selecciona esta SBC.</span><span class="sxs-lookup"><span data-stu-id="d64c7-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="d64c7-130">Se aplica la siguiente lógica: dos veces el intervalo medio cuando el SBC envía opciones (un minuto más un minuto = dos minutos) más cinco minutos = siete minutos.</span><span class="sxs-lookup"><span data-stu-id="d64c7-130">The following logic is applied: Two times the average interval when the SBC sends Options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="d64c7-131">Este es el valor del intervalo normal para la SBC.</span><span class="sxs-lookup"><span data-stu-id="d64c7-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="d64c7-132">Si el SBC de nuestro ejemplo envió opciones en cualquier período comprendido entre 11,08 AM y 11,15 AM (el momento en que se realizó la llamada), se considerará saludable.</span><span class="sxs-lookup"><span data-stu-id="d64c7-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="d64c7-133">De lo contrario, se degradará la SBC de la ruta.</span><span class="sxs-lookup"><span data-stu-id="d64c7-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="d64c7-134">La degradación significa que la SBC no se intentará en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="d64c7-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="d64c7-135">Por ejemplo, tenemos sbc1.contoso.com y sbc2.contoso.com con la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="d64c7-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="d64c7-136">Si sbc1.contoso.com no envía las opciones de SIP a un intervalo regular según se describe anteriormente, se degradará.</span><span class="sxs-lookup"><span data-stu-id="d64c7-136">If sbc1.contoso.com does not send SIP Options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="d64c7-137">A continuación, sbc2.contoso.com intenta la llamada.</span><span class="sxs-lookup"><span data-stu-id="d64c7-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="d64c7-138">Si sbc2. contoso. con no puede entregar la llamada, se intentará de nuevo el sbc1.contoso.com (degradado) antes de que se genere un error.</span><span class="sxs-lookup"><span data-stu-id="d64c7-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="d64c7-139">Supervisar los registros del panel de análisis de calidad de llamadas y de SBC</span><span class="sxs-lookup"><span data-stu-id="d64c7-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="d64c7-140">En algunos casos, especialmente durante el emparejamiento inicial, es posible que haya problemas relacionados con la configuración indebido de la configuración de SBCs o del servicio de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="d64c7-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="d64c7-141">Puede usar las siguientes herramientas para supervisar la configuración:</span><span class="sxs-lookup"><span data-stu-id="d64c7-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="d64c7-142">Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="d64c7-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="d64c7-143">Registros de SBC</span><span class="sxs-lookup"><span data-stu-id="d64c7-143">SBC logs</span></span> 

<span data-ttu-id="d64c7-144">El servicio de enrutamiento directo tiene códigos de error muy descriptivos que se han notificado a análisis de llamadas o a los registros de SBC.</span><span class="sxs-lookup"><span data-stu-id="d64c7-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="d64c7-145">El panel de calidad de llamadas proporciona información sobre la calidad de las llamadas y la fiabilidad.</span><span class="sxs-lookup"><span data-stu-id="d64c7-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="d64c7-146">Para obtener más información sobre cómo solucionar problemas con el análisis de llamadas, consulte [activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype empresarial online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) y [usar el análisis de llamadas para solucionar problemas de baja calidad de las llamadas](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="d64c7-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="d64c7-147">En caso de que se produzcan errores en las llamadas, el análisis de llamadas proporciona códigos SIP estándar para ayudarle a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="d64c7-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Código SIP de ejemplo para error de llamada](media/failed-response-code.png)

<span data-ttu-id="d64c7-149">Sin embargo, el análisis de llamadas solo puede ayudar cuando las llamadas llegan a los componentes internos del enrutamiento directo y producen errores.</span><span class="sxs-lookup"><span data-stu-id="d64c7-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="d64c7-150">En caso de problemas con el emparejamiento de SBC o problemas en los que se rechazó el "invitar" SIP (por ejemplo, el nombre del FQDN de tronco está configurado incorrectamente), el análisis de llamadas no le servirá.</span><span class="sxs-lookup"><span data-stu-id="d64c7-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="d64c7-151">En este caso, consulta los registros de SBC.</span><span class="sxs-lookup"><span data-stu-id="d64c7-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="d64c7-152">El enrutamiento directo envía una descripción detallada de los problemas al SBCs; estos problemas se pueden leer desde los registros de SBC.</span><span class="sxs-lookup"><span data-stu-id="d64c7-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
