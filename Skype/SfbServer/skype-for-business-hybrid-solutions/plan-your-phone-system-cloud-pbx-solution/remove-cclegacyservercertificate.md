---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: El cmdlet Remove-CcLegacyServerCertificate quita los certificados de servidores heredados en el almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew-CcServerCertificate.
ms.openlocfilehash: 5f148aa083b646565adf0158f34fb15314296170
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250905"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="6f00e-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="6f00e-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="6f00e-104">El cmdlet Remove-CcLegacyServerCertificate quita los certificados de servidores heredados en el almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew-CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="6f00e-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="6f00e-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6f00e-105">Examples</span></span>
<span data-ttu-id="6f00e-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6f00e-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="6f00e-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="6f00e-107">Example 1</span></span>

<span data-ttu-id="6f00e-108">En el siguiente ejemplo se quitan los certificados heredados emitidos para el almacén de administración central, el servidor de mediación y el servidor perimetral después de haber renovado los certificados:</span><span class="sxs-lookup"><span data-stu-id="6f00e-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="6f00e-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="6f00e-109">Example 2</span></span>

<span data-ttu-id="6f00e-110">En el siguiente ejemplo se quitan los certificados emitidos para el servidor de mediación y el servidor perimetral después de haber renovado los certificados: </span><span class="sxs-lookup"><span data-stu-id="6f00e-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="6f00e-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6f00e-111">Parameters</span></span>
<span data-ttu-id="6f00e-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6f00e-112"></span></span>

|<span data-ttu-id="6f00e-113">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="6f00e-113">**Parameter**</span></span>|<span data-ttu-id="6f00e-114">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="6f00e-114">**Required**</span></span>|<span data-ttu-id="6f00e-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6f00e-115">**Type**</span></span>|<span data-ttu-id="6f00e-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6f00e-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="6f00e-117">Roles</span><span class="sxs-lookup"><span data-stu-id="6f00e-117">Roles</span></span> <br/> |<span data-ttu-id="6f00e-118">Opcional</span><span class="sxs-lookup"><span data-stu-id="6f00e-118">Optional</span></span>  <br/> |<span data-ttu-id="6f00e-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="6f00e-119">System.Array</span></span>  <br/> | <span data-ttu-id="6f00e-120">Matriz de roles de servidor de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6f00e-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="6f00e-121">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="6f00e-121">Input Types</span></span>
<span data-ttu-id="6f00e-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f00e-122"></span></span>

<span data-ttu-id="6f00e-p101">Ninguno. El cmdlet Remove-CcLegacyServerCertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="6f00e-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6f00e-125">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="6f00e-125">Return Types</span></span>
<span data-ttu-id="6f00e-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f00e-126"></span></span>

<span data-ttu-id="6f00e-127">Ninguno</span><span class="sxs-lookup"><span data-stu-id="6f00e-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6f00e-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f00e-128">See also</span></span>
<span data-ttu-id="6f00e-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f00e-129"></span></span>

[<span data-ttu-id="6f00e-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="6f00e-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="6f00e-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="6f00e-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="6f00e-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="6f00e-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="6f00e-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="6f00e-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

