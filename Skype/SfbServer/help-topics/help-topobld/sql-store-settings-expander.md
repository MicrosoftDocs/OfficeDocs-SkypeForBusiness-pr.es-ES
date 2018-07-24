---
title: Expansor de configuración de almacén de SQL
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de base de datos de SQL Server. No puede usar el cuadro de diálogo Editar propiedades para realizar tareas tales como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede usar el cuadro de diálogo Editar propiedades para cambiar la instancia de SQL Server que hospeda el almacén de Administración Central.
ms.openlocfilehash: 66f75ba3aa92530f983f3415d690b0eb0ae1ed15
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971998"
---
# <a name="sql-store-settings-expander"></a>Expansor de configuración de almacén de SQL
 
Para editar las propiedades de una base de datos de SQL Server, debe cambiar la instancia de base de datos de SQL Server. No puede usar el cuadro de diálogo **Editar propiedades** para realizar tareas tales como mover la base de datos del servidor de archivado de un equipo a otro. Además, no puede usar el cuadro de diálogo **Editar propiedades** para cambiar la instancia de SQL Server que hospeda el almacén de Administración Central.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Editar las propiedades de una base de datos SQL Server

Para cambiar la instancia de SQL Server que se usa en cualquier base de datos que no sea el almacén de Administración Central, complete el procedimiento siguiente en el generador de topología:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Para modificar una instancia de SQL Server

1. Seleccione la base de datos adecuada en el nodo **SQL almacena** y, a continuación, haga clic en **Editar propiedades**.
    
2. En el cuadro de diálogo **Editar propiedades** , siga uno de estos procedimientos:
    
  - Para usar la instancia de SQL Server predeterminada, seleccione **Instancia predeterminada** y, a continuación, haga clic en **Aceptar**.
    
  - Para usar una instancia con nombre de la base de datos, seleccione **Instancia con nombre**, escriba el nombre de instancia en el cuadro de texto y, a continuación, haga clic en **Aceptar**. Debe escribir el nombre de instancia (por ejemplo, ArchivingInstance) y no la ruta completa de SQL Server.
    
Cuando se trabaja en el cuadro de diálogo **Editar propiedades** , Topology Builder no comprobará que la instancia de base de datos que ha escrito es una instancia válida. Por ejemplo, si se sin darse cuenta typeArchivingInstanec como el nombre de instancia y, a continuación, haga clic en **Aceptar**, Topology Builder aceptará esa instancia no válida. Antes de poder publicar esta topología, debe corregir este error: si no se encuentra una instancia de SQL Server, Topology Builder no crear esa instancia para usted.
  

