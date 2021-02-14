---
title: Configurar la federación para un proveedor de audioconferencia en la implementación híbrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumen: obtenga información sobre cómo configurar la federación para un proveedor de servicios de audioconferencia en Skype Empresarial Online.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726890"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="24028-103">Configurar la federación para un proveedor de audioconferencia en la implementación híbrida</span><span class="sxs-lookup"><span data-stu-id="24028-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="24028-104">**Resumen:** Obtenga información sobre cómo configurar la federación para un proveedor de audioconferencia en Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="24028-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="24028-105">Si desea usar un proveedor de audioconferencia (ACP) en su implementación híbrida (local con conexión), debe configurar la federación entre la implementación local y el asociado acp como un servidor de asociado permitido.</span><span class="sxs-lookup"><span data-stu-id="24028-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="24028-106">Puede configurar la federación agregando el dominio de socio ACP y el servidor perimetral (también denominado proxy de acceso) a la lista de dominios federados para la implementación local.</span><span class="sxs-lookup"><span data-stu-id="24028-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="24028-107">A continuación, el asociado del ACP debe agregar el FQDN del grupo de servidores perimetrales local a su lista de dominios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="24028-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="24028-108">Póngase en contacto con su proveedor de ACP para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="24028-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="24028-109">A continuación, el asociado del ACP debe agregar el FQDN del grupo de servidores perimetrales local a su lista de dominios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="24028-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="24028-110">**Agregar el dominio ACP y el servidor perimetral como un dominio federado permitido**</span><span class="sxs-lookup"><span data-stu-id="24028-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="24028-111">Para agregar el dominio ACP como un servidor de socio permitido (dominio federado permitido), siga los pasos descritos en Configurar compatibilidad para [dominios externos permitidos.](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)</span><span class="sxs-lookup"><span data-stu-id="24028-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="24028-112">Para el servidor perimetral, agregue el FQDN del servidor perimetral del socio ACP.</span><span class="sxs-lookup"><span data-stu-id="24028-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="24028-113">Es posible que tenga que ponerse en contacto con su partner de ACP para obtener el FQDN de su servidor perimetral, al que también puede hacer referencia su ACP como su proxy de acceso.</span><span class="sxs-lookup"><span data-stu-id="24028-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="24028-114">**Proporcionar el FQDN del grupo de servidores perimetrales al asociado del ACP**</span><span class="sxs-lookup"><span data-stu-id="24028-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="24028-115">El socio ACP debe configurar la federación para agregar el dominio local como un servidor de asociado permitido agregando el FQDN del grupo de servidores perimetrales como un dominio federado permitido.</span><span class="sxs-lookup"><span data-stu-id="24028-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


