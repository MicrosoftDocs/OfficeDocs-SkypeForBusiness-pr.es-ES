---
title: 'Lync Server 2013: validar la configuración del sistema de nombres de dominio para el equilibrio de carga'
description: 'Lync Server 2013: validar la configuración del sistema de nombres de dominio para el equilibrio de carga.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a218a79a541e9c9705a8403146fe7e134e8ed827
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547236"
---
# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="d9817-103">Validar la configuración del sistema de nombres de dominio para el equilibrio de carga en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9817-103">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9817-104">_**Última modificación del tema:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="d9817-104">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="d9817-p101">Para admitir el FQDN que usa el equilibrio de carga DNS, debe aprovisionar el DNS de modo que resuelva el FQDN del grupo de servidores (como, por ejemplo, pool01.contoso.com) como las direcciones IP de todos los servidores del grupo de servidores (por ejemplo, 192.168.1.1, 192.168.1.2, etc.). Solo deberá incluir las direcciones IP de los servidores implementados actualmente.</span><span class="sxs-lookup"><span data-stu-id="d9817-p101">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="d9817-107">Además, si usa el equilibrio de carga de DNS para los grupos de servidores perimetrales, se requieren las siguientes entradas DNS:</span><span class="sxs-lookup"><span data-stu-id="d9817-107">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="d9817-108">Para el servicio perimetral de acceso de Lync Server, debe tener una entrada por cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="d9817-108">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="d9817-109">Cada entrada debe resolver el FQDN del servicio perimetral de acceso de Lync Server (por ejemplo, sip.contoso.com) a la dirección IP del servicio perimetral de acceso de Lync Server en uno de los servidores perimetrales del grupo.</span><span class="sxs-lookup"><span data-stu-id="d9817-109">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="d9817-110">Para el servicio perimetral de conferencia Web de Lync Server, debe tener una entrada por cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="d9817-110">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="d9817-111">Cada entrada debe resolver el FQDN del servicio perimetral de conferencia Web de Lync Server (por ejemplo, webconf.contoso.com) en la dirección IP del servicio perimetral de conferencia Web de Lync Server en uno de los servidores perimetrales del grupo.</span><span class="sxs-lookup"><span data-stu-id="d9817-111">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="d9817-112">Para el servicio perimetral de audio y vídeo de Lync Server, debe tener una entrada por cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="d9817-112">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="d9817-113">Cada entrada debe resolver el FQDN del servicio perimetral de audio y vídeo de Lync Server (por ejemplo, av.contoso.com) en la dirección IP del servicio perimetral de audio y vídeo de Lync Server en uno de los servidores perimetrales del grupo.</span><span class="sxs-lookup"><span data-stu-id="d9817-113">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="d9817-114">Si desea usar el equilibrio de carga de DNS en la interfaz interna del grupo de servidores perimetrales, debe agregar un registro DNS, que resuelva el FQDN interno del grupo de servidores perimetrales en la dirección IP de cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="d9817-114">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="d9817-115">Para comprobar que el DNS devuelve los valores correctos para el equilibrio de carga de DNS, debe usar la herramienta nslookup.</span><span class="sxs-lookup"><span data-stu-id="d9817-115">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="d9817-116">Para devolver todos los valores de un registro DNS con Nslookup, debe ejecutar el comando:</span><span class="sxs-lookup"><span data-stu-id="d9817-116">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="d9817-117">Debe ejecutar este comando para cada FQDN usado en la configuración de equilibrio de carga de DNS para comprobar que cada registro configurado para el equilibrio de carga de DNS devolvió todas las entradas correctas.</span><span class="sxs-lookup"><span data-stu-id="d9817-117">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

