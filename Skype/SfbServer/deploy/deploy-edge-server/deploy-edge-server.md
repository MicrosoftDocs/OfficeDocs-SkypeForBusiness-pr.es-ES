---
title: Implementar el servidor perimetral en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Resumen: obtenga información sobre cómo implementar un servidor perimetral o un grupo de servidores perimetrales en su entorno de Skype Empresarial Server.'
ms.openlocfilehash: edd2ff501320c4252b8032d1528ede7b83b8fcd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804390"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="59dd6-103">Implementar el servidor perimetral en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="59dd6-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="59dd6-104">**Resumen:** Obtenga información sobre cómo implementar un servidor perimetral o un grupo de servidores perimetrales en su entorno de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="59dd6-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="59dd6-105">¿Por qué implementar un servidor perimetral o un grupo de servidores perimetrales en su entorno de Skype Empresarial Server?</span><span class="sxs-lookup"><span data-stu-id="59dd6-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="59dd6-106">Es necesario si necesita usuarios externos que no hayan iniciado sesión en la red interna de su organización para poder interactuar con usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="59dd6-106">It's necessary if you need external users who aren't logged into your organization's internal network to be able to interact with internal users.</span></span> <span data-ttu-id="59dd6-107">Estos usuarios externos podrían ser usuarios remotos autenticados y anónimos, socios federados u otros clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="59dd6-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="59dd6-108">Lista de comprobación de implementación para el servidor perimetral para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="59dd6-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="59dd6-109">Como se mencionó anteriormente, mucho va a una implementación de servidor perimetral para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="59dd6-109">As noted above, a lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="59dd6-110">Esta lista de comprobación proporciona información general sobre las tareas que deberá realizar y vínculos a pasos más detallados.</span><span class="sxs-lookup"><span data-stu-id="59dd6-110">This checklist gives you an overview of the tasks you'll need to perform, and links to more detailed steps.</span></span>
  
<span data-ttu-id="59dd6-111">Esperamos que haya comenzado en la sección Plan para implementaciones de servidores perimetrales [en Skype Empresarial Server.](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)</span><span class="sxs-lookup"><span data-stu-id="59dd6-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="59dd6-112">Si no es así, muchas de las cosas a las que nos referimos se detallan allí.</span><span class="sxs-lookup"><span data-stu-id="59dd6-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="59dd6-113">La sección de implementación contiene solo procedimientos, por lo que si desea conocer los motivos de estos pasos, la planeación es el lugar donde comenzar.</span><span class="sxs-lookup"><span data-stu-id="59dd6-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="59dd6-114">En esta documentación también se da por hecho que ya ha completado la implementación básica de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="59dd6-114">This documentation also presumes you've already completed the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="59dd6-115">Es posible que esté realizando esa implementación en paralelo con el servidor perimetral, pero primero debe seguir estos pasos y, a continuación, podrá realizar los cambios de topología para el servidor perimetral que se documentan aquí.</span><span class="sxs-lookup"><span data-stu-id="59dd6-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="59dd6-116">Estos son los pasos de alto nivel que deberá seguir y los lugares donde encontrará esos pasos:</span><span class="sxs-lookup"><span data-stu-id="59dd6-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="59dd6-117">Requisitos del sistema del servidor perimetral en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="59dd6-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="59dd6-118">Requisitos del entorno del servidor perimetral en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="59dd6-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="59dd6-119">Crear la topología perimetral para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="59dd6-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="59dd6-120">Implementar servidores perimetrales en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="59dd6-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="59dd6-121">Validar la implementación perimetral en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="59dd6-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

