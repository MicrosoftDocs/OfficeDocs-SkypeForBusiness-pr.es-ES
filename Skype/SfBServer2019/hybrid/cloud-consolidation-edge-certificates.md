---
title: Actualizar el certificado de servidor perimetral
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye los pasos detallados para actualizar el certificado de servidor perimetral como parte de la consolidación en la nube para equipos y Skype para la empresa.
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247726"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="83b0d-103">Actualizar el certificado de servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="83b0d-103">Update the edge certificate</span></span>

<span data-ttu-id="83b0d-104">Actualizar el certificado de servidor perimetral es el paso clave para asegurarse de que un entorno en prem con SipDomain1 puede unirse a un entorno de nube con SipDomain2 y garantizar el enrutamiento adecuado en un entorno de espacio de direcciones compartida entre los dos dominios SIP.</span><span class="sxs-lookup"><span data-stu-id="83b0d-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="83b0d-105">Consulte el paso 14 de [consolidación en la nube para equipos y Skype para la empresa](cloud-consolidation.md) para el contexto en el que es posible que realice este paso.</span><span class="sxs-lookup"><span data-stu-id="83b0d-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="83b0d-106">En los ejemplos, SipDomain1 es AcquiredCompany. <span>com y SipDomain2 es OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="83b0d-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="83b0d-107">El nombre alternativo de sujeto (SAN) del certificado en todos los servidores perimetrales en el entorno local debe actualizarse para incluir todos los dominios SIP que existen en el inquilino online puro (excluyendo cualquier onmicrosoft.<span> dominios de COM), con el formato "sip. \<dominio > ".</span><span class="sxs-lookup"><span data-stu-id="83b0d-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="83b0d-108">En nuestro ejemplo, esto es sip. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="83b0d-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="83b0d-109">Este paso es fundamental para hacer antes de migrar los usuarios a la nube.</span><span class="sxs-lookup"><span data-stu-id="83b0d-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="83b0d-110">**Pasos siguientes:**</span><span class="sxs-lookup"><span data-stu-id="83b0d-110">**Steps:**</span></span>

1.  <span data-ttu-id="83b0d-111">Obtener un nuevo certificado de perímetro externo para el borde que tiene todas las entradas más entradas adicionales en el SAN para todos los dominios SIP en el entorno de nube (excluyendo \*. onmicrosoft.com dominios) con el formato "sip. <DomainName>".</span><span class="sxs-lookup"><span data-stu-id="83b0d-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="83b0d-112">Instale el certificado localmente en cada servidor perimetral y asignar al servicio perimetral de Skype en cada uno de los servicio perimetral.</span><span class="sxs-lookup"><span data-stu-id="83b0d-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="83b0d-113">Para obtener instrucciones detalladas, consulte la sección "Certificados de interfaz de perímetro externo" en [Implementar servicio perimetral en Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="83b0d-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="83b0d-114">Reinicie el servicio perimetral en cada uno de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="83b0d-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="83b0d-115">Puede hacer esto para un cuadro único con los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="83b0d-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="83b0d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="83b0d-116">See also</span></span>

[<span data-ttu-id="83b0d-117">Consolidación de la nube para equipos y Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="83b0d-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)