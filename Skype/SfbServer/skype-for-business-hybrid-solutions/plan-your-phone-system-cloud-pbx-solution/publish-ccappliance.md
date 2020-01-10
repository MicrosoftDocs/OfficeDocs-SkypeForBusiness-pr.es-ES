---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 'El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración de inquilino en línea y la publica en el dispositivo de Skype Empresarial Cloud Connector Edition en el servidor host. '
ms.openlocfilehash: da9135f669cb5b8cbe127295b20d82fd1632a3d3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003090"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="b76e5-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b76e5-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="b76e5-104">El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración de inquilino en línea y la publica en el dispositivo de Skype Empresarial Cloud Connector Edition en el servidor host. </span><span class="sxs-lookup"><span data-stu-id="b76e5-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="b76e5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b76e5-105">Parameters</span></span>

<span data-ttu-id="b76e5-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b76e5-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b76e5-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b76e5-107">Examples</span></span>
<span data-ttu-id="b76e5-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b76e5-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="b76e5-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="b76e5-109">Example 1</span></span>

<span data-ttu-id="b76e5-110">En el ejemplo siguiente se obtiene información de alta disponibilidad de la configuración del inquilino en línea y se publica en el dispositivo de conector de nube en el servidor host:</span><span class="sxs-lookup"><span data-stu-id="b76e5-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="b76e5-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="b76e5-111">Detailed Description</span></span>
<span data-ttu-id="b76e5-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b76e5-112"></span></span>

<span data-ttu-id="b76e5-p101">La información de alta disponibilidad contiene los FQDN y las direcciones IP del servidor de mediación del sitio RTC. Se agregan nuevos registros A de DNS al servidor de AD para las direcciones IP del servidor de mediación. Se actualizan nuevo elementos de topología en el almacén de administración central para los FQDN y las direcciones IP del servidor de mediación. </span><span class="sxs-lookup"><span data-stu-id="b76e5-p101">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site. New DNS A records are added to the AD Server for Mediation Server IP addresses. New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="b76e5-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="b76e5-116">Input Types</span></span>
<span data-ttu-id="b76e5-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b76e5-117"></span></span>

<span data-ttu-id="b76e5-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b76e5-118">None.</span></span> <span data-ttu-id="b76e5-119">El cmdlet Publish-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="b76e5-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b76e5-120">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="b76e5-120">Return Types</span></span>
<span data-ttu-id="b76e5-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b76e5-121"></span></span>

<span data-ttu-id="b76e5-122">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b76e5-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b76e5-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b76e5-123">See also</span></span>
<span data-ttu-id="b76e5-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b76e5-124"></span></span>

[<span data-ttu-id="b76e5-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b76e5-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="b76e5-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b76e5-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="b76e5-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b76e5-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="b76e5-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b76e5-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

