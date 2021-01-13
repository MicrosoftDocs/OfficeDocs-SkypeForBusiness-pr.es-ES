---
title: Expansor de configuración general del servidor de archivado
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'En el Generador de topologías, puede editar las propiedades de un servidor individual que ejecute archivado haciendo clic con el botón secundario en el servidor que ejecuta archivado en el árbol de consola, haciendo clic en Acción en la barra de herramientas, o haciendo clic en una tarea en el panel Acciones y, a continuación, haciendo clic en Editar propiedades y cambiando cualquiera de las siguientes opciones:'
ms.openlocfilehash: 841343a54ac3681659614a8ab89c02990290d9d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800750"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="4df03-103">Expansor de configuración general del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="4df03-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="4df03-104">En el Generador de topologías, puede editar las propiedades de un servidor individual que ejecute  archivado haciendo clic con el botón secundario en el  servidor que ejecuta archivado en el árbol de consola, haciendo clic en Acción en la barra de herramientas, o haciendo clic en una tarea en el panel Acciones y, a continuación, haciendo clic en Editar propiedades y cambiando cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4df03-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="4df03-105">**FQDN**, para cambiar el nombre de dominio completo (FQDN) del servidor que desea implementar como servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="4df03-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="4df03-p101">**Almacén SQL**, para cambiar la instancia de SQL Server que debe usarse en el archivado de la base de datos de SQL Server. Si se cambia la base de datos de SQL Server de un servidor de archivado, para que surta efecto el cambio debe reiniciarse dicho servidor.</span><span class="sxs-lookup"><span data-stu-id="4df03-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="4df03-p102">**Recurso compartido de archivos**, para cambiar la carpeta que se usará para archivar el almacén de archivos. Si se cambia el recurso compartido de archivos de un servidor de archivado, para que surta efecto el cambio debe reiniciarse dicho servidor. Asimismo, deben moverse los archivos de conferencia anteriores a la nueva carpeta de almacén de archivos para evitar perder los archivos de conferencia archivados.</span><span class="sxs-lookup"><span data-stu-id="4df03-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4df03-111">Para cambiar los grupos de servidores asociados con un servidor de archivado, seleccione la opción **Editar propiedades** para el nodo Grupo de servidores front-end o el nodo Aplicación de sucursal con funciones de supervivencia que está asociado actualmente con el servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="4df03-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4df03-112">El nodo de archivado contiene un servidor de archivado si se ha agregado previamente un servidor de archivado a la topología en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="4df03-112">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder.</span></span> <span data-ttu-id="4df03-113">Puede editar las propiedades de cualquier servidor de archivado de la lista.</span><span class="sxs-lookup"><span data-stu-id="4df03-113">You can edit properties for any server running Archiving in the list.</span></span> <span data-ttu-id="4df03-114">Sin embargo, la mensajería instantánea o las conferencias web (mensajería) no se pueden archivar hasta que también configure el servicio para el servidor que ejecuta el archivado.</span><span class="sxs-lookup"><span data-stu-id="4df03-114">However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

