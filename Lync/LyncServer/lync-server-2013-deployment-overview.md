---
title: 'Lync Server 2013: información general sobre la implementación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d5fd5de9a72002d6ee8bd58ef5367b96634b80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Información general sobre la implementación de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-12_

La principal diferencia entre Lync Server 2013 Enterprise Edition y Lync Server 2013 Standard Edition es que Standard Edition no es compatible con las características de alta disponibilidad incluidas en Enterprise Edition. Para una alta disponibilidad, debe implementar varios servidores front-end en un grupo y, después, puede reflejar el servidor que ejecuta SQL Server. Con Enterprise Edition, puede elegir entre combinar o definir un servidor de mediación independiente. El servidor de supervisión y el servidor de archivado pueden usar un servidor de independiente que ejecute SQL Server. O bien, pueden tener instancias de SQL Server en ejecución en el servidor de bases de datos para los servidores front-end y los grupos de servidores.

Los servidores que ejecutan Lync Server 2013 Standard Edition están pensados para organizaciones más pequeñas y ubicaciones remotas, que se quitan geográficamente de la implementación principal de la organización. Dos servidores de servidor Standard Edition emparejados entre sí para la conmutación por error en caso de desastre pueden admitir hasta 5.000 usuarios. No se pueden agrupar los servidores Standard Edition de la misma manera que los servidores front-end de Enterprise Edition. Además, la base de datos de SQL Server que usa Standard Edition es un servidor colocado que ejecuta SQL Server Express y que está diseñado para administrar cargas de trabajo de servidor Standard Edition. Esto no quiere decir que todos los roles deben residir en un servidor Standard Edition. Puede tener servidores de mediación y servidores perimetrales independientes. La base de datos de SQL Server para el almacén de administración central y para los fines de Lync Server 2013 debe residir en el servidor Standard Edition, combinado con el servidor que ejecuta SQL Server. El servidor de supervisión y el servidor de archivado usan un servidor independiente con la base de datos de SQL Server.

</div>

<span> </span>

</div>

</div>

</div>

