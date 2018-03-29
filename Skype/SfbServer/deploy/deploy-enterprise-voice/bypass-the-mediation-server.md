---
title: Configurar la omisión de medios en Skype para Business Server 2015 se omite siempre el servidor de mediación
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Permitir omisión de medios omitir siempre el servidor de mediación en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 5a7ca70b6f060c9d6a5399934fb784c9247e95fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-media-bypass-in-skype-for-business-server-2015-to-always-bypass-the-mediation-server"></a><span data-ttu-id="300f6-103">Configurar la omisión de medios en Skype para Business Server 2015 se omite siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="300f6-103">Configure media bypass in Skype for Business Server 2015 to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="300f6-104">Permitir omisión de medios omitir siempre el servidor de mediación en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="300f6-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="300f6-105">Si utiliza omitir los pasos de este tema para configurar opciones globales de los medios de comunicación, la suposición es que tiene buena conectividad entre Skype para extremos de negocio y cualquier elemento del mismo nivel para el que configuró omisión de medios en la conexión de troncal.</span><span class="sxs-lookup"><span data-stu-id="300f6-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="300f6-106">Si no tiene buena conectividad entre Skype para extremos de negocios y todos los elementos del mismo nivel para el servidor de mediación cuyas conexiones tronco respectivo se han habilitado para la omisión de medios, debe configurar media global omisión para utilizar la información del sitio y región Cuando los medios de comunicación que emplean omitir.</span><span class="sxs-lookup"><span data-stu-id="300f6-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="300f6-107">Esto permite más control sobre la determinación cuando media pasa por alto el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="300f6-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="300f6-108">Para ello, utilice los pasos de [medios configurar Ignorar configuración global de Skype para Business Server 2015 utilizar la información del sitio y región](use-site-and-region-information.md) y [asociar una subred a un sitio de red](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="300f6-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server 2015 to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="300f6-109">Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="300f6-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="300f6-110">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="300f6-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="300f6-111">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="300f6-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="300f6-112">Haga doble clic en la configuración **Global** de la lista.</span><span class="sxs-lookup"><span data-stu-id="300f6-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="300f6-113">En la página **Editar configuración global**, seleccione la casilla **Habilitar omisión de medios**.</span><span class="sxs-lookup"><span data-stu-id="300f6-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="300f6-114">Haga clic en **Omitir siempre**.</span><span class="sxs-lookup"><span data-stu-id="300f6-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="300f6-115">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="300f6-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="300f6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="300f6-116">See also</span></span>

#### 

[<span data-ttu-id="300f6-117">Planear la omisión de medios en Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="300f6-117">Plan for media bypass in Skype for Business 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="300f6-118">Implementar la omisión de medios en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="300f6-118">Deploy media bypass in Skype for Business Server 2015</span></span>](deploy-media-bypass.md)

