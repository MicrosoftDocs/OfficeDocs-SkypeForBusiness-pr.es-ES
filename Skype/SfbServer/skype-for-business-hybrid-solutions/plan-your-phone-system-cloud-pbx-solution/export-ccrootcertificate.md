---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'El cmdlet Export-CcRootCertificate exporta el certificado de la CA raíz en un archivo local del servidor host de Skype Empresarial Cloud Connector Edition. '
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800920"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="f0eb3-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="f0eb3-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="f0eb3-104">El cmdlet Export-CcRootCertificate exporta el certificado de la CA raíz en un archivo local del servidor host de Skype Empresarial Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="f0eb3-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="f0eb3-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f0eb3-105">Examples</span></span>
<span data-ttu-id="f0eb3-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f0eb3-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="f0eb3-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="f0eb3-107">Example 1</span></span>

<span data-ttu-id="f0eb3-p101">El siguiente ejemplo establece el parámetro Path como una ruta de acceso del directorio, no como una ruta de archivo. Genera el archivo c:\test\CCERootCertificates.p7b.</span><span class="sxs-lookup"><span data-stu-id="f0eb3-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="f0eb3-110">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="f0eb3-110">Detailed Description</span></span>
<span data-ttu-id="f0eb3-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f0eb3-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="f0eb3-p102">El cmdlet Export-CcRootCertificate le permite guardar los certificados raíz e intermedio en una ruta de archivo. Esto puede ser útil en situaciones de recuperación ante desastres. </span><span class="sxs-lookup"><span data-stu-id="f0eb3-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="f0eb3-114">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0eb3-114">Parameters</span></span>
<span data-ttu-id="f0eb3-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f0eb3-115"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="f0eb3-116">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="f0eb3-116">**Parameter**</span></span>|<span data-ttu-id="f0eb3-117">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="f0eb3-117">**Required**</span></span>|<span data-ttu-id="f0eb3-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f0eb3-118">**Type**</span></span>|<span data-ttu-id="f0eb3-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f0eb3-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f0eb3-120"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="f0eb3-120">Path</span></span>  <br/> |<span data-ttu-id="f0eb3-121">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="f0eb3-121">Required</span></span>  <br/> |<span data-ttu-id="f0eb3-122">System.String</span><span class="sxs-lookup"><span data-stu-id="f0eb3-122">System.String</span></span>  <br/> |<span data-ttu-id="f0eb3-123">Ruta de archivo donde se almacenará el certificado. </span><span class="sxs-lookup"><span data-stu-id="f0eb3-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f0eb3-124">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="f0eb3-124">Input Types</span></span>
<span data-ttu-id="f0eb3-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f0eb3-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="f0eb3-p103">Ninguno. El cmdlet Export-CcRootCertificate no acepta entradas canalizadas. </span><span class="sxs-lookup"><span data-stu-id="f0eb3-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="f0eb3-128">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="f0eb3-128">Return Types</span></span>
<span data-ttu-id="f0eb3-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f0eb3-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="f0eb3-130">Ninguno </span><span class="sxs-lookup"><span data-stu-id="f0eb3-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f0eb3-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0eb3-131">See also</span></span>
<span data-ttu-id="f0eb3-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f0eb3-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="f0eb3-133">Ninguno</span><span class="sxs-lookup"><span data-stu-id="f0eb3-133">None</span></span>
  

