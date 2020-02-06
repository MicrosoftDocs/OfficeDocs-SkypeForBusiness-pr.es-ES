---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: El cmdlet Renew-CcCACertificate renueva los certificados de CA raíz de Skype Empresarial Cloud Connector Edition que están a punto de expirar o que ya han expirado. Este comando se cambió a Update-CcCACertificate en el conector en la nube 2,0 y versiones posteriores.
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824276"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="e99f1-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="e99f1-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="e99f1-105">El cmdlet Renew-CcCACertificate renueva los certificados de CA raíz de Skype Empresarial Cloud Connector Edition que están a punto de expirar o que ya han expirado.</span><span class="sxs-lookup"><span data-stu-id="e99f1-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="e99f1-106">Este comando se cambió a Update-CcCACertificate en el conector en la nube 2,0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e99f1-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="e99f1-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e99f1-107">Parameters</span></span>

<span data-ttu-id="e99f1-108">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e99f1-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e99f1-109">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e99f1-109">Examples</span></span>
<span data-ttu-id="e99f1-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e99f1-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e99f1-111">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e99f1-111">Example 1</span></span>

<span data-ttu-id="e99f1-112">En el siguiente ejemplo se renueva el certificado de CA raíz: </span><span class="sxs-lookup"><span data-stu-id="e99f1-112">The following example renews the root CA certificate:</span></span> 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="e99f1-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="e99f1-113">Detailed Description</span></span>
<span data-ttu-id="e99f1-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e99f1-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="e99f1-115">El certificado de CA raíz de Cloud Connector es válido durante cinco años a partir de la fecha en que se instaló el servicio de entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="e99f1-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="e99f1-p103">Si el certificado raíz está a punto de expirar o ya ha expirado, ejecute el cmdlet Renew-CcCACertificate cmdlet para renovar el certificado. Después de la renovación del certificado raíz, se emitirán nuevos certificados automáticamente para el servidor de AD, el almacén de administración central y el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="e99f1-p103">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="e99f1-118">Si hay varios dispositivos en el mismo sitio RTC, ejecute el cmdlet Renew-CcCACertificate en todos los dispositivos del mismo sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="e99f1-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="e99f1-119">Como último paso, ejecute Export-CcRootCertificate para exportar el certificado raíz a un archivo local en el primer dispositivo y después copie e instale el certificado exportado a sus puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="e99f1-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e99f1-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="e99f1-120">Input Types</span></span>
<span data-ttu-id="e99f1-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e99f1-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e99f1-p104">Ninguno. El cmdlet Renew-CcCACertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="e99f1-p104">None. The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e99f1-124">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="e99f1-124">Return Types</span></span>
<span data-ttu-id="e99f1-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e99f1-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e99f1-126">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e99f1-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e99f1-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e99f1-127">See also</span></span>
<span data-ttu-id="e99f1-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e99f1-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="e99f1-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="e99f1-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="e99f1-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="e99f1-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="e99f1-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="e99f1-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

