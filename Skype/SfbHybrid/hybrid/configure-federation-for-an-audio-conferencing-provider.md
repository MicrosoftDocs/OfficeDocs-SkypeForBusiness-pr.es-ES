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
description: 'Resumen: obtenga información sobre cómo configurar la federación para un proveedor de audioconferencia en Skype Empresarial Online.'
ms.openlocfilehash: 5d9c49299452f579cd7c58adf54facb09f0b8a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118979"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="24d68-103">Configurar la federación para un proveedor de audioconferencia en la implementación híbrida</span><span class="sxs-lookup"><span data-stu-id="24d68-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="24d68-104">**Resumen:** Obtenga información sobre cómo configurar la federación para un proveedor de audioconferencia en Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="24d68-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="24d68-105">Si desea usar un proveedor de audioconferencia (ACP) en la implementación híbrida (local con en línea), debe configurar la federación entre la implementación local y el partner ACP como un servidor de partners permitido.</span><span class="sxs-lookup"><span data-stu-id="24d68-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="24d68-106">Puede configurar la federación agregando el dominio de socio ACP y el servidor perimetral (esto también se puede llamar proxy de acceso) a la lista Dominios federados para la implementación local.</span><span class="sxs-lookup"><span data-stu-id="24d68-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="24d68-107">A continuación, el socio ACP debe agregar el FQDN del grupo de servidores perimetrales local a su lista de dominios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="24d68-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="24d68-108">Póngase en contacto con su proveedor de ACP para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="24d68-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="24d68-109">A continuación, el socio ACP debe agregar el FQDN del grupo de servidores perimetrales local a su lista de dominios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="24d68-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="24d68-110">**Agregar el dominio ACP y el servidor perimetral como un dominio federado permitido**</span><span class="sxs-lookup"><span data-stu-id="24d68-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="24d68-111">Para agregar el dominio ACP como un servidor asociado permitido (dominio federado permitido), siga los pasos descritos en Configurar la compatibilidad con [dominios externos permitidos](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains).</span><span class="sxs-lookup"><span data-stu-id="24d68-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains).</span></span> <span data-ttu-id="24d68-112">Para el servidor perimetral, agregue el FQDN del servidor perimetral del socio ACP.</span><span class="sxs-lookup"><span data-stu-id="24d68-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="24d68-113">Es posible que deba ponerse en contacto con su partner ACP para obtener el FQDN de su servidor perimetral, al que también puede hacer referencia su ACP como su proxy de acceso.</span><span class="sxs-lookup"><span data-stu-id="24d68-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="24d68-114">**Proporcionar el FQDN del grupo de servidores perimetrales al socio ACP**</span><span class="sxs-lookup"><span data-stu-id="24d68-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="24d68-115">El partner ACP debe configurar la federación para agregar el dominio local como un servidor de partners permitido agregando el FQDN del grupo de servidores perimetrales como un dominio federado permitido.</span><span class="sxs-lookup"><span data-stu-id="24d68-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>