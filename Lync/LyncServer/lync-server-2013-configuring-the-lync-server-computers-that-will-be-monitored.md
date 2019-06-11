---
title: 'Lync Server 2013: configuración de los equipos de Lync Server que se supervisarán'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a5d252035820f373183d1927b322a929340716
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="f56ef-102">Configurar los equipos de Lync Server que se supervisarán en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f56ef-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f56ef-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f56ef-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f56ef-104">Puesto que Lync Server 2013 no usa el proceso de detección central que se usa en Microsoft Lync Server 2010, cada equipo de Lync Server 2013 que desee supervisar debe poder autoinformar sobre su existencia en el servidor de administración.</span><span class="sxs-lookup"><span data-stu-id="f56ef-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="f56ef-105">Para que esto sea posible, debe instalar los archivos del agente Operations Manager en cada uno de los equipos que se van a supervisar.</span><span class="sxs-lookup"><span data-stu-id="f56ef-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="f56ef-106">Después de instalar los archivos del agente, debe configurar el equipo para que funcione como un proxy de System Center.</span><span class="sxs-lookup"><span data-stu-id="f56ef-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="f56ef-107">Tenga en cuenta que estos procedimientos deben llevarse a cabo después de haber instalado y configurado Lync Server en estos equipos.</span><span class="sxs-lookup"><span data-stu-id="f56ef-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

