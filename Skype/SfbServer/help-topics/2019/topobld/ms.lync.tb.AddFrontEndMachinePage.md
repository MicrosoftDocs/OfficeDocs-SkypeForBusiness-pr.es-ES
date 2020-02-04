---
title: Agregar equipo front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique el nombre de dominio completo (FQDN) de cada equipo que quiera agregar como servidor front-end en este grupo. Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología. Después de publicar la topología, cambiar el FQDN requiere que se elimine el servidor en el generador de topología y que, después, se agregue un nuevo servidor al grupo con el nuevo FQDN. Para obtener más información sobre cómo agregar un grupo de servidores front-end a la topología, vea definir y configurar un grupo de servidores front-end en la documentación de implementación.
ms.openlocfilehash: a11042c8d91089e74ab1bacfc5206eb7d2fa3f67
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689315"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="76083-106">Agregar equipo front-end</span><span class="sxs-lookup"><span data-stu-id="76083-106">Add Front End Machine</span></span>

<span data-ttu-id="76083-107">Especifique el nombre de dominio completo (FQDN) de cada equipo que quiera agregar como servidor front-end en este grupo.</span><span class="sxs-lookup"><span data-stu-id="76083-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="76083-108">Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="76083-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="76083-109">Después de publicar la topología, cambiar el FQDN requiere que se elimine el servidor en el generador de topología y que, después, se agregue un nuevo servidor al grupo con el nuevo FQDN.</span><span class="sxs-lookup"><span data-stu-id="76083-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="76083-110">Para obtener más información sobre cómo agregar un grupo de servidores front-end a la topología, vea [definir y configurar un grupo de servidores front-end](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="76083-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76083-111">Tenga en cuenta que el generador de topología indica que puede tener hasta 20 servidores front-end en un grupo.</span><span class="sxs-lookup"><span data-stu-id="76083-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="76083-112">El número máximo admitido de servidores es de 12.</span><span class="sxs-lookup"><span data-stu-id="76083-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="76083-113">Puede tener hasta 20 servidores statefull definidos en el tejido, de los cuales 12 puede estar activo y conectado en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="76083-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


