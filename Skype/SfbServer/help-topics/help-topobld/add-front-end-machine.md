---
title: Agregar equipo front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Especifique el nombre de dominio completo de cada equipo que desee agregar como servidor front-end en este grupo de servidores. Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología. Una vez publicada la topología, para cambiar el nombre de dominio se debe eliminar el servidor del Topology Builder y, a continuación, agregar un nuevo servidor al grupo de servidores con el nuevo nombre de dominio completo. Para obtener más información sobre cómo agregar un grupo de servidores front-end a la topología, consulte Definir y configurar un grupo de servidores front-end en la documentación sobre implementación.s
ms.openlocfilehash: b100cfd933f19c87213fa48d4d030eda52e90dc8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119769"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="8670a-106">Agregar equipo front-end</span><span class="sxs-lookup"><span data-stu-id="8670a-106">Add Front End Machine</span></span>

<span data-ttu-id="8670a-107">Especifique el nombre de dominio completo de cada equipo que desee agregar como servidor front-end en este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8670a-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="8670a-108">Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="8670a-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="8670a-109">Una vez publicada la topología, para cambiar el nombre de dominio se debe eliminar el servidor del Topology Builder y, a continuación, agregar un nuevo servidor al grupo de servidores con el nuevo nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="8670a-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="8670a-110">Para obtener más información sobre cómo agregar un grupo de servidores front-end a la topología, consulte [Definir y configurar un grupo de servidores front-end](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) en la documentación sobre implementación.s</span><span class="sxs-lookup"><span data-stu-id="8670a-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8670a-111">Tenga en cuenta que el Generador de topologías indica que puede tener hasta 20 servidores front-end en un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8670a-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="8670a-112">El número máximo de servidores admitido es 12.</span><span class="sxs-lookup"><span data-stu-id="8670a-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="8670a-113">Puede tener hasta 20 servidores con estado definidos en el tejido, de los cuales 12 pueden estar activos y en línea en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="8670a-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>