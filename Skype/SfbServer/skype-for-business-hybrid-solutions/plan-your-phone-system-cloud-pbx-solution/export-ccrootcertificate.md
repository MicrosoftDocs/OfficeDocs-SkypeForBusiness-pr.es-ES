---
title: CcRootCertificate de exportación
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: El cmdlet Export-CcRootCertificate exporta el certificado de la CA raíz en un archivo local del servidor host de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 9af3701fd89cf881b4f966c2b00500ad4e55bc9b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="5ef1d-103">CcRootCertificate de exportación</span><span class="sxs-lookup"><span data-stu-id="5ef1d-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="5ef1d-104">El cmdlet Export-CcRootCertificate exporta el certificado de la CA raíz en un archivo local del servidor host de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="5ef1d-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="5ef1d-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5ef1d-105">Examples</span></span>
<span data-ttu-id="5ef1d-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5ef1d-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="5ef1d-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="5ef1d-107">Example 1</span></span>

<span data-ttu-id="5ef1d-108">El siguiente ejemplo establece el parámetro Path como una ruta de acceso del directorio, no como una ruta de archivo.</span><span class="sxs-lookup"><span data-stu-id="5ef1d-108">The following example sets the Path parameter as a directory path—not a file path.</span></span> <span data-ttu-id="5ef1d-109">Genera el archivo c:\test\CCERootCertificates.p7b.</span><span class="sxs-lookup"><span data-stu-id="5ef1d-109">It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="5ef1d-110">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="5ef1d-110">Detailed Description</span></span>
<span data-ttu-id="5ef1d-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5ef1d-111"></span></span>

<span data-ttu-id="5ef1d-112">El cmdlet Export-CcRootCertificate le permite guardar los certificados raíz e intermedio en una ruta de archivo.</span><span class="sxs-lookup"><span data-stu-id="5ef1d-112">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path.</span></span> <span data-ttu-id="5ef1d-113">Esto puede ser útil en situaciones de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="5ef1d-113">This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="5ef1d-114">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ef1d-114">Parameters</span></span>
<span data-ttu-id="5ef1d-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5ef1d-115"></span></span>

|<span data-ttu-id="5ef1d-116">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="5ef1d-116">**Parameter**</span></span>|<span data-ttu-id="5ef1d-117">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="5ef1d-117">**Required**</span></span>|<span data-ttu-id="5ef1d-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5ef1d-118">**Type**</span></span>|<span data-ttu-id="5ef1d-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5ef1d-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5ef1d-120"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="5ef1d-120">Path</span></span>  <br/> |<span data-ttu-id="5ef1d-121"> Obligatorio</span><span class="sxs-lookup"><span data-stu-id="5ef1d-121">Required</span></span>  <br/> |<span data-ttu-id="5ef1d-122">System.String</span><span class="sxs-lookup"><span data-stu-id="5ef1d-122">System.String</span></span>  <br/> |<span data-ttu-id="5ef1d-123">Ruta de archivo donde se almacenará el certificado.</span><span class="sxs-lookup"><span data-stu-id="5ef1d-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5ef1d-124">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="5ef1d-124">Input Types</span></span>
<span data-ttu-id="5ef1d-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ef1d-125"></span></span>

<span data-ttu-id="5ef1d-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5ef1d-126">None.</span></span> <span data-ttu-id="5ef1d-127">El cmdlet Export-CcRootCertificate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="5ef1d-127">The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="5ef1d-128">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="5ef1d-128">Return Types</span></span>
<span data-ttu-id="5ef1d-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ef1d-129"></span></span>

<span data-ttu-id="5ef1d-130">Ninguno</span><span class="sxs-lookup"><span data-stu-id="5ef1d-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5ef1d-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ef1d-131">See also</span></span>
<span data-ttu-id="5ef1d-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ef1d-132"></span></span>

<span data-ttu-id="5ef1d-133">Ninguno</span><span class="sxs-lookup"><span data-stu-id="5ef1d-133">None</span></span>
  

