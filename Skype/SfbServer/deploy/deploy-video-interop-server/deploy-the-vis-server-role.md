---
title: Implementar el rol de servidor VIS en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Resumen: Implementar la función de servidor de interoperabilidad de vídeo (VIS) en Skype para Business Server 2015.'
ms.openlocfilehash: 4df688fa3c94f287269297ee895db192c1b924ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server-2015"></a><span data-ttu-id="8d34c-103">Implementar el rol de servidor VIS en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="8d34c-103">Deploy the VIS server role in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8d34c-104">**Resumen:** Implemente la función del servidor de interoperabilidad de vídeo (VIS) en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8d34c-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8d34c-105">Para configurar el servicio VIS en el servidor que acaba de crear en el generador de topología, iniciar el Skype para el Asistente para implementación de Business Server, presione la **instalación o actualización de Skype para el sistema de servidor empresarial** y siga estos pasos en el asistente:</span><span class="sxs-lookup"><span data-stu-id="8d34c-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="8d34c-106">Seleccione **Instalar almacén de configuración local**.</span><span class="sxs-lookup"><span data-stu-id="8d34c-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="8d34c-107">Seleccione **instalar o quitar Skype para los componentes de servidor empresariales**.</span><span class="sxs-lookup"><span data-stu-id="8d34c-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="8d34c-108">Seleccione **Solicitar, instalar o asignar certificados**.</span><span class="sxs-lookup"><span data-stu-id="8d34c-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="8d34c-109">Seleccione **Iniciar servicios**.</span><span class="sxs-lookup"><span data-stu-id="8d34c-109">Select **Start services**.</span></span>
    
<span data-ttu-id="8d34c-110">El software de este servicio ya está instalado y en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="8d34c-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="8d34c-111">Puede abrir la herramienta mmc de servicios para ver si está ejecutando el servicio de **Skype de Business Server interoperabilidad de vídeo** junto con otro Skype para Business Server services.</span><span class="sxs-lookup"><span data-stu-id="8d34c-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="8d34c-112">A continuación, debe configurar el servidor o grupo de servidores de VIS.</span><span class="sxs-lookup"><span data-stu-id="8d34c-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="8d34c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d34c-113">See also</span></span>

#### 

[<span data-ttu-id="8d34c-114">Configurar el servidor de interoperabilidad vídeo en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8d34c-114">Configure the Video Interop Server in Skype for Business Server 2015</span></span>](configure-the-vis.md)

