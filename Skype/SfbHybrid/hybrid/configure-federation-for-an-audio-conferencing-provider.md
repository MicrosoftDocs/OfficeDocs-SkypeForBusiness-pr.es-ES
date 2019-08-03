---
title: Configurar la Federación para un proveedor de servicios de audioconferencia en su implementación híbrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: 'Resumen: Obtenga información sobre cómo configurar la Federación para un proveedor de servicios de audioconferencia en Skype empresarial online.'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160770"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="c03a9-103">Configurar la Federación para un proveedor de servicios de audioconferencia en su implementación híbrida</span><span class="sxs-lookup"><span data-stu-id="c03a9-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="c03a9-104">**Resumen:** Obtenga información sobre cómo configurar la Federación para un proveedor de servicios de audioconferencia en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="c03a9-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="c03a9-105">Si desea usar un proveedor de servicios de audioconferencia (ACP) en su implementación híbrida (local con online), debe configurar la Federación entre su implementación local y el socio de ACP como servidor asociado permitido.</span><span class="sxs-lookup"><span data-stu-id="c03a9-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="c03a9-106">Puede configurar la Federación agregando el dominio del asociado del ACP y el servidor perimetral (esto también puede llamarse servidor proxy de acceso) a la lista de dominios federados para la implementación local.</span><span class="sxs-lookup"><span data-stu-id="c03a9-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="c03a9-107">A continuación, su partner ACP debe agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="c03a9-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="c03a9-108">Póngase en contacto con su proveedor de ACP para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="c03a9-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="c03a9-109">A continuación, su partner ACP debe agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="c03a9-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="c03a9-110">**Adición del dominio ACP y el servidor perimetral como un dominio federado permitido**</span><span class="sxs-lookup"><span data-stu-id="c03a9-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="c03a9-111">Para agregar el dominio ACP como servidor asociado permitido (dominio federado permitido), siga los pasos de [configurar la compatibilidad con dominios externos permitidos](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span><span class="sxs-lookup"><span data-stu-id="c03a9-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="c03a9-112">Para el servidor perimetral, agregue el FQDN del servidor perimetral del asociado del ACP.</span><span class="sxs-lookup"><span data-stu-id="c03a9-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="c03a9-113">Es posible que deba ponerse en contacto con su partner de ACP para obtener el FQDN de su servidor perimetral, al que también puede hacer referencia su ACP como su proxy de acceso.</span><span class="sxs-lookup"><span data-stu-id="c03a9-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="c03a9-114">**Suministro del FQDN de su grupo de servidores perimetrales al asociado del ACP**</span><span class="sxs-lookup"><span data-stu-id="c03a9-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="c03a9-115">El socio de ACP debe configurar la Federación para agregar el dominio local como servidor asociado permitido agregando el FQDN de su grupo de servidores perimetrales como un dominio federado permitido.</span><span class="sxs-lookup"><span data-stu-id="c03a9-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


