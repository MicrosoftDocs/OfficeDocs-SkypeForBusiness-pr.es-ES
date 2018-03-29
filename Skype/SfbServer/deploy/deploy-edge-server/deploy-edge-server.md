---
title: Implementar el servidor perimetral en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Resumen: Conozca cómo implementar un servidor perimetral o un grupo de servidores de borde en el Skype para entorno Business Server 2015.'
ms.openlocfilehash: 38eb0344488512a47f4dc21223d881c15f618e22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-edge-server-in-skype-for-business-server-2015"></a><span data-ttu-id="acf99-103">Implementar el servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="acf99-103">Deploy Edge Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="acf99-104">**Resumen:** Aprenda a implementar un servidor perimetral o un grupo de servidores de borde en el Skype para entorno Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="acf99-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server 2015 environment.</span></span>
  
<span data-ttu-id="acf99-105">¿Por qué implementar un servidor perimetral o un grupo de servidores de borde en el Skype para Business Server 2015 entorno?</span><span class="sxs-lookup"><span data-stu-id="acf99-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server 2015 environment?</span></span> <span data-ttu-id="acf99-106">Es necesario si necesita que usuarios externos que no hayan iniciado sesión en la red interna de las organizaciones puedan interactuar con los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="acf99-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="acf99-107">Estos usuarios externos podrían ser usuarios remotos anónimos y autenticados, socios federados u otros clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="acf99-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server-2015"></a><span data-ttu-id="acf99-108">Lista de comprobación de implementación para el borde de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="acf99-108">Deployment checklist for the Edge, for Skype for Business Server 2015</span></span>

<span data-ttu-id="acf99-109">Como se mencionó anteriormente, un lote entra en una implementación de servidor perimetral de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="acf99-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server 2015.</span></span> <span data-ttu-id="acf99-110">Esta lista de comprobación proporciona una visión general de las tareas que debe realizar y vínculos a pasos más detallados.</span><span class="sxs-lookup"><span data-stu-id="acf99-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="acf99-111">Esperamos que haya empezado en la sección [Planear implementaciones de servidor perimetral de Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) .</span><span class="sxs-lookup"><span data-stu-id="acf99-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="acf99-112">Si no es así, muchas de las cosas a las que nos referimos se detallan allí.</span><span class="sxs-lookup"><span data-stu-id="acf99-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="acf99-113">La sección de implementación contiene solo los procedimientos, por lo que si desea conocer la lógica que impera en estos pasos, la planificación es el lugar en el que empezar.</span><span class="sxs-lookup"><span data-stu-id="acf99-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="acf99-114">Esta documentación también supone que también se ha hecho la implementación básica de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="acf99-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server 2015.</span></span> <span data-ttu-id="acf99-115">Puede hacer esa implementación side-by-side con el borde, pero es necesario seguir primero esos pasos y, a continuación, podrá realizar los cambios de la topología del borde que se mencionan aquí.</span><span class="sxs-lookup"><span data-stu-id="acf99-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="acf99-116">Estos son los pasos de alto nivel que tendrá que seguir y los lugares en los que encontrará estos pasos:</span><span class="sxs-lookup"><span data-stu-id="acf99-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="acf99-117">Requisitos del sistema servidor de borde en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="acf99-117">Edge Server system requirements in Skype for Business Server 2015</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="acf99-118">Edge Server requisitos medioambientales en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="acf99-118">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="acf99-119">Crear la topología de borde para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="acf99-119">Create your Edge topology for Skype for Business Server 2015</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="acf99-120">Implementar servidores perimetrales en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="acf99-120">Deploy Edge Servers in Skype for Business Server 2015</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="acf99-121">Validar la implementación de borde en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="acf99-121">Validate your Edge deployment in Skype for Business Server 2015</span></span>](validate-edge-deployment.md)
    

