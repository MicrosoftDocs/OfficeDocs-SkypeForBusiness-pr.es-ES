---
title: Distribución de la carga de conferencias de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baa8230470fc765bbda7c3b2bf49e6962b3db22f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="d1126-102">Distribución de la carga de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1126-102">Conferencing load distribution in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1126-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d1126-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d1126-104">A diferencia de otras soluciones de conferencia dedicadas, la arquitectura de Lync Server es un modelo de hardware compartido.</span><span class="sxs-lookup"><span data-stu-id="d1126-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="d1126-105">Esto significa que muchos componentes de software comparten el mismo hardware, cada uno de los cuales es compatible con diferentes comunicaciones en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="d1126-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="d1126-106">Cada tipo de comunicación en tiempo real coloca cargas específicas en los servidores.</span><span class="sxs-lookup"><span data-stu-id="d1126-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="d1126-107">Por ejemplo, el servidor front-end puede ejecutar los componentes de enrutamiento protocolo de inicio de sesión (SIP), aplicaciones web (como la búsqueda de la libreta de direcciones), servicio de conferencias web, servicio de conferencia A/V, aplicaciones de voz empresariales (por ejemplo, aplicación del operador de conferencias y aplicación de grupo de respuesta) y servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d1126-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="d1126-108">Un conjunto de bases de datos en el servidor front-end también proporciona almacenamiento y procesamiento para datos de usuarios, contactos, presencia, Conferencia y enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="d1126-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="d1126-109">Con este uso compartido de hardware, los componentes, servicios y procesos se compiten por la CPU y los recursos de memoria, de modo que las cargas de trabajo sin conferencias tengan un impacto directo en la escala de servidores.</span><span class="sxs-lookup"><span data-stu-id="d1126-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="d1126-110">Comparado con otras soluciones de conferencia basadas en puertos de hardware, la arquitectura de conferencias de Lync Server es un modelo sin reserva.</span><span class="sxs-lookup"><span data-stu-id="d1126-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="d1126-111">Cuando un usuario programa una reunión, Lync Server crea un registro en la base de datos de conferencia, que almacena los datos de conferencia, pero no reserva los recursos de hardware para la reunión programada con antelación.</span><span class="sxs-lookup"><span data-stu-id="d1126-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="d1126-112">En su lugar, Lync Server tiene lógica de equilibrio de carga integrada para asignar dinámicamente los recursos de conferencia en los servidores front-end de modo que se distribuyan uniformemente en todos los servidores front-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="d1126-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="d1126-113">De esta manera, se aplican y utilizan recursos de hardware, pero hace que resulte desafiante dar soporte a reuniones muy grandes (especialmente sin un plan adecuado).</span><span class="sxs-lookup"><span data-stu-id="d1126-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="d1126-114">Por ejemplo, cuando se ejecuta una agrupación de Lync Server 2013 cerca de su capacidad máxima, cada servidor front-end podría hospedar aproximadamente 125 reuniones de tamaño medio.</span><span class="sxs-lookup"><span data-stu-id="d1126-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="d1126-115">Agregar otra reunión pequeña no sería un problema, pero agregar una reunión de 1000 usuarios sería un problema porque los servidores front-end probablemente no podrían admitir una reunión tan grande al mismo tiempo que las otras 125 reuniones.</span><span class="sxs-lookup"><span data-stu-id="d1126-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

