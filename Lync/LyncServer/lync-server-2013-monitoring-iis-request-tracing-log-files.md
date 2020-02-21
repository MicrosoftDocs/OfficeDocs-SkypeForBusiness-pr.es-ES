---
title: 'Lync Server 2013: supervisión de archivos de registro de seguimiento de solicitudes de IIS'
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
ms.openlocfilehash: d4eb6d1ec984d09f3868ad621add52fb947dd13b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="60909-102">Supervisión de los archivos de registro de seguimiento de solicitudes de IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60909-102">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60909-103">_**Última modificación del tema:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="60909-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="60909-104">Cuando se habilita el seguimiento de solicitudes de Internet Information Services (IIS) para Lync Server Mobility Service (MCX), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en disco por día.</span><span class="sxs-lookup"><span data-stu-id="60909-104">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="60909-105">El registro de seguimiento de IIS está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="60909-105">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="60909-106">Debe supervisar los servidores front-end para asegurarse de que no se quede sin espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="60909-106">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="60909-107">De forma predeterminada, IIS almacena los archivos de registro en%\\SystemDrive\\%\\Inetpub logfiles registros.</span><span class="sxs-lookup"><span data-stu-id="60909-107">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="60909-108">Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60909-108">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="60909-109">Para obtener más información \*\*\*\* sobre el comando httpLogging [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927), consulte.</span><span class="sxs-lookup"><span data-stu-id="60909-109">For details about the **httpLogging** command, see [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

