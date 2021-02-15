---
title: Expansor de configuración de control de admisión de llamadas
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: El control de admisión de llamadas (CAC) consiste en una red de regiones, sitios y subredes que permiten aplicar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Una vez configurada la red para CAC, el control de admisión de llamadas debe habilitarse para que se puedan aplicar las limitaciones de ancho de banda.
ms.openlocfilehash: 1278cb19e4c8df047d97e5f391ca940255f094cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833120"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="2bffc-104">Expansor de configuración de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="2bffc-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="2bffc-p102">El control de admisión de llamadas (CAC) consiste en una red de regiones, sitios y subredes que permiten aplicar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Una vez configurada la red para CAC, el control de admisión de llamadas debe habilitarse para que se puedan aplicar las limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="2bffc-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2bffc-107">También puede usar el panel de control o los cmdlets del Shell de administración para habilitar el CAC.</span><span class="sxs-lookup"><span data-stu-id="2bffc-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="2bffc-108">En la sección **Configuración del control de admisión de llamadas** del cuadro de diálogo **Editar propiedades** del sitio, puede cambiar las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2bffc-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="2bffc-109">**Habilitar el control de admisión de llamadas** Seleccione esta opción para habilitar el CAC.</span><span class="sxs-lookup"><span data-stu-id="2bffc-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="2bffc-110">Anule la selección de esta opción para deshabilitar el control de admisión de llamadas en toda la red.</span><span class="sxs-lookup"><span data-stu-id="2bffc-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="2bffc-111">Para habilitar el control de admisión de llamadas, la red debe haberse configurado para CAC.</span><span class="sxs-lookup"><span data-stu-id="2bffc-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="2bffc-112">Para obtener más información, consulte [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="2bffc-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="2bffc-113">**Grupo de servidores front-end para ejecutar el control de admisión de llamadas** Si habilitó el CAC, puede cambiar el grupo de servidores que lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="2bffc-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="2bffc-114">Seleccione el grupo de servidores en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2bffc-114">Select the pool from the drop-down list.</span></span>
    

