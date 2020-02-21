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

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>Supervisión de los archivos de registro de seguimiento de solicitudes de IIS en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

Cuando se habilita el seguimiento de solicitudes de Internet Information Services (IIS) para Lync Server Mobility Service (MCX), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en disco por día. El registro de seguimiento de IIS está habilitado de forma predeterminada. Debe supervisar los servidores front-end para asegurarse de que no se quede sin espacio en disco.

De forma predeterminada, IIS almacena los archivos de registro en%\\SystemDrive\\%\\Inetpub logfiles registros.

Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Para obtener más información **** sobre el comando httpLogging [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927), consulte.

</div>

<span> </span>

</div>

</div>

</div>

