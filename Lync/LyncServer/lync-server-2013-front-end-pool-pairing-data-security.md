---
title: 'Lync Server 2013: seguridad de datos de emparejamiento de grupo de servidores front-end'
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
ms.openlocfilehash: d86f60e81e053a1ba07878728dd9c7273bd7feeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500727"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="e2232-102">Seguridad de datos de emparejamiento de grupo de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2232-102">Front End pool pairing data security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2232-103">_**Última modificación del tema:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="e2232-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="e2232-104">El servicio de copia de seguridad es un mecanismo de replicación de datos que se incluye en Lync Server 2013 que transfiere datos de usuario y contenido de conferencia entre dos grupos de servidores front-end de forma continua en dos centros de datos para fines de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="e2232-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="e2232-105">Los datos de usuario contienen los URI de SIP, además de listas de contactos y configuraciones.</span><span class="sxs-lookup"><span data-stu-id="e2232-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="e2232-106">El contenido de la Conferencia incluye las cargas de Microsoft PowerPoint 2010, así como las pizarras usadas en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="e2232-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="e2232-107">En el grupo de servidores de origen, los datos de usuario y el contenido de las conferencias se exportan desde el almacenamiento local, se comprimen y se transfieren al grupo de servidores de destino, donde se descomprimirán e importarán al almacenamiento local.</span><span class="sxs-lookup"><span data-stu-id="e2232-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="e2232-108">El Servicio de copia de seguridad supone que el vínculo de comunicaciones entre los dos centros de datos está dentro de la red corporativa protegida de Internet.</span><span class="sxs-lookup"><span data-stu-id="e2232-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="e2232-109">No cifra los datos transferidos entre los centros de datos, ni se encapsulan de forma nativa dentro de un protocolo seguro, como HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e2232-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="e2232-110">Por tanto, cabe la posibilidad de que personal interno desde la red corporativa lance un ataque de tipo "man-in-the-middle" (MitM, o intermediario).</span><span class="sxs-lookup"><span data-stu-id="e2232-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="e2232-111">Evaluación de los riesgos de seguridad</span><span class="sxs-lookup"><span data-stu-id="e2232-111">Evaluating Security Risks</span></span>

<span data-ttu-id="e2232-112">Cualquier empresa que implemente Lync Server 2013 en varios centros de datos y use la característica de recuperación ante desastres debe asegurarse de que el tráfico del centro de datos cruzado esté protegido por su intranet corporativa.</span><span class="sxs-lookup"><span data-stu-id="e2232-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="e2232-113">Las empresas preocupadas por la protección de ataques internos deben proteger los vínculos de comunicación entre los centros de datos.</span><span class="sxs-lookup"><span data-stu-id="e2232-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="e2232-p103">Por regla general, se supone que los centros de datos de una empresa están protegidos detrás de la intranet corporativa. Existen otros muchos tipos de datos confidenciales de la empresa que se transfieren entre estos centros de datos. La infraestructura de TI de la empresa corre un grave riesgo si no protege estos vínculos de comunicación entre centros de datos.</span><span class="sxs-lookup"><span data-stu-id="e2232-p103">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard. There are many other types of corporate sensitive data transferred among these data centers. The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="e2232-p104">Si bien el riesgo de ataques de tipo "man in the middle" dentro de la red corporativa es real, es relativamente limitado en comparación con la exposición del tráfico a Internet. Concretamente, los datos de usuario que expone el Servicio de copia de seguridad (como los URI de SIP) suelen estar disponibles para todos los empleados de la compañía a través de otros medios, como la libreta de direcciones global de Exchange u otros programas informáticos de directorios. Por ello, el principal objetivo deber ser proteger la WAN entre los dos centros de datos cuando se usa el Servicio de copia de seguridad para copiar datos entre los dos grupos de servidores emparejados.</span><span class="sxs-lookup"><span data-stu-id="e2232-p104">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet. Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software. Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="e2232-120">Reducción de los riesgos de seguridad</span><span class="sxs-lookup"><span data-stu-id="e2232-120">Mitigating Security Risks</span></span>

<span data-ttu-id="e2232-121">Hay muchas formas de mejorar la protección de la seguridad para el tráfico del servicio de copia de seguridad, desde restringir el acceso a los centros de datos hasta asegurar el transporte WAN entre los dos centros de datos.</span><span class="sxs-lookup"><span data-stu-id="e2232-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="e2232-122">En la mayoría de los casos, las empresas que implementan Lync Server 2013 podrían tener la infraestructura de seguridad necesaria en su ubicación.</span><span class="sxs-lookup"><span data-stu-id="e2232-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="e2232-123">Para las empresas que buscan orientación, Microsoft proporciona una solución como un ejemplo de cómo crear una infraestructura de ti segura.</span><span class="sxs-lookup"><span data-stu-id="e2232-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="e2232-124">Sin embargo, esto no implica que sea la única solución, ni implica que es la mejor solución para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2232-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="e2232-125">Se recomienda que los clientes empresariales elijan la solución que se ajuste a sus necesidades específicas, en función de los requisitos y la infraestructura de seguridad de ti. La solución de Microsoft de ejemplo emplea IPSec y la Directiva de grupo para el aislamiento de servidor y dominio.</span><span class="sxs-lookup"><span data-stu-id="e2232-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="e2232-126">Para obtener más información, consulte [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) .</span><span class="sxs-lookup"><span data-stu-id="e2232-126">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="e2232-127">Para preguntas y comentarios, póngase en contacto con secwish@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e2232-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="e2232-128">Otra posible solución es usar IPSec solo para ayudar a proteger los datos enviados por el propio servicio de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e2232-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="e2232-129">Si elige este método, debe configurar las reglas IPSec para el protocolo SMB para los siguientes servidores, donde el grupo A y el grupo B son dos grupos de servidores front-end emparejados.</span><span class="sxs-lookup"><span data-stu-id="e2232-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="e2232-130">El servicio SMB (TCP/445) de cada servidor front-end del grupo A al almacén de archivos que usa el grupo B.</span><span class="sxs-lookup"><span data-stu-id="e2232-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="e2232-131">El servicio SMB (TCP/445) de cada servidor front-end del grupo de servidores B al almacén de archivos que usa el grupo A.</span><span class="sxs-lookup"><span data-stu-id="e2232-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e2232-132">IPsec no pretende ser un sustituto de la seguridad de nivel de aplicación, como SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="e2232-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="e2232-133">Una de las ventajas de usar IPsec es que puede proporcionar seguridad de tráfico de red para las aplicaciones existentes sin tener que cambiarlas.</span><span class="sxs-lookup"><span data-stu-id="e2232-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="e2232-134">Las empresas que quieran proteger el transporte entre los dos centros de datos deben consultar a sus respectivos proveedores de hardware de red sobre formas de configurar conexiones WAN seguras mediante el equipo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="e2232-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

