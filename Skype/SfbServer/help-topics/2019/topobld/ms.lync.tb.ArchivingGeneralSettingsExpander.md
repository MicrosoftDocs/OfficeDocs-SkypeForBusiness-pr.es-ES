---
title: Expansor de configuración general del servidor de archivado
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: 'En el generador, puede editar las propiedades de un servidor individual de archivado ya sea bien por el servidor que ejecuta el archivado en el árbol de consola y haga clic en acción en la barra de herramientas, o haciendo clic en una tarea en el panel de acciones y, a continuación, hace clic en Editar Las propiedades y cambiar cualquiera de las siguientes opciones:'
ms.openlocfilehash: 76225fe039fea402779e42dd5a33b68a3ab6a8ec
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="f465f-103">Expansor de configuración general del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="f465f-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="f465f-104">En el Generador de topologías se pueden editar las propiedades de un servidor individual de archivado. Para ello, haga clic con el botón secundario en el servidor que ejecuta el archivado en el árbol de consola, haga clic en **Acción** en la barra de herramientas, o bien haga clic en una tarea del panel Acciones y en **Editar propiedades** y, luego, cambie una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f465f-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="f465f-105">**FQDN**, para cambiar el nombre de dominio completo (FQDN) del servidor que desea implementar como servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="f465f-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="f465f-p101">**Almacén SQL**, para cambiar la instancia de SQL Server que se va a usar en la base de datos de SQL Server de archivado. Si se cambia la base de datos de SQL Server de un servidor de archivado, hay que reiniciar dicho servidor para que el cambio surta efecto.</span><span class="sxs-lookup"><span data-stu-id="f465f-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="f465f-p102">**Recurso compartido de archivos**, para cambiar la carpeta que se va a usar para el almacén de archivos de archivado. Si se cambia el recurso compartido de archivos de un servidor de archivado, hay que reiniciar dicho servidor para que el cambio surta efecto. Asimismo, los archivos de conferencia anteriores se necesitan mover a la nueva carpeta de almacén de archivos para no perder los archivos de conferencia archivados.</span><span class="sxs-lookup"><span data-stu-id="f465f-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f465f-111">Para cambiar los grupos de servidores asociados con un servidor de archivado, seleccione la opción **Editar propiedades** del nodo Grupo de servidores front-end o el nodo Aplicación de sucursal con funciones de supervivencia asociado actualmente con el servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="f465f-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f465f-p103">El nodo Archivado contiene un servidor de archivado si se ha agregado previamente un servidor de archivado a la topología en el Generador de topologías. Puede editar las propiedades de cualquier servidor de archivado de la lista. Pero, no se puede archivar contenido de mensajería instantánea ni de conferencias web hasta que se haya configurado el servicio del servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="f465f-p103">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder. You can edit properties for any server running Archiving in the list. However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

