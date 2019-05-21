---
title: Implementar el servidor perimetral en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Resumen: Aprenda a implementar un servidor perimetral o un grupo perimetral en su entorno de Skype empresarial Server.'
ms.openlocfilehash: bcb6f7fdd7b322411e793fe3466418db1dd00894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306954"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="65bcd-103">Implementar el servidor perimetral en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="65bcd-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="65bcd-104">**Resumen:** Aprenda a implementar un servidor perimetral o un grupo perimetral en su entorno de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="65bcd-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="65bcd-105">¿Por qué implementar un servidor perimetral o un grupo de límites en el entorno de Skype empresarial Server?</span><span class="sxs-lookup"><span data-stu-id="65bcd-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="65bcd-106">Es necesario si necesita que usuarios externos que no hayan iniciado sesión en la red interna de las organizaciones puedan interactuar con los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="65bcd-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="65bcd-107">Estos usuarios externos podrían ser usuarios remotos anónimos y autenticados, socios federados u otros clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="65bcd-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="65bcd-108">Lista de comprobación de la implementación del borde para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="65bcd-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="65bcd-109">Como se mencionó anteriormente, un lote entra en una implementación de servidor perimetral para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="65bcd-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="65bcd-110">Esta lista de comprobación le ofrece una descripción general de las tareas que debe realizar y vínculos a pasos más detallados.</span><span class="sxs-lookup"><span data-stu-id="65bcd-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="65bcd-111">Esperamos que haya comenzado en la sección [Plan for Edges Deployments in the Edge Server de Skype empresarial Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) .</span><span class="sxs-lookup"><span data-stu-id="65bcd-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="65bcd-112">Si no es así, muchas de las cosas a las que nos referimos se detallan allí.</span><span class="sxs-lookup"><span data-stu-id="65bcd-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="65bcd-113">La sección de implementación contiene solo los procedimientos, por lo que si desea conocer la lógica que impera en estos pasos, la planificación es el lugar en el que empezar.</span><span class="sxs-lookup"><span data-stu-id="65bcd-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="65bcd-114">En esta documentación también se presupone que también ha realizado la implementación básica de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="65bcd-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="65bcd-115">Es posible que esté haciendo esta implementación en paralelo con el borde, pero primero debe seguir los pasos que se indican a continuación y, después, podrá realizar los cambios de topología para el borde que se documenta aquí.</span><span class="sxs-lookup"><span data-stu-id="65bcd-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="65bcd-116">Estos son los pasos de alto nivel que tendrá que seguir y los lugares en los que encontrará estos pasos:</span><span class="sxs-lookup"><span data-stu-id="65bcd-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="65bcd-117">Requisitos del sistema del servidor perimetral en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="65bcd-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="65bcd-118">Requisitos ambientales para servidores perimetrales en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="65bcd-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="65bcd-119">Crear la topología perimetral para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="65bcd-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="65bcd-120">Implementar servidores perimetrales en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="65bcd-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="65bcd-121">Validar la implementación perimetral en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="65bcd-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

