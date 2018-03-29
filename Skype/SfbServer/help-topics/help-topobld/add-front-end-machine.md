---
title: Agregar equipo Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Especifique el nombre de dominio completo (FQDN) de cada equipo que desea agregar como un servidor Front-End de este grupo. Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología. Después de publicar la topología, el cambio del FQDN requiere eliminar el servidor en el generador de topología y, a continuación, agregar un nuevo servidor al grupo con el nuevo nombre de dominio completo. Para obtener más información acerca de cómo agregar un grupo de servidores Front-End a la topología, vea Definir y configurar un grupo de servidores frontales en la documentación de implementación.
ms.openlocfilehash: f4d8b197592a68cd3d19ba1bc2741b9f4743d19c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-machine"></a><span data-ttu-id="c2124-106">Agregar equipo Front-End</span><span class="sxs-lookup"><span data-stu-id="c2124-106">Add Front End Machine</span></span>
 
<span data-ttu-id="c2124-107">Especifique el nombre de dominio completo (FQDN) de cada equipo que desea agregar como un servidor Front-End de este grupo.</span><span class="sxs-lookup"><span data-stu-id="c2124-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="c2124-108">Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="c2124-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="c2124-109">Después de publicar la topología, el cambio del FQDN requiere eliminar el servidor en el generador de topología y, a continuación, agregar un nuevo servidor al grupo con el nuevo nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="c2124-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="c2124-110">Para obtener más información acerca de cómo agregar un grupo de servidores Front-End a la topología, vea [definir y configurar un grupo de servidores frontales](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="c2124-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c2124-111">Tenga en cuenta que el generador de topología indica que puede tener hasta 20 servidores frontales en un grupo.</span><span class="sxs-lookup"><span data-stu-id="c2124-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="c2124-112">El número máximo soportado de servidores es 12.</span><span class="sxs-lookup"><span data-stu-id="c2124-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="c2124-113">Puede tener hasta 20 servidores de estado definidos en el fabric, de los cuales 12 puede ser activa y en línea en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="c2124-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span> 
  

