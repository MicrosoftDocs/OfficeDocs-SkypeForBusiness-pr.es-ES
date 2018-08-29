---
title: Agregar equipo Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Especifique el nombre de dominio completo (FQDN) de cada equipo que desea agregar como un servidor Front-End de este grupo. Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología. Después de publicar la topología, el cambio del FQDN requiere eliminar el servidor en el generador de topología y, a continuación, agregar un nuevo servidor al grupo de servidores con el FQDN nuevo. Para obtener información detallada sobre cómo agregar un grupo de servidores Front-End a la topología, consulte definir y configurar un grupo de servidores Front-End en la documentación de implementación.
ms.openlocfilehash: 720ec4b727273a071ee0f8a9cd8628c50f4d6d39
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252901"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="3cc76-106">Agregar equipo Front-End</span><span class="sxs-lookup"><span data-stu-id="3cc76-106">Add Front End Machine</span></span>

<span data-ttu-id="3cc76-107">Especifique el nombre de dominio completo (FQDN) de cada equipo que desea agregar como un servidor Front-End de este grupo.</span><span class="sxs-lookup"><span data-stu-id="3cc76-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="3cc76-108">Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="3cc76-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="3cc76-109">Después de publicar la topología, el cambio del FQDN requiere eliminar el servidor en el generador de topología y, a continuación, agregar un nuevo servidor al grupo de servidores con el FQDN nuevo.</span><span class="sxs-lookup"><span data-stu-id="3cc76-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="3cc76-110">Para obtener información detallada sobre cómo agregar un grupo de servidores Front-End a la topología, consulte [definir y configurar un grupo de servidores Front-End](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="3cc76-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cc76-111">Tenga en cuenta que el generador de topología indica que puede tener un máximo de 20 servidores Front-End en un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3cc76-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="3cc76-112">El número máximo admitido de servidores es 12.</span><span class="sxs-lookup"><span data-stu-id="3cc76-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="3cc76-113">Puede tener un máximo de 20 servidores de estado definidos en el fabric, de los cuales 12 puede ser activa y en línea en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="3cc76-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


