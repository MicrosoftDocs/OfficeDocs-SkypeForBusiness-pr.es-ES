---
title: 'Lync Server 2013: Análisis de virus y comprobación de definiciones de virus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1825b96cc4ef2c0c71e04b369f1cf116b8070eb4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="afecb-102">Detección de virus y comprobación de definiciones de virus en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afecb-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afecb-103">_**Última modificación del tema:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="afecb-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="afecb-104">Se recomienda encarecidamente instalar un producto antivirus en el nivel de mi.</span><span class="sxs-lookup"><span data-stu-id="afecb-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="afecb-105">La mensajería instantánea es un origen muy conocido para la propagación rápida tanto de software malintencionado como de virus en una organización.</span><span class="sxs-lookup"><span data-stu-id="afecb-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="afecb-106">Microsoft Forefront® Security para Lync Server ofrece detección en varios motores con virus, software malintencionado, protección de filtros de archivos y palabras clave e integración sin problemas con Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="afecb-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="afecb-107">Además de Forefront Security para Lync Server, también se recomienda instalar una solución antivirus a nivel de archivo para proteger el sistema de archivos del servidor.</span><span class="sxs-lookup"><span data-stu-id="afecb-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="afecb-108">Es muy importante mantener actualizados los motores de análisis y las definiciones de virus.</span><span class="sxs-lookup"><span data-stu-id="afecb-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="afecb-109">La configuración y supervisión del estado de las actualizaciones garantiza que se esté usando la información de análisis más actualizada para proteger tanto el servidor de Office Communications Server como el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="afecb-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="afecb-110">Cuando se usa un software antivirus de nivel de archivo de un tercero en un servidor que ejecuta Lync Server 2013 y Forefront Security para Lync Server, asegúrese de que no se analizan las carpetas en las que Forefront Security para Lync Server y Lync Server están instalados, para evitar que sus daños.</span><span class="sxs-lookup"><span data-stu-id="afecb-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="afecb-111">Para obtener una lista completa de las exclusiones <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>, consulte.</span><span class="sxs-lookup"><span data-stu-id="afecb-111">For the full list of exclusions, see <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

