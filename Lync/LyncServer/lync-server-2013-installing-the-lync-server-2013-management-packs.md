---
title: 'Lync Server 2013: instalación de los módulos de administración de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fea443225744bfd0d0e2dfa90a317ffa4cc890ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="458bb-102">Instalar los módulos de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="458bb-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="458bb-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="458bb-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="458bb-104">Por sí solo, System Center Operations Manager tiene la capacidad de supervisar solo una pequeña parte del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="458bb-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="458bb-105">Sin embargo, puede ampliar las capacidades de System Center Operations Manager mediante la instalación de paquetes de administración, software que determina los elementos que System Center Operations Manager puede supervisar, incluido cómo se deben supervisar esos elementos y cómo deberían ser las alertas. desencadenado y notificado.</span><span class="sxs-lookup"><span data-stu-id="458bb-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="458bb-106">Microsoft Lync Server 2013 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="458bb-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="458bb-107">El componente y el paquete de administración de usuario (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) realiza un seguimiento de los problemas de Lync Server registrados en registros de eventos, registrados por contadores de rendimiento o registrados en los registros de detalles de llamadas (CDR) o la calidad de la experiencia (QoE). bases.</span><span class="sxs-lookup"><span data-stu-id="458bb-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="458bb-108">En el caso de problemas críticos, System Center Operations Manager se puede configurar para que notifiquen inmediatamente a los administradores a través de mensajes de correo electrónico, mensajes instantáneos o mensajes SMS.</span><span class="sxs-lookup"><span data-stu-id="458bb-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="458bb-109">SMS es la tecnología que se usa para enviar mensajes de texto desde un dispositivo móvil a otro.</span><span class="sxs-lookup"><span data-stu-id="458bb-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="458bb-110">Para obtener más información sobre la configuración de notificaciones de Operations Manager, vea configurar <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>notificaciones en la biblioteca de TechNet en.</span><span class="sxs-lookup"><span data-stu-id="458bb-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="458bb-111">El paquete de supervisión activa (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) prueba de forma proactiva componentes de Lync Server clave, como iniciar sesión en el sistema, intercambiar mensajes instantáneos o hacer llamadas a un teléfono que se encuentra en el teléfono conmutado público. red (RTC).</span><span class="sxs-lookup"><span data-stu-id="458bb-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="458bb-112">Estas pruebas se realizan mediante los cmdlets de transacciones sintéticas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="458bb-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="458bb-113">Por ejemplo, el cmdlet **Test-CsIM** se usa para simular una conversación de mensajería instantánea entre dos usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="458bb-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="458bb-114">Si se produce un error en esta conversación de mensajería simulada, se generará una alerta.</span><span class="sxs-lookup"><span data-stu-id="458bb-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="458bb-115">Los dos módulos de administración incluidos en Lync Server 2013 incluyen un gran número de mejoras en los paquetes de administración que se usan con Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="458bb-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="458bb-116">Por ejemplo, el módulo de administración de componentes de Lync Server 2013 no se limita a supervisar el servidor de Lync en sí.</span><span class="sxs-lookup"><span data-stu-id="458bb-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="458bb-117">Además de supervisar los registros de eventos y los contadores de rendimiento de Lync Server, el módulo de administración de componentes también puede realizar un seguimiento del rendimiento de elementos esenciales, como por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="458bb-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="458bb-118">**Las alertas de servicios de Internet Information Server (IIS)**   se emitirán si servicios de Internet Information Server se desconecta.</span><span class="sxs-lookup"><span data-stu-id="458bb-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="458bb-119">Esto es importante porque los servicios Web de Lync Server dependen de IIS.</span><span class="sxs-lookup"><span data-stu-id="458bb-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="458bb-120">\*\*\*\*   Las alertas de uso de procesos se emitirán si los recursos del sistema (como la memoria disponible) comienzan a agotarse.</span><span class="sxs-lookup"><span data-stu-id="458bb-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="458bb-121">Estas alertas se emitirán incluso si Lync Server no es responsable del uso elevado del sistema.</span><span class="sxs-lookup"><span data-stu-id="458bb-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="458bb-122">\*\*\*\*   Las alertas de eventos de error de equipo se emitirán en caso de un problema de hardware o software que amenace la viabilidad de un servidor.</span><span class="sxs-lookup"><span data-stu-id="458bb-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="458bb-123">Por ejemplo, los administradores de Lync Server recibirán una notificación si un servidor parece estar en peligro de experimentar un error en el disco duro.</span><span class="sxs-lookup"><span data-stu-id="458bb-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="458bb-124">Los nuevos paquetes de administración también ofrecen informes mejorados.</span><span class="sxs-lookup"><span data-stu-id="458bb-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="458bb-125">Los nuevos informes para Lync Server 2013 incluyen:</span><span class="sxs-lookup"><span data-stu-id="458bb-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="458bb-126">**Informe de disponibilidad de escenario de principio a fin**   este informe detalla la disponibilidad y el tiempo de actividad de los servicios clave de Lync Server, como el registro o la presencia.</span><span class="sxs-lookup"><span data-stu-id="458bb-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="458bb-127">**Informe de capacidad**   con información de contador de rendimiento, este informe muestra tendencias de componentes del sistema, como la disponibilidad de memoria y el uso del procesador.</span><span class="sxs-lookup"><span data-stu-id="458bb-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="458bb-128">**Informe de componente**   este informe enumera los principales generadores de alertas agrupados por el componente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="458bb-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="458bb-129">Además de estos informes prediseñados, los módulos de administración para Lync Server 2013 automáticamente notifican las alertas de confiabilidad de llamadas (métricas medidas por la grabación de detalles de llamadas) y los Estados de QoE (métricas medidas según la calidad de la experiencia).</span><span class="sxs-lookup"><span data-stu-id="458bb-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="458bb-130">Si ha habilitado la grabación de detalles de llamadas, puede revisar las alertas de confiabilidad de llamadas completando el siguiente procedimiento de la consola de System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="458bb-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="458bb-131">Expanda **supervisión**, expanda **Estado 2013 de Microsoft Lync Server**, expanda **fiabilidad y calidad multimedia**y, después, haga clic en confiabilidad de la **llamada**.</span><span class="sxs-lookup"><span data-stu-id="458bb-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="458bb-132">Para ver las alertas de calidad de la experiencia, complete este procedimiento desde la consola de System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="458bb-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="458bb-133">Expanda **supervisión**, expanda **Estado de Microsoft Lync Server 2013**, expanda **fiabilidad y calidad multimedia**y, después, expanda **calidad de multimedia**.</span><span class="sxs-lookup"><span data-stu-id="458bb-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="458bb-134">Los módulos de administración para Lync Server 2013 ahora usan la detección a nivel de equipo en lugar del mecanismo de detección central usado en Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="458bb-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="458bb-135">Esto significa que cada agente de System Center se descubre por sí mismo e informa de su existencia en el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="458bb-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="458bb-136">El uso de detección en el nivel de equipo simplifica la administración de la infraestructura de System Center y también permite el uso de diferentes versiones de los paquetes de administración de Lync Server (por ejemplo, módulos de administración para Lync Server 2010 y paquetes de administración para Lync Server 2013) para existi.</span><span class="sxs-lookup"><span data-stu-id="458bb-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

