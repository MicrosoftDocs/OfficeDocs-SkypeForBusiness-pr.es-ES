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
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: El cmdlet Start-CcDownload descarga el archivo MSI y los bits de Skype empresarial Cloud Connector Edition de forma sincrónica.
ms.openlocfilehash: 5c493862151a308208bf83e142421f3257e476e0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003190"
---
# <a name="start-ccdownload"></a><span data-ttu-id="4a1db-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="4a1db-103">Start-CcDownload</span></span>
 
<span data-ttu-id="4a1db-104">El cmdlet Start-CcDownload descarga el archivo MSI y los bits de Skype empresarial Cloud Connector Edition de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="4a1db-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="4a1db-105">Con la versión 2,0 y posteriores del conector para la nube, también puede especificar el parámetro DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="4a1db-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="4a1db-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4a1db-106">Examples</span></span>
<span data-ttu-id="4a1db-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4a1db-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="4a1db-108">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="4a1db-108">Example 1</span></span>

<span data-ttu-id="4a1db-109">En el siguiente ejemplo se descarga el archivo MSI y los bits de conector de la nube de forma sincrónica desde el sitio de descarga pública de conector en la nube:</span><span class="sxs-lookup"><span data-stu-id="4a1db-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="4a1db-110">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="4a1db-110">Example 2</span></span>

<span data-ttu-id="4a1db-111">El siguiente ejemplo descarga los bits de conector de la nube y el archivo MSI de forma sincrónica desde un sitio de descarga privada:</span><span class="sxs-lookup"><span data-stu-id="4a1db-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="4a1db-112">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="4a1db-112">Example 3</span></span>

<span data-ttu-id="4a1db-113">El tercer ejemplo descarga los bits de conector de la nube y el archivo MSI de forma sincrónica desde un sitio de descarga privada.</span><span class="sxs-lookup"><span data-stu-id="4a1db-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="4a1db-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="4a1db-114">Detailed Description</span></span>
<span data-ttu-id="4a1db-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4a1db-115"></span></span>

<span data-ttu-id="4a1db-116">Si hay una nueva versión disponible en el sitio de descarga, Start-CcDownload se descargará e instalará el archivo MSI desde el sitio de descarga y, a continuación, descargará los bits de conector de nube de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="4a1db-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="4a1db-117">Si no hay ninguna versión nueva del archivo MSI, Start-CcDownload se descargará solo los bits de conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="4a1db-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="4a1db-118">Si los bits de conector de la nube ya se han descargado, Start-CcDownload no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="4a1db-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="4a1db-119">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4a1db-119">Parameters</span></span>
<span data-ttu-id="4a1db-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4a1db-120"></span></span>

|<span data-ttu-id="4a1db-121">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="4a1db-121">**Parameter**</span></span>|<span data-ttu-id="4a1db-122">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="4a1db-122">**Required**</span></span>|<span data-ttu-id="4a1db-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4a1db-123">**Type**</span></span>|<span data-ttu-id="4a1db-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4a1db-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4a1db-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="4a1db-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="4a1db-126">Opcional </span><span class="sxs-lookup"><span data-stu-id="4a1db-126">Optional</span></span> <br/> |<span data-ttu-id="4a1db-127">System.String</span><span class="sxs-lookup"><span data-stu-id="4a1db-127">System.String</span></span>  <br/> | <span data-ttu-id="4a1db-128">La dirección URL completa de una versión específica del conector de nube en el sitio de descarga privada.</span><span class="sxs-lookup"><span data-stu-id="4a1db-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="4a1db-129">Use este parámetro con precaución: Asegúrese de estar al tanto de qué versión del conector de nube está descargando.</span><span class="sxs-lookup"><span data-stu-id="4a1db-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="4a1db-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="4a1db-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="4a1db-131">Opcional</span><span class="sxs-lookup"><span data-stu-id="4a1db-131">Optional</span></span>  <br/> |<span data-ttu-id="4a1db-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="4a1db-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="4a1db-133">Omita el paso para descargar e instalar MSI desde el sitio de descarga, descargar solo los bits de conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="4a1db-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4a1db-134">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="4a1db-134">Input Types</span></span>
<span data-ttu-id="4a1db-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4a1db-135"></span></span>

<span data-ttu-id="4a1db-136">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4a1db-136">None.</span></span> <span data-ttu-id="4a1db-137">El cmdlet Start-CcDownload no acepta la entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="4a1db-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4a1db-138">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="4a1db-138">Return Types</span></span>
<span data-ttu-id="4a1db-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4a1db-139"></span></span>

<span data-ttu-id="4a1db-140">Ninguno </span><span class="sxs-lookup"><span data-stu-id="4a1db-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4a1db-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a1db-141">See also</span></span>
<span data-ttu-id="4a1db-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4a1db-142"></span></span>

<span data-ttu-id="4a1db-143">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4a1db-143">None</span></span>
  

