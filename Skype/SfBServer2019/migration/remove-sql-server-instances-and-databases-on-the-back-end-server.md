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
description: Se quitan las Microsoft SQL Server de datos y las instancias después de quitar los servidores que dependen de ellos o después de volver a configurar los servidores para que usen otra base de datos. Debe realizar el procedimiento de este tema al retirar el SQL Server actual o volver a configurar el servidor actual de forma que las bases de datos estén obsoletas o no estén disponibles.
ms.openlocfilehash: f9e942f1f5516c0bf3437dd3fc9e2dc25b4cc4236e3cffabbf07ff08dde1e404
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306213"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Quitar instancias de SQL Server y bases de datos en el servidor back-end

Se quitan las Microsoft SQL Server de datos y las instancias después de quitar los servidores que dependen de ellos o después de volver a configurar los servidores para que usen otra base de datos. Debe realizar el procedimiento de este tema al retirar el SQL Server actual o volver a configurar el servidor actual de forma que las bases de datos estén obsoletas o no estén disponibles.
  
Para quitar las bases de datos o instancias del servidor de archivado o del servidor de supervisión, primero debe quitar el rol de servidor. Del mismo modo, para quitar las instancias o bases de datos del grupo de servidores front-end, primero debe quitar o volver a configurar el rol de servidor dependiente. Estos procedimientos no distinguen entre bases de datos combinadas o instancias independientes de los servidores. Los procedimientos no se ven afectados por la combinación de bases de datos.
  
## <a name="in-this-section"></a>En esta sección

- [Quitar la base de datos de SQL Server para un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Quitar la base de datos de SQL Server de un servidor de supervisión](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Quitar la base de datos de SQL Server de un servidor de archivado](remove-the-sql-server-database-for-an-archiving-server.md)
    

