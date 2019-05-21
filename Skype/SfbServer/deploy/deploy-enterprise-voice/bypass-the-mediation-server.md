---
title: Configurar la omisión de elementos multimedia en Skype empresarial Server para omitir siempre el servidor de mediación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilitar omisión de elementos multimedia para omitir siempre el servidor de mediación en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 0e45f8ede38411974f9433c17ccd0a0946b427ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275881"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="d6b99-103">Configurar la omisión de elementos multimedia en Skype empresarial Server para omitir siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="d6b99-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="d6b99-104">Habilitar omisión de elementos multimedia para omitir siempre el servidor de mediación en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d6b99-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="d6b99-105">Si usa los pasos de este tema para establecer la configuración global para la omisión de medios, se supone que tiene una buena conectividad entre los puntos de conexión de Skype empresarial y cualquier otro elemento del mismo nivel para el que haya configurado el bypass de medios en la conexión troncal.</span><span class="sxs-lookup"><span data-stu-id="d6b99-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="d6b99-106">Si no tiene buena conectividad entre los puntos de conexión de Skype empresarial y todos los elementos del servidor de media cuyas conexiones troncales se hayan habilitado para la omisión de medios, debe configurar la configuración de omisión de multimedia global para usar la información del sitio y de la región. al emplear la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="d6b99-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="d6b99-107">Esto permite un mayor control para determinar cuándo el contenido multimedia pasa por alto el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d6b99-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="d6b99-108">Para ello, use los pasos de [configurar la configuración global de omisión de medios en Skype empresarial Server para usar la información del sitio y de la región](use-site-and-region-information.md) y asociar [una subred con un sitio de red](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="d6b99-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="d6b99-109">Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="d6b99-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="d6b99-110">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d6b99-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="d6b99-111">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="d6b99-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="d6b99-112">Haga doble clic en la configuración **Global** de la lista.</span><span class="sxs-lookup"><span data-stu-id="d6b99-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="d6b99-113">En la página **Editar configuración global**, seleccione la casilla **Habilitar omisión de medios**.</span><span class="sxs-lookup"><span data-stu-id="d6b99-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="d6b99-114">Haga clic en **Omitir siempre**.</span><span class="sxs-lookup"><span data-stu-id="d6b99-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="d6b99-115">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d6b99-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d6b99-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6b99-116">See also</span></span>

[<span data-ttu-id="d6b99-117">Plan de omisión de multimedia en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="d6b99-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="d6b99-118">Implementación de omisión de contenido multimedia en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d6b99-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

