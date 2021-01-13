---
title: Expansor de configuración general del servidor de archivado
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: 'En el Generador de topologías, puede editar las propiedades de un servidor individual que ejecute archivado haciendo clic con el botón secundario en el servidor que ejecuta archivado en el árbol de consola, haciendo clic en Acción en la barra de herramientas, o haciendo clic en una tarea en el panel Acciones y, a continuación, haciendo clic en Editar propiedades y cambiando cualquiera de las siguientes opciones:'
ms.openlocfilehash: 091f6f9b83c6127975654c32a81782621f7af70d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803400"
---
# <a name="archiving-server-general-settings-expander"></a>Expansor de configuración general del servidor de archivado
 
En el Generador de topologías, puede editar las propiedades de un servidor individual que ejecute  archivado haciendo clic con el botón secundario en el  servidor que ejecuta archivado en el árbol de consola, haciendo clic en Acción en la barra de herramientas, o haciendo clic en una tarea en el panel Acciones y, a continuación, haciendo clic en Editar propiedades y cambiando cualquiera de las siguientes opciones:
  
- **FQDN**, para cambiar el nombre de dominio completo (FQDN) del servidor que desea implementar como servidor de archivado.
    
- **Almacén SQL**, para cambiar la instancia de SQL Server que debe usarse en el archivado de la base de datos de SQL Server. Si se cambia la base de datos de SQL Server de un servidor de archivado, para que surta efecto el cambio debe reiniciarse dicho servidor.
    
- **Recurso compartido de archivos**, para cambiar la carpeta que se usará para archivar el almacén de archivos. Si se cambia el recurso compartido de archivos de un servidor de archivado, para que surta efecto el cambio debe reiniciarse dicho servidor. Asimismo, deben moverse los archivos de conferencia anteriores a la nueva carpeta de almacén de archivos para evitar perder los archivos de conferencia archivados.
    
> [!NOTE]
> Para cambiar los grupos de servidores asociados con un servidor de archivado, seleccione la opción **Editar propiedades** para el nodo Grupo de servidores front-end o el nodo Aplicación de sucursal con funciones de supervivencia que está asociado actualmente con el servidor de archivado.
  
> [!NOTE]
> El nodo de archivado contiene un servidor de archivado si se ha agregado previamente un servidor de archivado a la topología en el Generador de topologías. Puede editar las propiedades de cualquier servidor de archivado de la lista. Sin embargo, la mensajería instantánea o las conferencias web (mensajería) no se pueden archivar hasta que también configure el servicio para el servidor que ejecuta el archivado. 
  

