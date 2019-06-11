---
title: 'Lync Server 2013: Conmutación por recuperación de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cade83015f57e86e08978ac3bfd9fb848dae9563
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>Conmutación por recuperación de grupo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Después de que el grupo que experimentó el desastre vuelva a estar conectado (es decir, Pool1 en este ejemplo), siga estos pasos para restaurar la implementación a su estado de funcionamiento normal.

Tenga en cuenta que el proceso de recuperación tras error tarda varios minutos en completarse.Como referencia, se espera que tarde 60 minutos como máximo para un grupo de 20 000 usuarios.

1.  Conmutar por error a los usuarios que originalmente se encontraban en Pool1 y se ha producido un error en Pool2 escribiendo el siguiente cmdlet:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

No es necesario realizar ningún otro paso. Si se ha producido un error en el servidor de administración central, puede dejarlo en Pool2.

</div>

<span> </span>

</div>

</div>

</div>

