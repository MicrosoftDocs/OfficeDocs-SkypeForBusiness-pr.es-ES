---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 'El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración de inquilino en línea y la publica en el dispositivo de Skype Empresarial Cloud Connector Edition en el servidor host. '
ms.openlocfilehash: 119b5e816555eedf221d9db06be15e6a778936d4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879808"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="0e279-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0e279-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="0e279-104">El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración de inquilino en línea y la publica en el dispositivo de Skype Empresarial Cloud Connector Edition en el servidor host. </span><span class="sxs-lookup"><span data-stu-id="0e279-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="0e279-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e279-105">Parameters</span></span>

<span data-ttu-id="0e279-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0e279-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="0e279-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0e279-107">Examples</span></span>
<span data-ttu-id="0e279-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0e279-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="0e279-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="0e279-109">Example 1</span></span>

<span data-ttu-id="0e279-110">El siguiente ejemplo obtiene información de alta disponibilidad de la configuración de inquilino en línea y publica en el dispositivo de conector en la nube en el servidor host:</span><span class="sxs-lookup"><span data-stu-id="0e279-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="0e279-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="0e279-111">Detailed Description</span></span>
<span data-ttu-id="0e279-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0e279-112"></span></span>

<span data-ttu-id="0e279-p101">La información de alta disponibilidad contiene los FQDN y las direcciones IP del servidor de mediación del sitio RTC. Se agregan nuevos registros A de DNS al servidor de AD para las direcciones IP del servidor de mediación. Se actualizan nuevo elementos de topología en el almacén de administración central para los FQDN y las direcciones IP del servidor de mediación. </span><span class="sxs-lookup"><span data-stu-id="0e279-p101">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site. New DNS A records are added to the AD Server for Mediation Server IP addresses. New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="0e279-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="0e279-116">Input Types</span></span>
<span data-ttu-id="0e279-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e279-117"></span></span>

<span data-ttu-id="0e279-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0e279-118">None.</span></span> <span data-ttu-id="0e279-119">El cmdlet Publish-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="0e279-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0e279-120">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="0e279-120">Return Types</span></span>
<span data-ttu-id="0e279-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e279-121"></span></span>

<span data-ttu-id="0e279-122">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0e279-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e279-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e279-123">See also</span></span>
<span data-ttu-id="0e279-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e279-124"></span></span>

[<span data-ttu-id="0e279-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0e279-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="0e279-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0e279-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="0e279-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0e279-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="0e279-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0e279-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

