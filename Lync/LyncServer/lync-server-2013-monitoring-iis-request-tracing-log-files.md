---
title: 'Lync Server 2013: supervisión de archivos de registro de seguimiento de solicitudes de IIS'
description: 'Lync Server 2013: supervisión de archivos de registro de seguimiento de solicitudes de IIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09692b79b1cc59ad18ad520885c0a795736b53cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569956"
---
# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="1248a-103">Supervisión de los archivos de registro de seguimiento de solicitudes de IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1248a-103">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1248a-104">_**Última modificación del tema:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="1248a-104">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="1248a-105">Cuando se habilita el seguimiento de solicitudes de Internet Information Services (IIS) para Lync Server Mobility Service (MCX), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en disco por día.</span><span class="sxs-lookup"><span data-stu-id="1248a-105">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="1248a-106">El registro de seguimiento de IIS está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1248a-106">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="1248a-107">Debe supervisar los servidores front-end para asegurarse de que no se quede sin espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="1248a-107">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="1248a-108">De forma predeterminada, IIS almacena los archivos de registro en% SystemDrive% \\ Inetpub \\ \\ logfiles registros.</span><span class="sxs-lookup"><span data-stu-id="1248a-108">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="1248a-109">Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1248a-109">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="1248a-110">Para obtener más información sobre el comando **httpLogging** , consulte [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927) .</span><span class="sxs-lookup"><span data-stu-id="1248a-110">For details about the **httpLogging** command, see [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

