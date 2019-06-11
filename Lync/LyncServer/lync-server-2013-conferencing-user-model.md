---
title: Modelo de usuario de conferencia de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d4e8f55a9538c9cb70847bc090680662047b6ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="7ee73-102">El modelo de usuario de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ee73-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ee73-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7ee73-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7ee73-104">Una parte crítica del modelo de usuario de conferencia de Lync Server es el tamaño de la reunión.</span><span class="sxs-lookup"><span data-stu-id="7ee73-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="7ee73-105">Después de recopilar datos de los diversos puntos de datos (tal y como se describe en la sección anterior), determinamos lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ee73-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="7ee73-106">La mayoría de las reuniones son pequeñas reuniones de colaboración con un promedio de cuatro a seis participantes</span><span class="sxs-lookup"><span data-stu-id="7ee73-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="7ee73-107">Aproximadamente el 80 por ciento de las reuniones tiene menos de 20 participantes.</span><span class="sxs-lookup"><span data-stu-id="7ee73-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="7ee73-108">el 99,98 por ciento de las reuniones tiene menos de 100 participantes.</span><span class="sxs-lookup"><span data-stu-id="7ee73-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="7ee73-109">Además del tamaño de la reunión, el modelo de usuario de conferencia también tiene en cuenta diversos factores, como:</span><span class="sxs-lookup"><span data-stu-id="7ee73-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="7ee73-110">**Reuniones simultáneas**   ¿cuántos usuarios esperan estar en las reuniones al mismo tiempo?</span><span class="sxs-lookup"><span data-stu-id="7ee73-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="7ee73-111">\*\*\*\*¿Qué tipos de elementos multimedia están disponibles y qué usuarios de las reuniones pueden usarlos?   </span><span class="sxs-lookup"><span data-stu-id="7ee73-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="7ee73-112">\*\*\*\*   ¿Los tipos de usuario son usuarios internos, usuarios remotos, usuarios federados o usuarios anónimos?</span><span class="sxs-lookup"><span data-stu-id="7ee73-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="7ee73-113">**Tiempo de aumento**   de la reunión ¿cuánto tiempo tardan los usuarios de una reunión en unirse a una reunión?</span><span class="sxs-lookup"><span data-stu-id="7ee73-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="7ee73-114">Para obtener más información sobre el modelo de usuario, consulte [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="7ee73-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="7ee73-115">Para determinar el número de reuniones y usuarios que se van a usar para las pruebas, hicimos lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ee73-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="7ee73-116">Ha tomado el número total de usuarios de una organización (por ejemplo, 80.000 usuarios) y la ha multiplicado por la tasa de simultaneidad de la reunión (por ejemplo, el 5% de todos los usuarios) para determinar el número total de usuarios que se espera que estén en las reuniones al mismo tiempo (en este ejemplo , 4000 usuarios).</span><span class="sxs-lookup"><span data-stu-id="7ee73-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="7ee73-117">Dividir el número total de usuarios por el número de servidores de Lync Server 2013, front-end en la implementación (por ejemplo, 8 servidores) para determinar el número estimado de participantes de la reunión por servidor front-end (en este ejemplo, 500 usuarios por servidor front-end).</span><span class="sxs-lookup"><span data-stu-id="7ee73-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="7ee73-118">Divide el número de usuarios por servidor front-end por el tamaño medio de la reunión (por ejemplo, 4 usuarios) para determinar el número promedio estimado de reuniones por servidor front-end (en este ejemplo, 125 reuniones por servidor front-end).</span><span class="sxs-lookup"><span data-stu-id="7ee73-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="7ee73-119">Para obtener la carga por multimedia de cada servidor front-end, hemos estimado la combinación de medios.</span><span class="sxs-lookup"><span data-stu-id="7ee73-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="7ee73-120">Por ejemplo, suponiendo que el 75% de las reuniones necesite algo más que compatibilidad de audio y el 50% de esas reuniones requieren compartir aplicaciones, un promedio de 47 reuniones y 188 usuarios se conectan simultáneamente a cada servidor front-end para el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7ee73-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="7ee73-121">Se han probado diversos tamaños de reunión (basados en nuestro modelo de usuario de hasta 250 usuarios en un grupo compartido) para garantizar la escalabilidad del servidor.</span><span class="sxs-lookup"><span data-stu-id="7ee73-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

