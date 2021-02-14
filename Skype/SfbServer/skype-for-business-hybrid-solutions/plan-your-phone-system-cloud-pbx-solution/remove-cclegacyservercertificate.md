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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: El cmdlet Remove-CcLegacyServerCertificate quita los certificados de servidor heredados en el almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew CcServerCertificate.
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824286"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="25701-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="25701-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="25701-104">El cmdlet Remove-CcLegacyServerCertificate quita los certificados de servidor heredados en el almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="25701-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="25701-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="25701-105">Examples</span></span>
<span data-ttu-id="25701-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="25701-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="25701-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="25701-107">Example 1</span></span>

<span data-ttu-id="25701-108">En el siguiente ejemplo se quitan los certificados heredados emitidos para el almacén de administración central, el servidor de mediación y el servidor perimetral después de haber renovado los certificados:</span><span class="sxs-lookup"><span data-stu-id="25701-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="25701-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="25701-109">Example 2</span></span>

<span data-ttu-id="25701-110">En el siguiente ejemplo se quitan los certificados emitidos para el servidor de mediación y el servidor perimetral después de haber renovado los certificados:</span><span class="sxs-lookup"><span data-stu-id="25701-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="25701-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25701-111">Parameters</span></span>
<span data-ttu-id="25701-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="25701-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="25701-113">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="25701-113">**Parameter**</span></span>|<span data-ttu-id="25701-114">**Required**</span><span class="sxs-lookup"><span data-stu-id="25701-114">**Required**</span></span>|<span data-ttu-id="25701-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="25701-115">**Type**</span></span>|<span data-ttu-id="25701-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="25701-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="25701-117">Roles</span><span class="sxs-lookup"><span data-stu-id="25701-117">Roles</span></span> <br/> |<span data-ttu-id="25701-118">Opcional</span><span class="sxs-lookup"><span data-stu-id="25701-118">Optional</span></span>  <br/> |<span data-ttu-id="25701-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="25701-119">System.Array</span></span>  <br/> | <span data-ttu-id="25701-120">Matriz de roles de servidor de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="25701-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="25701-121">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="25701-121">Input Types</span></span>
<span data-ttu-id="25701-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="25701-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="25701-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="25701-123">None.</span></span> <span data-ttu-id="25701-124">El Remove-CcLegacyServerCertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="25701-124">The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="25701-125">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="25701-125">Return Types</span></span>
<span data-ttu-id="25701-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="25701-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="25701-127">Ninguno</span><span class="sxs-lookup"><span data-stu-id="25701-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="25701-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="25701-128">See also</span></span>
<span data-ttu-id="25701-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="25701-129"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="25701-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="25701-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="25701-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="25701-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="25701-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="25701-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="25701-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="25701-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

