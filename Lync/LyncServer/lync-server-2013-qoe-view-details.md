---
title: 'Lync Server 2013: detalles de la vista QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bba917427e42dcba689d3b248c7d889c798368f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512167"
---
# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="faba6-102">Detalles de la vista QoE en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faba6-102">QoE view details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faba6-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="faba6-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="faba6-104">Las vistas abarcan la mayoría de los escenarios en los que se recuperan datos de la base de datos de SQL de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="faba6-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="faba6-105">Se recomienda usar vistas para crear informes personalizados en lugar de acceder directamente a las tablas de la base de datos, ya que, en futuras versiones de producto, es más probable que las vistas conserven la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="faba6-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="faba6-106">Nombre de la vista</span><span class="sxs-lookup"><span data-stu-id="faba6-106">View Name</span></span></th>
<th><span data-ttu-id="faba6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="faba6-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="faba6-108"><a href="lync-server-2013-audiostreamdetail-view.md">Vista AudioStreamDetail en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="faba6-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="faba6-109">Almacena información sobre cada transmisión de audio en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="faba6-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faba6-110"><a href="lync-server-2013-medialine-view.md">Vista MediaLine en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="faba6-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="faba6-111">Almacena información sobre cada línea de medios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="faba6-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="faba6-112">Una sesión de audio normalmente contiene una línea de medios de audio.</span><span class="sxs-lookup"><span data-stu-id="faba6-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="faba6-113">Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión podría contener dos líneas de medios de vídeo si se usa un dispositivo de conferencias o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="faba6-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faba6-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Vista NetworkConfigurationSettings en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="faba6-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="faba6-115">Almacena información sobre la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="faba6-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faba6-116"><a href="lync-server-2013-session-view.md">Vista de sesión en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="faba6-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="faba6-117">Almacena información sobre las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="faba6-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faba6-118"><a href="lync-server-2013-useragent-view.md">Vista UserAgent en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="faba6-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="faba6-119">Almacena información sobre los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="faba6-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faba6-120"><a href="lync-server-2013-videostreamdetail-view.md">Vista VideoStreamDetail en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="faba6-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="faba6-121">Almacena información sobre cada transmisión de vídeo en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="faba6-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

