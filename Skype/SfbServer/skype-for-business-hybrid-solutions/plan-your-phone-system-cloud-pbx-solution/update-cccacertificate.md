---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: El cmdlet Update-CcCACertificate renueva el Skype para certificado de entidad emisora de certificados raíz de Business Edition de conector en la nube que está cerca de expiración o ya ha caducado.
ms.openlocfilehash: d123474240fb18ffcb6c1c037cc5407eb4c6c4e3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877936"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="f95ec-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f95ec-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="f95ec-104">El cmdlet Update-CcCACertificate renueva el Skype para certificado de entidad emisora de certificados raíz de Business Edition de conector en la nube que está cerca de expiración o ya ha caducado.</span><span class="sxs-lookup"><span data-stu-id="f95ec-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="f95ec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f95ec-105">Parameters</span></span>

<span data-ttu-id="f95ec-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f95ec-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="f95ec-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f95ec-107">Examples</span></span>
<span data-ttu-id="f95ec-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f95ec-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="f95ec-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="f95ec-109">Example 1</span></span>

<span data-ttu-id="f95ec-110">En el siguiente ejemplo se renueva el certificado de CA raíz: </span><span class="sxs-lookup"><span data-stu-id="f95ec-110">The following example renews the root CA certificate:</span></span> 
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="f95ec-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="f95ec-111">Detailed Description</span></span>
<span data-ttu-id="f95ec-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f95ec-112"></span></span>

<span data-ttu-id="f95ec-113">El certificado de CA raíz de Cloud Connector es válido durante cinco años a partir de la fecha en que se instaló el servicio de entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="f95ec-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="f95ec-114">Si el certificado raíz esté cerca de expiración o ya ha caducado, ejecute el cmdlet Update-CcCACertificate para renovar el certificado.</span><span class="sxs-lookup"><span data-stu-id="f95ec-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="f95ec-115">Después de la renovación del certificado raíz, se emitirán nuevos certificados automáticamente para el servidor de AD, el almacén de administración central y el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="f95ec-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="f95ec-116">Si hay varios dispositivos en el mismo sitio de RTC, ejecute el cmdlet Update-CcCACertificate en todos los equipos del mismo sitio de RTC.</span><span class="sxs-lookup"><span data-stu-id="f95ec-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="f95ec-117">Como último paso, ejecute Export-CcRootCertificate para exportar el certificado raíz a un archivo local en el primer dispositivo y después copie e instale el certificado exportado a sus puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="f95ec-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="f95ec-118">Este comando reemplaza el cmdlet renovar CcCACertificate en la nube conector 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f95ec-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="f95ec-119">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="f95ec-119">Input Types</span></span>
<span data-ttu-id="f95ec-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f95ec-120"></span></span>

<span data-ttu-id="f95ec-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f95ec-121">None.</span></span> <span data-ttu-id="f95ec-122">El cmdlet Update-CcCACertificate no acepta entradas transferidas.</span><span class="sxs-lookup"><span data-stu-id="f95ec-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f95ec-123">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="f95ec-123">Return Types</span></span>
<span data-ttu-id="f95ec-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f95ec-124"></span></span>

<span data-ttu-id="f95ec-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f95ec-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f95ec-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f95ec-126">See also</span></span>
<span data-ttu-id="f95ec-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f95ec-127"></span></span>

[<span data-ttu-id="f95ec-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f95ec-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="f95ec-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f95ec-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="f95ec-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="f95ec-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

