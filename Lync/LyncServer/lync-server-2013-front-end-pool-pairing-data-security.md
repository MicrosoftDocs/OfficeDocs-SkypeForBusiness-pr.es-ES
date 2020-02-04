---
title: 'Lync Server 2013: seguridad de datos en el emparejamiento de grupos de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efe51da622107183d3dbf2897a9e2a708acd78dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="c33f7-102">Seguridad de datos en el emparejamiento de grupos de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c33f7-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c33f7-103">_**Última modificación del tema:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="c33f7-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="c33f7-104">El servicio de copia de seguridad es un mecanismo de replicación de datos introducido en Lync Server 2013 que transfiere continuamente los datos de usuario y el contenido de conferencia entre dos grupos front-end de dos en dos centros de datos para fines de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="c33f7-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="c33f7-105">Los datos de usuario contienen URI del SIP del usuario, así como listas de contactos y configuración.</span><span class="sxs-lookup"><span data-stu-id="c33f7-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="c33f7-106">El contenido en conferencia incluye las cargas de Microsoft PowerPoint 2010, así como las pizarras que se usan en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="c33f7-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="c33f7-107">Desde el grupo de origen, los datos del usuario y el contenido de la Conferencia se exportan desde el almacenamiento local, zip, transferido al grupo de destino, donde se descomprime y se importa al almacenamiento local.</span><span class="sxs-lookup"><span data-stu-id="c33f7-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="c33f7-108">El servicio de copia de seguridad supone que el vínculo de comunicación entre los dos centros de datos se encuentra dentro de la red corporativa y que se protege de Internet.</span><span class="sxs-lookup"><span data-stu-id="c33f7-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="c33f7-109">No cifra los datos transferidos entre los dos centros de datos ni se encapsula de forma nativa dentro de un protocolo seguro, como HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c33f7-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="c33f7-110">Por lo tanto, es posible que el ataque de hombre en el medio del personal interno dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="c33f7-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="c33f7-111">Evaluación de los riesgos de seguridad</span><span class="sxs-lookup"><span data-stu-id="c33f7-111">Evaluating Security Risks</span></span>

<span data-ttu-id="c33f7-112">Cualquier empresa que implemente Lync Server 2013 en varios centros de datos y use la característica de recuperación de desastres debe garantizar que el tráfico del centro de datos cruzados esté protegido por su intranet corporativa.</span><span class="sxs-lookup"><span data-stu-id="c33f7-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="c33f7-113">Las empresas que tengan que preocuparse por la protección interna de ataques deben proteger los vínculos de comunicación entre los centros de datos.</span><span class="sxs-lookup"><span data-stu-id="c33f7-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="c33f7-114">El supuesto de que los centros de datos de una empresa estén protegidos detrás de la intranet corporativa es estándar.</span><span class="sxs-lookup"><span data-stu-id="c33f7-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="c33f7-115">Hay muchos otros tipos de datos confidenciales corporativos que se transfieren entre estos centros de datos.</span><span class="sxs-lookup"><span data-stu-id="c33f7-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="c33f7-116">La infraestructura de TI de la empresa está en riesgo de ser arriesgada si estos vínculos del centro de datos cruzados no están protegidos.</span><span class="sxs-lookup"><span data-stu-id="c33f7-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="c33f7-117">Si bien el riesgo de ataques de tipo "Man in the middle" dentro de la red corporativa es real, es relativamente limitado en comparación con la exposición del tráfico en Internet.</span><span class="sxs-lookup"><span data-stu-id="c33f7-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="c33f7-118">En concreto, los datos de usuario expuestos por el servicio de copia de seguridad (como URI de SIP) están generalmente disponibles para todos los empleados de la empresa a través de otros medios, como la libreta de direcciones global de Exchange u otro software de directorio.</span><span class="sxs-lookup"><span data-stu-id="c33f7-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="c33f7-119">Por lo tanto, el foco debe estar en la seguridad de la WAN entre los dos centros de datos cuando se usa el servicio de copia de seguridad para copiar datos entre los dos pools emparejados.</span><span class="sxs-lookup"><span data-stu-id="c33f7-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="c33f7-120">Mitigar los riesgos de seguridad</span><span class="sxs-lookup"><span data-stu-id="c33f7-120">Mitigating Security Risks</span></span>

<span data-ttu-id="c33f7-121">Existen muchas maneras de mejorar la protección de la seguridad del tráfico del servicio de copia de seguridad, que abarca desde restringir el acceso a los centros de datos, a fin de asegurar el transporte WAN entre los dos centros de datos.</span><span class="sxs-lookup"><span data-stu-id="c33f7-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="c33f7-122">En la mayoría de los casos, es posible que las empresas que implementan Lync Server 2013 ya dispongan de la infraestructura de seguridad necesaria.</span><span class="sxs-lookup"><span data-stu-id="c33f7-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="c33f7-123">Para empresas que buscan orientación, Microsoft ofrece la solución como un ejemplo de cómo crear una infraestructura de ti segura.</span><span class="sxs-lookup"><span data-stu-id="c33f7-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="c33f7-124">Sin embargo, esto no implica que sea la única solución, ni implica que es la solución preferida para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c33f7-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="c33f7-125">Recomendamos que los clientes empresariales elijan la solución que se adapte a sus necesidades específicas, en función de la infraestructura y los requisitos de seguridad de ti. La solución de ejemplo de Microsoft emplea IPSec y la Directiva de grupo para el aislamiento de servidor y dominio.</span><span class="sxs-lookup"><span data-stu-id="c33f7-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="c33f7-126">Para obtener más información [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544), consulte.</span><span class="sxs-lookup"><span data-stu-id="c33f7-126">For details, see [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="c33f7-127">Para obtener preguntas y comentarios, póngase en contacto con secwish@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c33f7-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="c33f7-128">Otra posible solución consiste en usar IPsec solamente para que proteger los datos enviados por el propio servicio de copia de seguridad sea más fácil.</span><span class="sxs-lookup"><span data-stu-id="c33f7-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="c33f7-129">Si eliges este método, necesitarás configurar las reglas IPsec del protocolo SMB para los siguientes servidores, donde los grupos A y B son dos grupos de servidores front-end emparejados.</span><span class="sxs-lookup"><span data-stu-id="c33f7-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="c33f7-130">El servicio SMB (TCP/445) de cada servidor front-end del grupo A al almacén de archivos que usa el grupo B.</span><span class="sxs-lookup"><span data-stu-id="c33f7-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="c33f7-131">El servicio SMB (TCP/445) de cada servidor front-end del grupo B al almacén de archivos que usa el grupo A.</span><span class="sxs-lookup"><span data-stu-id="c33f7-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c33f7-132">IPsec no está pensado para reemplazar la seguridad de la aplicación, como SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="c33f7-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="c33f7-133">Una ventaja de utilizar IPsec es que puede ofrecer seguridad de tráfico de red para las aplicaciones existentes sin necesidad de cambiarlas.</span><span class="sxs-lookup"><span data-stu-id="c33f7-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="c33f7-134">Las empresas que, simplemente, quieren proteger el transporte entre los dos centros de datos necesitan consultar a sus respectivos proveedores de hardware de redes sobre las formas de configurar conexiones WAN seguras con los equipos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c33f7-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

