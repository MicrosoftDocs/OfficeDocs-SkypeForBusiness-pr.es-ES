---
title: Expansor de configuración de almacén SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de la base de datos de SQL Server. No puede usar el cuadro de diálogo Editar propiedades para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede usar el cuadro de diálogo Editar propiedades para cambiar la instancia de SQL Server que hospeda el almacén de administración central.
ms.openlocfilehash: 816733627bcaf1156e5ad34955bb8aa9cf580642
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303021"
---
# <a name="sql-store-settings-expander"></a>Expansor de configuración de almacén SQL
 
Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de la base de datos de SQL Server. No puede usar el cuadro de diálogo **Editar propiedades** para realizar tareas como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede usar el cuadro de diálogo **Editar propiedades** para cambiar la instancia de SQL Server que hospeda el almacén de administración central.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Editar las propiedades de una base de datos de SQL Server

Para cambiar la instancia de SQL Server que se usa en cualquier base de datos que no sea el almacén de administración central, complete el procedimiento siguiente en el generador de topología:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Para modificar una instancia de SQL Server

1. Seleccione la base de datos adecuada en el nodo **almacenes de SQL** y, a continuación, haga clic en **Editar propiedades**.
    
2. En el cuadro de diálogo **Editar propiedades** , realice una de las siguientes acciones:
    
   - Para usar la instancia de SQL Server predeterminada, seleccione **instancia predeterminada** y, a continuación, haga clic en **Aceptar**.
    
   - Para usar una instancia de base de datos con nombre, seleccione **instancia con nombre**, escriba el nombre de la instancia en el cuadro de texto y haga clic en **Aceptar**. Solo debe escribir el nombre de la instancia (por ejemplo, ArchivingInstance) y no toda la ruta de SQL Server.
    
Cuando esté trabajando en el cuadro de diálogo **Editar propiedades** , el generador de topología no comprobará que la instancia de base de datos especificada sea válida. Por ejemplo, si inadvertidamente typeArchivingInstanec como el nombre de la instancia y luego hace clic en **Aceptar**, el generador de topología aceptará esa instancia no válida. Antes de poder publicar esta topología, debe corregir este error: Si no se puede encontrar una instancia de SQL Server, Topology Builder no creará esa instancia para usted.
  

