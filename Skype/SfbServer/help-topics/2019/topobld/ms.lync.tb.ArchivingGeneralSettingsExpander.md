---
title: Expansor de configuración general del servidor de archivado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'En el Generador de topologías se pueden editar las propiedades de un servidor individual de archivado. Para ello, haga clic con el botón secundario en el servidor que ejecuta el archivado en el árbol de consola, haga clic en Acción en la barra de herramientas, o bien haga clic en una tarea del panel Acciones y en Editar propiedades y, luego, cambie una de las opciones siguientes:'
ms.openlocfilehash: 9f68ed29d1ff58e3c89c5b5e50e83e8a8730a338
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220772"
---
# <a name="archiving-server-general-settings-expander"></a>Expansor de configuración general del servidor de archivado
 
En el Generador de topologías se pueden editar las propiedades de un servidor individual de archivado. Para ello, haga clic con el botón secundario en el servidor que ejecuta el archivado en el árbol de consola, haga clic en **Acción** en la barra de herramientas, o bien haga clic en una tarea del panel Acciones y en **Editar propiedades** y, luego, cambie una de las opciones siguientes:
  
- **FQDN**, para cambiar el nombre de dominio completo (FQDN) del servidor que desea implementar como servidor de archivado.
    
- **Almacén SQL**, para cambiar la instancia de SQL Server que se va a usar en la base de datos de SQL Server de archivado. Si se cambia la base de datos de SQL Server de un servidor de archivado, hay que reiniciar dicho servidor para que el cambio surta efecto.
    
- **Recurso compartido de archivos**, para cambiar la carpeta que se va a usar para el almacén de archivos de archivado. Si se cambia el recurso compartido de archivos de un servidor de archivado, hay que reiniciar dicho servidor para que el cambio surta efecto. Asimismo, los archivos de conferencia anteriores se necesitan mover a la nueva carpeta de almacén de archivos para no perder los archivos de conferencia archivados.
    
> [!NOTE]
> Para cambiar los grupos de servidores asociados con un servidor de archivado, seleccione la opción **Editar propiedades** del nodo Grupo de servidores front-end o el nodo Aplicación de sucursal con funciones de supervivencia asociado actualmente con el servidor de archivado.
  
> [!NOTE]
> El nodo Archivado contiene un servidor de archivado si se ha agregado previamente un servidor de archivado a la topología en el Generador de topologías. Puede editar las propiedades de cualquier servidor de archivado de la lista. Pero, no se puede archivar contenido de mensajería instantánea ni de conferencias web hasta que se haya configurado el servicio del servidor de archivado. 
  

