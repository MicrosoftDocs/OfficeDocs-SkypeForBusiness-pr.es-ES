---
title: CcServerCertificate renovar
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: El cmdlet Renew-CcServerCertificate renueva los certificados de Skype Empresarial Cloud Connector Edition cuando están a punto de expirar o ya han expirado. Este comando se cambió a CcServerCertificate de actualización en nube conector 2.0 y versiones posteriores.
ms.openlocfilehash: 3d895a24c4cc8b400aa48ce394324435cfbb3979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="c970f-104">CcServerCertificate renovar</span><span class="sxs-lookup"><span data-stu-id="c970f-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="c970f-105">El cmdlet Renew-CcServerCertificate renueva los certificados de Skype Empresarial Cloud Connector Edition cuando están a punto de expirar o ya han expirado.</span><span class="sxs-lookup"><span data-stu-id="c970f-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="c970f-106">Este comando se cambió a CcServerCertificate de actualización en nube conector 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="c970f-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="c970f-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c970f-107">Examples</span></span>
<span data-ttu-id="c970f-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c970f-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="c970f-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="c970f-109">Example 1</span></span>

<span data-ttu-id="c970f-110">En el siguiente ejemplo se renuevan los certificados del almacén de administración central, el servidor de mediación y el servidor perimetral cuando los certificados están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="c970f-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="c970f-111">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="c970f-111">Example 2</span></span>

<span data-ttu-id="c970f-112">En el siguiente ejemplo se renuevan los certificados del servidor de mediación y el servidor perimetral cuando están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="c970f-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="c970f-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="c970f-113">Detailed Description</span></span>
<span data-ttu-id="c970f-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c970f-114"></span></span>

<span data-ttu-id="c970f-115">Conector de nube emiten certificados internos en el almacén de Administración Central, el servidor de mediación y el servidor perimetral son válidas durante dos años después de que se emiten desde un servicio de entidad emisora de certificados.</span><span class="sxs-lookup"><span data-stu-id="c970f-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="c970f-116">Si los certificados están a punto de expirar o ya han expirado, ejecute el cmdlet Renew-CcServerCertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="c970f-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="c970f-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c970f-117">Parameters</span></span>
<span data-ttu-id="c970f-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c970f-118"></span></span>

|<span data-ttu-id="c970f-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="c970f-119">**Parameter**</span></span>|<span data-ttu-id="c970f-120">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="c970f-120">**Required**</span></span>|<span data-ttu-id="c970f-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c970f-121">**Type**</span></span>|<span data-ttu-id="c970f-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c970f-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c970f-123">Roles</span><span class="sxs-lookup"><span data-stu-id="c970f-123">Roles</span></span>  <br/> |<span data-ttu-id="c970f-124">Opcional </span><span class="sxs-lookup"><span data-stu-id="c970f-124">Optional</span></span>  <br/> |<span data-ttu-id="c970f-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="c970f-125">System.Array</span></span>  <br/> | <span data-ttu-id="c970f-126">Matriz de roles de servidor de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c970f-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c970f-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="c970f-127">Input Types</span></span>
<span data-ttu-id="c970f-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c970f-128"></span></span>

<span data-ttu-id="c970f-p104">Ninguno. El cmdlet Renew-CcServerCertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="c970f-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c970f-131">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="c970f-131">Return Types</span></span>
<span data-ttu-id="c970f-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c970f-132"></span></span>

<span data-ttu-id="c970f-133">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c970f-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c970f-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c970f-134">See also</span></span>
<span data-ttu-id="c970f-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c970f-135"></span></span>

[<span data-ttu-id="c970f-136">Restablecer CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="c970f-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="c970f-137">CcServerCertificate renovar</span><span class="sxs-lookup"><span data-stu-id="c970f-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="c970f-138">CcRootCertificate de exportación</span><span class="sxs-lookup"><span data-stu-id="c970f-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

