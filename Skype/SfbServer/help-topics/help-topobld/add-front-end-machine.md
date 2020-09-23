---
title: Agregar equipo front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 69837016022f30453a287b6264936e20ec4883ca
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218321"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="b4b75-106">Agregar equipo front-end</span><span class="sxs-lookup"><span data-stu-id="b4b75-106">Add Front End Machine</span></span>

<span data-ttu-id="b4b75-107">Especifique el nombre de dominio completo de cada equipo que desee agregar como servidor front-end en este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="b4b75-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="b4b75-108">Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="b4b75-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="b4b75-109">Una vez publicada la topología, para cambiar el nombre de dominio se debe eliminar el servidor del Topology Builder y, a continuación, agregar un nuevo servidor al grupo de servidores con el nuevo nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="b4b75-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="b4b75-110">Para obtener más información sobre cómo agregar un grupo de servidores front-end a la topología, consulte [Definir y configurar un grupo de servidores front-end](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación sobre implementación.s</span><span class="sxs-lookup"><span data-stu-id="b4b75-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4b75-111">Tenga en cuenta que el generador de topologías indica que puede tener hasta 20 servidores front-end en un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="b4b75-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="b4b75-112">El número máximo admitido de servidores es 12.</span><span class="sxs-lookup"><span data-stu-id="b4b75-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="b4b75-113">Puede tener hasta 20 servidores de statefull definidos en el tejido, de los cuales 12 puede estar activo y en línea en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="b4b75-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


