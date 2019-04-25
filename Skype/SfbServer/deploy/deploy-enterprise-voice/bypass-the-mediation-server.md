---
title: Configurar el desvío de medios en Skype para Business Server omitir siempre el servidor de mediación
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilitar desvío de medios omitir siempre el servidor de mediación en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 31ecb80df342ac68ba6bb28b20248648bd5808c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223778"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="1cdfb-103">Configurar el desvío de medios en Skype para Business Server omitir siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="1cdfb-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="1cdfb-104">Habilitar desvío de medios omitir siempre el servidor de mediación en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="1cdfb-105">Si usa los pasos descritos en este tema para establecer la configuración global para los medios de desvío, es de la suposición de que dispone de buena conectividad entre Skype para los extremos de negocio y cualquier elemento del mismo nivel para los que ha configurado el desvío de medios en la conexión del tronco.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="1cdfb-106">Si no se dispone de buena conectividad entre Skype para los extremos de negocio y todos los elementos del mismo nivel para el servidor de mediación cuyas conexiones de tronco respectivos han sido habilitadas para el desvío de medios, debe establecer la configuración de desvío de medios global para usar información de sitio y región Cuando el desvío de medios que emplean.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="1cdfb-107">Esto permite más control sobre la determinación de cuándo medios omiten el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="1cdfb-108">Para ello, utilice los pasos descritos en [la configuración global en Skype para Business Server usar la información de sitio y región de desvío de medios de configurar](use-site-and-region-information.md) y [asociar una subred a un sitio de red](deploy-network.md#BKMK_AssociateSubnets) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="1cdfb-109">Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="1cdfb-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="1cdfb-110">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="1cdfb-111">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="1cdfb-112">Haga doble clic en la configuración **Global** de la lista.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="1cdfb-113">En la página **Editar configuración global**, seleccione la casilla **Habilitar omisión de medios**.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="1cdfb-114">Haga clic en **Omitir siempre**.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="1cdfb-115">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1cdfb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cdfb-116">See also</span></span>

[<span data-ttu-id="1cdfb-117">Planear el desvío de medios en Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="1cdfb-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="1cdfb-118">Implementar el desvío de medios en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="1cdfb-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

