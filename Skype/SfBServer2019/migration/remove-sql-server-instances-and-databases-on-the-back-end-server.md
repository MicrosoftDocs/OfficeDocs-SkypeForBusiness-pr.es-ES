---
title: Quitar instancias de SQL Server y bases de datos en el servidor back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede quitar las bases de datos y las instancias de Microsoft SQL Server después de quitar los servidores que dependen de ellos o después de volver a configurar los servidores para que usen otra base de datos. Debe realizar el procedimiento de este tema cuando retire el servidor SQL Server actual o vuelva a configurar el servidor actual de modo tal que represente las bases de datos obsoletas o no disponibles.
ms.openlocfilehash: 2d0902293c675143609dd720cd33734edd538d87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301121"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Quitar instancias de SQL Server y bases de datos en el servidor back-end

Puede quitar las bases de datos y las instancias de Microsoft SQL Server después de quitar los servidores que dependen de ellos o después de volver a configurar los servidores para que usen otra base de datos. Debe realizar el procedimiento de este tema cuando retire el servidor SQL Server actual o vuelva a configurar el servidor actual de modo tal que represente las bases de datos obsoletas o no disponibles.
  
Para quitar las bases de datos o instancias del servidor de archivado o del servidor de supervisión, primero debe quitar el rol de servidor. De forma similar, para quitar las instancias o bases de datos de un grupo de servidores front-end, primero debe quitar o volver a configurar la función de servidor dependiente. Estos procedimientos no hacen distinción entre bases de datos colocadas o instancias independientes para servidores. Los procedimientos no se ven afectados por la collocation de las bases de datos.
  
## <a name="in-this-section"></a>En esta sección

- [Quitar la base de datos de SQL Server para un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Quitar la base de datos de SQL Server de un servidor de supervisión](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Quitar la base de datos de SQL Server de un servidor de archivado](remove-the-sql-server-database-for-an-archiving-server.md)
    

