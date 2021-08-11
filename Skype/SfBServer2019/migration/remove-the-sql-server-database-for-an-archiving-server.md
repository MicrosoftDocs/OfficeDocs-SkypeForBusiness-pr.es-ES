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
description: Después de quitar un servidor de archivado, puede quitar las bases de datos SQL Server que hospedaban los datos del grupo. Use los siguientes procedimientos para quitar las definiciones del Generador de topologías y, a continuación, quite los archivos de base de datos y registro del servidor de bases de datos.
ms.openlocfilehash: 3b0b41944941cd6984dec72c52405a1bce63fd8bff87e14cfd94fc723e262d49
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279568"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Quitar la base de datos de SQL Server de un servidor de archivado

Después de quitar un servidor de archivado, puede quitar las bases de datos SQL Server que hospedaban los datos del grupo. Use los siguientes procedimientos para quitar las definiciones del Generador de topologías y, a continuación, quite los archivos de base de datos y registro del servidor de bases de datos.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base SQL Server de datos mediante el Generador de topologías

1. En el Skype Empresarial Server front-end de 2019, abra el Generador de topologías.
    
2. En el Generador de  topologías, vaya a Componentes compartidos y, SQL Server **Almacenes,** haga clic con el botón secundario en la instancia de SQL Server asociada con el servidor de archivado quitado o reconfigurado y, a continuación, haga clic en **Eliminar**.
    
3. Publique la topología y compruebe el estado de replicación. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para quitar los archivos de base de datos del servidor SQL Server

1. Para quitar las bases de datos del servidor SQL Server, debe pertenecer al grupo sysadmin de SQL Server del servidor SQL Server del que se van a eliminar los archivos de base de datos. 
    
2. Abra el Shell Skype Empresarial Server administración.
    
3. Escriba lo siguiente en la línea de comandos:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde es el nombre de dominio completo (FQDN) del servidor de base de datos y es la instancia de base de datos con nombre (es decir, si se  _\<FQDN\>_  _\<instance\>_ definió uno). 
    
4. Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione Y (o Entrar) para continuar, o presione N y, a continuación, Escriba si desea detener el cmdlet (si hay errores). 
    

