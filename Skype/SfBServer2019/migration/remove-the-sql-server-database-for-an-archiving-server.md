---
title: Quitar la base de datos de SQL Server de un servidor de archivado
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
description: Después de quitar un servidor de archivado, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo. Use los procedimientos siguientes para quitar las definiciones del generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753312"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Quitar la base de datos de SQL Server de un servidor de archivado

Después de quitar un servidor de archivado, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo. Use los procedimientos siguientes para quitar las definiciones del generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base de datos de SQL Server mediante el generador de topologías

1. En el servidor front-end de Skype empresarial Server 2019, abra el generador de topologías.
    
2. En el generador de topologías, vaya a **componentes compartidos** y, a continuación, a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada con el servidor de archivado quitado o reconfigurado y, a continuación, haga clic en **eliminar**.
    
3. Publique la topología y compruebe el estado de replicación. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para quitar los archivos de base de datos del servidor SQL Server

1. Para quitar las bases de datos del servidor SQL Server, debe pertenecer al grupo sysadmin de SQL Server del servidor SQL Server del que se van a eliminar los archivos de base de datos. 
    
2. Abra el shell de administración de Skype empresarial Server.
    
3. Escriba lo siguiente en la línea de comandos:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde _\<FQDN\>_ es el nombre de dominio completo (FQDN) del servidor de base de datos y _\<instance\>_ es la instancia de base de datos con nombre (es decir, si se definió una). 
    
4. Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione s (o entrar) para continuar, o presione N y, a continuación, entrar si desea detener el cmdlet (si hay errores). 
    

