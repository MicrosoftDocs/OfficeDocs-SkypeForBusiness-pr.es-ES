---
title: Implementar el rol de servidor de respecto de Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Resumen: Implementar el rol de servidor de interoperabilidad de vídeo (VISIBLES) de Skype para Business Server.'
ms.openlocfilehash: b52980a727ad0ce13e45e2c833c971598afafa1e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993446"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="17925-103">Implementar el rol de servidor de respecto de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="17925-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="17925-104">**Resumen:** Implementar el rol de servidor de interoperabilidad de vídeo (VISIBLES) de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="17925-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="17925-105">Para configurar el servicio VISIBLES en el servidor que acaba de crear en el generador, iniciar el Skype para el Asistente para la implementación de servidor empresarial, presione **instalación o actualización de Skype para Business Server System** y siga estos pasos en el Asistente para:</span><span class="sxs-lookup"><span data-stu-id="17925-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="17925-106">Seleccione **Instalar almacén de configuración local**.</span><span class="sxs-lookup"><span data-stu-id="17925-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="17925-107">Seleccione **instalar o quitar Skype para los componentes de servidor empresariales**.</span><span class="sxs-lookup"><span data-stu-id="17925-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="17925-108">Seleccione **Solicitar, instalar o asignar certificados**.</span><span class="sxs-lookup"><span data-stu-id="17925-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="17925-109">Seleccione **Iniciar servicios**.</span><span class="sxs-lookup"><span data-stu-id="17925-109">Select **Start services**.</span></span>
    
<span data-ttu-id="17925-110">El software de este servicio ya está instalado y en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="17925-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="17925-111">Puede abrir la herramienta de mmc de servicios para ver si se está ejecutando el servicio de **Skype para Business Server vídeo interoperabilidad Server** junto con otro Skype para servicios de Business Server.</span><span class="sxs-lookup"><span data-stu-id="17925-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="17925-112">A continuación, debe configurar el servidor o grupo de servidores de VIS.</span><span class="sxs-lookup"><span data-stu-id="17925-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="17925-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="17925-113">See also</span></span>

[<span data-ttu-id="17925-114">Configurar el servidor de interoperabilidad vídeo en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="17925-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)