---
title: Implementar el control de admisión de llamadas en Skype Empresarial Server 2015
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre. Para obtener más información, consulte Plan de control de admisión de llamadas en Skype para Business Server 2015.
ms.openlocfilehash: 0302663546a099e682b5dc405625d4519fe998d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="d4fd9-104">Implementar el control de admisión de llamadas en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d4fd9-104">Deploy call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d4fd9-105">El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-105">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="d4fd9-106">Para obtener más información, consulte [Plan de control de admisión de llamada en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="d4fd9-106">For more information, see [Plan for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="d4fd9-107">Para implementar el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="d4fd9-107">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="d4fd9-108">Recopilar toda la información necesaria para la topología de red de la empresa, como se describe en [ejemplo: recopilación de requisitos para el control de admisión de llamada en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4fd9-108">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="d4fd9-109">Si todavía no lo ha hecho, debe definir los sitios y las regiones de red, y asociar subredes a sitios de red.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-109">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="d4fd9-110">Para obtener más información, vea [implementar regiones de red, sitios y subredes en Skype para negocios 2015](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="d4fd9-110">For details, see [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
3. <span data-ttu-id="d4fd9-111">Crear perfiles de directiva, como se describe en [crear perfiles de directiva de ancho de banda en Skype para Business Server 2015](create-bandwidth-policy-profiles.md) de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="d4fd9-111">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server 2015](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="d4fd9-112">Crear vínculos de región de la red, como se detalla en la [creación de vínculos de red región en Skype para Business Server 2015](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="d4fd9-112">Create network region links, as detailed in [Create network region links in Skype for Business Server 2015](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="d4fd9-113">Crear rutas de Inter-región de la red, como se describe en [crear red interregional las rutas en Skype para Business Server 2015](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="d4fd9-113">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server 2015](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="d4fd9-114">Crear directivas entre sitios de la red, como se detalla en [directivas entre sitios de red crear en Skype para Business Server 2015](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d4fd9-114">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server 2015](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="d4fd9-115">Habilitar control de admisión de llamada, como se describe en [Habilitar control de admisión de llamada en Skype para Business Server 2015](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="d4fd9-115">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="d4fd9-116">Realice unas comprobaciones finales de la configuración para asegurarse de que todo funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-116">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="d4fd9-117">Para obtener más información, consulte [llamar a la implementación de control de admisión: lista de comprobación final para Skype para Business Server 2015](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="d4fd9-117">For details, see [Call admission control deployment: final checklist for Skype for Business Server 2015](final-checklist.md).</span></span>
    

