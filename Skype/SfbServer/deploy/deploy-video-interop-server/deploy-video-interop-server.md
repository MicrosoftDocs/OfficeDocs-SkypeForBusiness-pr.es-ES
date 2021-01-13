---
title: Implementar el servidor de interoperabilidad de vídeo en Skype Empresarial Server
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
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Resumen: implemente el rol de servidor VIS en Skype Empresarial Server.'
ms.openlocfilehash: 7b3ee96b1ff2e6c633efa9e1cc98aa14bb5babc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801960"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="12866-103">Implementar el servidor de interoperabilidad de vídeo en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="12866-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="12866-104">**Resumen:** Implemente el rol de servidor VIS en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="12866-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="12866-105">Skype Empresarial Server ahora puede integrarse directamente con los sistemas de teleconferencia (VTC) de Cisco, como Cisco C60 o Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="12866-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="12866-106">Esto requiere la introducción de un nuevo rol de servidor denominado servidor de interoperabilidad de vídeo (VIS) y la configuración correcta tanto del VIS como del equipo con el que interoperará.</span><span class="sxs-lookup"><span data-stu-id="12866-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="12866-107">Un VTC se registra con la infraestructura de Cisco existente, como Cisco Unified Communication Manager (CUCM), y se usa un tronco SIP de vídeo entre CUCM y el grupo vis.</span><span class="sxs-lookup"><span data-stu-id="12866-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="12866-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="12866-108">In this section</span></span>

<span data-ttu-id="12866-109">La configuración de la interoperabilidad entre un servidor o grupo de servidores VIS y sistemas VTC requiere realizar los cinco procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="12866-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="12866-110">Crear un grupo vis en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="12866-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="12866-111">Implementar el rol de servidor VIS en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="12866-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="12866-112">Configurar el servidor de interoperabilidad de vídeo en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="12866-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="12866-113">Configurar CUCM para interoperación con Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="12866-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="12866-114">Configurar una VTC para interoperación con Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="12866-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="12866-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="12866-115">Related sections</span></span>

[<span data-ttu-id="12866-116">Planear el servidor de interoperabilidad de vídeo en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="12866-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

