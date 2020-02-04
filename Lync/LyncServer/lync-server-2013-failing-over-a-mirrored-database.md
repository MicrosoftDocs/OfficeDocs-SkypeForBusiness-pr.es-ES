---
title: 'Lync Server 2013: Conmutación por error de una base de datos reflejada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 822a7a2fa13ce444bbaf590ee0d8ba2144debcc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Conmutación por error de una base de datos reflejada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-14_

Si ha configurado la base de datos back-end para usar el reflejo sincronizado con un testigo, la conmutación por error es automática. Si ha configurado el reflejo sincronizado sin un testigo, puede usar los siguientes procedimientos para realizar la conmutación por error y la recuperación de la base de datos. También puede usar estos procedimientos para realizar un failover manual de las bases de datos y hacer un failback, incluso si ha configurado un testigo.

<div>

## <a name="to-fail-over-your-back-end-database"></a>Para conmutar por error a la base de datos back-end

1.  Antes de realizar la conmutación por error, determine qué base de datos back-end es el principal y cuál es el reflejo; para ello, escriba el siguiente cmdlet:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Si el almacén de administración central está hospedado en este grupo, escriba el siguiente cmdlet para determinar cuál es el principal y cuál es el reflejo del almacén central de administración:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Realice la conmutación por error de la base de datos de usuario:
    
      - Si el principal ha fallado y se está produciendo un error en el reflejo, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Si el reflejo ha fallado y se está conmutando por error al principal, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Si el grupo hospeda el servidor de administración central, realice la conmutación por error del almacén de administración central.
    
      - Si el principal ha fallado y se está produciendo un error en el reflejo, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Si el reflejo ha fallado y se está conmutando por error al principal, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

