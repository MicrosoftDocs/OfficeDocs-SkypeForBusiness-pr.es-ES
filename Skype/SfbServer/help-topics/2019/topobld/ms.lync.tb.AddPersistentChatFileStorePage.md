---
title: Agregar almacén de archivos de chat persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Debe especificar el recurso compartido de archivos que se debe usar como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
ms.openlocfilehash: 989e11adfd7059c94067dd8360527d86759ae81c
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2018
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="24047-104">Agregar almacén de archivos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="24047-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="24047-p102">Debe especificar el recurso compartido de archivos que se debe usar como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.</span><span class="sxs-lookup"><span data-stu-id="24047-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="24047-107">El recurso compartido de archivos de Skype para Business Server no se puede ubicar en Enterprise Edition Front-End Server, pero puede estar ubicada en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="24047-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="24047-108">El recurso compartido de archivos se puede definir en el Generador de topologías antes de crearlo; sin embargo, el recurso compartido de archivos se debe crear en la ubicación indicada antes de publicar la topología</span><span class="sxs-lookup"><span data-stu-id="24047-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="24047-109">Al agregar un servidor de Chat persistente o servidor de Chat persistente debe poder configurar el archivo de grupo de servidores a la topología, Topology Builder almacenar y configurar el control de acceso discrecional (DACL) se enumeran en el recurso compartido de archivos que se usará para el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="24047-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="24047-110">Esto implica que, al ejecutar el Generador de topologías para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="24047-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="24047-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="24047-111">See also</span></span>

#### 

[<span data-ttu-id="24047-112">Planeación de servidor de Chat persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="24047-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="24047-113">Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="24047-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="24047-114">Requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="24047-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="24047-115">Requisitos de servidor de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="24047-115">Server requirements for Skype for Business Server 2015</span></span>](../../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="24047-116">Conceptos básicos de la topología de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="24047-116">Topology Basics for Skype for Business Server 2015</span></span>](../../../plan-your-deployment/topology-basics/topology-basics.md)

