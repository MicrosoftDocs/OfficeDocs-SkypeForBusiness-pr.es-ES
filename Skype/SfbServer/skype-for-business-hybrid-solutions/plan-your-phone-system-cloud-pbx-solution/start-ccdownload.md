---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: El cmdlet Start-CcDownload descarga el Skype para bits Business Edition de conector en la nube y el archivo msi de forma sincrónica.
ms.openlocfilehash: cc157825df75a4534422cb0a2fd07abb0ae0daea
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893841"
---
# <a name="start-ccdownload"></a><span data-ttu-id="73c62-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="73c62-103">Start-CcDownload</span></span>
 
<span data-ttu-id="73c62-104">El cmdlet Start-CcDownload descarga el Skype para bits Business Edition de conector en la nube y el archivo msi de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="73c62-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="73c62-105">Con la nube conector versión 2.0 y versiones posterior, también puede especificar el parámetro DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="73c62-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="73c62-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="73c62-106">Examples</span></span>
<span data-ttu-id="73c62-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="73c62-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="73c62-108">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="73c62-108">Example 1</span></span>

<span data-ttu-id="73c62-109">En el ejemplo siguiente se descarga los bits de conector en la nube y el archivo msi de forma sincrónica desde el sitio de descarga pública de conector en la nube:</span><span class="sxs-lookup"><span data-stu-id="73c62-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="73c62-110">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="73c62-110">Example 2</span></span>

<span data-ttu-id="73c62-111">En el ejemplo siguiente se descarga los bits de conector en la nube y el archivo msi de forma sincrónica desde un sitio de descarga privada:</span><span class="sxs-lookup"><span data-stu-id="73c62-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="73c62-112">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="73c62-112">Example 3</span></span>

<span data-ttu-id="73c62-113">El tercer ejemplo descarga los bits de conector en la nube y el archivo msi de forma sincrónica desde un sitio de descarga privada.</span><span class="sxs-lookup"><span data-stu-id="73c62-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="73c62-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="73c62-114">Detailed Description</span></span>
<span data-ttu-id="73c62-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="73c62-115"></span></span>

<span data-ttu-id="73c62-116">Si hay una nueva versión en el sitio de descarga, inicio CcDownload descargar e instalar el archivo msi desde el sitio de descarga y, a continuación, descargue los bits de conector en la nube de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="73c62-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="73c62-117">Si no hay ninguna versión nueva del archivo msi, inicio CcDownload descargará sólo los bits de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="73c62-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="73c62-118">Si ya se descargan los bits de conector en la nube, CcDownload de inicio no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="73c62-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="73c62-119">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73c62-119">Parameters</span></span>
<span data-ttu-id="73c62-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="73c62-120"></span></span>

|<span data-ttu-id="73c62-121">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="73c62-121">**Parameter**</span></span>|<span data-ttu-id="73c62-122">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="73c62-122">**Required**</span></span>|<span data-ttu-id="73c62-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="73c62-123">**Type**</span></span>|<span data-ttu-id="73c62-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="73c62-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="73c62-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="73c62-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="73c62-126">Opcional </span><span class="sxs-lookup"><span data-stu-id="73c62-126">Optional</span></span> <br/> |<span data-ttu-id="73c62-127">System.String</span><span class="sxs-lookup"><span data-stu-id="73c62-127">System.String</span></span>  <br/> | <span data-ttu-id="73c62-128">Sitio de descarga de la dirección URL completa de una versión específica de conector en la nube en privado.</span><span class="sxs-lookup"><span data-stu-id="73c62-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="73c62-129">Utilice este parámetro con precaución: asegúrese de tener en cuenta qué versión del conector de la nube de descarga.</span><span class="sxs-lookup"><span data-stu-id="73c62-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="73c62-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="73c62-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="73c62-131">Opcional</span><span class="sxs-lookup"><span data-stu-id="73c62-131">Optional</span></span>  <br/> |<span data-ttu-id="73c62-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="73c62-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="73c62-133">Omitir el paso para descargar e instalar MSI desde el sitio de descarga, descargue sólo los bits de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="73c62-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="73c62-134">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="73c62-134">Input Types</span></span>
<span data-ttu-id="73c62-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73c62-135"></span></span>

<span data-ttu-id="73c62-136">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="73c62-136">None.</span></span> <span data-ttu-id="73c62-137">El cmdlet Start-CcDownload no acepta entradas transferidas.</span><span class="sxs-lookup"><span data-stu-id="73c62-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="73c62-138">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="73c62-138">Return Types</span></span>
<span data-ttu-id="73c62-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73c62-139"></span></span>

<span data-ttu-id="73c62-140">Ninguno </span><span class="sxs-lookup"><span data-stu-id="73c62-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="73c62-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73c62-141">See also</span></span>
<span data-ttu-id="73c62-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73c62-142"></span></span>

<span data-ttu-id="73c62-143">Ninguno</span><span class="sxs-lookup"><span data-stu-id="73c62-143">None</span></span>
  

