---
title: 'Lync Server 2013: instalación de los paquetes de administración de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2a6cd3ca0c58a6101d6e46e253e3edf09dec025
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="fa395-102">Instalación de los paquetes de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa395-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa395-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="fa395-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="fa395-104">Por sí sola, System Center Operations Manager tiene la capacidad de supervisar solo una pequeña parte del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="fa395-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="fa395-105">Sin embargo, puede ampliar las capacidades de System Center Operations Manager mediante la instalación de los paquetes de administración, el software que determina qué elementos puede supervisar System Center Operations Manager, incluido cómo se deben supervisar esos elementos y cómo deben realizarse las alertas desencadenado y notificado.</span><span class="sxs-lookup"><span data-stu-id="fa395-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="fa395-106">Microsoft Lync Server 2013 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes capacidades:</span><span class="sxs-lookup"><span data-stu-id="fa395-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="fa395-107">El componente y el módulo de administración de usuarios (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) realiza un seguimiento de los problemas de Lync Server registrados en los registros de eventos, registrados por los contadores de rendimiento o registrados en los registros de detalles de llamadas (CDR) o la calidad de la experiencia (QoE). bases.</span><span class="sxs-lookup"><span data-stu-id="fa395-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="fa395-108">Para los problemas críticos, System Center Operations Manager se puede configurar para que notifique inmediatamente a los administradores a través de mensajes de correo electrónico, mensajes instantáneos o servicio de mensajes cortos (SMS).</span><span class="sxs-lookup"><span data-stu-id="fa395-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="fa395-109">SMS es la tecnología que se usa para enviar mensajes de texto entre dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="fa395-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fa395-110">Para obtener más información sobre cómo configurar la notificación de Operations Manager, vea configuración de <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>la notificación en la biblioteca de TechNet en.</span><span class="sxs-lookup"><span data-stu-id="fa395-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="fa395-111">El paquete de supervisión activo (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) prueba de forma proactiva los componentes clave de Lync Server como, por ejemplo, el inicio de sesión en el sistema, el intercambio de mensajes instantáneos o la realización de llamadas a un teléfono ubicado en el teléfono conmutado público red (RTC).</span><span class="sxs-lookup"><span data-stu-id="fa395-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="fa395-112">Estas pruebas se llevan a cabo con los cmdlets de transacciones sintéticas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa395-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="fa395-113">Por ejemplo, el cmdlet **Test-CsIM** se usa para simular una conversación de mensajería instantánea entre dos usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="fa395-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="fa395-114">Si esta conversación de mensajería simulada tiene errores, se genera una alerta.</span><span class="sxs-lookup"><span data-stu-id="fa395-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="fa395-115">Los dos módulos de administración que se incluyen en Lync Server 2013 incluyen un gran número de mejoras a través de los paquetes de administración que se usan con Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fa395-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="fa395-116">Por ejemplo, el módulo de administración de componentes de Lync Server 2013 no está limitado a la supervisión del propio Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa395-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="fa395-117">Además de supervisar los registros de eventos y los contadores de rendimiento de Lync Server, el módulo de administración de componentes también puede realizar un seguimiento del rendimiento y emitir alertas para elementos cruciales, como:</span><span class="sxs-lookup"><span data-stu-id="fa395-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="fa395-118">**Se emitirán alertas de Internet Information Services (IIS)**   si Internet Information Services se desconecta.</span><span class="sxs-lookup"><span data-stu-id="fa395-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="fa395-119">Esto es importante porque los servicios Web de Lync Server se basan en IIS.</span><span class="sxs-lookup"><span data-stu-id="fa395-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="fa395-120">\*\*\*\*   Las alertas de uso del proceso se emitirán si los recursos del sistema (como la memoria disponible) comienzan a ejecutarse en un nivel bajo.</span><span class="sxs-lookup"><span data-stu-id="fa395-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="fa395-121">Estas alertas se emitirán incluso si Lync Server no es responsable del uso elevado del sistema.</span><span class="sxs-lookup"><span data-stu-id="fa395-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="fa395-122">**Eventos de error del equipo**   se emitirán alertas en caso de un problema de hardware o software que amenace la viabilidad de un servidor.</span><span class="sxs-lookup"><span data-stu-id="fa395-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="fa395-123">Por ejemplo, se notificará a los administradores de Lync Server si un servidor parece estar en peligro de experimentar un error de disco duro.</span><span class="sxs-lookup"><span data-stu-id="fa395-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="fa395-124">En los nuevos módulos de administración también se ha mejorado la creación de informes.</span><span class="sxs-lookup"><span data-stu-id="fa395-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="fa395-125">Los nuevos informes para Lync Server 2013 incluyen:</span><span class="sxs-lookup"><span data-stu-id="fa395-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="fa395-126">**Informe de disponibilidad de escenario de principio a fin**   este informe detalla la disponibilidad o el tiempo activo para los servicios clave de Lync Server, como el registro o la presencia.</span><span class="sxs-lookup"><span data-stu-id="fa395-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="fa395-127">**Informe de capacidad**   con información de contador de rendimiento, este informe muestra las tendencias de los componentes del sistema, como la disponibilidad de la memoria y el uso del procesador.</span><span class="sxs-lookup"><span data-stu-id="fa395-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="fa395-128">**Informe de componentes**   este informe enumera los principales generadores de alertas agrupados por el componente de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa395-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="fa395-129">Además de estos informes prediseñados, los paquetes de administración de Lync Server 2013 notifican automáticamente las alertas para la confiabilidad de las llamadas (métricas que miden el registro detallado de llamadas) y los Estados de la QoE (métricas medidas por calidad de la experiencia).</span><span class="sxs-lookup"><span data-stu-id="fa395-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="fa395-130">Si ha habilitado el registro detallado de llamadas, puede revisar las alertas de confiabilidad de llamadas completando el siguiente procedimiento desde la consola de System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="fa395-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="fa395-131">Expanda **Supervisión**, **Estado de Microsoft Lync Server 2013** y **Confiabilidad de llamadas y calidad de medios**, y haga clic en **Confiabilidad de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="fa395-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="fa395-132">Para ver las alertas de calidad de la experiencia, complete este procedimiento desde la consola de System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="fa395-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="fa395-133">Expanda **Supervisión**, **Estado de Microsoft Lync Server 2013**, **Confiabilidad de llamadas y calidad de medios** y **Calidad de medios**.</span><span class="sxs-lookup"><span data-stu-id="fa395-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="fa395-134">Los paquetes de administración de Lync Server 2013 ahora usan la detección en el nivel de equipo en lugar del mecanismo de detección central usado en Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fa395-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="fa395-135">Esto significa que cada agente de System Center se Descubre a sí mismo e informa de su existencia al servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="fa395-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="fa395-136">El uso de la detección en el nivel de máquina simplifica la administración de la infraestructura de System Center y también permite diferentes versiones de los paquetes de administración de Lync Server (por ejemplo, los módulos de administración de Lync Server 2010 y los paquetes de administración de Lync Server 2013) a simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="fa395-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

