---
title: 'Lync Server 2013: Compatibilidad con protocolo IP y de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a35395c9bb7eb8d90e5618ba6afde17defdbbcfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="ecb9b-102">Compatibilidad con protocolo IP y de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecb9b-102">IP and networking protocol support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecb9b-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ecb9b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ecb9b-104">Lync Server 2013 admite los siguientes protocolos de IP y de red:</span><span class="sxs-lookup"><span data-stu-id="ecb9b-104">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="ecb9b-105">**Protocolos IP.**    Lync Server 2013 admite IP versión 4 (IPv4) o IP versión 6 (IPv6) para la red del servidor.</span><span class="sxs-lookup"><span data-stu-id="ecb9b-105">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecb9b-106">Lync Server 2013 puede funcionar en una red con dos pilas IP habilitadas.</span><span class="sxs-lookup"><span data-stu-id="ecb9b-106">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="ecb9b-107">**Protocolos de transporte SIP.**    De forma genérica, SIP puede usar al menos tres tipos de transporte: Protocolo de datagrama de usuario (UDP), protocolo de control de transmisión (TCP) y seguridad de nivel de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="ecb9b-107">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="ecb9b-108">En la configuración de transporte SIP predeterminada, TLS se ejecuta sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="ecb9b-108">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="ecb9b-109">TLS se usa dentro de la red de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ecb9b-109">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="ecb9b-110">En el extremo de la red, Lync Server 2013 puede interoperar sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="ecb9b-110">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="ecb9b-111">Lync Server 2013 no admite UDP para el transporte SIP porque no cumple con los estándares mínimos de seguridad, confiabilidad y escalabilidad de las comunicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="ecb9b-111">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="ecb9b-112">Para obtener más información, vea el artículo del blog de NextHop, "to UDP, o not to UDP, que es la [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)pregunta" en.</span><span class="sxs-lookup"><span data-stu-id="ecb9b-112">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecb9b-113">El contenido de los blogs y sus URL están sujetos a cambios sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="ecb9b-113">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

