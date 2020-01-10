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
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'El cmdlet Export-CcRootCertificate exporta el certificado de la CA raíz en un archivo local del servidor host de Skype Empresarial Cloud Connector Edition. '
ms.openlocfilehash: 90eadb257d91a05c05fabbfe1db84b8160ad4a7c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003420"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="ec700-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="ec700-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="ec700-104">El cmdlet Export-CcRootCertificate exporta el certificado de la CA raíz en un archivo local del servidor host de Skype Empresarial Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="ec700-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="ec700-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ec700-105">Examples</span></span>
<span data-ttu-id="ec700-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ec700-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="ec700-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="ec700-107">Example 1</span></span>

<span data-ttu-id="ec700-p101">El siguiente ejemplo establece el parámetro Path como una ruta de acceso del directorio, no como una ruta de archivo. Genera el archivo c:\test\CCERootCertificates.p7b.</span><span class="sxs-lookup"><span data-stu-id="ec700-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="ec700-110">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="ec700-110">Detailed Description</span></span>
<span data-ttu-id="ec700-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ec700-111"></span></span>

<span data-ttu-id="ec700-p102">El cmdlet Export-CcRootCertificate le permite guardar los certificados raíz e intermedio en una ruta de archivo. Esto puede ser útil en situaciones de recuperación ante desastres. </span><span class="sxs-lookup"><span data-stu-id="ec700-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="ec700-114">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec700-114">Parameters</span></span>
<span data-ttu-id="ec700-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ec700-115"></span></span>

|<span data-ttu-id="ec700-116">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="ec700-116">**Parameter**</span></span>|<span data-ttu-id="ec700-117">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="ec700-117">**Required**</span></span>|<span data-ttu-id="ec700-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ec700-118">**Type**</span></span>|<span data-ttu-id="ec700-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ec700-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ec700-120"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="ec700-120">Path</span></span>  <br/> |<span data-ttu-id="ec700-121">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="ec700-121">Required</span></span>  <br/> |<span data-ttu-id="ec700-122">System.String</span><span class="sxs-lookup"><span data-stu-id="ec700-122">System.String</span></span>  <br/> |<span data-ttu-id="ec700-123">Ruta de archivo donde se almacenará el certificado. </span><span class="sxs-lookup"><span data-stu-id="ec700-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ec700-124">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="ec700-124">Input Types</span></span>
<span data-ttu-id="ec700-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec700-125"></span></span>

<span data-ttu-id="ec700-p103">Ninguno. El cmdlet Export-CcRootCertificate no acepta entradas canalizadas. </span><span class="sxs-lookup"><span data-stu-id="ec700-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="ec700-128">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="ec700-128">Return Types</span></span>
<span data-ttu-id="ec700-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec700-129"></span></span>

<span data-ttu-id="ec700-130">Ninguno </span><span class="sxs-lookup"><span data-stu-id="ec700-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec700-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec700-131">See also</span></span>
<span data-ttu-id="ec700-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec700-132"></span></span>

<span data-ttu-id="ec700-133">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ec700-133">None</span></span>
  

