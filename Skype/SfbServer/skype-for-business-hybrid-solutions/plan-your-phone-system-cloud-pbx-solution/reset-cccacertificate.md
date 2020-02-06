---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: El cmdlet Reset-CcCACertificate reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824256"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="e00f9-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="e00f9-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="e00f9-104">El cmdlet Reset-CcCACertificate reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.</span><span class="sxs-lookup"><span data-stu-id="e00f9-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="e00f9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e00f9-105">Parameters</span></span>

<span data-ttu-id="e00f9-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e00f9-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e00f9-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e00f9-107">Examples</span></span>
<span data-ttu-id="e00f9-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e00f9-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e00f9-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e00f9-109">Example 1</span></span>

<span data-ttu-id="e00f9-110">En el siguiente ejemplo se reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz:</span><span class="sxs-lookup"><span data-stu-id="e00f9-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="e00f9-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="e00f9-111">Detailed Description</span></span>
<span data-ttu-id="e00f9-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e00f9-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="e00f9-113">Si el certificado de CA raíz está en peligro o ya no es seguro, deberá actualizar este certificado y todos los certificados emitidos por la CA raíz.</span><span class="sxs-lookup"><span data-stu-id="e00f9-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="e00f9-114">El cmdlet Reset-CcCACertificate revoca todos los certificados, desinstala y vuelve a instalar la entidad de certificación, y limpia todos los certificados relacionados con el servicio de la entidad de certificación antigua.</span><span class="sxs-lookup"><span data-stu-id="e00f9-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="e00f9-115">Para obtener más información, consulte "los certificados de la entidad emisora de certificados o los certificados internos emitidos para CMS, servidor de mediación y servidor perimetral están cerca de la fecha de expiración o se han visto comprometidos" en solucionar problemas de implementación en la nube.</span><span class="sxs-lookup"><span data-stu-id="e00f9-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e00f9-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="e00f9-116">Input Types</span></span>
<span data-ttu-id="e00f9-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e00f9-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e00f9-p102">Ninguno. El cmdlet Reset-CcCACertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="e00f9-p102">None. The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e00f9-120">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="e00f9-120">Return Types</span></span>
<span data-ttu-id="e00f9-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e00f9-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e00f9-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e00f9-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e00f9-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e00f9-123">See also</span></span>
<span data-ttu-id="e00f9-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e00f9-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e00f9-125">[Renovar-CcCACertificate](renew-cccacertificate.md) Versión 1.4.2</span><span class="sxs-lookup"><span data-stu-id="e00f9-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="e00f9-126">[Renovar-CcServerCertificate](renew-ccservercertificate.md) Versión 1.4.2</span><span class="sxs-lookup"><span data-stu-id="e00f9-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="e00f9-127">[Update-CcCACertificate](update-cccacertificate.md) Versión 2,0 y posteriores</span><span class="sxs-lookup"><span data-stu-id="e00f9-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="e00f9-128">[Renovar-CcServerCertificate](renew-ccservercertificate.md) Versión 2,0 y posteriores</span><span class="sxs-lookup"><span data-stu-id="e00f9-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="e00f9-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="e00f9-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

