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
ms.openlocfilehash: 637897bce0a160a8cc3b199ec6aee3ffd7375852
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="f25cd-102">Implementación de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f25cd-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f25cd-103">_**Última modificación del tema:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="f25cd-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="f25cd-104">Se han realizado cambios importantes en la infraestructura de supervisión de Microsoft Lync Server 2013, comenzando con el hecho de que el rol de servidor de supervisión ha quedado obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f25cd-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="f25cd-105">En lugar de roles de servidor de supervisión independientes (que suelen requerir que las organizaciones configuren equipos dedicados para que actúen como servidores de supervisión), los servicios de supervisión ahora se colocan en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f25cd-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="f25cd-106">Entre otras cosas, este cambio ayuda a:</span><span class="sxs-lookup"><span data-stu-id="f25cd-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="f25cd-107">Reduzca el número de roles de servidor necesarios al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f25cd-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="f25cd-108">En este caso, disminuir la función de servidor de supervisión también ayuda a reducir los costos al eliminar la necesidad de mantener servidores dedicados para la supervisión.</span><span class="sxs-lookup"><span data-stu-id="f25cd-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="f25cd-109">Reduzca la complejidad de la configuración y la administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f25cd-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="f25cd-110">Collocating automáticamente los servicios de supervisión en cada servidor front-end que ya no necesita para instalar, configurar y administrar el rol servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="f25cd-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f25cd-111">El rol servidor de archivado también ha quedado obsoleto en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f25cd-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="f25cd-112">Al igual que los servicios de supervisión, los servicios de archivado de Lync Server 2013 ahora se colocan en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f25cd-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="f25cd-113">Es importante destacar simplemente porque la supervisión y el archivado comparten a menudo la misma instancia de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f25cd-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="f25cd-114">Como cabría esperar, estos cambios tienen una repercusión importante en el modo en que se instalan y administran los servicios de supervisión.</span><span class="sxs-lookup"><span data-stu-id="f25cd-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="f25cd-115">Por ejemplo, puesto que el rol servidor de supervisión ya no existe, el nodo servidor de supervisión se ha quitado del generador de topología de Lync Server; a su vez, esto significa que ya no usará el nuevo Asistente para servidor de supervisión de topología Builder para agregar un nuevo servidor de supervisión a su topología.</span><span class="sxs-lookup"><span data-stu-id="f25cd-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="f25cd-116">(El asistente ya no existe). En su lugar, normalmente implementará servicios de supervisión dentro de su topología completando los dos pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f25cd-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="f25cd-117">Habilitar la supervisión al mismo tiempo que se configura un nuevo grupo de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f25cd-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="f25cd-118">(En Lync Server 2013, la supervisión está habilitada o deshabilitada para cada grupo). Tenga en cuenta que puede habilitar la supervisión de un grupo sin recopilar realmente datos de supervisión, un proceso descrito en la sección configuración de la configuración de registro de detalles de llamadas y calidad de la experiencia de esta documentación.</span><span class="sxs-lookup"><span data-stu-id="f25cd-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="f25cd-p107">Al asociar un almacén de supervisión (es decir, una base de datos de supervisión) con el nuevo grupo de servidores. Tenga en cuenta que un único almacén de supervisión se puede asociar con varios grupos de servidores. En función de la cantidad de usuarios hospedados en los grupos de registradores, no tiene que configurar una base de datos de supervisión independiente para cada uno de los grupos. En su lugar, varios grupos de servidores pueden usar el almacén de supervisión único.</span><span class="sxs-lookup"><span data-stu-id="f25cd-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="f25cd-123">Aunque a menudo es más sencillo habilitar la supervisión al mismo tiempo que crea un nuevo grupo de servidores, también es posible crear un nuevo grupo de servidores con la supervisión deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="f25cd-123">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled.</span></span> <span data-ttu-id="f25cd-124">Si lo hace, posteriormente podrá usar el Generador de topología para habilitar el servicio: el Generador de topologías ofrece una manera de habilitar o deshabilitar la supervisión para un grupo de servidores, o para asociar un grupo de servidores con un almacén de supervisión diferente.</span><span class="sxs-lookup"><span data-stu-id="f25cd-124">If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store.</span></span> <span data-ttu-id="f25cd-125">Tenga en cuenta que, aunque ya no haya un rol de servidor de supervisión, tendrá que crear uno o varios almacenes: bases de datos de back-end usadas para almacenar los datos recopilados por el servicio de supervisión.</span><span class="sxs-lookup"><span data-stu-id="f25cd-125">Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service.</span></span> <span data-ttu-id="f25cd-126">Estas bases de datos de back-end se pueden crear con Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="f25cd-126">These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f25cd-127">Si se ha habilitado la supervisión para un grupo, puede deshabilitar el proceso de recopilación de datos de supervisión sin tener que cambiar su topología: el shell de administración de Lync Server le permite deshabilitar (y volver a habilitar más adelante) la grabación de detalles de llamadas (CDR) o la calidad of Experience (QoE) recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="f25cd-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="f25cd-128">Para obtener más información, vea la sección de configuración del registro de detalles de llamadas y los valores de calidad de experiencia de este documento.</span><span class="sxs-lookup"><span data-stu-id="f25cd-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="f25cd-129">Otra mejora importante para la supervisión en Lync Server 2013 es el hecho de que los informes de supervisión de Lync Server ahora son compatibles con IPv6: los informes que usan el campo dirección IP mostrarán direcciones IPv4 o IPv6, en función de: 1, la consulta SQL que se usa; y 2) donde la dirección IPv6 está almacenada en la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="f25cd-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f25cd-130">Asegúrese de que el tipo de inicio del servicio del Agente SQL Server sea automático y de que el servicio del Agente SQL Server se esté ejecutando para la instancia de SQL que contiene las bases de datos de supervisión, de manera que las tareas de mantenimiento predeterminadas de supervisión de SQL Server puedan ejecutarse según se programaron, bajo el control del servicio del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f25cd-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="f25cd-131">Esta documentación le guiará a través del proceso de instalación y configuración de los informes de supervisión y supervisión de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f25cd-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="f25cd-132">En la documentación se proporcionan instrucciones detalladas que le ayudarán a:</span><span class="sxs-lookup"><span data-stu-id="f25cd-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="f25cd-133">Habilitar la supervisión en la topología y asociar un almacén de supervisión a un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f25cd-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="f25cd-134">Instale SQL Server Reporting Services y los informes de supervisión de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f25cd-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="f25cd-135">Los informes de supervisión son informes previamente configurados que ofrecen diferentes vistas sobre la información almacenada en una base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="f25cd-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="f25cd-136">Configurar la recopilación de datos de grabación de detalles de llamadas (CDR) y calidad de la experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="f25cd-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="f25cd-137">La grabación de detalles de llamadas le permite realizar un seguimiento del uso de las funciones de Lync Server, como llamadas telefónicas de voz a través de IP (VoIP); mensajería instantánea (mi); transferencias de archivos; conferencias de audio y vídeo (A/V); y sesiones de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f25cd-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="f25cd-138">Las métricas QoE controlan la calidad de las llamadas de audio y vídeo de la organización, incluyen datos sobre el número de paquetes perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).</span><span class="sxs-lookup"><span data-stu-id="f25cd-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="f25cd-139">Purgue de forma manual los registros de CDR o de QoE de la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="f25cd-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

