---
title: Implementación de control de admisión de llamadas en Skype para Business Server
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre.
ms.openlocfilehash: 52fcedaab781e9ed76222afb32b56840a3b07c1c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892867"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="2178a-103">Implementación de control de admisión de llamadas en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="2178a-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="2178a-104">El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre.</span><span class="sxs-lookup"><span data-stu-id="2178a-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="2178a-105">Para obtener más información, consulte [Plan para el control de admisión de llamadas en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="2178a-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="2178a-106">Para implementar el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="2178a-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="2178a-107">Recopilar toda la información necesaria para la topología de red de empresa, tal como se describe en [ejemplo: recopilación de requisitos de control de admisión de llamadas en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2178a-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="2178a-108">Si todavía no lo ha hecho, debe definir los sitios y las regiones de red, y asociar subredes a sitios de red.</span><span class="sxs-lookup"><span data-stu-id="2178a-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="2178a-109">Para obtener información detallada, consulte [Deploy regiones de red, sitios y las subredes de Skype para la empresa](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="2178a-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="2178a-110">Crear perfiles de directiva, como se detalla en [crear perfiles de directiva de ancho de banda en Skype para Business Server](create-bandwidth-policy-profiles.md) de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="2178a-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="2178a-111">Crear vínculos de región de red, como se detalla en [crear vínculos de región de red en Skype para Business Server](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="2178a-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="2178a-112">Crear rutas de entre regiones de red, como se detalla en [interregionales rutas de red de crear en Skype para Business Server](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="2178a-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="2178a-113">Crear directivas entre sitios de red, como se detalla en [directivas entre sitios de red crear en Skype para Business Server](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2178a-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="2178a-114">Habilitar el control de admisión de llamadas, como se detalla en [Habilitar control de admisión de llamadas en Skype para Business Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="2178a-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="2178a-115">Realice unas comprobaciones finales de la configuración para asegurarse de que todo funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="2178a-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="2178a-116">Para obtener información detallada, vea [implementación de control de admisión de llamadas: lista de comprobación de final de Skype para Business Server](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="2178a-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

