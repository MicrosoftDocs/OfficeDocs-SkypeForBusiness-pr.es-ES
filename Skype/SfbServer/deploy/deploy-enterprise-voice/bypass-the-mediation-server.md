---
title: Configurar la omisión de medios en Skype Empresarial Server para que siempre omita el servidor de mediación
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilite la omisión de medios para omitir siempre el servidor de mediación en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804220"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="5cd1a-103">Configurar la omisión de medios en Skype Empresarial Server para que siempre omita el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="5cd1a-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="5cd1a-104">Habilite la omisión de medios para omitir siempre el servidor de mediación en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="5cd1a-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="5cd1a-105">Si usa los pasos de este tema para configurar la configuración global para la omisión de medios, se supone que tiene una buena conectividad entre los puntos de conexión de Skype Empresarial y cualquier sistema del mismo nivel para el que configuró la omisión de medios en la conexión troncal.</span><span class="sxs-lookup"><span data-stu-id="5cd1a-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="5cd1a-106">Si no tiene una buena conectividad entre los puntos de conexión de Skype Empresarial y todos los sistemas del mismo nivel con el servidor de mediación cuyas conexiones troncales respectivas se han habilitado para la omisión de medios, debe configurar las opciones globales de omisión de medios para usar información de sitio y región al usar la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="5cd1a-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="5cd1a-107">Con esto se permite un control más preciso para determinar cuándo los medios omiten el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="5cd1a-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="5cd1a-108">Para ello, siga los pasos descritos en Configure [media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and Associate a subnet with a network [site](deploy-network.md#BKMK_AssociateSubnets) instead.</span><span class="sxs-lookup"><span data-stu-id="5cd1a-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="5cd1a-109">Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="5cd1a-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="5cd1a-110">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5cd1a-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="5cd1a-111">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="5cd1a-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="5cd1a-112">Haga doble clic en la configuración **Global** de la lista.</span><span class="sxs-lookup"><span data-stu-id="5cd1a-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="5cd1a-113">En la página **Editar configuración global**, seleccione la casilla **Habilitar desvío de medios**.</span><span class="sxs-lookup"><span data-stu-id="5cd1a-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="5cd1a-114">Haga clic en **Desviar siempre**.</span><span class="sxs-lookup"><span data-stu-id="5cd1a-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="5cd1a-115">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5cd1a-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5cd1a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cd1a-116">See also</span></span>

[<span data-ttu-id="5cd1a-117">Planear la omisión de medios en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5cd1a-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="5cd1a-118">Implementar la omisión de medios en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5cd1a-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

