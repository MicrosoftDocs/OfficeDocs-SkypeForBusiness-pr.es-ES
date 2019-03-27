---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: El cmdlet Reset-CcCACertificate reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.
ms.openlocfilehash: 1ed9aaa8b7caf1edd5324d082094fa247c858853
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898539"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="73431-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="73431-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="73431-104">El cmdlet Reset-CcCACertificate reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.</span><span class="sxs-lookup"><span data-stu-id="73431-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="73431-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73431-105">Parameters</span></span>

<span data-ttu-id="73431-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="73431-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="73431-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="73431-107">Examples</span></span>
<span data-ttu-id="73431-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="73431-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="73431-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="73431-109">Example 1</span></span>

<span data-ttu-id="73431-110">En el siguiente ejemplo se reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz:</span><span class="sxs-lookup"><span data-stu-id="73431-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="73431-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="73431-111">Detailed Description</span></span>
<span data-ttu-id="73431-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="73431-112"></span></span>

<span data-ttu-id="73431-113">Si el certificado de CA raíz está en peligro o ya no es seguro, deberá actualizar este certificado y todos los certificados emitidos por la CA raíz.</span><span class="sxs-lookup"><span data-stu-id="73431-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="73431-114">El cmdlet Reset-CcCACertificate revoca todos los certificados, desinstala y vuelve a instalar la entidad de certificación, y limpia todos los certificados relacionados con el servicio de la entidad de certificación antigua.</span><span class="sxs-lookup"><span data-stu-id="73431-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="73431-115">Para obtener más información, vea "Certificado certificados de entidad de certificación o interno certificados emitidos a CMS, el servidor de mediación, servidor perimetral están cerca de expiración o se ve comprometidos" la solución de problemas de la implementación del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="73431-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="73431-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="73431-116">Input Types</span></span>
<span data-ttu-id="73431-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73431-117"></span></span>

<span data-ttu-id="73431-p102">Ninguno. El cmdlet Reset-CcCACertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="73431-p102">None. The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="73431-120">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="73431-120">Return Types</span></span>
<span data-ttu-id="73431-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73431-121"></span></span>

<span data-ttu-id="73431-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="73431-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="73431-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73431-123">See also</span></span>
<span data-ttu-id="73431-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73431-124"></span></span>

<span data-ttu-id="73431-125">[CcCACertificate renovar](renew-cccacertificate.md) Versión 1.4.2</span><span class="sxs-lookup"><span data-stu-id="73431-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="73431-126">[CcServerCertificate renovar](renew-ccservercertificate.md) Versión 1.4.2</span><span class="sxs-lookup"><span data-stu-id="73431-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="73431-127">[Actualización de CcCACertificate](update-cccacertificate.md) Versión 2.0 y versiones posterior</span><span class="sxs-lookup"><span data-stu-id="73431-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="73431-128">[CcServerCertificate renovar](renew-ccservercertificate.md) Versión 2.0 y versiones posterior</span><span class="sxs-lookup"><span data-stu-id="73431-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="73431-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="73431-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

