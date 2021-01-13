---
title: Implementar el rol de servidor VIS en Skype Empresarial Server
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
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Resumen: implemente el rol de servidor de interoperabilidad de vídeo (VIS) en Skype Empresarial Server.'
ms.openlocfilehash: 773e2ddf790aa1b6c36ff6926d8bc4d16ea613f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801970"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="70052-103">Implementar el rol de servidor VIS en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="70052-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="70052-104">**Resumen:** Implemente el rol de servidor de interoperabilidad de vídeo (VIS) en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="70052-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="70052-105">Para configurar el servicio VIS en el servidor que acaba de crear en el Generador de topologías, inicie el Asistente para la implementación de Skype Empresarial Server, presione Instalar o actualizar el sistema **de Skype** Empresarial Server y siga estos pasos en el asistente:</span><span class="sxs-lookup"><span data-stu-id="70052-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="70052-106">Seleccione **Instalar almacén de configuración local.**</span><span class="sxs-lookup"><span data-stu-id="70052-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="70052-107">Seleccione **Instalar o quitar componentes de Skype Empresarial Server.**</span><span class="sxs-lookup"><span data-stu-id="70052-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="70052-108">Seleccione **Solicitar, instalar o asignar certificados.**</span><span class="sxs-lookup"><span data-stu-id="70052-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="70052-109">Seleccione **Iniciar servicios**.</span><span class="sxs-lookup"><span data-stu-id="70052-109">Select **Start services**.</span></span>
    
<span data-ttu-id="70052-110">El software para este servicio ya está instalado y en ejecución.</span><span class="sxs-lookup"><span data-stu-id="70052-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="70052-111">Puede abrir la herramienta Mmc de servicios para ver si el servicio de servidor de interoperabilidad de vídeo de Skype Empresarial **Server** se está ejecutando junto con otros servicios de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="70052-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="70052-112">A continuación, debe configurar el servidor o el grupo de servidores vis.</span><span class="sxs-lookup"><span data-stu-id="70052-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="70052-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="70052-113">See also</span></span>

[<span data-ttu-id="70052-114">Configurar el servidor de interoperabilidad de vídeo en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="70052-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
