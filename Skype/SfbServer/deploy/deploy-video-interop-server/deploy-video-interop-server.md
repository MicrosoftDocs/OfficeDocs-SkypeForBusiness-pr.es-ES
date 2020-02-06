---
title: Implementar el servidor de interoperabilidad de vídeo en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Resumen: implementar el rol de servidor VIS en Skype empresarial Server.'
ms.openlocfilehash: 51db16a115871f7720379157aa1b97ae89e9031f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798037"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="2eb23-103">Implementar el servidor de interoperabilidad de vídeo en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2eb23-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="2eb23-104">**Resumen:** Implementar el rol de servidor VIS en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2eb23-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="2eb23-105">Skype empresarial Server ahora puede integrarse directamente con los sistemas de conferencia de Cisco (VTCs), como Cisco C60 o Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="2eb23-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="2eb23-106">Esto requiere la introducción de un nuevo rol de servidor denominado servidor de interoperabilidad de vídeo (VIS) y la configuración correcta de la VIS y del equipo con el que interoperará.</span><span class="sxs-lookup"><span data-stu-id="2eb23-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="2eb23-107">Los VTC se registran con una infraestructura existente de Cisco, como Cisco Unified Communication Manager (CUCM), y se utiliza un tronco SIP de vídeo entre CUCM y el grupo de VIS.</span><span class="sxs-lookup"><span data-stu-id="2eb23-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="2eb23-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2eb23-108">In this section</span></span>

<span data-ttu-id="2eb23-109">Para configurar la interoperabilidad entre el servidor o un grupo de servidores de VIS y sistemas de VTC, es necesario realizar los siguientes cinco procesos:</span><span class="sxs-lookup"><span data-stu-id="2eb23-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="2eb23-110">Crear un grupo de VIS en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2eb23-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="2eb23-111">Implementar el rol de servidor VIS en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2eb23-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="2eb23-112">Configurar el servidor de interoperabilidad de vídeo en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2eb23-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="2eb23-113">Configurar CUCM para interoperabilidad con Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2eb23-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="2eb23-114">Configurar un VTC para la interoperabilidad con Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2eb23-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="2eb23-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2eb23-115">Related sections</span></span>

[<span data-ttu-id="2eb23-116">Planear el servidor de interoperabilidad de vídeo en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2eb23-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

