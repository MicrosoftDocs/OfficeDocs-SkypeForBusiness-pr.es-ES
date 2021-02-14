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
description: El Update-CcCACertificate cmdlet renueva el certificado de CA raíz de Skype Empresarial Cloud Connector Edition que está a punto de expirar o que ya ha expirado.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824124"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="ef99e-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="ef99e-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="ef99e-104">El Update-CcCACertificate cmdlet renueva el certificado de CA raíz de Skype Empresarial Cloud Connector Edition que está a punto de expirar o que ya ha expirado.</span><span class="sxs-lookup"><span data-stu-id="ef99e-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="ef99e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef99e-105">Parameters</span></span>

<span data-ttu-id="ef99e-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ef99e-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="ef99e-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ef99e-107">Examples</span></span>
<span data-ttu-id="ef99e-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ef99e-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ef99e-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="ef99e-109">Example 1</span></span>

<span data-ttu-id="ef99e-110">En el siguiente ejemplo se renueva el certificado de ca raíz:</span><span class="sxs-lookup"><span data-stu-id="ef99e-110">The following example renews the root CA certificate:</span></span> 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="ef99e-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="ef99e-111">Detailed Description</span></span>
<span data-ttu-id="ef99e-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ef99e-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="ef99e-113">El certificado de entidad de certificación raíz de Cloud Connector es válido durante cinco años a partir de la fecha en que se instala el servicio de entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="ef99e-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="ef99e-114">Si el certificado raíz está a punto de expirar o ya ha expirado, ejecute el cmdlet Update-CcCACertificate para renovar el certificado.</span><span class="sxs-lookup"><span data-stu-id="ef99e-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="ef99e-115">Una vez renovado el certificado raíz, el servidor de AD, el Almacén de administración central y el servidor perimetral recibirán nuevos certificados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ef99e-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="ef99e-116">Si hay varios dispositivos en el mismo sitio RTC, ejecute el cmdlet Update-CcCACertificate en todos los dispositivos del mismo sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="ef99e-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="ef99e-117">Como último paso, ejecute Export-CcRootCertificate para exportar el certificado raíz a un archivo local en el primer dispositivo y, a continuación, copie e instale el certificado exportado en las puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="ef99e-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="ef99e-118">Este comando reemplaza el cmdlet Renew-CcCACertificate en Cloud Connector 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ef99e-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="ef99e-119">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="ef99e-119">Input Types</span></span>
<span data-ttu-id="ef99e-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef99e-120"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ef99e-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ef99e-121">None.</span></span> <span data-ttu-id="ef99e-122">El Update-CcCACertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="ef99e-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ef99e-123">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="ef99e-123">Return Types</span></span>
<span data-ttu-id="ef99e-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef99e-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ef99e-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ef99e-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ef99e-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef99e-126">See also</span></span>
<span data-ttu-id="ef99e-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef99e-127"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="ef99e-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="ef99e-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="ef99e-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="ef99e-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="ef99e-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="ef99e-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

