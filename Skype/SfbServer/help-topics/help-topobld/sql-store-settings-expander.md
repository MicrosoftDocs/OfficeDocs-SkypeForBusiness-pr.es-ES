---
title: Expansor de configuración de almacén SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de la base de datos de SQL Server. No puede usar el cuadro de diálogo Editar propiedades para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede usar el cuadro de diálogo Editar propiedades para cambiar la instancia de SQL Server que hospeda el almacén de administración central.
ms.openlocfilehash: e3b16d8c6eab4f4918ef39b3c4f1ab4d0c6fc057
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219615"
---
# <a name="sql-store-settings-expander"></a>Expansor de configuración de almacén SQL
 
Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de la base de datos de SQL Server. No puede usar el cuadro de diálogo **Editar propiedades** para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede usar el cuadro de diálogo **Editar propiedades** para cambiar la instancia de SQL Server que hospeda el almacén de administración central.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Edición de las propiedades de una base de datos de SQL Server

Para cambiar la instancia de SQL Server que usa cualquier base de datos que no sea el almacén de administración central, realice el siguiente procedimiento en el generador de topologías:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Para modificar una instancia de SQL Server

1. Seleccione la base de datos adecuada en el nodo **almacenes de SQL** y, a continuación, haga clic en **Editar propiedades**.
    
2. En el cuadro de diálogo **Editar propiedades**, realice una de las siguientes acciones:
    
   - Para usar la instancia predeterminada de SQL Server, seleccione **instancia predeterminada** y, a continuación, haga clic en **Aceptar**.
    
   - Para usar una instancia de base de datos con nombre, seleccione **Instancia con nombre**, indique un nombre en el cuadro de texto y haga clic en **Aceptar**. Solo debe escribir el nombre de la instancia (por ejemplo, ArchivingInstance) y no la ruta completa de SQL Server.
    
Cuando trabaje en el cuadro de diálogo **Editar propiedades** , el generador de topologías no comprobará que la instancia de base de datos que ha escrito sea una instancia válida. Por ejemplo, si por equivocación typeArchivingInstanec es el nombre de la instancia y, a continuación, hace clic en **Aceptar**, el generador de topologías aceptará esa instancia no válida. Para poder publicar esta topología, debe corregir este error: Si no se encuentra una instancia de SQL Server, el generador de topologías no creará esa instancia por usted.
  

