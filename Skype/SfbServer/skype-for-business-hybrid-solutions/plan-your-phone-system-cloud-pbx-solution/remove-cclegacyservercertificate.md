---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: El cmdlet Remove-CcLegacyServerCertificate quita los certificados de servidores heredados en el almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew-CcServerCertificate.
ms.openlocfilehash: ab332f6f0c88de01f59342002f6387ab8a83a13b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287079"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="ed6d7-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="ed6d7-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="ed6d7-104">El cmdlet Remove-CcLegacyServerCertificate quita los certificados de servidores heredados en el almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew-CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="ed6d7-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="ed6d7-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ed6d7-105">Examples</span></span>
<span data-ttu-id="ed6d7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6d7-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="ed6d7-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="ed6d7-107">Example 1</span></span>

<span data-ttu-id="ed6d7-108">En el siguiente ejemplo se quitan los certificados heredados emitidos para el almacén de administración central, el servidor de mediación y el servidor perimetral después de haber renovado los certificados:</span><span class="sxs-lookup"><span data-stu-id="ed6d7-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="ed6d7-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="ed6d7-109">Example 2</span></span>

<span data-ttu-id="ed6d7-110">En el siguiente ejemplo se quitan los certificados emitidos para el servidor de mediación y el servidor perimetral después de haber renovado los certificados: </span><span class="sxs-lookup"><span data-stu-id="ed6d7-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="ed6d7-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed6d7-111">Parameters</span></span>
<span data-ttu-id="ed6d7-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6d7-112"></span></span>

|<span data-ttu-id="ed6d7-113">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="ed6d7-113">**Parameter**</span></span>|<span data-ttu-id="ed6d7-114">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="ed6d7-114">**Required**</span></span>|<span data-ttu-id="ed6d7-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ed6d7-115">**Type**</span></span>|<span data-ttu-id="ed6d7-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ed6d7-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ed6d7-117">Roles</span><span class="sxs-lookup"><span data-stu-id="ed6d7-117">Roles</span></span> <br/> |<span data-ttu-id="ed6d7-118">Opcional</span><span class="sxs-lookup"><span data-stu-id="ed6d7-118">Optional</span></span>  <br/> |<span data-ttu-id="ed6d7-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="ed6d7-119">System.Array</span></span>  <br/> | <span data-ttu-id="ed6d7-120">Matriz de roles de servidor de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ed6d7-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ed6d7-121">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="ed6d7-121">Input Types</span></span>
<span data-ttu-id="ed6d7-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6d7-122"></span></span>

<span data-ttu-id="ed6d7-p101">Ninguno. El cmdlet Remove-CcLegacyServerCertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="ed6d7-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ed6d7-125">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="ed6d7-125">Return Types</span></span>
<span data-ttu-id="ed6d7-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6d7-126"></span></span>

<span data-ttu-id="ed6d7-127">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ed6d7-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ed6d7-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed6d7-128">See also</span></span>
<span data-ttu-id="ed6d7-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6d7-129"></span></span>

[<span data-ttu-id="ed6d7-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="ed6d7-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="ed6d7-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="ed6d7-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="ed6d7-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="ed6d7-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="ed6d7-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="ed6d7-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

