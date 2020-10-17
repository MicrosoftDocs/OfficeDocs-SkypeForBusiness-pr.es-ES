---
title: Quitar instancias de SQL Server y bases de datos en el servidor back-end
description: Quite las bases de datos y las instancias de SQL Server en el servidor back-end.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c87426a3496e6def2ad65775f5dadb1a0141ae3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551286"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Quitar instancias de SQL Server y bases de datos en el servidor back-end

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Quite las bases de datos e instancias de Microsoft SQL Server después de quitar los servidores que ejecutan Lync Server 2010 que dependen de ellos, o después de volver a configurar los servidores que ejecutan Lync Server 2010 para usar otra base de datos. Debe realizar el procedimiento de este tema cuando retire el servidor SQL Server actual o vuelva a configurar el servidor actual que ejecuta Lync Server 2010 de forma que represente las bases de datos obsoletas o no disponibles.

Para quitar las bases de datos o instancias para el servidor de archivado o el servidor de supervisión, primero debe quitar la función de servidor. De forma similar, para quitar las instancias o bases de datos del grupo de servidores front-end, primero debe quitar o volver a configurar la función de servidor dependiente. Estos procedimientos no distinguen entre bases de datos combinadas o instancias independientes de los servidores. Los procedimientos no se ven afectados por la combinación de bases de datos.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Quitar la base de datos de SQL Server para un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Quitar la base de datos de SQL Server de un servidor de supervisión](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Quitar la base de datos de SQL Server de un servidor de archivado](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

