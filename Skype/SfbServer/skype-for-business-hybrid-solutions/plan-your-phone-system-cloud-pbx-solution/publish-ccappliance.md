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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración de inquilino en línea y la publica en el dispositivo de Skype Empresarial Cloud Connector Edition en el servidor host.
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824316"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="4f54b-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="4f54b-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="4f54b-104">El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración de inquilino en línea y la publica en el dispositivo de Skype Empresarial Cloud Connector Edition en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="4f54b-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="4f54b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f54b-105">Parameters</span></span>

<span data-ttu-id="4f54b-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4f54b-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="4f54b-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4f54b-107">Examples</span></span>
<span data-ttu-id="4f54b-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4f54b-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="4f54b-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="4f54b-109">Example 1</span></span>

<span data-ttu-id="4f54b-110">En el siguiente ejemplo se obtiene información de alta disponibilidad de la configuración de inquilino en línea y se publica en el dispositivo de Cloud Connector en el servidor host:</span><span class="sxs-lookup"><span data-stu-id="4f54b-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="4f54b-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="4f54b-111">Detailed Description</span></span>
<span data-ttu-id="4f54b-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4f54b-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="4f54b-113">La información de alta disponibilidad contiene los FQDN del servidor de mediación y las direcciones IP del sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="4f54b-113">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site.</span></span> <span data-ttu-id="4f54b-114">Se agregan nuevos registros A de DNS al servidor de AD para las direcciones IP del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="4f54b-114">New DNS A records are added to the AD Server for Mediation Server IP addresses.</span></span> <span data-ttu-id="4f54b-115">Los nuevos elementos de topología se actualizan en el Almacén de administración central para los FQDN y las direcciones IP del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="4f54b-115">New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="4f54b-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="4f54b-116">Input Types</span></span>
<span data-ttu-id="4f54b-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4f54b-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="4f54b-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4f54b-118">None.</span></span> <span data-ttu-id="4f54b-119">El Publish-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="4f54b-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4f54b-120">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="4f54b-120">Return Types</span></span>
<span data-ttu-id="4f54b-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4f54b-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="4f54b-122">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4f54b-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4f54b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f54b-123">See also</span></span>
<span data-ttu-id="4f54b-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4f54b-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="4f54b-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="4f54b-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="4f54b-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="4f54b-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="4f54b-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="4f54b-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="4f54b-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="4f54b-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

