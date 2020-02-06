---
title: Quitar la base de datos de SQL Server de un servidor de supervisión
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
description: Después de quitar un servidor de supervisión, puede quitar las bases de datos de SQL Server que hospedaron los datos del servidor. Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.
ms.openlocfilehash: 275c69f2c35428bcff2d12799cad3fbc129abc23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812828"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Quitar la base de datos de SQL Server de un servidor de supervisión

Después de quitar un servidor de supervisión, puede quitar las bases de datos de SQL Server que hospedaron los datos del servidor. Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base de datos de SQL Server con el generador de topologías

1. En el servidor front-end de Skype empresarial Server 2019, abra Topology Builder.
    
2. En el generador de topología, vaya a **componentes compartidos** y, a continuación, a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada al servidor de supervisión eliminado o reconfigurado y, a continuación, haga clic en **eliminar**.
    
3. Publique la topología y, a continuación, compruebe el estado de replicación.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para quitar los archivos de base de datos de SQL Server

1. Para quitar las bases de datos en el servidor basado en SQL Server, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor de SQL Server en el que va a quitar los archivos de base de datos.
    
2. Abra el shell de administración de Skype empresarial Server.
    
3. En la línea de comandos, escriba:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Donde _ \<FQDN\> _ es el nombre de dominio completo (FQDN) del servidor de base de datos _ \<e\> instancia_ es la instancia de base de datos con nombre opcional. 
    
4. Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione s (o entrar) para continuar, o presione N y después entrar si quiere detener el cmdlet (si hay errores). 
    

