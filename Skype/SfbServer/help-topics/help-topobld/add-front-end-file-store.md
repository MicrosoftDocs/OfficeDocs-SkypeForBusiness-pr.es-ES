---
title: Agregar almacén de archivos front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: Debe especificar el recurso compartido de archivos que debe usarse como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end de Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
ms.openlocfilehash: 4e2c732e0003f23cf183374880592ccd24fbe9bb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218351"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="b18d2-104">Agregar almacén de archivos front-end</span><span class="sxs-lookup"><span data-stu-id="b18d2-104">Add Front End File Store</span></span>

<span data-ttu-id="b18d2-p102">Debe especificar el recurso compartido de archivos que debe usarse como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end de Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.</span><span class="sxs-lookup"><span data-stu-id="b18d2-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b18d2-107">El recurso compartido de archivos no se puede ubicar en el servidor front-end Enterprise Edition, pero puede estar ubicado en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b18d2-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b18d2-108">El recurso compartido de archivos puede definirse en Topology Builder antes de crearlo; sin embargo, el recurso compartido de archivos debe crearse en la ubicación indicada antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="b18d2-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b18d2-p103">Al agregar un grupo de servidores front-end de Enterprise Edition o un servidor Standard Edition en la topología, Topology Builder debe poder instalar el recurso compartido de archivos y configurar listas de control de acceso discrecional en el recurso compartido de archivos para usarse almacén de archivos. Esto implica que, al ejecutar Topology Builder para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="b18d2-p103">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="b18d2-111">Para obtener más información sobre la compatibilidad de almacenamiento de los recursos compartidos de archivos, consulte [File Storage support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) en la documentación de compatibilidad y [SQL Server Data and log file Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="b18d2-111">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="b18d2-112">Para más información sobre la combinación del recurso compartido de archivos, consulte [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="b18d2-112">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="b18d2-113">Para obtener más información sobre cómo diseñar la topología de un grupo de servidores front-end de Enterprise Edition, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="b18d2-113">For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>


