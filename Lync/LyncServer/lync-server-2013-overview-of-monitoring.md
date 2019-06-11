---
title: 'Lync Server 2013: información general sobre la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88bfb8170b2334c322c612628daa1f8b9db2473c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="35a8f-102">Información general de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35a8f-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35a8f-103">_**Última modificación del tema:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="35a8f-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="35a8f-104">En Microsoft Lync Server 2013, la supervisión se usa para recopilar información de uso y datos de la calidad de la experiencia (QoE) sobre las sesiones de comunicación en las que participan los usuarios.</span><span class="sxs-lookup"><span data-stu-id="35a8f-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="35a8f-105">Una sesión es un término genérico que cubre la conexión de un usuario a:</span><span class="sxs-lookup"><span data-stu-id="35a8f-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="35a8f-106">Una conferencia</span><span class="sxs-lookup"><span data-stu-id="35a8f-106">Conference</span></span>

  - <span data-ttu-id="35a8f-107">Modalidad de conferencia (como audio/vídeo o uso compartido de aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="35a8f-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="35a8f-108">Otro usuario a través de una conversación punto a punto, como un mensaje instantáneo o una llamada de audio</span><span class="sxs-lookup"><span data-stu-id="35a8f-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35a8f-109">Lync Server 2013 realiza un seguimiento de la información sobre cada sesión: quién llamó a quién; los puntos de conexión que se usaron en la sesión; la duración de la sesión es la última. Cuál fue la calidad percibida de la sesión; y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="35a8f-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="35a8f-110">Sin embargo, Lync Server no graba y almacena la propia llamada real.</span><span class="sxs-lookup"><span data-stu-id="35a8f-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="35a8f-111">Esto incluye también sesiones de mensajería instantánea: aunque Lync Server registra información sobre las sesiones de mensajería instantánea, no mantiene un registro de todos los mensajes instantáneos que se enviaron durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="35a8f-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="35a8f-112">La información de detalles de la llamada recopilada por Lync Server puede utilizarse para cualquier cantidad de usos, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="35a8f-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="35a8f-113">Rentabilidad **de la inversión**.</span><span class="sxs-lookup"><span data-stu-id="35a8f-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="35a8f-114">Los administradores pueden comparar los datos de uso recopilados por el servidor de supervisión con datos similares recopilados para su sistema de telefonía anterior con el fin de mostrar ahorros de costos y ayudar a justificar la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35a8f-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="35a8f-115">**Administración del inventario de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="35a8f-115">**Device Inventory Management**.</span></span> <span data-ttu-id="35a8f-116">La información de administración de activos ayuda a los administradores a identificar los dispositivos antiguos en uso que necesitan ser reemplazados, así como identificar dispositivos caros que no parecen usarse.</span><span class="sxs-lookup"><span data-stu-id="35a8f-116">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="35a8f-117">Servicio de asistencia.</span><span class="sxs-lookup"><span data-stu-id="35a8f-117">Help Desk.</span></span> <span data-ttu-id="35a8f-118">La solución de problemas de datos permite a los ingenieros de soporte determinar por qué falla la llamada de un usuario y hacerlo sin tener que recopilar registros del lado del servidor o del cliente.</span><span class="sxs-lookup"><span data-stu-id="35a8f-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="35a8f-119">Esta información puede ser accesible y comprensible para el personal de soporte técnico que no tiene un profundo conocimiento técnico de Microsoft Lync 2013 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35a8f-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="35a8f-p106">**Solución de problemas del sistema**. Los administradores pueden detectar problemas importantes que pueden impedir que los usuarios finales lleven a cabo tareas básicas, como unirse a una conferencia, realizar una llamada o enviar un mensaje instantáneo.</span><span class="sxs-lookup"><span data-stu-id="35a8f-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="35a8f-122">Además de esta información básica sobre llamadas, el servidor de supervisión también proporciona un mecanismo que permite que los puntos de conexión SIP (como Lync 2013) proporcionen información de solución de problemas a la que el servidor no tendría acceso de otra manera:</span><span class="sxs-lookup"><span data-stu-id="35a8f-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="35a8f-123">**Métricas multimedia que afectan**a la calidad.</span><span class="sxs-lookup"><span data-stu-id="35a8f-123">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="35a8f-124">Estas métricas se ocupan de la transmisión real de la llamada; es decir, proporcionan un tipo de registro de viaje a medida que la llamada viaja por la red.</span><span class="sxs-lookup"><span data-stu-id="35a8f-124">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="35a8f-125">Estas métricas (que incluyen factores como la pérdida de paquetes, la vibración y los tiempos de ida y vuelta) proporcionan información sobre lo que sucedió con la llamada desde el momento en que llegó hasta el momento en que llegó al punto final de la otra persona.</span><span class="sxs-lookup"><span data-stu-id="35a8f-125">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="35a8f-126">**Problemas notificados al usuario final**.</span><span class="sxs-lookup"><span data-stu-id="35a8f-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="35a8f-127">Estas métricas incluyen notificaciones de mala calidad que Lync 2013 presenta a los usuarios finales en casos en los que están demasiado lejos de un micrófono, hablan demasiado de forma suave, tienen una mala conexión de red o experimentan una mala calidad porque otro programa del equipo está consumir los recursos disponibles.</span><span class="sxs-lookup"><span data-stu-id="35a8f-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="35a8f-p109">**Información del entorno**. Estas métricas detallan los factores de calidad de la llamada, como el tipo de micrófono y altavoces que se usan, si el usuario se conecta a través de una conexión VPN y si tiene una conexión inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="35a8f-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="35a8f-130">Al final de cada llamada, los extremos conformes con SIP transmiten automáticamente esta información al servidor front-end que facilita la llamada.</span><span class="sxs-lookup"><span data-stu-id="35a8f-130">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="35a8f-131">No tiene que hacer nada para obtener puntos de conexión para transmitir esa información; ese comportamiento está integrado en el protocolo SIP.</span><span class="sxs-lookup"><span data-stu-id="35a8f-131">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="35a8f-132">Sin embargo, si desea recopilar y almacenar esa información, tendrá que instalar y habilitar la supervisión.</span><span class="sxs-lookup"><span data-stu-id="35a8f-132">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="35a8f-133">Si instala y habilita la supervisión, la información de la llamada se recopila por parte de los agentes que se ejecutan en el servidor front-end y lo retransmiten a un par de bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35a8f-133">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="35a8f-134">Tenga en cuenta que el proceso de instalación y configuración de la supervisión se ha simplificado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35a8f-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="35a8f-135">En versiones anteriores del software, la supervisión requería una función de servidor de supervisión independiente, que normalmente significaba un equipo independiente reservado para su uso como servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="35a8f-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="35a8f-136">En Lync Server 2013, sin embargo, se eliminó la función de servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="35a8f-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="35a8f-137">En su lugar, el servicio de supervisión (en forma de "agentes de recopilación de datos unificados") se ha colocado en todos los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="35a8f-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="35a8f-138">Esto tiene al menos dos beneficios principales.</span><span class="sxs-lookup"><span data-stu-id="35a8f-138">This has at least two major benefits.</span></span> <span data-ttu-id="35a8f-139">Collocation del servicio de supervisión:</span><span class="sxs-lookup"><span data-stu-id="35a8f-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="35a8f-140">Disminuye el número de roles de servidor necesarios al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35a8f-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="35a8f-141">Disminuir la función de servidor de supervisión también ayuda a reducir los costos al eliminar la necesidad de mantener servidores dedicados para la supervisión.</span><span class="sxs-lookup"><span data-stu-id="35a8f-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="35a8f-142">Reduce la complejidad de la configuración y la administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35a8f-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="35a8f-143">Al collocating los servicios de supervisión en cada servidor front-end que ya no necesita para instalar, configurar y administrar la función de servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="35a8f-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="35a8f-144">Para obtener más información, vea el tema sobre la [implementación de la supervisión en Lync server 2013](lync-server-2013-deploying-monitoring.md) en la guía de implementación de lync Server 2013 2013.</span><span class="sxs-lookup"><span data-stu-id="35a8f-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

