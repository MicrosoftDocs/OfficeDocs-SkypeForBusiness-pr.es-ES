---
title: Actualizar el certificado perimetral
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye pasos detallados para actualizar el certificado perimetral como parte de la consolidación en la nube para Teams y Skype empresarial.
ms.openlocfilehash: 1c3aaa8859db530ceccbebc68ae76f21e8d4a77f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160783"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="45351-103">Actualizar el certificado perimetral</span><span class="sxs-lookup"><span data-stu-id="45351-103">Update the edge certificate</span></span>

<span data-ttu-id="45351-104">La actualización del certificado perimetral es el paso clave para garantizar que un entorno local con SipDomain1 puede unirse a un entorno en la nube con SipDomain2 y garantizar el enrutamiento adecuado en un entorno de espacio de direcciones compartido entre los dos dominios SIP.</span><span class="sxs-lookup"><span data-stu-id="45351-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="45351-105">Vea el paso 14 de [consolidación en la nube para Teams y Skype empresarial](cloud-consolidation.md) para el contexto en el que puede realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="45351-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="45351-106">En los ejemplos, SipDomain1 es AcquiredCompany. <span>com y SipDomain2 es OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="45351-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="45351-107">El nombre alternativo de sujeto (SAN) del certificado en todos los servidores perimetrales en el entorno local debe actualizarse para incluir todos los dominios SIP que existen en el espacio empresarial en línea puro (excepto cualquier<span> objeto de Microsoft. los dominios com), con el formato "SIP. \<> de dominio ".</span><span class="sxs-lookup"><span data-stu-id="45351-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="45351-108">En nuestro ejemplo, es SIP. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="45351-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="45351-109">Es fundamental realizar este paso antes de migrar los usuarios a la nube.</span><span class="sxs-lookup"><span data-stu-id="45351-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="45351-110">**Pasos:**</span><span class="sxs-lookup"><span data-stu-id="45351-110">**Steps:**</span></span>

1.  <span data-ttu-id="45351-111">Obtenga un nuevo certificado perimetral externo para el servidor perimetral que tiene todas las entradas existentes además de entradas adicionales en el SAN para todos los dominios SIP en el entorno de la nube (excluyendo los dominios \*. onmicrosoft.com) con el formato "SIP. <DomainName>".</span><span class="sxs-lookup"><span data-stu-id="45351-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="45351-112">Instale el certificado de forma local en cada servidor perimetral y asígnelo al servicio perimetral de Skype en cada uno de los servicios perimetrales.</span><span class="sxs-lookup"><span data-stu-id="45351-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="45351-113">Para conocer los pasos detallados, consulte la sección "certificados de la interfaz perimetral externa" en [deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="45351-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="45351-114">Reinicie el servicio perimetral en cada uno de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="45351-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="45351-115">Puede hacerlo para un único cuadro con los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="45351-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="45351-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="45351-116">See also</span></span>

[<span data-ttu-id="45351-117">Consolidación en la nube para Teams y Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="45351-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)