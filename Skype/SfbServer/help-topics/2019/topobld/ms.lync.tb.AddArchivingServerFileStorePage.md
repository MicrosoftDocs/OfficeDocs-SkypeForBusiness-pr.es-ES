---
title: Agregar almacén de archivos de servidor de archivado
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: Para habilitar el archivado del contenido de mensajería instantánea y conferencia web, debe especificar un recurso compartido de archivos que se use como almacén de archivos para las copias de todo el contenido de conferencia web. Para ello, use un recurso compartido de archivos existente o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
ms.openlocfilehash: d0b9f836857d978cb9968fcddedfad634b55afda
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21060540"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="5fadf-104">Agregar almacén de archivos de servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="5fadf-104">Add Archiving Server File Store</span></span>
 
<span data-ttu-id="5fadf-p102">Para habilitar el archivado del contenido de mensajería instantánea y conferencia web, debe especificar un recurso compartido de archivos que se use como almacén de archivos para las copias de todo el contenido de conferencia web. Para ello, use un recurso compartido de archivos existente o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.</span><span class="sxs-lookup"><span data-stu-id="5fadf-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5fadf-107">El recurso compartido de archivos puede definirse en el Generador de topologías antes de crearlo; sin embargo, el recurso compartido de archivos debe crearse en la ubicación indicada antes de publicar la topología</span><span class="sxs-lookup"><span data-stu-id="5fadf-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="5fadf-108">> Cuando se agrega un servidor de archivado a la topología, debe poder Topology Builder configurar el almacén de archivos de archivado y configurar listas de control de acceso discrecional (DACL) en el recurso compartido de archivos que se usará para el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="5fadf-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="5fadf-109">Esto implica que, al ejecutar el Generador de topologías para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="5fadf-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
<span data-ttu-id="5fadf-110">Para obtener información detallada sobre la compatibilidad de almacenamiento de información de recursos compartidos de archivos, consulte [Soporte de almacenamiento de información de archivo](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) en la documentación de compatibilidad y la [ubicación del archivo de registro y de datos de SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="5fadf-110">For details about storage support for file shares, see [File Storage Support](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="5fadf-111">Para obtener información detallada sobre la combinación de recurso compartido de archivos, consulte [Supported Server Collocation](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) en la documentación referente a.</span><span class="sxs-lookup"><span data-stu-id="5fadf-111">For details about collocation of the file share, see [Supported Server Collocation](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>
  

