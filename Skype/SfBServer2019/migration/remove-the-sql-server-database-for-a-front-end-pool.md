---
title: Quitar la base de datos de SQL Server para un grupo de servidores front-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de quitar un grupo de servidores Front-End o volver a configurar el grupo de servidores para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedan los datos del grupo de servidores. Use los procedimientos siguientes para quitar las definiciones de generador de topología y, a continuación, quitar los archivos de registro y base de datos desde el servidor de base de datos.
ms.openlocfilehash: 4ba60a905d5f4cda56cf5277e1be2db80d906ca0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893785"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Quitar la base de datos de SQL Server para un grupo de servidores front-end

Después de quitar un grupo de servidores Front-End o volver a configurar el grupo de servidores para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedan los datos del grupo de servidores. Use los procedimientos siguientes para quitar las definiciones de generador de topología y, a continuación, quitar los archivos de registro y base de datos desde el servidor de base de datos.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base de datos de SQL Server mediante el generador de topología

1. De Skype para profesionales de 2019 Front-End Server, abra el generador de topologías y descargue la topología existente. 
    
2. En el generador, vaya a **Componentes compartidos** y, a continuación, en **Almacenes de SQL Server**, haga clic en la instancia de SQL Server asociada con el grupo de servidores Front-End se ha quitado o reconfigurado y, a continuación, haga clic en **Eliminar**.
    
3. Publique la topología y, a continuación, compruebe el estado de replicación. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Para quitar las bases de datos de usuario y la aplicación de SQL server

1. Para quitar las bases de datos en SQL server, debe ser miembro del grupo de administradores del sistema de SQL Server para el que se van a eliminar los archivos de base de datos SQL server. 
    
2. Abra Skype para Shell de administración de servidor empresarial.
    
3. Para quitar la base de datos para el almacén de usuario del grupo, escriba:
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde _ \<FQDN\> _ es el nombre de dominio completo (FQDN) del servidor de base de datos, y _ \<instancia\> _ es la instancia con nombre de la base de datos (es decir, si se ha definido uno). 
    
4. Para quitar la base de datos para el almacén de aplicación de grupo de servidores, escriba:
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde _ \<FQDN\> _ es el FQDN del servidor de base de datos, y _ \<instancia\> _ es la instancia con nombre de la base de datos (es decir, si se ha definido uno). 
    
5. Cuando el cmdlet **Uninstall-CsDataBase** en el que se le pide que confirme acciones, lea la información y, a continuación, presione S (o ENTRAR) para continuar, o presione N y, a continuación, ENTRAR si desea detener el cmdlet (si hay errores). 
    

