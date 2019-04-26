---
title: Implemente el servidor perimetral en Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Resumen: Obtenga información sobre cómo implementar un servidor perimetral o un grupo de servidores perimetrales en su Skype para el entorno de servidor empresarial.'
ms.openlocfilehash: bbc331a6abf07450519f58395beda47446e6cef8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223806"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="92965-103">Implemente el servidor perimetral en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="92965-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="92965-104">**Resumen:** Obtenga información sobre cómo implementar un servidor perimetral o un grupo de servidores perimetrales en su Skype para el entorno de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="92965-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="92965-105">¿Razones para implementar un servidor perimetral o un grupo de servidores perimetrales en su Skype para el entorno de servidor empresarial?</span><span class="sxs-lookup"><span data-stu-id="92965-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="92965-106">Es necesario si necesita que usuarios externos que no hayan iniciado sesión en la red interna de las organizaciones puedan interactuar con los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="92965-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="92965-107">Estos usuarios externos podrían ser usuarios remotos anónimos y autenticados, socios federados u otros clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="92965-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="92965-108">Lista de comprobación de implementación para el borde de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="92965-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="92965-109">Como se mencionó anteriormente, un lote se coloca en una implementación de servidor perimetral de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="92965-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="92965-110">Esta lista de comprobación le ofrece una visión general de las tareas que necesitará para hacer y vínculos a los pasos más detallados.</span><span class="sxs-lookup"><span data-stu-id="92965-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="92965-111">Esperamos que ha comenzado a en la sección de [planeación para las implementaciones de servidor perimetral de Skype para Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) .</span><span class="sxs-lookup"><span data-stu-id="92965-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="92965-112">Si no es así, muchas de las cosas a las que nos referimos se detallan allí.</span><span class="sxs-lookup"><span data-stu-id="92965-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="92965-113">La sección de implementación contiene solo los procedimientos, por lo que si desea conocer la lógica que impera en estos pasos, la planificación es el lugar en el que empezar.</span><span class="sxs-lookup"><span data-stu-id="92965-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="92965-114">Esta documentación también da por supuesto que ha hecho también la implementación básica de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="92965-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="92965-115">Pueden realizar esa implementación en paralelo con el borde, pero debe seguir estos pasos en primer lugar y, a continuación, podrá realizar los cambios de topología para el borde que se documentan aquí.</span><span class="sxs-lookup"><span data-stu-id="92965-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="92965-116">Estos son los pasos de alto nivel que tendrá que seguir y los lugares en los que encontrará estos pasos:</span><span class="sxs-lookup"><span data-stu-id="92965-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="92965-117">Requisitos del sistema del servidor de bordes en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="92965-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="92965-118">Borde de requisitos de entorno de servidor en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="92965-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="92965-119">Creación de la topología perimetral para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="92965-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="92965-120">Implemente servidores perimetrales en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="92965-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="92965-121">Validar la implementación perimetral en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="92965-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

