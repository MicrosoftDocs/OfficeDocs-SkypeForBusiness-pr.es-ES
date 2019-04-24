---
title: Quitar instancias de SQL Server y bases de datos en el servidor back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Quitar las bases de datos de Microsoft SQL Server y sesiones después de quitar los servidores que ejecutan son dependientes en ellos, o después de volver a configurar los servidores para usar otra base de datos. Debe realizar el procedimiento de este tema al retirar la versión actual de SQL Server o volver a configurar el servidor actual de forma que se representa las bases de datos obsoletos o no está disponible.
ms.openlocfilehash: 531d4c06daa7dacd2a616244c13207b3e79dca4c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231507"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Quitar instancias de SQL Server y bases de datos en el servidor back-end

Quitar las bases de datos de Microsoft SQL Server y sesiones después de quitar los servidores que ejecutan son dependientes en ellos, o después de volver a configurar los servidores para usar otra base de datos. Debe realizar el procedimiento de este tema al retirar la versión actual de SQL Server o volver a configurar el servidor actual de forma que se representa las bases de datos obsoletos o no está disponible.
  
Para quitar las bases de datos o instancias para el servidor de archivado o el servidor de supervisión, primero debe quitar el rol de servidor. De forma similar, para quitar las instancias o las bases de datos para el grupo de servidores Front-End, primero debe quitar o volver a configurar el rol de servidor dependientes. Estos procedimientos no realizar ninguna distinción entre bases de datos combinadas o separada para los servidores. Los procedimientos se ven afectados por la combinación de las bases de datos.
  
## <a name="in-this-section"></a>En esta sección

- [Quitar la base de datos de SQL Server para un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Quitar la base de datos de SQL Server de un servidor de supervisión](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Quitar la base de datos de SQL Server de un servidor de archivado](remove-the-sql-server-database-for-an-archiving-server.md)
    

