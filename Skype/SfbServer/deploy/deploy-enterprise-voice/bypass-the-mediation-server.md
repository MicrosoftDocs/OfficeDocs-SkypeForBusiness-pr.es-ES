---
title: Configurar el desvío de medios en Skype para Business Server 2015 omitir siempre el servidor de mediación
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilitar desvío de medios omitir siempre el servidor de mediación en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 9e28af8bd794c3c0924e9a6688eeca159c435d28
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500437"
---
# <a name="configure-media-bypass-in-skype-for-business-server-2015-to-always-bypass-the-mediation-server"></a><span data-ttu-id="9844e-103">Configurar el desvío de medios en Skype para Business Server 2015 omitir siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="9844e-103">Configure media bypass in Skype for Business Server 2015 to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="9844e-104">Habilitar desvío de medios omitir siempre el servidor de mediación en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9844e-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="9844e-105">Si usa los pasos descritos en este tema para establecer la configuración global para los medios de desvío, es de la suposición de que dispone de buena conectividad entre Skype para los extremos de negocio y cualquier elemento del mismo nivel para los que ha configurado el desvío de medios en la conexión del tronco.</span><span class="sxs-lookup"><span data-stu-id="9844e-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="9844e-106">Si no se dispone de buena conectividad entre Skype para los extremos de negocio y todos los elementos del mismo nivel para el servidor de mediación cuyas conexiones de tronco respectivos han sido habilitadas para el desvío de medios, debe establecer la configuración de desvío de medios global para usar información de sitio y región Cuando el desvío de medios que emplean.</span><span class="sxs-lookup"><span data-stu-id="9844e-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="9844e-107">Esto permite más control sobre la determinación de cuándo medios omiten el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="9844e-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="9844e-108">Para ello, utilice los pasos descritos en [la configuración global en Skype para Business Server 2015 utilizar la información de sitio y región de desvío de medios de configurar](use-site-and-region-information.md) y [asociar una subred a un sitio de red](deploy-network.md#BKMK_AssociateSubnets) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9844e-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server 2015 to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="9844e-109">Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="9844e-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="9844e-110">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="9844e-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="9844e-111">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="9844e-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="9844e-112">Haga doble clic en la configuración **Global** de la lista.</span><span class="sxs-lookup"><span data-stu-id="9844e-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="9844e-113">En la página **Editar configuración global**, seleccione la casilla **Habilitar omisión de medios**.</span><span class="sxs-lookup"><span data-stu-id="9844e-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="9844e-114">Haga clic en **Omitir siempre**.</span><span class="sxs-lookup"><span data-stu-id="9844e-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="9844e-115">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9844e-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9844e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9844e-116">See also</span></span>

[<span data-ttu-id="9844e-117">Planeación de desvío de medios en Skype para profesionales de 2015</span><span class="sxs-lookup"><span data-stu-id="9844e-117">Plan for media bypass in Skype for Business 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="9844e-118">Implementar el desvío de medios en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9844e-118">Deploy media bypass in Skype for Business Server 2015</span></span>](deploy-media-bypass.md)