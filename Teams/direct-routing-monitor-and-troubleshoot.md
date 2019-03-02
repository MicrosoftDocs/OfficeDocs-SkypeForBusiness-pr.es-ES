---
title: Supervisar y solucionar problemas de enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: En este artículo se describe cómo supervisar y solucionar problemas de la configuración de enrutamiento directo.
ms.openlocfilehash: 75f116004c0385aa7d13b0173380221304590814
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30350989"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="be715-103">Supervisar y solucionar problemas de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="be715-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="be715-104">En este artículo se describe cómo supervisar y solucionar problemas de la configuración de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="be715-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="be715-105">La capacidad de realizar y recibir llamadas mediante el uso de enrutamiento directo implica los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="be715-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="be715-106">Controladores de borde de sesión (SBCs)</span><span class="sxs-lookup"><span data-stu-id="be715-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="be715-107">Componentes de enrutamiento directos en el Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="be715-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="be715-108">Troncos de telecomunicaciones</span><span class="sxs-lookup"><span data-stu-id="be715-108">Telecom trunks</span></span> 

<span data-ttu-id="be715-109">Si tiene dificultades para solución de problemas, abra un caso de soporte con el proveedor SBC o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="be715-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="be715-110">Microsoft está trabajando en proporcionar más herramientas de supervisión y solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="be715-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="be715-111">Compruebe la documentación de forma periódica para obtener actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="be715-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="be715-112">Supervisar la disponibilidad de controladores de borde de sesión mediante mensajes de las opciones de protocolo de inicio de sesión (SIP)</span><span class="sxs-lookup"><span data-stu-id="be715-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) Options messages</span></span>

<span data-ttu-id="be715-113">Enrutamiento directo usa opciones de SIP enviadas por los controladores de borde de sesión para supervisar el estado SBC.</span><span class="sxs-lookup"><span data-stu-id="be715-113">Direct Routing uses SIP Options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="be715-114">No hay ninguna acción necesaria desde el Administrador de inquilinos para habilitar la supervisión de las opciones de SIP.</span><span class="sxs-lookup"><span data-stu-id="be715-114">There are no actions required from the tenant administrator to enable the SIP Options monitoring.</span></span> <span data-ttu-id="be715-115">La información recopilada se toma en cuenta cuando se toman las decisiones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="be715-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="be715-116">Por ejemplo, si, para un usuario específico, hay varias SBCs disponibles para enrutar una llamada, el enrutamiento directo considera que la información de opciones de SIP recibida desde cada SBC para determinar el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="be715-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP Options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="be715-117">En el siguiente diagrama muestra un ejemplo de la configuración:</span><span class="sxs-lookup"><span data-stu-id="be715-117">The following diagram shows an example of the configuration:</span></span> 

![Ejemplo de configuración de opciones de SIP](media/sip-options-config-example.png)

<span data-ttu-id="be715-119">Cuando un usuario realiza una llamada al número +1 425 \<cualquier digits> siete, enrutamiento directo da como resultado la ruta.</span><span class="sxs-lookup"><span data-stu-id="be715-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="be715-120">Hay dos SBCs en la ruta: sbc1.contoso.com y sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="be715-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="be715-121">Ambos SBCs tienen la misma prioridad en la ruta.</span><span class="sxs-lookup"><span data-stu-id="be715-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="be715-122">Antes de seleccionar un SBC, el mecanismo de enrutamiento, se evalúa como el mantenimiento de la SBCs según cuando la SBC envía las opciones de SIP por última vez.</span><span class="sxs-lookup"><span data-stu-id="be715-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP Options last time.</span></span> 

<span data-ttu-id="be715-123">Un SBC se considera correcto si las estadísticas en el momento del envío de la llamada se muestran que el SBC envía las opciones en un intervalo regular.</span><span class="sxs-lookup"><span data-stu-id="be715-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="be715-124">Enrutamiento directo calcula intervalos regulares siguiendo dos veces el promedio cuando la SBC envía opciones antes de realizar la llamada y adición de cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="be715-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends Options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="be715-125">Por ejemplo, se supone lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="be715-125">For example, assume the following:</span></span> 

- <span data-ttu-id="be715-126">Un SBC está configurado enviar las opciones de cada minuto.</span><span class="sxs-lookup"><span data-stu-id="be715-126">An SBC is configured to send Options every minute.</span></span> 
- <span data-ttu-id="be715-127">Se ha emparejado el SBC a las 11:00 de la AM.</span><span class="sxs-lookup"><span data-stu-id="be715-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="be715-128">La SBC envía las opciones de 11.01 AM, 11.02 AM y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="be715-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="be715-129">En 11.15, un usuario realiza una llamada y el mecanismo de enrutamiento selecciona este SBC.</span><span class="sxs-lookup"><span data-stu-id="be715-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="be715-130">Se aplica la lógica siguiente: dos veces el intervalo promedio cuando la SBC envía opciones (de un minuto más de un minuto = dos minutos) plus cinco minutos = siete minutos.</span><span class="sxs-lookup"><span data-stu-id="be715-130">The following logic is applied: Two times the average interval when the SBC sends Options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="be715-131">Éste es el valor del intervalo regular para la SBC.</span><span class="sxs-lookup"><span data-stu-id="be715-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="be715-132">Si la SBC en nuestro ejemplo envía las opciones en cualquier período entre 11:08 A.M. y 11:15 A.M. (el tiempo que se realizó la llamada), se considera correcto.</span><span class="sxs-lookup"><span data-stu-id="be715-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="be715-133">En caso contrario, se degradará la SBC desde la ruta.</span><span class="sxs-lookup"><span data-stu-id="be715-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="be715-134">Disminución de nivel significa que la SBC no se intentará en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="be715-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="be715-135">Por ejemplo, tenemos sbc1.contoso.com y sbc2.contoso.com con la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="be715-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="be715-136">Si sbc1.contoso.com no envía las opciones de SIP en un intervalo regular como se describió anteriormente, se degrada.</span><span class="sxs-lookup"><span data-stu-id="be715-136">If sbc1.contoso.com does not send SIP Options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="be715-137">A continuación, se intenta sbc2.contoso.com para la llamada.</span><span class="sxs-lookup"><span data-stu-id="be715-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="be715-138">Si sbc2.contoso.con no puede entregar la llamada, el sbc1.contoso.com (cuyo nivel ha disminuido) se volverá a intentar antes de que se genere un error.</span><span class="sxs-lookup"><span data-stu-id="be715-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="be715-139">Supervise el panel de análisis de calidad de llamadas y los registros SBC</span><span class="sxs-lookup"><span data-stu-id="be715-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="be715-140">En algunos casos, especialmente durante el emparejamiento inicial, puede haber problemas relacionados con una configuración incorrecta de la SBCs o el servicio de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="be715-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="be715-141">Puede usar las siguientes herramientas para supervisar la configuración:</span><span class="sxs-lookup"><span data-stu-id="be715-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="be715-142">Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="be715-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="be715-143">Registros SBC</span><span class="sxs-lookup"><span data-stu-id="be715-143">SBC logs</span></span> 

<span data-ttu-id="be715-144">El servicio de enrutamiento directo tiene códigos de error muy descriptivo que se notifiquen al análisis de llamadas o los registros de SBC.</span><span class="sxs-lookup"><span data-stu-id="be715-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="be715-145">El panel de calidad de llamadas proporciona información acerca de la calidad de la llamada y la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="be715-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="be715-146">Para obtener más información acerca de cómo solucionar problemas con el análisis de llamadas, vea [activar y con el panel de calidad de llamadas para los equipos de Microsoft y Skype para profesionales en línea](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) y [Análisis de uso de llamadas para solucionar problemas de calidad de la llamada deficiente](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="be715-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="be715-147">En el caso de errores de llamadas, llamada análisis proporciona códigos de SIP estándar para ayudarle a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="be715-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Código de error de llamada SIP de ejemplo](media/failed-response-code.png)

<span data-ttu-id="be715-149">Sin embargo, solo puede ayudar llamar análisis cuando las llamadas llegar a los componentes internos de enrutamiento directo y se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="be715-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="be715-150">En caso de problemas con el emparejamiento SBC o donde se rechazó SIP "Invitar" (por ejemplo, el nombre del tronco que FQDN está mal configurado), no le ayudará llamar a análisis.</span><span class="sxs-lookup"><span data-stu-id="be715-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="be715-151">En este caso, consulte los registros de SBC.</span><span class="sxs-lookup"><span data-stu-id="be715-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="be715-152">Enrutamiento directo envía una descripción detallada de los problemas a la SBCs; estos problemas se pueden leer desde los registros de SBC.</span><span class="sxs-lookup"><span data-stu-id="be715-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
