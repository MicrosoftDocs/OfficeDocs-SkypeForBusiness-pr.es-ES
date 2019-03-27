---
title: Implementar servidor de interoperabilidad vídeo en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Resumen: Implementación de la función de servidor de respecto de Skype para Business Server.'
ms.openlocfilehash: 3f3c48279ba08ca124f11ac0fb90c457ae69ac9d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884562"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="3c58c-103">Implementar servidor de interoperabilidad vídeo en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3c58c-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="3c58c-104">**Resumen:** Implemente la función de servidor de respecto de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3c58c-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="3c58c-105">Skype para Business Server ahora puede integrarse directamente con sistemas de teleconferencia de Cisco (VTCs) como el Cisco C60 o Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="3c58c-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="3c58c-106">Esto requiere la introducción de una nueva función de servidor llamada el servidor de interoperabilidad de vídeo (VISIBLES) y la configuración correcta del frente y en los equipos de interoperará con.</span><span class="sxs-lookup"><span data-stu-id="3c58c-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="3c58c-107">Los VTC se registran con una infraestructura existente de Cisco, como Cisco Unified Communication Manager (CUCM), y se utiliza un tronco SIP de vídeo entre CUCM y el grupo de VIS.</span><span class="sxs-lookup"><span data-stu-id="3c58c-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="3c58c-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3c58c-108">In this section</span></span>

<span data-ttu-id="3c58c-109">Para configurar la interoperabilidad entre el servidor o un grupo de servidores de VIS y sistemas de VTC, es necesario realizar los siguientes cinco procesos:</span><span class="sxs-lookup"><span data-stu-id="3c58c-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="3c58c-110">Crear un grupo de servidores con respecto de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3c58c-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="3c58c-111">Implementar el rol de servidor de respecto de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3c58c-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="3c58c-112">Configurar el servidor de interoperabilidad vídeo en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3c58c-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="3c58c-113">Configurar CUCM para la interoperación con Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3c58c-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="3c58c-114">Configurar un VTC para la interoperación con Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3c58c-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="3c58c-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3c58c-115">Related sections</span></span>

[<span data-ttu-id="3c58c-116">Planeación de servidor de interoperabilidad vídeo en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3c58c-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

