---
title: Quitar instancias de SQL Server y bases de datos en el servidor back-end
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Las bases Microsoft SQL Server de datos y las instancias se quitan después de quitar los servidores que dependen de ellas o después de volver a configurar los servidores para que usen otra base de datos. Debe realizar el procedimiento descrito en este tema cuando retire el SQL Server actual o vuelva a configurar el servidor actual de modo que las bases de datos queden obsoletas o no disponibles.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752162"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Quitar instancias de SQL Server y bases de datos en el servidor back-end

Las bases Microsoft SQL Server de datos y las instancias se quitan después de quitar los servidores que dependen de ellas o después de volver a configurar los servidores para que usen otra base de datos. Debe realizar el procedimiento descrito en este tema cuando retire el SQL Server actual o vuelva a configurar el servidor actual de modo que las bases de datos queden obsoletas o no disponibles.
  
Para quitar las bases de datos o instancias del servidor de archivado o del servidor de supervisión, primero debe quitar el rol de servidor. Del mismo modo, para quitar las instancias o bases de datos del grupo de servidores front-end, primero debe quitar o volver a configurar el rol de servidor dependiente. Estos procedimientos no distinguen entre bases de datos combinadas o instancias independientes de los servidores. Los procedimientos no se ven afectados por la combinación de bases de datos.
  
## <a name="in-this-section"></a>En esta sección

- [Quitar la base de datos de SQL Server para un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Quitar la base de datos de SQL Server de un servidor de supervisión](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Quitar la base de datos de SQL Server de un servidor de archivado](remove-the-sql-server-database-for-an-archiving-server.md)
    

