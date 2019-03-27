---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: El cmdlet Update-CcServerCertificate renueva los certificados de Skype para conector de nube Business Edition cuando estén cerca de expiración o ya ha caducado.
ms.openlocfilehash: 92f914db04d3a3621624efd5b6a72e249b3eb19e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899662"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="4447e-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="4447e-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="4447e-104">El cmdlet Update-CcServerCertificate renueva los certificados de Skype para conector de nube Business Edition cuando estén cerca de expiración o ya ha caducado.</span><span class="sxs-lookup"><span data-stu-id="4447e-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="4447e-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4447e-105">Examples</span></span>
<span data-ttu-id="4447e-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4447e-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="4447e-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="4447e-107">Example 1</span></span>

<span data-ttu-id="4447e-108">En el siguiente ejemplo se renuevan los certificados del almacén de administración central, el servidor de mediación y el servidor perimetral cuando los certificados están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="4447e-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="4447e-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="4447e-109">Example 2</span></span>

<span data-ttu-id="4447e-110">En el siguiente ejemplo se renuevan los certificados del servidor de mediación y el servidor perimetral cuando están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="4447e-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="4447e-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="4447e-111">Detailed Description</span></span>
<span data-ttu-id="4447e-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4447e-112"></span></span>

<span data-ttu-id="4447e-113">Conector de nube emitidos los certificados internos para el almacén de Administración Central, el servidor de mediación y el servidor perimetral son válidos para dos años después de que se emiten desde un servicio de la entidad emisora de certificados.</span><span class="sxs-lookup"><span data-stu-id="4447e-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="4447e-114">Si los certificados están cerca de expiración o ya ha expirado, ejecutan el cmdlet Update-CcServerCertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="4447e-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="4447e-115">Este comando reemplaza el cmdlet renovar CcServerCertificate en la nube conector 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4447e-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="4447e-116">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4447e-116">Parameters</span></span>
<span data-ttu-id="4447e-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4447e-117"></span></span>

|<span data-ttu-id="4447e-118">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="4447e-118">**Parameter**</span></span>|<span data-ttu-id="4447e-119">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="4447e-119">**Required**</span></span>|<span data-ttu-id="4447e-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4447e-120">**Type**</span></span>|<span data-ttu-id="4447e-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4447e-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4447e-122">Roles</span><span class="sxs-lookup"><span data-stu-id="4447e-122">Roles</span></span>  <br/> |<span data-ttu-id="4447e-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="4447e-123">Optional</span></span>  <br/> |<span data-ttu-id="4447e-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="4447e-124">System.Array</span></span>  <br/> | <span data-ttu-id="4447e-125">Matriz de roles de servidor de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4447e-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4447e-126">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="4447e-126">Input Types</span></span>
<span data-ttu-id="4447e-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4447e-127"></span></span>

<span data-ttu-id="4447e-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4447e-128">None.</span></span> <span data-ttu-id="4447e-129">El cmdlet Update-CcServerCertificate no acepta entradas transferidas.</span><span class="sxs-lookup"><span data-stu-id="4447e-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4447e-130">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="4447e-130">Return Types</span></span>
<span data-ttu-id="4447e-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4447e-131"></span></span>

<span data-ttu-id="4447e-132">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4447e-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4447e-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4447e-133">See also</span></span>
<span data-ttu-id="4447e-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4447e-134"></span></span>

[<span data-ttu-id="4447e-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="4447e-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="4447e-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="4447e-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="4447e-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="4447e-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

