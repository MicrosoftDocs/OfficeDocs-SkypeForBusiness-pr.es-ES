---
title: Renew-CcServerCertificate
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
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: El cmdlet Renew-CcServerCertificate renueva los certificados de Skype Empresarial Cloud Connector Edition cuando están a punto de expirar o ya han expirado. Este comando se cambió a Update-CcServerCertificate en el conector en la nube 2,0 y versiones posteriores.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824266"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="66467-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="66467-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="66467-105">El cmdlet Renew-CcServerCertificate renueva los certificados de Skype Empresarial Cloud Connector Edition cuando están a punto de expirar o ya han expirado.</span><span class="sxs-lookup"><span data-stu-id="66467-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="66467-106">Este comando se cambió a Update-CcServerCertificate en el conector en la nube 2,0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="66467-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="66467-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="66467-107">Examples</span></span>
<span data-ttu-id="66467-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="66467-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="66467-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="66467-109">Example 1</span></span>

<span data-ttu-id="66467-110">En el siguiente ejemplo se renuevan los certificados del almacén de administración central, el servidor de mediación y el servidor perimetral cuando los certificados están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="66467-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="66467-111">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="66467-111">Example 2</span></span>

<span data-ttu-id="66467-112">En el siguiente ejemplo se renuevan los certificados del servidor de mediación y el servidor perimetral cuando están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="66467-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="66467-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="66467-113">Detailed Description</span></span>
<span data-ttu-id="66467-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="66467-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="66467-115">Los certificados internos del conector de nube emitidos para el almacén central de administración, el servidor de mediación y el servidor perimetral son válidos durante dos años después de su emisión desde un servicio de autoridad de certificación.</span><span class="sxs-lookup"><span data-stu-id="66467-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="66467-116">Si los certificados están a punto de expirar o ya han expirado, ejecute el cmdlet Renew-CcServerCertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="66467-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="66467-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66467-117">Parameters</span></span>
<span data-ttu-id="66467-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="66467-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="66467-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="66467-119">**Parameter**</span></span>|<span data-ttu-id="66467-120">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="66467-120">**Required**</span></span>|<span data-ttu-id="66467-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="66467-121">**Type**</span></span>|<span data-ttu-id="66467-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="66467-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="66467-123">Roles</span><span class="sxs-lookup"><span data-stu-id="66467-123">Roles</span></span>  <br/> |<span data-ttu-id="66467-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="66467-124">Optional</span></span>  <br/> |<span data-ttu-id="66467-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="66467-125">System.Array</span></span>  <br/> | <span data-ttu-id="66467-126">Matriz de roles de servidor de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="66467-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="66467-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="66467-127">Input Types</span></span>
<span data-ttu-id="66467-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66467-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="66467-p104">Ninguno. El cmdlet Renew-CcServerCertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="66467-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="66467-131">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="66467-131">Return Types</span></span>
<span data-ttu-id="66467-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66467-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="66467-133">Ninguno</span><span class="sxs-lookup"><span data-stu-id="66467-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="66467-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66467-134">See also</span></span>
<span data-ttu-id="66467-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66467-135"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="66467-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="66467-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="66467-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="66467-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="66467-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="66467-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

