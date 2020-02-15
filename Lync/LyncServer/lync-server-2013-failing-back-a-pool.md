---
title: 'Lync Server 2013: conmutación por recuperación de un grupo de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5929ed5fc3d29c0a42c223403a78f83154c5bef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>Conmutación por recuperación de un grupo de servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Una vez que el grupo que experimentó el desastre está de nuevo en línea (es decir, el Grupo1 en este ejemplo), siga los pasos siguientes para restaurar su implementación al estado de funcionamiento normal.

Tenga en cuenta que el proceso de conmutación por error tarda en completarse. Como referencia, un grupo de 20.000  usuarios suele tardar 60 minutos.

1.  Realice la recuperación de los usuarios que estaban hospedados originalmente en el Grupo1 y se han conmutado por error al Grupo2 escribiendo el siguiente cmdlet:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

No es necesario realizar otros. Si se ha producido un error en el servidor de administración central, puede dejarlo en grupo2.

</div>

<span> </span>

</div>

</div>

</div>

