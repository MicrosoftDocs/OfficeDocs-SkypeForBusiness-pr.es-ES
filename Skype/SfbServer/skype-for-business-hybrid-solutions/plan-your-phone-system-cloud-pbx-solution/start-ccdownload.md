---
title: Inicio CcDownload
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: El cmdlet Start-CcDownload descarga el Skype para bits de conector de nube Business Edition y el archivo msi sincrónicamente.
ms.openlocfilehash: aec8d5c1848e7e55d6ed4b7e4d3633942f74ab55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="start-ccdownload"></a><span data-ttu-id="1c68b-103">Inicio CcDownload</span><span class="sxs-lookup"><span data-stu-id="1c68b-103">Start-CcDownload</span></span>
 
<span data-ttu-id="1c68b-104">El cmdlet Start-CcDownload descarga el Skype para bits de conector de nube Business Edition y el archivo msi sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="1c68b-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="1c68b-105">Con conector de nube 2.0 y versiones posteriores, también puede especificar el parámetro DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="1c68b-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="1c68b-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1c68b-106">Examples</span></span>
<span data-ttu-id="1c68b-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1c68b-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="1c68b-108">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="1c68b-108">Example 1</span></span>

<span data-ttu-id="1c68b-109">El ejemplo siguiente descarga los bits de la nube de conector y el archivo msi sincrónicamente desde el sitio de descarga pública de conector de nube:</span><span class="sxs-lookup"><span data-stu-id="1c68b-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="1c68b-110">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="1c68b-110">Example 2</span></span>

<span data-ttu-id="1c68b-111">En el ejemplo siguiente descarga los bits de la nube de conector y el archivo msi sincrónicamente desde un sitio de descarga privada:</span><span class="sxs-lookup"><span data-stu-id="1c68b-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="1c68b-112">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="1c68b-112">Example 3</span></span>

<span data-ttu-id="1c68b-113">El tercer ejemplo descarga los bits de la nube de conector y el archivo msi sincrónicamente desde un sitio de descarga privada.</span><span class="sxs-lookup"><span data-stu-id="1c68b-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="1c68b-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="1c68b-114">Detailed Description</span></span>
<span data-ttu-id="1c68b-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1c68b-115"></span></span>

<span data-ttu-id="1c68b-116">Si hay una nueva versión disponible en el sitio de descarga, inicio CcDownload descargar e instalar el archivo msi desde el sitio de descarga y, a continuación, descargar los bits de nube conector sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="1c68b-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="1c68b-117">Si no hay ninguna versión nueva del archivo msi, inicio CcDownload descargará sólo los bits del conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="1c68b-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="1c68b-118">Si ya se descargan los bits del conector de la nube, CcDownload de inicio no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="1c68b-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1c68b-119">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c68b-119">Parameters</span></span>
<span data-ttu-id="1c68b-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1c68b-120"></span></span>

|<span data-ttu-id="1c68b-121">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="1c68b-121">**Parameter**</span></span>|<span data-ttu-id="1c68b-122">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="1c68b-122">**Required**</span></span>|<span data-ttu-id="1c68b-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1c68b-123">**Type**</span></span>|<span data-ttu-id="1c68b-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1c68b-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1c68b-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="1c68b-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="1c68b-126">Opcional </span><span class="sxs-lookup"><span data-stu-id="1c68b-126">Optional</span></span> <br/> |<span data-ttu-id="1c68b-127">System.String</span><span class="sxs-lookup"><span data-stu-id="1c68b-127">System.String</span></span>  <br/> | <span data-ttu-id="1c68b-128">Sitio de descarga de la dirección URL completa de una versión específica de conector de nube en privado.</span><span class="sxs-lookup"><span data-stu-id="1c68b-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="1c68b-129">Utilice este parámetro con precaución: asegúrese de que es consciente de qué versión de conector de nube está descargando.</span><span class="sxs-lookup"><span data-stu-id="1c68b-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="1c68b-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="1c68b-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="1c68b-131">Opcional</span><span class="sxs-lookup"><span data-stu-id="1c68b-131">Optional</span></span>  <br/> |<span data-ttu-id="1c68b-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1c68b-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="1c68b-133">Omitir el paso para descargar e instalar el MSI desde el sitio de descarga, descargue sólo los bits del conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="1c68b-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1c68b-134">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="1c68b-134">Input Types</span></span>
<span data-ttu-id="1c68b-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c68b-135"></span></span>

<span data-ttu-id="1c68b-136">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1c68b-136">None.</span></span> <span data-ttu-id="1c68b-137">El cmdlet Start-CcDownload no acepta entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="1c68b-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1c68b-138">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="1c68b-138">Return Types</span></span>
<span data-ttu-id="1c68b-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c68b-139"></span></span>

<span data-ttu-id="1c68b-140">Ninguno</span><span class="sxs-lookup"><span data-stu-id="1c68b-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c68b-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c68b-141">See also</span></span>
<span data-ttu-id="1c68b-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c68b-142"></span></span>

<span data-ttu-id="1c68b-143">Ninguno</span><span class="sxs-lookup"><span data-stu-id="1c68b-143">None</span></span>
  

