---
title: Configurar la federación para un proveedor de conferencias de audio en su implementación híbrida
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
description: 'Resumen: Obtenga información sobre cómo configurar la federación para un proveedor de conferencias de audio en Skype para profesionales en línea.'
ms.openlocfilehash: 95ca4e369e42bf265d243842067f531907e26531
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="705f5-103">Configurar la federación para un proveedor de conferencias de audio en su implementación híbrida</span><span class="sxs-lookup"><span data-stu-id="705f5-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>
 
<span data-ttu-id="705f5-104">**Resumen:** Obtenga información sobre cómo configurar la federación para un proveedor de conferencias de audio en Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="705f5-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>
  
<span data-ttu-id="705f5-105">Si desea usar un proveedor de audioconferencia (ACP) para la implementación híbrida (local con en línea), tiene que configurar la federación entre la implementación local y el asociado del ACP como servidor del asociado permitido.</span><span class="sxs-lookup"><span data-stu-id="705f5-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="705f5-106">Para configurar la federación, agregue el dominio del asociado del ACP y el servidor perimetral (también se puede denominar servidor proxy de acceso) a la lista de dominios federados para la implementación local.</span><span class="sxs-lookup"><span data-stu-id="705f5-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="705f5-107">Luego, su asociado del ACP tendrá que agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="705f5-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="705f5-108">Póngase en contacto con su proveedor del ACP para más detalles.</span><span class="sxs-lookup"><span data-stu-id="705f5-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="705f5-109">Su asociado del ACP tendrá que agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="705f5-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>
  
- <span data-ttu-id="705f5-110">**Cómo agregar el dominio del ACP y el servidor perimetral como un dominio federado permitido**</span><span class="sxs-lookup"><span data-stu-id="705f5-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="705f5-111">Para agregar el dominio ACP como un servidor de socio permitido (permitido dominio federado), siga los pasos de [Configuración de compatibilidad con dominios externos permitidos](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span><span class="sxs-lookup"><span data-stu-id="705f5-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="705f5-112">Para el servidor perimetral, agregue el FQDN del servidor perimetral del socio ACP.</span><span class="sxs-lookup"><span data-stu-id="705f5-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="705f5-113">Puede que tenga que contactar con el asociado del ACP para obtener el FQDN del servidor perimetral, que el ACP también puede denominar servidor proxy de acceso.</span><span class="sxs-lookup"><span data-stu-id="705f5-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>
    
- <span data-ttu-id="705f5-114">**Proporcionar el FQDN de su grupo de servidores perimetrales al asociado del ACP**</span><span class="sxs-lookup"><span data-stu-id="705f5-114">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="705f5-115">El asociado del ACP tiene que configurar la federación para agregar su dominio local como un servidor de asociado permitido agregando el FQDN de su grupo de servidores perimetrales como un dominio federado permitido.</span><span class="sxs-lookup"><span data-stu-id="705f5-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>
    

