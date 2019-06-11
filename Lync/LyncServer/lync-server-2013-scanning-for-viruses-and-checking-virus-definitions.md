---
title: 'Lync Server 2013: examen de virus y comprobación de definiciones de virus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 357c2c2053aca6b7b18a966756ece2768a8e71c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="22136-102">Buscar virus y comprobar las definiciones de virus en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22136-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22136-103">_**Última modificación del tema:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="22136-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="22136-104">Se recomienda instalar un producto antivirus de nivel de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="22136-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="22136-105">La mensajería instantánea es una fuente conocida para difundir rápidamente tanto el software malintencionado como el virus en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="22136-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="22136-106">Microsoft Forefront® Security para Lync Server proporciona detección de varios motores con virus, software malintencionado, protección de filtros de archivos y palabras clave y integración transparente con Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="22136-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="22136-107">Además de Forefront Security para Lync Server, también recomendamos encarecidamente instalar una solución antivirus a nivel de archivo para proteger el sistema de archivos del servidor.</span><span class="sxs-lookup"><span data-stu-id="22136-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="22136-108">Es muy importante mantener actualizados los motores de análisis y las definiciones de virus.</span><span class="sxs-lookup"><span data-stu-id="22136-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="22136-109">La configuración y supervisión del estado de las actualizaciones garantiza que se esté usando la información de análisis más reciente para proteger tanto Office Communications Server como el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="22136-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="22136-110">Al usar un software antivirus de nivel de archivo de un tercero en un servidor que ejecuta Lync Server 2013 y Forefront Security para Lync Server, asegúrese de que las carpetas en las que Forefront Security para Lync Server y Lync Server están instaladas no se analizan, para evitar sus daños.</span><span class="sxs-lookup"><span data-stu-id="22136-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="22136-111">Para obtener la lista completa de exclusiones, <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>consulte.</span><span class="sxs-lookup"><span data-stu-id="22136-111">For the full list of exclusions, see <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

