---
title: Quitar la base de datos de SQL Server para un servidor de archivado
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de quitar un servidor de archivado, puede quitar las bases de datos de SQL Server que hospedan los datos del grupo de servidores. Use los procedimientos siguientes para quitar las definiciones de generador de topología y, a continuación, quitar los archivos de registro y base de datos desde el servidor de base de datos.
ms.openlocfilehash: b7c1fe6591564a690ea1da55fb65eb1071661d63
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370804"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Quitar la base de datos de SQL Server para un servidor de archivado

Después de quitar un servidor de archivado, puede quitar las bases de datos de SQL Server que hospedan los datos del grupo de servidores. Use los procedimientos siguientes para quitar las definiciones de generador de topología y, a continuación, quitar los archivos de registro y base de datos desde el servidor de base de datos.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base de datos de SQL Server mediante el generador de topología

1. En Skype para profesionales de 2019 Front-End Server, abra el generador de topología.
    
2. En el generador, vaya a **Componentes compartidos** y, a continuación, en **Almacenes de SQL Server**, haga clic en el servidor SQL Server instancia había asociada con el se ha quitado o volver a configurar el servidor de archivado y, a continuación, haga clic en **Eliminar**.
    
3. Publique la topología y, a continuación, comprobar el estado de replicación. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para quitar los archivos de base de datos de SQL Server

1. Para quitar las bases de datos en SQL Server, debe ser miembro del grupo de administradores del sistema de SQL Server para el que se van a eliminar los archivos de base de datos de SQL Server. 
    
2. Abra el Skype para Shell de administración de servidor empresarial.
    
3. En la línea de comandos, escriba:
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde _ \<FQDN\> _ es el nombre de dominio completo (FQDN) del servidor de base de datos, y _ \<instancia\> _ es la instancia con nombre de la base de datos (es decir, si se ha definido uno). 
    
4. Cuando el cmdlet **Uninstall-CsDataBase** en el que se le pide que confirme acciones, lea la información y, a continuación, presione S (o ENTRAR) para continuar, o presione N y, a continuación, ENTRAR si desea detener el cmdlet (si hay errores). 
    

