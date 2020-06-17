---
title: Quitar la base de datos de SQL Server para un grupo de servidores front-end
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
description: Después de quitar un grupo de servidores front-end o volver a configurar el grupo para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo. Use los procedimientos siguientes para quitar las definiciones del generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753412"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Quitar la base de datos de SQL Server para un grupo de servidores front-end

Después de quitar un grupo de servidores front-end o volver a configurar el grupo para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo. Use los procedimientos siguientes para quitar las definiciones del generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base de datos de SQL Server mediante el generador de topologías

1. Desde el servidor front-end de Skype empresarial Server 2019, abra el generador de topologías y descargue la topología existente. 
    
2. En el generador de topologías, vaya a **componentes compartidos** y a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada con el grupo de servidores front-end quitado o reconfigurado y, a continuación, haga clic en **eliminar**.
    
3. Publique la topología y compruebe el estado de replicación. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Para quitar las bases de datos de usuario y de aplicación del servidor SQL Server

1. Para quitar las bases de datos de SQL Server, debe ser miembro del grupo sysadmins de SQL Server para el servidor SQL Server en el que va a quitar los archivos de base de datos. 
    
2. Abra el shell de administración de Skype empresarial Server.
    
3. Para quitar la base de datos correspondiente al almacén de usuarios del grupo, escriba lo siguiente:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde _\<FQDN\>_ es el nombre de dominio completo (FQDN) del servidor de base de datos y _\<instance\>_ es la instancia de base de datos con nombre (es decir, si se definió una). 
    
4. Para quitar la base de datos correspondiente al almacén de aplicaciones del grupo, escriba lo siguiente:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde _\<FQDN\>_ es el FQDN del servidor de base de datos y _\<instance\>_ es la instancia de base de datos con nombre (es decir, si se definió una). 
    
5. Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione s (o entrar) para continuar, o presione N y, a continuación, entrar si desea detener el cmdlet (si hay errores). 
    

