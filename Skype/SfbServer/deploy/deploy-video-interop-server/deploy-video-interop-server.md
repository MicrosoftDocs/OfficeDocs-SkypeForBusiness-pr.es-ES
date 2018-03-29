---
title: Implementar el servidor de interoperabilidad de vídeo en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Resumen: Implementar el rol de servidor de VIS de Skype para Business Server 2015.'
ms.openlocfilehash: 0716ce427814c7cf17385074727a7af4f45cfd66
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-video-interop-server-in-skype-for-business-server-2015"></a><span data-ttu-id="7e464-103">Implementar el servidor de interoperabilidad de vídeo en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="7e464-103">Deploy Video Interop Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7e464-104">**Resumen:** Implementar la función de servidor de VIS en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7e464-104">**Summary:** Deploy the VIS server role in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7e464-105">Skype para Business Server ahora puede integrarse directamente con sistemas de teleconferencia de Cisco (VTCs) como el Cisco C60 o MX300 de Cisco.</span><span class="sxs-lookup"><span data-stu-id="7e464-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="7e464-106">Esto requiere la introducción de una nueva función de servidor denominada servidor de interoperabilidad de vídeo (VIS) y la configuración correcta de la VIS y equipamiento interoperará con.</span><span class="sxs-lookup"><span data-stu-id="7e464-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="7e464-107">Los VTC se registran con una infraestructura existente de Cisco, como Cisco Unified Communication Manager (CUCM), y se utiliza un tronco SIP de vídeo entre CUCM y el grupo de VIS.</span><span class="sxs-lookup"><span data-stu-id="7e464-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7e464-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7e464-108">In this section</span></span>

<span data-ttu-id="7e464-109">Para configurar la interoperabilidad entre el servidor o un grupo de servidores de VIS y sistemas de VTC, es necesario realizar los siguientes cinco procesos:</span><span class="sxs-lookup"><span data-stu-id="7e464-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="7e464-110">Crear un grupo de VIS en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7e464-110">Create a VIS pool in Skype for Business Server 2015</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="7e464-111">Implementar la función de servidor de VIS en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7e464-111">Deploy the VIS server role in Skype for Business Server 2015</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="7e464-112">Configurar el servidor de interoperabilidad vídeo en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7e464-112">Configure the Video Interop Server in Skype for Business Server 2015</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="7e464-113">Configurar CUCM para la interoperación con Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7e464-113">Configure CUCM for Interoperation with Skype for Business Server 2015</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="7e464-114">Configurar una VTC para la interoperación con Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7e464-114">Configure a VTC for Interoperation with Skype for Business Server 2015</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="7e464-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7e464-115">Related sections</span></span>

[<span data-ttu-id="7e464-116">Plan de vídeo servidor interoperabilidad en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7e464-116">Plan for Video Interop Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/video-interop-server.md)
  

