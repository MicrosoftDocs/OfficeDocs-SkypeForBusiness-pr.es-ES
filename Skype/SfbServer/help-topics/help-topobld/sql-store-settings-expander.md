---
title: Ampliador de configuración de almacén de SQL
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de base de datos de SQL Server. No puede utilizar el cuadro de diálogo Editar propiedades para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede utilizar el cuadro de diálogo Editar propiedades para cambiar la instancia de SQL Server que aloja el almacén de Administración Central.
ms.openlocfilehash: 2a1fc051e3dc848272a7cad539eaa749ff95d9b9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sql-store-settings-expander"></a>Ampliador de configuración de almacén de SQL
 
Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de base de datos de SQL Server. No puede utilizar el cuadro de diálogo **Editar propiedades** para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede utilizar el cuadro de diálogo **Editar propiedades** para cambiar la instancia de SQL Server que aloja el almacén de Administración Central.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Editar las propiedades de una base de datos de SQL Server

Para cambiar la instancia de SQL Server que utiliza cualquier base de datos distinta del almacén de Administración Central, siga el procedimiento siguiente en el generador de topología:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Para modificar una instancia de SQL Server

1. Seleccione la base de datos correspondiente en el nodo **SQL almacena** y, a continuación, haga clic en **Editar propiedades**.
    
2. En el cuadro de diálogo **Editar propiedades** , siga uno de estos procedimientos:
    
  - Para usar la instancia predeterminada de SQL Server, seleccione **Instancia predeterminada** y, a continuación, haga clic en **Aceptar**.
    
  - Para utilizar una instancia con nombre de la base de datos, seleccione la **Instancia con nombre**, escriba el nombre de instancia en el cuadro de texto y, a continuación, haga clic en **Aceptar**. Debe especificar el nombre de instancia (por ejemplo, ArchivingInstance) y no el trazado completo de SQL Server.
    
Cuando se trabaja en el cuadro de diálogo **Editar propiedades** , el generador de topología no comprobará que la instancia de base de datos que ha introducido es una instancia válida. Por ejemplo, si usted inadvertidamente typeArchivingInstanec como nombre de instancia y, a continuación, haga clic en **Aceptar**, el generador de topología aceptará esa instancia no válida. Para poder publicar esta topología, debe corregir este error: si no se encuentra una instancia de SQL Server, el generador de topología no creará esa instancia de.
  

