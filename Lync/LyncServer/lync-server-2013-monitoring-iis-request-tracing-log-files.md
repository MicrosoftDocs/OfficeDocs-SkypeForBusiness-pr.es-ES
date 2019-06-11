---
title: 'Lync Server 2013: supervisión de archivos de registro de seguimiento de solicitudes de IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1257e350dd7695bf132959d6b4cde4843192e41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>Supervisar los archivos de registro de seguimiento de solicitudes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

Al habilitar el seguimiento de solicitudes de servicios de Internet Information Server (IIS) para el servicio de movilidad de Lync Server (MCX), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en el disco por día. El registro de seguimiento de IIS está habilitado de manera predeterminada. Debe supervisar los servidores front-end para asegurarse de que no se quede sin espacio en disco.

De forma predeterminada, IIS almacena los archivos de registro en%\\SystemDrive\\%\\Inetpub registra logfiles.

Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Para obtener más información **** sobre el comando httpLogging [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927), consulte.

</div>

<span> </span>

</div>

</div>

</div>

