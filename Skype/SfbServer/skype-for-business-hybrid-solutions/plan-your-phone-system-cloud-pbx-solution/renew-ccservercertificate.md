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
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: El cmdlet Renew-CcServerCertificate renueva los certificados de Skype Empresarial Cloud Connector Edition cuando están a punto de expirar o ya han expirado. Este comando se cambió a Update-CcServerCertificate en el conector en la nube 2,0 y versiones posteriores.
ms.openlocfilehash: 611eeb648c88411afa5d74cc7564703a5e37e9bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287065"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="f4882-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f4882-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="f4882-105">El cmdlet Renew-CcServerCertificate renueva los certificados de Skype Empresarial Cloud Connector Edition cuando están a punto de expirar o ya han expirado.</span><span class="sxs-lookup"><span data-stu-id="f4882-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="f4882-106">Este comando se cambió a Update-CcServerCertificate en el conector en la nube 2,0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f4882-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="f4882-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f4882-107">Examples</span></span>
<span data-ttu-id="f4882-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f4882-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="f4882-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="f4882-109">Example 1</span></span>

<span data-ttu-id="f4882-110">En el siguiente ejemplo se renuevan los certificados del almacén de administración central, el servidor de mediación y el servidor perimetral cuando los certificados están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="f4882-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="f4882-111">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="f4882-111">Example 2</span></span>

<span data-ttu-id="f4882-112">En el siguiente ejemplo se renuevan los certificados del servidor de mediación y el servidor perimetral cuando están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="f4882-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="f4882-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="f4882-113">Detailed Description</span></span>
<span data-ttu-id="f4882-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f4882-114"></span></span>

<span data-ttu-id="f4882-115">Los certificados internos del conector de nube emitidos para el almacén central de administración, el servidor de mediación y el servidor perimetral son válidos durante dos años después de su emisión desde un servicio de autoridad de certificación.</span><span class="sxs-lookup"><span data-stu-id="f4882-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="f4882-116">Si los certificados están a punto de expirar o ya han expirado, ejecute el cmdlet Renew-CcServerCertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="f4882-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="f4882-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4882-117">Parameters</span></span>
<span data-ttu-id="f4882-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f4882-118"></span></span>

|<span data-ttu-id="f4882-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="f4882-119">**Parameter**</span></span>|<span data-ttu-id="f4882-120">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="f4882-120">**Required**</span></span>|<span data-ttu-id="f4882-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f4882-121">**Type**</span></span>|<span data-ttu-id="f4882-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f4882-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f4882-123">Roles</span><span class="sxs-lookup"><span data-stu-id="f4882-123">Roles</span></span>  <br/> |<span data-ttu-id="f4882-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="f4882-124">Optional</span></span>  <br/> |<span data-ttu-id="f4882-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="f4882-125">System.Array</span></span>  <br/> | <span data-ttu-id="f4882-126">Matriz de roles de servidor de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f4882-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f4882-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="f4882-127">Input Types</span></span>
<span data-ttu-id="f4882-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f4882-128"></span></span>

<span data-ttu-id="f4882-p104">Ninguno. El cmdlet Renew-CcServerCertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="f4882-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f4882-131">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="f4882-131">Return Types</span></span>
<span data-ttu-id="f4882-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f4882-132"></span></span>

<span data-ttu-id="f4882-133">Ninguno</span><span class="sxs-lookup"><span data-stu-id="f4882-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f4882-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4882-134">See also</span></span>
<span data-ttu-id="f4882-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f4882-135"></span></span>

[<span data-ttu-id="f4882-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f4882-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="f4882-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f4882-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="f4882-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="f4882-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

