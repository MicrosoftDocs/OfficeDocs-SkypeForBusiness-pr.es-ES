---
title: 'Lync Server 2013: configuración de intervalos de puertos para servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b526611e2e29f1b8d11e731381898a7db5e71aa8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="6627d-102">Configuración de intervalos de puertos para los servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6627d-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6627d-103">_**Última modificación del tema:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="6627d-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="6627d-104">Con los servidores perimetrales no es necesario configurar intervalos de puertos independientes para el uso compartido de audio, vídeo y aplicaciones; del mismo modo, los intervalos de puertos usados para los servidores perimetrales no tienen que coincidir con los intervalos de puertos usados con los servidores de conferencia, aplicación y mediación.</span><span class="sxs-lookup"><span data-stu-id="6627d-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="6627d-105">Antes de continuar con nuestro ejemplo, es importante destacar que aunque esta opción existe, le recomendamos que no cambie los intervalos de puertos, ya que esto puede afectar negativamente a algunos escenarios si sale del intervalo de puertos 50000.</span><span class="sxs-lookup"><span data-stu-id="6627d-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="6627d-106">Por ejemplo, supongamos que ha configurado los servidores de conferencia, aplicación y mediación para que usen estos intervalos de puertos:</span><span class="sxs-lookup"><span data-stu-id="6627d-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6627d-107">Tipo de paquete</span><span class="sxs-lookup"><span data-stu-id="6627d-107">Packet Type</span></span></th>
<th><span data-ttu-id="6627d-108">Puerto inicial</span><span class="sxs-lookup"><span data-stu-id="6627d-108">Starting Port</span></span></th>
<th><span data-ttu-id="6627d-109">Número de puertos reservados</span><span class="sxs-lookup"><span data-stu-id="6627d-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6627d-110">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="6627d-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="6627d-111">40803</span><span class="sxs-lookup"><span data-stu-id="6627d-111">40803</span></span></p></td>
<td><p><span data-ttu-id="6627d-112">8348</span><span class="sxs-lookup"><span data-stu-id="6627d-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6627d-113">Audio</span><span class="sxs-lookup"><span data-stu-id="6627d-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="6627d-114">49152</span><span class="sxs-lookup"><span data-stu-id="6627d-114">49152</span></span></p></td>
<td><p><span data-ttu-id="6627d-115">8348</span><span class="sxs-lookup"><span data-stu-id="6627d-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6627d-116">Vídeo</span><span class="sxs-lookup"><span data-stu-id="6627d-116">Video</span></span></p></td>
<td><p><span data-ttu-id="6627d-117">57500</span><span class="sxs-lookup"><span data-stu-id="6627d-117">57500</span></span></p></td>
<td><p><span data-ttu-id="6627d-118">8034</span><span class="sxs-lookup"><span data-stu-id="6627d-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6627d-119"><strong>Totales</strong></span><span class="sxs-lookup"><span data-stu-id="6627d-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="6627d-120">24730</span><span class="sxs-lookup"><span data-stu-id="6627d-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6627d-121">Como puede ver, los intervalos de puertos para el audio, el vídeo y el uso compartido de aplicaciones se inician en el puerto 40803 y abarcan un total de 24732 puertos.</span><span class="sxs-lookup"><span data-stu-id="6627d-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="6627d-122">Si lo prefiere, puede configurar un servidor perimetral determinado para que utilice estos valores de puerto generales con un comando similar a este del Shell de administración de Communications Server:</span><span class="sxs-lookup"><span data-stu-id="6627d-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="6627d-123">También puede usar el comando siguiente para configurar simultáneamente todos los servidores perimetrales de su organización:</span><span class="sxs-lookup"><span data-stu-id="6627d-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="6627d-124">Puede comprobar la configuración de puerto actual para los servidores perimetrales con este comando del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="6627d-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="6627d-125">Una vez más, aunque proporcionamos estas opciones, se recomienda encarecidamente dejar cosas como para la configuración del puerto.</span><span class="sxs-lookup"><span data-stu-id="6627d-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

