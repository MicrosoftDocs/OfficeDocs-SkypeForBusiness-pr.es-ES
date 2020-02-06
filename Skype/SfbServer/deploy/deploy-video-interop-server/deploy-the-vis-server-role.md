---
title: Implementar el rol de servidor VIS en Skype empresarial Server
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
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Resumen: implementar el rol servidor de interoperabilidad de video (VIS) en Skype empresarial Server.'
ms.openlocfilehash: 1fadab718a37dba2ffee5338d4dc898316b4d24d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798047"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="96c32-103">Implementar el rol de servidor VIS en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="96c32-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="96c32-104">**Resumen:** Implementar el rol servidor de interoperabilidad de video (VIS) en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="96c32-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="96c32-105">Para configurar el servicio VIS en el servidor que se acaba de crear en el generador de topología, inicie el Asistente para la implementación de Skype empresarial Server, pulse **instalar o actualice el sistema de Skype empresarial Server** y siga estos pasos en el asistente:</span><span class="sxs-lookup"><span data-stu-id="96c32-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="96c32-106">Seleccione **Instalar almacén de configuración local**.</span><span class="sxs-lookup"><span data-stu-id="96c32-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="96c32-107">Seleccione **configurar o quitar componentes de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="96c32-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="96c32-108">Seleccione **Solicitar, instalar o asignar certificados**.</span><span class="sxs-lookup"><span data-stu-id="96c32-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="96c32-109">Seleccione **Iniciar servicios**.</span><span class="sxs-lookup"><span data-stu-id="96c32-109">Select **Start services**.</span></span>
    
<span data-ttu-id="96c32-110">The software for this service is now installed and running.</span><span class="sxs-lookup"><span data-stu-id="96c32-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="96c32-111">Puede abrir la herramienta servicios de MMC para ver si el servicio **servidor de interoperabilidad de Skype empresarial Server** se está ejecutando junto con otros servicios de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="96c32-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="96c32-112">Next, you must configure the VIS server or pool.</span><span class="sxs-lookup"><span data-stu-id="96c32-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="96c32-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="96c32-113">See also</span></span>

[<span data-ttu-id="96c32-114">Configurar el servidor de interoperabilidad de vídeo en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="96c32-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
