---
title: Actualización CcServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: El cmdlet Update-CcServerCertificate renueva los certificados por Skype para conector de nube Business Edition cuando estén cerca de caducidad o ya expiró.
ms.openlocfilehash: 1971f754a7c850d72a3d870e7181738267c99101
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="a85d2-103">Actualización CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="a85d2-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="a85d2-104">El cmdlet Update-CcServerCertificate renueva los certificados por Skype para conector de nube Business Edition cuando estén cerca de caducidad o ya expiró.</span><span class="sxs-lookup"><span data-stu-id="a85d2-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="a85d2-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a85d2-105">Examples</span></span>
<span data-ttu-id="a85d2-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a85d2-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="a85d2-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a85d2-107">Example 1</span></span>

<span data-ttu-id="a85d2-108">En el siguiente ejemplo se renuevan los certificados del almacén de administración central, el servidor de mediación y el servidor perimetral cuando los certificados están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="a85d2-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="a85d2-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="a85d2-109">Example 2</span></span>

<span data-ttu-id="a85d2-110">En el siguiente ejemplo se renuevan los certificados del servidor de mediación y el servidor perimetral cuando están a punto de expirar o ya han expirado:</span><span class="sxs-lookup"><span data-stu-id="a85d2-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="a85d2-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="a85d2-111">Detailed Description</span></span>
<span data-ttu-id="a85d2-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a85d2-112"></span></span>

<span data-ttu-id="a85d2-113">Conector de nube emiten certificados internos en el almacén de Administración Central, el servidor de mediación y el servidor perimetral son válidas durante dos años después de que se emiten desde un servicio de entidad emisora de certificados.</span><span class="sxs-lookup"><span data-stu-id="a85d2-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="a85d2-114">Si los certificados están cerca de caducidad o ya expiró, ejecute el cmdlet Update-CcServerCertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="a85d2-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="a85d2-115">Este comando reemplaza el cmdlet renovar CcServerCertificate en nube conector 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a85d2-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a85d2-116">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a85d2-116">Parameters</span></span>
<span data-ttu-id="a85d2-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a85d2-117"></span></span>

|<span data-ttu-id="a85d2-118">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="a85d2-118">**Parameter**</span></span>|<span data-ttu-id="a85d2-119">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="a85d2-119">**Required**</span></span>|<span data-ttu-id="a85d2-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a85d2-120">**Type**</span></span>|<span data-ttu-id="a85d2-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a85d2-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a85d2-122">Roles</span><span class="sxs-lookup"><span data-stu-id="a85d2-122">Roles</span></span>  <br/> |<span data-ttu-id="a85d2-123">Opcional </span><span class="sxs-lookup"><span data-stu-id="a85d2-123">Optional</span></span>  <br/> |<span data-ttu-id="a85d2-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="a85d2-124">System.Array</span></span>  <br/> | <span data-ttu-id="a85d2-125">Matriz de roles de servidor de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a85d2-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a85d2-126">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="a85d2-126">Input Types</span></span>
<span data-ttu-id="a85d2-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a85d2-127"></span></span>

<span data-ttu-id="a85d2-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a85d2-128">None.</span></span> <span data-ttu-id="a85d2-129">El cmdlet Update-CcServerCertificate no acepta entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="a85d2-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a85d2-130">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="a85d2-130">Return Types</span></span>
<span data-ttu-id="a85d2-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a85d2-131"></span></span>

<span data-ttu-id="a85d2-132">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a85d2-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a85d2-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a85d2-133">See also</span></span>
<span data-ttu-id="a85d2-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a85d2-134"></span></span>

[<span data-ttu-id="a85d2-135">Restablecer CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="a85d2-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="a85d2-136">CcServerCertificate renovar</span><span class="sxs-lookup"><span data-stu-id="a85d2-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="a85d2-137">CcRootCertificate de exportación</span><span class="sxs-lookup"><span data-stu-id="a85d2-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

