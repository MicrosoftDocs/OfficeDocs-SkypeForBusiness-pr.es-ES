---
title: 'Lync Server 2013: Introducción general a la implementación'
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
ms.openlocfilehash: 3d237e0ba3f94f81ce3988e2ce8994d49f97087d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Introducción general a la implementación para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-12_

La principal diferencia entre Lync Server 2013 Enterprise Edition y Lync Server 2013 Standard es que Standard Edition no es compatible con las características de alta disponibilidad incluidas en Enterprise Edition. Para una alta disponibilidad, necesita implementar varios servidores front-end en un grupo y, a continuación, puede reflejar el servidor que ejecuta SQL Server. Con Enterprise Edition puede elegir Collocate o definir un servidor de mediación independiente. El servidor de supervisión y el servidor de archivado pueden usar un servidor independiente que ejecute SQL Server. O bien, pueden tener instancias de SQL Server ejecutándose en el servidor de bases de datos para los servidores y los grupos de aplicaciones para el usuario.

Los servidores que ejecutan Lync Server 2013 Standard Edition están pensados para organizaciones más pequeñas y ubicaciones remotas, que se han quitado geográficamente de la implementación principal de la organización. Dos servidores de servidor Standard Edition acoplados para conmutación por error en caso de desastre pueden admitir hasta 5.000 usuarios. No puede agrupar servidores Standard Edition como servidores front-end en Enterprise Edition. Además, la base de datos de SQL Server que usa Standard Edition es un servidor en el que se ejecuta SQL Server Express diseñado para controlar las cargas de trabajo de los servidores Standard Edition. Esto no quiere decir que todos los roles deben residir en un servidor Standard Edition. Puede tener servidores de mediación y servidores perimetrales independientes. La base de datos de SQL Server para el almacén de administración central y para los fines de Lync Server 2013 debe residir en el servidor Standard Edition, que se encuentra en el servidor que ejecuta SQL Server. El servidor de supervisión y el servidor de archivado usan un servidor independiente con la base de datos de SQL Server.

</div>

<span> </span>

</div>

</div>

</div>

