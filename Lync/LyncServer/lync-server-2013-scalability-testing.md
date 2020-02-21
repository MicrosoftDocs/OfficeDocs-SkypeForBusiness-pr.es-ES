---
title: Pruebas de escalabilidad de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be4dc8d08b9d8b1363af67af1a12aa56b59f0b9a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="91f66-102">Pruebas de escalabilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91f66-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91f66-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="91f66-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="91f66-104">Lync Server 2013 proporciona la infraestructura de servidor para todas las comunicaciones en tiempo real de Lync Server, incluidas la mensajería instantánea (mi) y la presencia, la Conferencia y la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="91f66-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="91f66-105">Esto incluye todas las características que usan los recursos de hardware de un grupo de servidores de Lync Server 2013 y, por lo tanto, afectan al rendimiento y la escala.</span><span class="sxs-lookup"><span data-stu-id="91f66-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="91f66-106">No todas las organizaciones usan todas las características del mismo modo.</span><span class="sxs-lookup"><span data-stu-id="91f66-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="91f66-107">Por ejemplo, algunas organizaciones pueden usar vídeo en las conferencias con mucha frecuencia mientras que otras apenas lo usan o no lo usan en absoluto.</span><span class="sxs-lookup"><span data-stu-id="91f66-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="91f66-108">Algunas organizaciones prefieren compartir diapositivas de PowerPoint a realizar un uso compartido de las aplicaciones, mientras que otras prefieren lo contrario.</span><span class="sxs-lookup"><span data-stu-id="91f66-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="91f66-109">Las organizaciones que implementan la telefonía IP empresarial podrían o no usar la aplicación de grupo de respuesta en gran medida.</span><span class="sxs-lookup"><span data-stu-id="91f66-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="91f66-110">La mayoría de las organizaciones implementan servidores de supervisión, pero no muchos de ellos implementan servidores de archivado.</span><span class="sxs-lookup"><span data-stu-id="91f66-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="91f66-111">Además, no todas las organizaciones tienen la misma infraestructura (por ejemplo, las capacidades de hardware y red, o el número y el tamaño de los grupos implementados).</span><span class="sxs-lookup"><span data-stu-id="91f66-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="91f66-112">La diversidad de características e infraestructuras supone un desafío para las pruebas de escalabilidad, ya que no se pueden simular todas las combinaciones posibles de características e infraestructuras.</span><span class="sxs-lookup"><span data-stu-id="91f66-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="91f66-113">Para determinar la compatibilidad de escalabilidad para Lync Server, se realizan pruebas mediante el uso de todas las características de Lync Server a la vez, basadas en un modelo de uso medio (modelo de usuario).</span><span class="sxs-lookup"><span data-stu-id="91f66-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="91f66-114">Para determinar un modelo de usuario adecuado para las cargas de trabajo de Lync Server, analizamos muchos puntos de datos, incluidos los estudios de clientes, los comentarios del programa para la mejora de la experiencia del usuario de Microsoft, los datos de uso de Lync Server del Departamento de TI interno de Microsoft. y los datos extraídos de nuestro servicio Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="91f66-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="91f66-115">En muchos casos, el modelo de usuario incluye una desviación hacia las cargas más pesadas para proporcionar un margen cómodo de uso a la organización.</span><span class="sxs-lookup"><span data-stu-id="91f66-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="91f66-116">En nuestras pruebas de escalabilidad, configuramos los grupos de servidores de Lync Server 2013 de acuerdo con las especificaciones de hardware y software recomendadas, incluidos los componentes de la infraestructura, como los servicios de dominio de Active Directory, los equilibradores de carga de hardware y los firewalls.</span><span class="sxs-lookup"><span data-stu-id="91f66-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="91f66-117">Los entornos de Lync Server se configuran de la forma más parecida posible a los entornos típicos del mundo real.</span><span class="sxs-lookup"><span data-stu-id="91f66-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="91f66-118">A continuación, usamos la herramienta stress and performance de Lync Server 2013 para simular las cargas de Lync Server 2013 (según nuestro modelo de usuario).</span><span class="sxs-lookup"><span data-stu-id="91f66-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="91f66-119">.</span><span class="sxs-lookup"><span data-stu-id="91f66-119">.</span></span>

<span data-ttu-id="91f66-p105">Las pruebas de escalabilidad se repiten varias veces (incluidas varias ejecuciones de pruebas de tres semanas). Los resultados de todas las pruebas se usan para mejorar el ajuste del rendimiento y comprobar la compatibilidad de las cifras de escalabilidad del modelo de usuario.</span><span class="sxs-lookup"><span data-stu-id="91f66-p105">We do multiple iterations of scalability tests (including multiple three-week test runs). We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

