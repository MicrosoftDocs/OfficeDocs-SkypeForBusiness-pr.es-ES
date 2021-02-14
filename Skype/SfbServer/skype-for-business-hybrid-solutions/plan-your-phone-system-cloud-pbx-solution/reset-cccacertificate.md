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
description: El Reset-CcCACertificate cmdlet reinstala el servidor ad de servicio de entidad de certificación para crear un nuevo certificado de CA raíz.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824256"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="993d3-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="993d3-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="993d3-104">El Reset-CcCACertificate cmdlet reinstala el servidor ad de servicio de entidad de certificación para crear un nuevo certificado de CA raíz.</span><span class="sxs-lookup"><span data-stu-id="993d3-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="993d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="993d3-105">Parameters</span></span>

<span data-ttu-id="993d3-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="993d3-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="993d3-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="993d3-107">Examples</span></span>
<span data-ttu-id="993d3-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="993d3-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="993d3-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="993d3-109">Example 1</span></span>

<span data-ttu-id="993d3-110">En el siguiente ejemplo se vuelve a instalar el servidor ad de servicio de entidad de certificación para crear un nuevo certificado de entidad de certificación raíz:</span><span class="sxs-lookup"><span data-stu-id="993d3-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="993d3-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="993d3-111">Detailed Description</span></span>
<span data-ttu-id="993d3-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="993d3-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="993d3-113">Si el certificado de ca raíz está en peligro o ya no es seguro, debe actualizar el certificado de ca raíz y todos los certificados emitidos por la CA raíz.</span><span class="sxs-lookup"><span data-stu-id="993d3-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="993d3-114">El Reset-CcCACertificate revoca todos los certificados, desinstala y reinstala la entidad de certificación y, a continuación, limpia todos los certificados relacionados con el antiguo servicio de entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="993d3-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="993d3-115">Para obtener más información, consulte "Los certificados de entidad de certificación o los certificados internos emitidos a CMS, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro" en la solución de problemas de la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="993d3-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="993d3-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="993d3-116">Input Types</span></span>
<span data-ttu-id="993d3-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="993d3-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="993d3-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="993d3-118">None.</span></span> <span data-ttu-id="993d3-119">El Reset-CcCACertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="993d3-119">The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="993d3-120">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="993d3-120">Return Types</span></span>
<span data-ttu-id="993d3-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="993d3-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="993d3-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="993d3-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="993d3-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="993d3-123">See also</span></span>
<span data-ttu-id="993d3-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="993d3-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="993d3-125">[Renew-CcCACertificate](renew-cccacertificate.md) Solo la versión 1.4.2</span><span class="sxs-lookup"><span data-stu-id="993d3-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="993d3-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Solo la versión 1.4.2</span><span class="sxs-lookup"><span data-stu-id="993d3-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="993d3-127">[Update-CcCACertificate](update-cccacertificate.md) Versión 2.0 y posteriores</span><span class="sxs-lookup"><span data-stu-id="993d3-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="993d3-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Versión 2.0 y posteriores</span><span class="sxs-lookup"><span data-stu-id="993d3-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="993d3-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="993d3-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

