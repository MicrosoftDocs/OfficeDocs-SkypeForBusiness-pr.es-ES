---
title: 'Lync Server 2013: compatibilidad con IP y Protocolo de red'
description: 'Lync Server 2013: compatibilidad con IP y Protocolo de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbd8022dd7197524334e0c70ea0ad875a30446de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553126"
---
# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="459a3-103">Compatibilidad de protocolo de red e IP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="459a3-103">IP and networking protocol support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="459a3-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="459a3-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="459a3-105">Lync Server 2013 admite los siguientes protocolos IP y de red:</span><span class="sxs-lookup"><span data-stu-id="459a3-105">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="459a3-106">**Protocolos IP.**     Lync Server 2013 admite IP versión 4 (IPv4) o IP versión 6 (IPv6) para la red del servidor.</span><span class="sxs-lookup"><span data-stu-id="459a3-106">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="459a3-107">Lync Server 2013 puede funcionar en una red con una pila IP dual habilitada.</span><span class="sxs-lookup"><span data-stu-id="459a3-107">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="459a3-108">**Protocolos de transporte SIP.**     Genéricamente, SIP puede usar al menos tres tipos de transporte: Protocolo de datagramas de usuario (UDP), protocolo de control de transmisión (TCP) y seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="459a3-108">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="459a3-109">En la configuración de transporte SIP predeterminada, TLS se ejecuta sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="459a3-109">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="459a3-110">TLS se usa dentro de la red de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="459a3-110">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="459a3-111">En el perímetro de la red, Lync Server 2013 puede interoperar sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="459a3-111">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="459a3-112">Lync Server 2013 no admite UDP para el transporte SIP porque no cumple con los estándares mínimos para la seguridad, la confiabilidad y la escalabilidad de las comunicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="459a3-112">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="459a3-113">Para obtener más información, consulte el artículo del blog NextHop, "to UDP, or Not to UDP, que es la pregunta" en [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369) .</span><span class="sxs-lookup"><span data-stu-id="459a3-113">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="459a3-114">El contenido de cada blog y su dirección URL están sujetos a cambio sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="459a3-114">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

