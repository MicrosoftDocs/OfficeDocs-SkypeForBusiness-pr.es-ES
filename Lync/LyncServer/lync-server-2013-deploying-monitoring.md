---
title: 'Lync Server 2013: implementación de la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49d62537f91145803f60f51c18b86816a0af657f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="99260-102">Implementación de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99260-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99260-103">_**Última modificación del tema:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="99260-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="99260-104">Se han realizado cambios importantes en la infraestructura de supervisión de Microsoft Lync Server 2013, comenzando con el hecho de que la función de servidor de supervisión está en desuso.</span><span class="sxs-lookup"><span data-stu-id="99260-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="99260-105">En lugar de roles de servidor de supervisión independientes (que normalmente requerían que las organizaciones configuraran equipos dedicados para que actuaran como servidores de supervisión) se instalan ahora servicios de supervisión en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="99260-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="99260-106">Entre otras cuestiones, este cambio ayuda a:</span><span class="sxs-lookup"><span data-stu-id="99260-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="99260-107">Reduzca el número de roles de servidor necesarios al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="99260-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="99260-108">En este caso, al dejar de usar el servidor de supervisión también se contribuye a reducir costes eliminando la necesidad de mantener servidores dedicados para supervisión.</span><span class="sxs-lookup"><span data-stu-id="99260-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="99260-109">Reduzca la complejidad de la configuración y la administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99260-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="99260-110">Al instalar automáticamente los servicios de supervisión en cada servidor front-end ya no tiene que instalar, configurar y administrar el rol del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="99260-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99260-111">El rol de servidor de archivado también está en desuso en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="99260-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="99260-112">Al igual que los servicios de supervisión, los servicios de archivado de Lync Server 2013 ahora se colocan en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="99260-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="99260-113">Esto es importante tenerlo en cuenta simplemente porque la supervisión y el archivado a menudo comparten la misma instancia de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99260-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="99260-114">Como puede esperar, estos cambios tienen un impacto principal en la manera en que se instalan y se administran los servicios de supervisión.</span><span class="sxs-lookup"><span data-stu-id="99260-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="99260-115">Por ejemplo, como el rol del servidor de supervisión ya no existe, el nodo del servidor de supervisión se ha quitado del generador de topologías de Lync Server; a su vez, esto significa que ya no usa el nuevo servidor de supervisión del generador de topologías para agregar un nuevo servidor de supervisión a la topología.</span><span class="sxs-lookup"><span data-stu-id="99260-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="99260-116">(El asistente ya no existe). En su lugar, normalmente implementará los servicios de supervisión en la topología completando los dos pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="99260-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="99260-117">Habilitación de la supervisión al mismo tiempo que configura un nuevo grupo de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99260-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="99260-118">(En Lync Server 2013, la supervisión está habilitada o deshabilitada de forma agrupada por grupo). Tenga en cuenta que puede habilitar la supervisión de un grupo de servidores sin realmente recopilar datos de supervisión, un proceso que se explica en la sección configuración del registro de detalles de llamadas y de la calidad de la experiencia de esta documentación.</span><span class="sxs-lookup"><span data-stu-id="99260-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="99260-p107">Asociando un almacén de supervisión (es decir, una base de datos de supervisión) con el nuevo grupo de servidores. Tenga en cuenta que un único almacén de supervisión se puede asociar con varios grupos de servidores. En función del número de usuarios hospedados en sus grupos de servidores del registrador, eso significa que no tiene que configurar una base de datos de supervisión independiente para cada uno de sus grupos de servidores. En su lugar, el almacén de supervisión único se puede usar por varios grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="99260-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="99260-p108">Aunque a menudo es más sencillo habilitar la supervisión al mismo tiempo que crea un nuevo grupo de servidores, también es posible crear un nuevo grupo de servidores con la supervisión deshabilitada. Si lo hace, posteriormente podrá usar el Generador de topología para habilitar el servicio: el Generador de topologías ofrece una manera de habilitar o deshabilitar la supervisión para un grupo de servidores, o para asociar un grupo de servidores con un almacén de supervisión diferente. Tenga en cuenta que aunque ya no hay un rol de servidor de supervisión, todavía tendrá que crear uno o más almacenes de supervisión: bases de datos back-end usadas para almacenar los datos recopilados por el servicio de supervisión. Estas bases de datos back-end se pueden crear con Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="99260-p108">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled. If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store. Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service. These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99260-127">Si se ha habilitado la supervisión para un grupo de servidores, puede deshabilitar el proceso de recopilación de datos de supervisión sin tener que cambiar la topología: el shell de administración de Lync Server proporciona una forma de deshabilitar (y volver a habilitar) el registro detallado de llamadas (CDR) o la calidad de la experiencia (QoE) de recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="99260-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="99260-128">Para obtener más información, vea la sección de configuración del registro de detalles de llamadas y los valores de calidad de experiencia de este documento.</span><span class="sxs-lookup"><span data-stu-id="99260-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="99260-129">Otra mejora importante para la supervisión en Lync Server 2013 es que los informes de supervisión de Lync Server ahora admiten IPv6: los informes que usan el campo de dirección IP mostrarán las direcciones IPv4 o IPv6, según: 1) la consulta SQL que se usa; y 2) donde la dirección IPv6 se almacena en la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="99260-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99260-130">Asegúrese de que el tipo de inicio del servicio Agente SQL Server es automático y de que el servicio del Agente SQL Server se está ejecutando para la instancia de SQL que retiene las bases de datos de supervisión, de modo que los trabajos de mantenimiento de SQL Server de supervisión predeterminada puedan ejecutarse de acuerdo a su programación. bajo el control del servicio del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99260-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="99260-131">Esta documentación le guiará por el proceso de instalación y configuración de los informes de supervisión y supervisión para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="99260-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="99260-132">La documentación proporciona instrucciones detalladas que le ayudarán a:</span><span class="sxs-lookup"><span data-stu-id="99260-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="99260-133">Habilitar la supervisión en su topología y asociar un almacén de supervisión a un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="99260-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="99260-134">Instale SQL Server Reporting Services y los informes de supervisión de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99260-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="99260-135">Los informes de supervisión son informes preconfigurados que ofrecen diferentes vistas sobre la información almacenada en una base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="99260-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="99260-136">Configure el registro de detalles de llamada (CDR) y la recopilación de datos de calidad de experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="99260-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="99260-137">El registro detallado de llamadas permite realizar un seguimiento del uso de las capacidades de Lync Server, como llamadas telefónicas de voz sobre IP (VoIP); mensajería instantánea (mi); transferencias de archivos; Conferencia de audio/vídeo (A/V); y sesiones de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="99260-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="99260-138">Las métricas QoE controlan la calidad de las llamadas de audio y vídeo de la organización, incluyen datos sobre el número de paquetes perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).</span><span class="sxs-lookup"><span data-stu-id="99260-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="99260-139">Depure manualmente los registros de CDR y/o QoE de la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="99260-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

