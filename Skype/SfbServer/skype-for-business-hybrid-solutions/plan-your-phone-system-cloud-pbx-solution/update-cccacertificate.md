---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: El cmdlet Update-CcCACertificate renueva el certificado de la entidad emisora raíz de Skype empresarial Cloud Connector Edition que está cerca de la fecha de expiración o ya ha expirado.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824124"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="2d40f-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="2d40f-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="2d40f-104">El cmdlet Update-CcCACertificate renueva el certificado de la entidad emisora raíz de Skype empresarial Cloud Connector Edition que está cerca de la fecha de expiración o ya ha expirado.</span><span class="sxs-lookup"><span data-stu-id="2d40f-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="2d40f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d40f-105">Parameters</span></span>

<span data-ttu-id="2d40f-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2d40f-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="2d40f-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2d40f-107">Examples</span></span>
<span data-ttu-id="2d40f-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2d40f-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2d40f-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="2d40f-109">Example 1</span></span>

<span data-ttu-id="2d40f-110">En el siguiente ejemplo se renueva el certificado de CA raíz: </span><span class="sxs-lookup"><span data-stu-id="2d40f-110">The following example renews the root CA certificate:</span></span> 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="2d40f-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="2d40f-111">Detailed Description</span></span>
<span data-ttu-id="2d40f-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2d40f-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2d40f-113">El certificado de CA raíz de Cloud Connector es válido durante cinco años a partir de la fecha en que se instaló el servicio de entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="2d40f-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="2d40f-114">Si el certificado raíz está cerca o expirado, ejecute el cmdlet Update-CcCACertificate para renovar el certificado.</span><span class="sxs-lookup"><span data-stu-id="2d40f-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="2d40f-115">Después de la renovación del certificado raíz, se emitirán nuevos certificados automáticamente para el servidor de AD, el almacén de administración central y el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="2d40f-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="2d40f-116">Si hay varios dispositivos en el mismo sitio de la RTC, ejecute el cmdlet Update-CcCACertificate en todos los dispositivos del mismo sitio de la RTC.</span><span class="sxs-lookup"><span data-stu-id="2d40f-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="2d40f-117">Como último paso, ejecute Export-CcRootCertificate para exportar el certificado raíz a un archivo local en el primer dispositivo y después copie e instale el certificado exportado a sus puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="2d40f-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="2d40f-118">Este comando reemplaza el cmdlet Renew-CcCACertificate en el conector en la nube 2,0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="2d40f-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="2d40f-119">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="2d40f-119">Input Types</span></span>
<span data-ttu-id="2d40f-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2d40f-120"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2d40f-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2d40f-121">None.</span></span> <span data-ttu-id="2d40f-122">El cmdlet Update-CcCACertificate no acepta la entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="2d40f-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2d40f-123">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="2d40f-123">Return Types</span></span>
<span data-ttu-id="2d40f-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2d40f-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2d40f-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2d40f-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2d40f-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d40f-126">See also</span></span>
<span data-ttu-id="2d40f-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2d40f-127"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="2d40f-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="2d40f-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="2d40f-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="2d40f-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="2d40f-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="2d40f-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

