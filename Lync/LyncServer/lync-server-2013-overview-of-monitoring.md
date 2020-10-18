---
title: 'Lync Server 2013: información general sobre la supervisión'
description: 'Lync Server 2013: información general sobre la supervisión.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f27d6aff71442c6193c220154af231481399ac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577326"
---
# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="6050f-103">Información general sobre la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6050f-103">Overview of monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6050f-104">_**Última modificación del tema:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="6050f-104">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="6050f-105">En Microsoft Lync Server 2013, la supervisión se usa para recopilar información de uso y datos de calidad de la experiencia (QoE) sobre las sesiones de comunicación en las que participan los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6050f-105">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="6050f-106">Una sesión es un término genérico que cubre la conexión de un usuario a:</span><span class="sxs-lookup"><span data-stu-id="6050f-106">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="6050f-107">Conferencia</span><span class="sxs-lookup"><span data-stu-id="6050f-107">Conference</span></span>

  - <span data-ttu-id="6050f-108">Modalidad de conferencia (como audio/vídeo o uso compartido de aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="6050f-108">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="6050f-109">Otro usuario a través de una conversación punto a punto, como la mensajería instantánea o una llamada de audio</span><span class="sxs-lookup"><span data-stu-id="6050f-109">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6050f-110">Lync Server 2013 realiza un seguimiento de la información sobre cada sesión: quién ha llamado quién; los puntos de conexión que se usaron en la sesión; la duración de la sesión finalizó por última vez; Cuál era la calidad percibida de la sesión; y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="6050f-110">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="6050f-111">Sin embargo, Lync Server no registra y almacena la propia llamada real.</span><span class="sxs-lookup"><span data-stu-id="6050f-111">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="6050f-112">Esto incluye también sesiones de mensajería instantánea: aunque Lync Server registra información sobre las sesiones de mensajería instantánea, no mantiene un registro de los mensajes instantáneos que se enviaron durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="6050f-112">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="6050f-113">La información de detalles de llamadas recopilada por Lync Server puede usarse para cualquier cantidad de usos, como:</span><span class="sxs-lookup"><span data-stu-id="6050f-113">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="6050f-114">**Retorno de la inversión (ROI)**.</span><span class="sxs-lookup"><span data-stu-id="6050f-114">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="6050f-115">Los administradores pueden comparar los datos de uso recopilados por el servidor de supervisión con datos similares recopilados para el sistema de telefonía anterior con el fin de mostrar ahorros de costos y ayudar a justificar la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6050f-115">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="6050f-116">**Administración del inventario de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="6050f-116">**Device Inventory Management**.</span></span> <span data-ttu-id="6050f-117">La información de administración de activos ayuda a los administradores a identificar los dispositivos antiguos en uso que se deben reemplazar, así como identificar dispositivos caros que no parece que se usen en absoluto.</span><span class="sxs-lookup"><span data-stu-id="6050f-117">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="6050f-118">Servicio de asistencia.</span><span class="sxs-lookup"><span data-stu-id="6050f-118">Help Desk.</span></span> <span data-ttu-id="6050f-119">Los datos de solución de problemas permiten a los ingenieros de soporte técnico determinar por qué se ha producido un error en la llamada de un usuario y hacerlo sin tener que recopilar registros del servidor o del cliente.</span><span class="sxs-lookup"><span data-stu-id="6050f-119">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="6050f-120">El personal de soporte técnico puede tener acceso a esta información y entenderla fácilmente que no tienen un profundo conocimiento técnico de Microsoft Lync 2013 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6050f-120">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="6050f-121">**Solución de problemas del sistema**.</span><span class="sxs-lookup"><span data-stu-id="6050f-121">**System Troubleshooting**.</span></span> <span data-ttu-id="6050f-122">Permite a los administradores detectar los principales problemas que podrían impedir que los usuarios finales realicen tareas básicas, como unirse a una conferencia, establecer una llamada o enviar un mensaje instantáneo.</span><span class="sxs-lookup"><span data-stu-id="6050f-122">Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="6050f-123">Además de esta información básica de llamadas, el servidor de supervisión también proporciona un mecanismo que permite que los extremos SIP (como Lync 2013) proporcionen información de solución de problemas que, de otro modo, el servidor no tendría acceso a:</span><span class="sxs-lookup"><span data-stu-id="6050f-123">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="6050f-124">**Métricas multimedia que afectan**a la calidad.</span><span class="sxs-lookup"><span data-stu-id="6050f-124">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="6050f-125">Estas métricas tratan con la transmisión real de la propia llamada; es decir, proporcionan un tipo de registro de viajes a medida que los recorridos de llamadas a través de la red.</span><span class="sxs-lookup"><span data-stu-id="6050f-125">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="6050f-126">Estas métricas (que incluyen aspectos como la pérdida de paquetes, la vibración y los tiempos de ida y vuelta) proporcionan información sobre lo que sucedió con la llamada desde el momento en que llegó el extremo hasta el momento en que llegó al punto de conexión de la otra persona.</span><span class="sxs-lookup"><span data-stu-id="6050f-126">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="6050f-127">**Problemas notificados al usuario final**.</span><span class="sxs-lookup"><span data-stu-id="6050f-127">**Issues Reported to the End User**.</span></span> <span data-ttu-id="6050f-128">Estas métricas incluyen notificaciones de mala calidad que Lync 2013 presenta a los usuarios finales en los casos en los que están demasiado lejos de un micrófono, hablando con demasiada suavidad, tienen una mala conexión de red o presentan una calidad deficiente porque otro programa del equipo está consumiendo los recursos disponibles.</span><span class="sxs-lookup"><span data-stu-id="6050f-128">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="6050f-129">**Información del entorno**.</span><span class="sxs-lookup"><span data-stu-id="6050f-129">**Environment Information**.</span></span> <span data-ttu-id="6050f-130">Estas métricas detallan los factores de calidad de las llamadas, como el tipo de micrófono y los altavoces que se usan, si el usuario está conectado a través de una conexión VPN y si el usuario está en una conexión inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="6050f-130">These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="6050f-131">Al final de cada llamada, los extremos compatibles con SIP transmiten automáticamente esta información al servidor front-end que facilita la llamada.</span><span class="sxs-lookup"><span data-stu-id="6050f-131">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="6050f-132">No tiene que hacer nada para obtener los extremos para transmitir esa información; ese comportamiento se integra en el protocolo SIP.</span><span class="sxs-lookup"><span data-stu-id="6050f-132">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="6050f-133">Sin embargo, si desea recopilar y almacenar esa información, debe instalar y habilitar la supervisión.</span><span class="sxs-lookup"><span data-stu-id="6050f-133">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="6050f-134">Si instala y habilita la supervisión, la información de llamadas se recopila a través de los agentes que se ejecutan en el servidor front-end y los retransmite a un par de bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6050f-134">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="6050f-135">Tenga en cuenta que el proceso de instalación y configuración de la supervisión se ha simplificado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6050f-135">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="6050f-136">En versiones anteriores del software, la supervisión requería una función de servidor de supervisión independiente, que normalmente significaba un equipo independiente reservado para su uso como servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="6050f-136">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="6050f-137">Sin embargo, en Lync Server 2013, la función del servidor de supervisión se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="6050f-137">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="6050f-138">En su lugar, el servicio de supervisión (en forma de "agentes de recopilación de datos unificados") se ha combinado en todos los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6050f-138">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="6050f-139">Esto tiene al menos dos beneficios principales.</span><span class="sxs-lookup"><span data-stu-id="6050f-139">This has at least two major benefits.</span></span> <span data-ttu-id="6050f-140">Combinación del servicio de supervisión:</span><span class="sxs-lookup"><span data-stu-id="6050f-140">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="6050f-141">Reduce el número de roles de servidor necesarios al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6050f-141">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="6050f-142">La disminución de la función de servidor de supervisión también contribuye a reducir los costos al eliminar la necesidad de mantener servidores dedicados para la supervisión.</span><span class="sxs-lookup"><span data-stu-id="6050f-142">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="6050f-143">Reduce la complejidad de la instalación y administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6050f-143">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="6050f-144">Al combinar los servicios de supervisión en cada servidor front-end que ya no tiene para instalar, configurar y administrar el rol de servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="6050f-144">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="6050f-145">Para obtener más información, consulte el tema [Deploying Monitoring in Lync server 2013](lync-server-2013-deploying-monitoring.md) en la guía de implementación de lync Server 2013 2013.</span><span class="sxs-lookup"><span data-stu-id="6050f-145">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

