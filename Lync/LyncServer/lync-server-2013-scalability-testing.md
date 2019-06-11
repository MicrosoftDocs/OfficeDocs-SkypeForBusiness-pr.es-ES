---
title: Pruebas de escalabilidad de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f454ad3d78affb7106bcd0e750adae13624d9c9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="c5edc-102">Pruebas de escalabilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5edc-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5edc-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c5edc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c5edc-104">Lync Server 2013 proporciona la infraestructura de servidor para todas las comunicaciones en tiempo real de Lync Server, incluidas la mensajería instantánea (mi) y la presencia, Conferencia y telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="c5edc-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="c5edc-105">Esto incluye todas las características que usan los recursos de hardware de un grupo de 2013 de Lync Server y, por lo tanto, afectan al rendimiento y la escala.</span><span class="sxs-lookup"><span data-stu-id="c5edc-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="c5edc-106">Todas las organizaciones no usan todas las características.</span><span class="sxs-lookup"><span data-stu-id="c5edc-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="c5edc-107">Por ejemplo, es posible que algunas organizaciones usen el vídeo en conferencias muy intensa, mientras que otras pueden tener poco o ningún uso de video.</span><span class="sxs-lookup"><span data-stu-id="c5edc-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="c5edc-108">Algunas organizaciones prefieren el uso compartido de diapositivas de PowerPoint para compartir aplicaciones, mientras que otras prefieren lo opuesto.</span><span class="sxs-lookup"><span data-stu-id="c5edc-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="c5edc-109">Las organizaciones que implementan la telefonía IP empresarial pueden o no usar en gran medida la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5edc-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="c5edc-110">La mayoría de las organizaciones implementan servidores de supervisión, pero no muchos de ellos implementan servidores de archivado.</span><span class="sxs-lookup"><span data-stu-id="c5edc-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="c5edc-111">Además, las organizaciones no tienen las mismas infraestructuras, entre ellas, capacidades de hardware, capacidades de red y la cantidad de pools y el tamaño de los pools implementados.</span><span class="sxs-lookup"><span data-stu-id="c5edc-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="c5edc-112">La diversidad de características e infraestructuras supone un reto para las pruebas de escalabilidad; no es posible simular todas las combinaciones posibles de las características y las infraestructuras.</span><span class="sxs-lookup"><span data-stu-id="c5edc-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="c5edc-113">Para determinar la compatibilidad de escalabilidad de Lync Server, realizamos pruebas con todas las características de Lync Server de forma simultánea, en función de un modelo de uso promedio (modelo de usuario).</span><span class="sxs-lookup"><span data-stu-id="c5edc-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="c5edc-114">Para determinar un modelo de usuario adecuado para las cargas de trabajo de Lync Server, analizamos muchos puntos de datos, entre los que se incluyen encuestas de clientes, comentarios del programa para la mejora de la experiencia del usuario de Microsoft, datos de uso de Lync Server del Departamento de TI interno en Microsoft. y datos extraídos de nuestro servicio de Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="c5edc-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="c5edc-115">En muchos casos, el modelo de usuario tiene un sesgo hacia cargas más pesadas para proporcionar un margen cómodo para el uso dentro de una organización.</span><span class="sxs-lookup"><span data-stu-id="c5edc-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="c5edc-116">En nuestras pruebas de escalabilidad, configuramos los grupos de aplicaciones de Lync Server 2013 según las especificaciones de hardware y software recomendadas, incluidos los componentes de la infraestructura, como los servicios de dominio de Active Directory, los equilibradores de carga de hardware y los firewalls.</span><span class="sxs-lookup"><span data-stu-id="c5edc-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="c5edc-117">La configuración de entornos de Lync Server es lo más parecida a la de los entornos reales típicos.</span><span class="sxs-lookup"><span data-stu-id="c5edc-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="c5edc-118">A continuación, usamos la herramienta de estrés y rendimiento de Lync Server 2013 para simular las cargas de Lync Server 2013 (según nuestro modelo de usuario).</span><span class="sxs-lookup"><span data-stu-id="c5edc-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="c5edc-119">.</span><span class="sxs-lookup"><span data-stu-id="c5edc-119"></span></span>

<span data-ttu-id="c5edc-120">Realizamos varias iteraciones de pruebas de escalabilidad (incluidas varias ejecuciones de prueba de tres semanas).</span><span class="sxs-lookup"><span data-stu-id="c5edc-120">We do multiple iterations of scalability tests (including multiple three-week test runs).</span></span> <span data-ttu-id="c5edc-121">Usamos los resultados de todas las pruebas para ayudar con el ajuste de rendimiento y para comprobar la compatibilidad con los números de escalabilidad en nuestro modelo de usuario.</span><span class="sxs-lookup"><span data-stu-id="c5edc-121">We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

