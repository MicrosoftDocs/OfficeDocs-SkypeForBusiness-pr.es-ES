---
title: Agregar almacén de archivos de director
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: Debe especificar un recurso compartido de archivos para usarlo como almacén de archivos de los directores. Puede utilizar un recurso compartido de archivos existente como almacén o elegir uno nuevo especificando el nombre de dominio completo (FQDN) del servidor de archivos en el que se deba ubicar el recurso compartido de archivos y un nombre de carpeta para el nuevo recurso compartido de archivos.
ms.openlocfilehash: f134d561a948dbdb89ce655d59e5d5fc205bcbf4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811890"
---
# <a name="add-director-file-store"></a><span data-ttu-id="26678-104">Agregar almacén de archivos de director</span><span class="sxs-lookup"><span data-stu-id="26678-104">Add Director File Store</span></span>

<span data-ttu-id="26678-p102">Debe especificar un recurso compartido de archivos para usarlo como almacén de archivos de los directores. Puede utilizar un recurso compartido de archivos existente como almacén o elegir uno nuevo especificando el nombre de dominio completo (FQDN) del servidor de archivos en el que se deba ubicar el recurso compartido de archivos y un nombre de carpeta para el nuevo recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="26678-p102">You must specify a file share to be used as the file store for Directors. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26678-p103">Al agregar directores a una topología, la publicación de topología requiere un acceso adecuado para configurar el almacén de archivos y las listas de control de acceso discrecional (DACL) en el recurso compartido de archivos que se utilizará para el almacén de archivos. Para ello, es necesario que al ejecutar el Topology Builder y publicar la nueva topología, haya iniciado una sesión con una cuenta con todos los permisos de control (lectura/escritura/modificación) para el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="26678-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="26678-109">Para obtener más información sobre [](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) la compatibilidad con el almacenamiento para recursos compartidos de archivos, consulte La compatibilidad con el almacenamiento de archivos en la documentación sobre compatibilidad y [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="26678-109">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="26678-110">Para más información sobre la combinación del recurso compartido de archivos, consulte [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="26678-110">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="26678-111">Para más información sobre cómo diseñar la topología para directores, consulte [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="26678-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in the Deployment documentation.</span></span>


