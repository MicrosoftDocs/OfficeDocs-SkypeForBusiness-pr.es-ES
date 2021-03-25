---
title: Actualizar el certificado de límite
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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye pasos detallados para actualizar el certificado perimetral como parte de la consolidación de la nube para Teams y Skype Empresarial.
ms.openlocfilehash: 724ac63239c881283368fbd617ce0654d49fc0e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120349"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="cdf7a-103">Actualizar el certificado de límite</span><span class="sxs-lookup"><span data-stu-id="cdf7a-103">Update the edge certificate</span></span>

<span data-ttu-id="cdf7a-104">Actualizar el certificado perimetral es el paso clave para garantizar que un entorno local con SipDomain1 pueda unirse a un entorno de nube con SipDomain2 y garantizar el enrutamiento adecuado en un entorno de espacio de direcciones compartido en los dos dominios SIP.</span><span class="sxs-lookup"><span data-stu-id="cdf7a-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="cdf7a-105">Vea el paso 14 en [Consolidación](cloud-consolidation.md) en la nube para Teams y Skype Empresarial para ver el contexto en el que puede realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="cdf7a-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="cdf7a-106">En nuestros ejemplos, SipDomain1 es AcquiredCompany. <span> com y SipDomain2 es OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="cdf7a-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="cdf7a-107">El nombre alternativo de sujeto (SAN) del certificado en todos los servidores perimetrales del entorno local debe actualizarse para incluir todos los dominios SIP que existen en el espacio empresarial en línea puro (excluyendo cualquier onmicrosoft. <span> dominios com), con el formato "sip. \<domain> ".</span><span class="sxs-lookup"><span data-stu-id="cdf7a-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="cdf7a-108">En nuestro ejemplo, se trata de sip. OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="cdf7a-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="cdf7a-109">Este paso es fundamental antes de migrar cualquier usuario a la nube.</span><span class="sxs-lookup"><span data-stu-id="cdf7a-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="cdf7a-110">**Pasos:**</span><span class="sxs-lookup"><span data-stu-id="cdf7a-110">**Steps:**</span></span>

1.  <span data-ttu-id="cdf7a-111">Obtenga un nuevo certificado perimetral externo para el servidor perimetral que tenga todas las entradas existentes más entradas adicionales en el SAN para todos los dominios SIP del entorno de nube (excluyendo los dominios \*.onmicrosoft.com) con el formato <DomainName> "sip.".</span><span class="sxs-lookup"><span data-stu-id="cdf7a-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="cdf7a-112">Instale el certificado localmente en cada servidor perimetral y asígnelo al servicio perimetral de Skype en cada uno de los servicios perimetrales.</span><span class="sxs-lookup"><span data-stu-id="cdf7a-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="cdf7a-113">Para obtener pasos detallados, vea la sección "Certificados de interfaz perimetral externa" en [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="cdf7a-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).</span></span>
3.  <span data-ttu-id="cdf7a-114">Reinicie el servicio perimetral en cada uno de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="cdf7a-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="cdf7a-115">Puede hacerlo en un solo cuadro con los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cdf7a-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="cdf7a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdf7a-116">See also</span></span>

[<span data-ttu-id="cdf7a-117">Consolidación en la nube para Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="cdf7a-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)