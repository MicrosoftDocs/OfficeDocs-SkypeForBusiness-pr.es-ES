---
title: Implementar el control de admisión de llamadas en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre.
ms.openlocfilehash: 0b2df103c432cd6b304f93b3a36af6e87c4bc2e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233193"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="e204f-103">Implementar el control de admisión de llamadas en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e204f-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="e204f-104">El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre.</span><span class="sxs-lookup"><span data-stu-id="e204f-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="e204f-105">Para obtener más información, consulte [planear el control de admisión de llamadas en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="e204f-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="e204f-106">Para implementar el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="e204f-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="e204f-107">Reúna toda la información necesaria para la topología de red de su empresa, como se describe en [ejemplo: recopilación de requisitos para el control de admisión de llamadas en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e204f-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="e204f-108">Si todavía no lo ha hecho, debe definir los sitios y las regiones de red, y asociar subredes a sitios de red.</span><span class="sxs-lookup"><span data-stu-id="e204f-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="e204f-109">Para obtener más información, consulte [implementar regiones, sitios y subredes de la red en Skype empresarial](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="e204f-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="e204f-110">Crear perfiles de directiva de ancho de banda, como se detalla en [crear perfiles de directiva de ancho de banda en Skype empresarial Server](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e204f-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="e204f-111">Cree vínculos de región de red, como se describe en [vínculos a regiones de red en Skype empresarial Server](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="e204f-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="e204f-112">Cree rutas entre regiones de red, como se detalla en [crear rutas interregional de red en Skype empresarial Server](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="e204f-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="e204f-113">Cree directivas de intersitios de red, como se detalla en [crear directivas entre sitios de red en Skype empresarial Server](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e204f-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="e204f-114">Habilite el control de admisión de llamadas, como se detalla en [Habilitar el control de admisión de llamadas en Skype empresarial Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="e204f-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="e204f-115">Realice unas comprobaciones finales de la configuración para asegurarse de que todo funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="e204f-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="e204f-116">Para obtener más información, consulte [llamar a la implementación de control de admisión: lista de comprobación final para Skype empresarial Server](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="e204f-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

