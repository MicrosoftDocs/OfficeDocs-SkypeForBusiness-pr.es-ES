---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: El cmdlet Update-CcServerCertificate renueva los certificados para Skype empresarial Cloud Connector Edition cuando están cerca de la expiración o ya han expirado.
ms.openlocfilehash: da52efcd3fdf6a0793e085098bf6f72725115e9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824114"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="2908b-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="2908b-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="2908b-104">El cmdlet Update-CcServerCertificate renueva los certificados para Skype empresarial Cloud Connector Edition cuando están cerca de la expiración o ya han expirado.</span><span class="sxs-lookup"><span data-stu-id="2908b-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="2908b-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2908b-105">Examples</span></span>
<span data-ttu-id="2908b-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2908b-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2908b-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="2908b-107">Example 1</span></span>

<span data-ttu-id="2908b-108">En el siguiente ejemplo se renuevan los certificados del almacén de administración central, el servidor de mediación y el servidor perimetral cuando los certificados están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="2908b-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="2908b-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="2908b-109">Example 2</span></span>

<span data-ttu-id="2908b-110">En el siguiente ejemplo se renuevan los certificados del servidor de mediación y el servidor perimetral cuando están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="2908b-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="2908b-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="2908b-111">Detailed Description</span></span>
<span data-ttu-id="2908b-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2908b-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2908b-113">Los certificados internos del conector de nube emitidos para el almacén central de administración, el servidor de mediación y el servidor perimetral son válidos durante dos años después de su emisión desde un servicio de autoridad de certificación.</span><span class="sxs-lookup"><span data-stu-id="2908b-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="2908b-114">Si los certificados están cercanos a la expiración o ya han expirado, ejecute el cmdlet Update-CcServerCertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="2908b-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="2908b-115">Este comando reemplaza el cmdlet Renew-CcServerCertificate en el conector en la nube 2,0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="2908b-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2908b-116">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2908b-116">Parameters</span></span>
<span data-ttu-id="2908b-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2908b-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="2908b-118">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="2908b-118">**Parameter**</span></span>|<span data-ttu-id="2908b-119">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="2908b-119">**Required**</span></span>|<span data-ttu-id="2908b-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2908b-120">**Type**</span></span>|<span data-ttu-id="2908b-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2908b-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2908b-122">Roles</span><span class="sxs-lookup"><span data-stu-id="2908b-122">Roles</span></span>  <br/> |<span data-ttu-id="2908b-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="2908b-123">Optional</span></span>  <br/> |<span data-ttu-id="2908b-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="2908b-124">System.Array</span></span>  <br/> | <span data-ttu-id="2908b-125">Matriz de roles de servidor de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2908b-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2908b-126">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="2908b-126">Input Types</span></span>
<span data-ttu-id="2908b-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2908b-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2908b-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2908b-128">None.</span></span> <span data-ttu-id="2908b-129">El cmdlet Update-CcServerCertificate no acepta la entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="2908b-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2908b-130">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="2908b-130">Return Types</span></span>
<span data-ttu-id="2908b-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2908b-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2908b-132">Ninguno</span><span class="sxs-lookup"><span data-stu-id="2908b-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2908b-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2908b-133">See also</span></span>
<span data-ttu-id="2908b-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2908b-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="2908b-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="2908b-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="2908b-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="2908b-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="2908b-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="2908b-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

