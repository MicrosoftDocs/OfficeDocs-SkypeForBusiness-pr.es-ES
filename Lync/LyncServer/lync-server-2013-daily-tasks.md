---
title: 'Lync Server 2013: tareas diarias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 777d0fdfc8857022c0a54fcb1cd237b90f68d9d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516647"
---
# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="a1226-102">Tareas diarias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1226-102">Daily tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1226-103">_**Última modificación del tema:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="a1226-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="a1226-104">Para ayudar a garantizar la disponibilidad y confiabilidad de la implementación de Lync Server 2013, debe formar parte de los elementos de prueba y de supervisión de rutina diaria que son muy importantes para el funcionamiento del sistema, lo que incluye la plataforma física, el sistema operativo y todos los servicios importantes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a1226-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="a1226-105">El mantenimiento preventivo y la supervisión proactiva le ayudarán a identificar posibles errores y problemas que puedan afectar negativamente a la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a1226-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="a1226-106">La supervisión de la implementación de Lync Server 2013 implica la comprobación de problemas con conexiones, servicios, recursos del servidor y recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="a1226-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="a1226-107">Los sistemas operativos Windows Server, junto con System Center Operations Manager, y Lync Server le proporcionan muchas herramientas y servicios de supervisión para ayudarle a garantizar que la organización de Lync Server funciona sin problemas.</span><span class="sxs-lookup"><span data-stu-id="a1226-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="a1226-108">Cuando se implementan estas tecnologías juntas, los administradores podrán recibir alertas cuando se produzcan problemas o antes de que ocurran.</span><span class="sxs-lookup"><span data-stu-id="a1226-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="a1226-109">Las ventajas principales de la supervisión diaria son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1226-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="a1226-110">Cumplimiento de los requisitos de rendimiento y disponibilidad de los SLAs definidos.</span><span class="sxs-lookup"><span data-stu-id="a1226-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="a1226-111">Completar correctamente tareas administrativas específicas, como operaciones de copia de seguridad diarias, y comprobar el estado del servidor.</span><span class="sxs-lookup"><span data-stu-id="a1226-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="a1226-112">Detección y solución de problemas, como cuellos de botella en el rendimiento del servidor o necesidad de recursos adicionales antes de que afecten a la productividad.</span><span class="sxs-lookup"><span data-stu-id="a1226-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="a1226-113">Las tareas de mantenimiento diario ayudan al equipo administrativo a definir o establecer criterios o líneas de base para las operaciones normales de los sistemas dentro de la organización, así como para detectar cualquier actividad anormal.</span><span class="sxs-lookup"><span data-stu-id="a1226-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="a1226-114">Es importante implementar estas tareas de mantenimiento diario para que el equipo administrativo pueda capturar y mantener datos sobre la infraestructura de Lync Server 2013, como los niveles de uso, posibles cuellos de botella de rendimiento y cambios administrativos.</span><span class="sxs-lookup"><span data-stu-id="a1226-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="a1226-115">Para ayudar a organizar el rendimiento de las tareas diarias, use la [lista de comprobación de tareas diarias](lync-server-2013-operations-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="a1226-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a1226-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1226-116">See Also</span></span>


[<span data-ttu-id="a1226-117">Lista de comprobación de tareas diarias</span><span class="sxs-lookup"><span data-stu-id="a1226-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

