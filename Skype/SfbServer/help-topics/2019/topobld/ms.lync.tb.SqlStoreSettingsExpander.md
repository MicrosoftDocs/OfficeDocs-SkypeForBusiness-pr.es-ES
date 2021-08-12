---
title: Expansor de configuración de almacén SQL
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar las propiedades de una SQL Server base de datos, debe cambiar la SQL Server de base de datos. No puede usar el cuadro de diálogo Editar propiedades para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede usar el cuadro de diálogo Editar propiedades para cambiar la instancia de SQL Server que hospeda el almacén de administración central.
ms.openlocfilehash: c40f50ad7b2341c62b26fd973fd8b91061f49675ed0ca31813a893ba31f2b0e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309799"
---
# <a name="sql-store-settings-expander"></a>Expansor de configuración de almacén SQL
 
Para editar las propiedades de una SQL Server base de datos, debe cambiar la SQL Server de base de datos. No puede usar el cuadro **de diálogo Editar** propiedades para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede usar el cuadro de diálogo **Editar** propiedades para cambiar la instancia de SQL Server que hospeda el almacén de administración central.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Edición de las propiedades de una base de datos SQL Server datos

Para cambiar la instancia de SQL Server que usa cualquier base de datos que no sea el almacén de administración central, complete el siguiente procedimiento en Topology Builder:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Para modificar una instancia de SQL Server

1. Seleccione la base de datos adecuada en el **nodo SQL almacenes** y, a continuación, haga clic en Editar **propiedades**.
    
2. En el cuadro de diálogo **Editar propiedades**, realice una de las siguientes acciones:
    
   - Para usar la instancia SQL Server predeterminada, seleccione **Instancia predeterminada** y, a continuación, haga clic en **Aceptar**.
    
   - Para usar una instancia de base de datos con nombre, seleccione **Instancia con nombre**, indique un nombre en el cuadro de texto y haga clic en **Aceptar**. Debe escribir solo el nombre de instancia (por ejemplo, ArchivingInstance) y no toda la ruta de acceso SQL Server instancia.
    
Cuando trabaje en el cuadro de diálogo **Editar** propiedades, el Generador de topologías no comprobará que la instancia de base de datos que ha escrito sea una instancia válida. Por ejemplo, si escribe AccidentalmenteArchivingInstanec como el nombre de instancia y, a continuación, hace clic en **Aceptar,** el Generador de topologías aceptará esa instancia no válida. Antes de poder publicar esta topología, debe corregir este error: si no se puede encontrar una instancia de SQL Server, el Generador de topologías no creará esa instancia por usted.
  

