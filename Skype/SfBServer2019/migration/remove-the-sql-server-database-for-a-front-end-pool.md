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
ms.localizationpriority: medium
description: Después de quitar un grupo de servidores front-end o volver a configurar el grupo para que use una base de datos diferente, puede quitar las bases de datos SQL Server que hospedaban los datos del grupo. Use los siguientes procedimientos para quitar las definiciones del Generador de topologías y, a continuación, quite los archivos de base de datos y registro del servidor de bases de datos.
ms.openlocfilehash: 2a11057811035b0dc51810d3a6b7eb8220c7df1f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580114"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Quitar la base de datos de SQL Server para un grupo de servidores front-end

Después de quitar un grupo de servidores front-end o volver a configurar el grupo para que use una base de datos diferente, puede quitar las bases de datos SQL Server que hospedaban los datos del grupo. Use los siguientes procedimientos para quitar las definiciones del Generador de topologías y, a continuación, quite los archivos de base de datos y registro del servidor de bases de datos.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base SQL Server de datos mediante el Generador de topologías

1. Desde el Skype Empresarial Server front-end de 2019, abra el Generador de topologías y descargue la topología existente. 
    
2. En el Generador de topologías, vaya a **Componentes** compartidos y, SQL Server **Almacenes,** haga clic con el botón secundario en la instancia de SQL Server asociada con el grupo de servidores front-end eliminado o reconfigurado y, a continuación, haga clic en **Eliminar**.
    
3. Publique la topología y compruebe el estado de replicación. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Para quitar bases de datos de usuarios y aplicaciones del SQL servidor

1. Para quitar las bases de datos en el servidor SQL, debe ser miembro del grupo sysadmins de SQL Server para el servidor SQL donde va a quitar los archivos de base de datos. 
    
2. Abra Skype Empresarial Server Shell de administración.
    
3. Para quitar la base de datos correspondiente al almacén de usuarios del grupo, escriba lo siguiente:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde es el nombre de dominio completo (FQDN) del servidor de base de datos y es la instancia de base de datos con nombre (es decir, si se  _\<FQDN\>_  _\<instance\>_ definió uno). 
    
4. Para quitar la base de datos correspondiente al almacén de aplicaciones del grupo, escriba lo siguiente:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde es el FQDN del servidor de base de datos y es la instancia de base de datos con nombre  _\<FQDN\>_  _\<instance\>_ (es decir, si se definió una). 
    
5. Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione Y (o Entrar) para continuar, o presione N y, a continuación, Escriba si desea detener el cmdlet (si hay errores). 
    

