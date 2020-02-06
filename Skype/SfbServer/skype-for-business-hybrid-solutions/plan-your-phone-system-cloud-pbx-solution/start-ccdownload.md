---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: El cmdlet Start-CcDownload descarga el archivo MSI y los bits de Skype empresarial Cloud Connector Edition de forma sincrónica.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824184"
---
# <a name="start-ccdownload"></a><span data-ttu-id="7617e-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="7617e-103">Start-CcDownload</span></span>
 
<span data-ttu-id="7617e-104">El cmdlet Start-CcDownload descarga el archivo MSI y los bits de Skype empresarial Cloud Connector Edition de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="7617e-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="7617e-105">Con la versión 2,0 y posteriores del conector para la nube, también puede especificar el parámetro DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="7617e-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="7617e-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7617e-106">Examples</span></span>
<span data-ttu-id="7617e-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7617e-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="7617e-108">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="7617e-108">Example 1</span></span>

<span data-ttu-id="7617e-109">En el siguiente ejemplo se descarga el archivo MSI y los bits de conector de la nube de forma sincrónica desde el sitio de descarga pública de conector en la nube:</span><span class="sxs-lookup"><span data-stu-id="7617e-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="7617e-110">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="7617e-110">Example 2</span></span>

<span data-ttu-id="7617e-111">El siguiente ejemplo descarga los bits de conector de la nube y el archivo MSI de forma sincrónica desde un sitio de descarga privada:</span><span class="sxs-lookup"><span data-stu-id="7617e-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="7617e-112">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="7617e-112">Example 3</span></span>

<span data-ttu-id="7617e-113">El tercer ejemplo descarga los bits de conector de la nube y el archivo MSI de forma sincrónica desde un sitio de descarga privada.</span><span class="sxs-lookup"><span data-stu-id="7617e-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="7617e-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="7617e-114">Detailed Description</span></span>
<span data-ttu-id="7617e-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7617e-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="7617e-116">Si hay una nueva versión disponible en el sitio de descarga, Start-CcDownload se descargará e instalará el archivo MSI desde el sitio de descarga y, a continuación, descargará los bits de conector de nube de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="7617e-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="7617e-117">Si no hay ninguna versión nueva del archivo MSI, Start-CcDownload se descargará solo los bits de conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="7617e-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="7617e-118">Si los bits de conector de la nube ya se han descargado, Start-CcDownload no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="7617e-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="7617e-119">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7617e-119">Parameters</span></span>
<span data-ttu-id="7617e-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7617e-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="7617e-121">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="7617e-121">**Parameter**</span></span>|<span data-ttu-id="7617e-122">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="7617e-122">**Required**</span></span>|<span data-ttu-id="7617e-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7617e-123">**Type**</span></span>|<span data-ttu-id="7617e-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7617e-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7617e-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="7617e-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="7617e-126">Opcional </span><span class="sxs-lookup"><span data-stu-id="7617e-126">Optional</span></span> <br/> |<span data-ttu-id="7617e-127">System.String</span><span class="sxs-lookup"><span data-stu-id="7617e-127">System.String</span></span>  <br/> | <span data-ttu-id="7617e-128">La dirección URL completa de una versión específica del conector de nube en el sitio de descarga privada.</span><span class="sxs-lookup"><span data-stu-id="7617e-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="7617e-129">Use este parámetro con precaución: Asegúrese de estar al tanto de qué versión del conector de nube está descargando.</span><span class="sxs-lookup"><span data-stu-id="7617e-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="7617e-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="7617e-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="7617e-131">Opcional</span><span class="sxs-lookup"><span data-stu-id="7617e-131">Optional</span></span>  <br/> |<span data-ttu-id="7617e-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7617e-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="7617e-133">Omita el paso para descargar e instalar MSI desde el sitio de descarga, descargar solo los bits de conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="7617e-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="7617e-134">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="7617e-134">Input Types</span></span>
<span data-ttu-id="7617e-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7617e-135"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="7617e-136">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7617e-136">None.</span></span> <span data-ttu-id="7617e-137">El cmdlet Start-CcDownload no acepta la entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="7617e-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7617e-138">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="7617e-138">Return Types</span></span>
<span data-ttu-id="7617e-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7617e-139"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="7617e-140">Ninguno </span><span class="sxs-lookup"><span data-stu-id="7617e-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7617e-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7617e-141">See also</span></span>
<span data-ttu-id="7617e-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7617e-142"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="7617e-143">Ninguno</span><span class="sxs-lookup"><span data-stu-id="7617e-143">None</span></span>
  

