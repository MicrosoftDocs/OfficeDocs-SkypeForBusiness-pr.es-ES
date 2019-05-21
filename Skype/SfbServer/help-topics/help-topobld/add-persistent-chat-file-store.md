---
title: Agregar almacén de archivos de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Debe especificar el recurso compartido de archivos que se debe usar como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
ms.openlocfilehash: 99c08f188c39c6d5b20227dc65332549a383ec67
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292867"
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="2d2dd-104">Agregar almacén de archivos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2d2dd-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="2d2dd-p102">Debe especificar el recurso compartido de archivos que se debe usar como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.</span><span class="sxs-lookup"><span data-stu-id="2d2dd-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2d2dd-107">El recurso compartido de archivos de Skype empresarial Server no se puede ubicar en el servidor de aplicaciones para el usuario de Enterprise Edition, pero puede estar ubicado en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2d2dd-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2d2dd-108">El recurso compartido de archivos se puede definir en el Generador de topologías antes de crearlo; sin embargo, el recurso compartido de archivos se debe crear en la ubicación indicada antes de publicar la topología</span><span class="sxs-lookup"><span data-stu-id="2d2dd-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2d2dd-109">Al agregar un servidor de chat persistente o un grupo de servidores de chat persistente a su topología, el generador de topología debe poder configurar el almacén de archivos y configurar listas de control de acceso discrecional (DACL) en el recurso compartido de archivos para usarlos en el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="2d2dd-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="2d2dd-110">Esto implica que, al ejecutar el Generador de topologías para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="2d2dd-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2d2dd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d2dd-111">See also</span></span>

[<span data-ttu-id="2d2dd-112">Planificar el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d2dd-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="2d2dd-113">Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2d2dd-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="2d2dd-114">Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d2dd-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="2d2dd-115">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d2dd-115">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="2d2dd-116">Conceptos básicos de topología de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d2dd-116">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
