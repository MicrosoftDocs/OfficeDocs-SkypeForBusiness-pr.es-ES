---
title: 'Lync Server 2013: conmutación por error de una base de datos reflejada'
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
ms.openlocfilehash: a5be1bfa3a2c9cfac24529de65d91d7b58f13842
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Conmutación por error de una base de datos reflejada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-14_

Si ha configurado su base de datos back-end para que use la creación de reflejos sincronizados con un testigo, la conmutación por error es automática. Si ha configurado la creación de reflejos sincronizados sin testigo, puede usar los siguientes procedimientos para conmutar por error y conmutar por recuperación su base de datos. También puede usar estos procedimientos para conmutar por error y conmutar por recuperación manualmente sus bases de datos aunque haya configurado un testigo.

<div>

## <a name="to-fail-over-your-back-end-database"></a>Procedimiento para conmutar por error su base de datos back-end

1.  Antes de la conmutación por error, determine qué base de datos back-end es la principal y cuál es la reflejada escribiendo el siguiente cmdlet:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Si el almacén de administración central está hospedado en este grupo de servidores, escriba el siguiente cmdlet para determinar cuál es el principal y cuál es el reflejo del almacén de administración central:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Realice la conmutación por error de la base de datos del usuario:
    
      - Si ha fallado la principal y está realizando la conmutación por error de la reflejada, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Si ha fallado la reflejada y está realizando la conmutación por error de la principal, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Si el grupo hospeda el servidor de administración central, realice la conmutación por error del almacén de administración central.
    
      - Si ha fallado la principal y está realizando la conmutación por error de la reflejada, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Si ha fallado la reflejada y está realizando la conmutación por error de la principal, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

