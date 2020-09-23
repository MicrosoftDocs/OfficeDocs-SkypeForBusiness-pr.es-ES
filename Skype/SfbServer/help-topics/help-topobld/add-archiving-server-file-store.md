---
title: Agregar almacén de archivos de servidor de archivado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 22f7de704b3d7a611d4601df4c14ed75f7466c1c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217431"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="421ee-104">Agregar almacén de archivos de servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="421ee-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="421ee-p102">Para habilitar el archivado del contenido de mensajería instantánea y conferencia web, debe especificar un recurso compartido de archivos que se use como almacén de archivos para las copias de todo el contenido de conferencia web. Para ello, use un recurso compartido de archivos existente o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.</span><span class="sxs-lookup"><span data-stu-id="421ee-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="421ee-107">El recurso compartido de archivos puede definirse en el Topology Builder antes de crearlo; sin embargo, el recurso compartido de archivos debe crearse en la ubicación indicada antes de publicar la topología</span><span class="sxs-lookup"><span data-stu-id="421ee-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="421ee-108">> cuando se agrega un servidor de archivado a la topología, el generador de topologías debe ser capaz de configurar el almacén de archivos de archivado y configurar listas de control de acceso discrecional (DACL) en el recurso compartido de archivos que se usará para el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="421ee-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="421ee-109">Esto implica que, al ejecutar el Topology Builder para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="421ee-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="421ee-110">Para obtener más información sobre la compatibilidad de almacenamiento de los recursos compartidos de archivos, consulte [File Storage support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) en la documentación de compatibilidad y [SQL Server Data and log file Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="421ee-110">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="421ee-111">Para más información sobre la combinación del recurso compartido de archivos, consulte [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="421ee-111">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


