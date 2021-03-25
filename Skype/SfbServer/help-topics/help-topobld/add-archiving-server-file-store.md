---
title: Agregar almacén de archivos de servidor de archivado
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
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Para habilitar el archivado del contenido de mensajería instantánea y conferencia web, debe especificar un recurso compartido de archivos que se use como almacén de archivos para las copias de todo el contenido de conferencia web. Para ello, use un recurso compartido de archivos existente o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
ms.openlocfilehash: bd904a746cad5765fafa42d8bff6ea0611311a32
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119859"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="aa27e-104">Agregar almacén de archivos de servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="aa27e-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="aa27e-p102">Para habilitar el archivado del contenido de mensajería instantánea y conferencia web, debe especificar un recurso compartido de archivos que se use como almacén de archivos para las copias de todo el contenido de conferencia web. Para ello, use un recurso compartido de archivos existente o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.</span><span class="sxs-lookup"><span data-stu-id="aa27e-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa27e-107">El recurso compartido de archivos puede definirse en el Topology Builder antes de crearlo; sin embargo, el recurso compartido de archivos debe crearse en la ubicación indicada antes de publicar la topología</span><span class="sxs-lookup"><span data-stu-id="aa27e-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="aa27e-108">> Al agregar un servidor de archivado a la topología, el Generador de topologías debe poder configurar el almacén de archivos de archivado y configurar listas de control de acceso discrecional (DACL) en el recurso compartido de archivos que se usará para el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="aa27e-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="aa27e-109">Esto implica que, al ejecutar el Topology Builder para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="aa27e-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="aa27e-110">Para obtener más información acerca de la compatibilidad con almacenamiento para recursos compartidos de archivos, consulte [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) en la documentación de compatibilidad y SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="aa27e-110">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="aa27e-111">Para más información sobre la combinación del recurso compartido de archivos, consulte [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="aa27e-111">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span>