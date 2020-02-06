---
title: Quitar la base de datos de SQL Server para un grupo de servidores front-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de quitar un grupo de servidores front-end o volver a configurar el grupo para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaron los datos del grupo. Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.
ms.openlocfilehash: 8644760f9f3a18f737fcccd80e20eb091efe2f4b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812858"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Quitar la base de datos de SQL Server para un grupo de servidores front-end

Después de quitar un grupo de servidores front-end o volver a configurar el grupo para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaron los datos del grupo. Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base de datos de SQL Server con el generador de topologías

1. Desde el servidor front-end de Skype empresarial Server 2019, abra Topology Builder y descargue la topología existente. 
    
2. En el generador de topología, vaya a **componentes compartidos** y, a continuación, a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada al grupo front-end eliminado o reconfigurado y, a continuación, haga clic en **eliminar**.
    
3. Publique la topología y, a continuación, compruebe el estado de replicación. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Para quitar bases de datos de usuario y de aplicación de SQL Server

1. Para quitar las bases de datos de SQL Server, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor SQL donde va a quitar los archivos de base de datos. 
    
2. Abra el shell de administración de Skype empresarial Server.
    
3. Para quitar la base de datos para el almacén de usuario del grupo, escriba:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde _ \<FQDN\> _ es el nombre de dominio completo (FQDN) del servidor de la base de datos, e _ \<instancia\> _ es la instancia de la base de datos con nombre (es decir, si se definió una). 
    
4. Para quitar la base de datos para el almacén de aplicaciones del grupo, escriba:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde _ \<FQDN\> _ es el nombre completo del servidor de la base de datos e _ \<instancia\> _ es la instancia de la base de datos nombrada (es decir, si se definió una). 
    
5. Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione s (o entrar) para continuar, o presione N y después entrar si quiere detener el cmdlet (si hay errores). 
    

