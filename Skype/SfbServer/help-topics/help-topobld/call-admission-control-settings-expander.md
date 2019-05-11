---
title: Expansor de configuración de control de admisión de llamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: El control de admisión de llamadas (CAC) es una red de regiones, sitios y subredes que permiten colocar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Después de configurar la red para el control de admisión de llamadas, deberá habilitarlo para forzar las limitaciones de ancho de banda.
ms.openlocfilehash: afc7f8ef5410b1fc921ef7c6250b79a31ca5c3cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903603"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="346ef-104">Expansor de configuración de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="346ef-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="346ef-p102">El control de admisión de llamadas (CAC) es una red de regiones, sitios y subredes que permiten colocar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Después de configurar la red para el control de admisión de llamadas, deberá habilitarlo para forzar las limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="346ef-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="346ef-107">También puede usar el panel de control o los cmdlets del Shell de administración para habilitar CAC.</span><span class="sxs-lookup"><span data-stu-id="346ef-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="346ef-108">En la sección **Configuración del control de admisión de llamadas** del cuadro de diálogo **Editar propiedades** del sitio, puede cambiar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="346ef-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="346ef-109">**Habilitar el Control de admisión de llamadas** Seleccione esta opción para habilitar el CAC.</span><span class="sxs-lookup"><span data-stu-id="346ef-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="346ef-110">No la seleccione la opción para deshabilitar el control de admisión de llamadas en toda la red.</span><span class="sxs-lookup"><span data-stu-id="346ef-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="346ef-111">Para habilitarlo, debe tener la red convenientemente configurada para ello.</span><span class="sxs-lookup"><span data-stu-id="346ef-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="346ef-112">Para obtener información detallada, vea [implementar el control de admisión de Skype para Business Server 2015 de llamadas](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="346ef-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="346ef-113">**Grupo de servidores Front-End para ejecutar el Control de admisión de llamadas** Si se habilita el CAC, puede cambiar el grupo de servidores que lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="346ef-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="346ef-114">Seleccione el grupo en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="346ef-114">Select the pool from the drop-down list.</span></span>
    

