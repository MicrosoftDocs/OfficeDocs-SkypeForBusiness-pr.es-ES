---
title: 'Lync Server 2013: validar la configuración del sistema de nombres de dominio para el equilibrio de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d56219dc36859eb37a766a94f827fb0c28a9909
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="8035d-102">Validar la configuración del sistema de nombres de dominio para el equilibrio de carga en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8035d-102">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8035d-103">_**Última modificación del tema:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="8035d-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="8035d-p101">Para admitir el FQDN que usa el equilibrio de carga de DNS, necesita aprovisionar el DNS, de modo que resuelva el FQDN del grupo (como, por ejemplo, pool01.contoso.com) en las direcciones IP de todos los servidores del grupo (por ejemplo, 192.168.1.1, 192.168.1.2, etc.). Necesita incluir solo las direcciones IP de los servidores implementados actualmente.</span><span class="sxs-lookup"><span data-stu-id="8035d-p101">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="8035d-106">Además, si usa el equilibrio de carga de DNS para los grupos de límites, se requieren las siguientes entradas DNS:</span><span class="sxs-lookup"><span data-stu-id="8035d-106">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="8035d-107">Para el servicio perimetral de acceso de Lync Server, debe tener una entrada para cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="8035d-107">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="8035d-108">Cada entrada debe resolver el FQDN del servicio perimetral de acceso de Lync Server (por ejemplo, sip.contoso.com) a la dirección IP del servicio perimetral de acceso de Lync Server en uno de los servidores perimetrales del grupo.</span><span class="sxs-lookup"><span data-stu-id="8035d-108">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="8035d-109">Para el servicio perimetral de conferencias web de Lync Server, debe tener una entrada para cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="8035d-109">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="8035d-110">Cada entrada debe resolver el FQDN del servicio perimetral de conferencias web de Lync Server (por ejemplo, webconf.contoso.com) a la dirección IP del servicio perimetral de conferencias web de Lync Server en uno de los servidores perimetrales del grupo.</span><span class="sxs-lookup"><span data-stu-id="8035d-110">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="8035d-111">Para el servicio perimetral de audio/vídeo de Lync Server, debe tener una entrada para cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="8035d-111">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="8035d-112">Cada entrada debe resolver el FQDN del servicio perimetral de audio/vídeo de Lync Server (por ejemplo, av.contoso.com) a la dirección IP del servicio perimetral de audio/vídeo de Lync Server en uno de los servidores perimetrales del grupo.</span><span class="sxs-lookup"><span data-stu-id="8035d-112">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="8035d-113">Si desea usar el equilibrio de carga de DNS en la interfaz interna del grupo Edge, debe agregar un registro DNS, que resuelve el nombre completo interno del grupo Edge a la dirección IP de cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="8035d-113">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="8035d-114">Para comprobar que DNS está devolviendo los valores correctos para el equilibrio de carga de DNS, debe usar la herramienta nslookup.</span><span class="sxs-lookup"><span data-stu-id="8035d-114">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="8035d-115">Para devolver todos los valores de un registro DNS con Nslookup, debe ejecutar el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="8035d-115">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="8035d-116">Debe ejecutar este comando para cada FQDN usado en la configuración del equilibrio de carga de DNS para comprobar que cada registro configurado para el equilibrio de carga de DNS ha devuelto todas las entradas correctas.</span><span class="sxs-lookup"><span data-stu-id="8035d-116">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

