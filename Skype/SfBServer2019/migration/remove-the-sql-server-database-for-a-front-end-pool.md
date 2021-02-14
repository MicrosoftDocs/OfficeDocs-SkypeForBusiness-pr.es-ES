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
description: Después de quitar un grupo de servidores front-end o volver a configurarlo para que use una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo. Use los siguientes procedimientos para quitar las definiciones del Generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753412"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Quitar la base de datos de SQL Server para un grupo de servidores front-end

Después de quitar un grupo de servidores front-end o volver a configurarlo para que use una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo. Use los siguientes procedimientos para quitar las definiciones del Generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base SQL Server de datos mediante topology Builder

1. Desde el servidor front-end de Skype Empresarial Server 2019, abra el Generador de topologías y descargue la topología existente. 
    
2. En el Generador de  topologías, vaya a Componentes compartidos y, SQL Server **Almacenes,** haga clic con el botón secundario en la instancia de SQL Server asociada con el grupo de servidores front-end quitado o reconfigurado y, a continuación, haga clic en Eliminar **.**
    
3. Publique la topología y compruebe el estado de replicación. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Para quitar bases de datos de usuarios y aplicaciones del servidor SQL cliente

1. Para quitar las bases de datos del servidor SQL, debe ser miembro del grupo sysadmins de SQL Server para el servidor de SQL en el que va a quitar los archivos de base de datos. 
    
2. Abra el Shell de administración de Skype Empresarial Server.
    
3. Para quitar la base de datos correspondiente al almacén de usuarios del grupo, escriba lo siguiente:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde está el nombre de dominio completo (FQDN) del servidor de base de datos y es la instancia de base de datos con nombre (es decir, si se  _\<FQDN\>_  _\<instance\>_ definió una). 
    
4. Para quitar la base de datos correspondiente al almacén de aplicaciones del grupo, escriba lo siguiente:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dónde está el FQDN del servidor de bases de datos y es la instancia de base de datos con nombre  _\<FQDN\>_  _\<instance\>_ (es decir, si se definió una). 
    
5. Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione Y (o Entrar) para continuar, o presione N y, a continuación, escriba si desea detener el cmdlet (si hay errores). 
    

