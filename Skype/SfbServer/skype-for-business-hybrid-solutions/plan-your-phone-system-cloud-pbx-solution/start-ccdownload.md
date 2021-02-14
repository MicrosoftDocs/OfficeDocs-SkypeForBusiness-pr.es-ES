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
description: El cmdlet Start-CcDownload descarga los bits de Skype Empresarial Cloud Connector Edition y el archivo msi de forma sincrónica.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824184"
---
# <a name="start-ccdownload"></a><span data-ttu-id="a691a-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="a691a-103">Start-CcDownload</span></span>
 
<span data-ttu-id="a691a-104">El cmdlet Start-CcDownload descarga los bits de Skype Empresarial Cloud Connector Edition y el archivo msi de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="a691a-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="a691a-105">Con Cloud Connector versión 2.0 y versiones posteriores, también puede especificar el parámetro DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="a691a-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="a691a-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a691a-106">Examples</span></span>
<span data-ttu-id="a691a-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a691a-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="a691a-108">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a691a-108">Example 1</span></span>

<span data-ttu-id="a691a-109">En el siguiente ejemplo se descargan los bits de Cloud Connector y el archivo msi de forma sincrónica desde el sitio de descarga pública de Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="a691a-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="a691a-110">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="a691a-110">Example 2</span></span>

<span data-ttu-id="a691a-111">En el siguiente ejemplo se descargan los bits de Cloud Connector y el archivo msi de forma sincrónica desde un sitio de descarga privado:</span><span class="sxs-lookup"><span data-stu-id="a691a-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="a691a-112">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="a691a-112">Example 3</span></span>

<span data-ttu-id="a691a-113">El tercer ejemplo descarga los bits de Cloud Connector y el archivo msi de forma sincrónica desde un sitio de descarga privado.</span><span class="sxs-lookup"><span data-stu-id="a691a-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="a691a-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="a691a-114">Detailed Description</span></span>
<span data-ttu-id="a691a-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a691a-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="a691a-116">Si hay una nueva versión disponible en el sitio de descarga, Start-CcDownload descargará e instalará el archivo msi desde el sitio de descarga y, a continuación, descargará los bits de Cloud Connector de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="a691a-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="a691a-117">Si no hay ninguna nueva versión del archivo msi, Start-CcDownload descargará solo los bits de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a691a-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="a691a-118">Si los bits de Cloud Connector ya están descargados, Start-CcDownload no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="a691a-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a691a-119">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a691a-119">Parameters</span></span>
<span data-ttu-id="a691a-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a691a-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="a691a-121">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="a691a-121">**Parameter**</span></span>|<span data-ttu-id="a691a-122">**Required**</span><span class="sxs-lookup"><span data-stu-id="a691a-122">**Required**</span></span>|<span data-ttu-id="a691a-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a691a-123">**Type**</span></span>|<span data-ttu-id="a691a-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a691a-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a691a-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="a691a-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="a691a-126">Opcional</span><span class="sxs-lookup"><span data-stu-id="a691a-126">Optional</span></span> <br/> |<span data-ttu-id="a691a-127">System.String</span><span class="sxs-lookup"><span data-stu-id="a691a-127">System.String</span></span>  <br/> | <span data-ttu-id="a691a-128">La dirección URL completa de una versión específica de Cloud Connector en el sitio de descarga privado.</span><span class="sxs-lookup"><span data-stu-id="a691a-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="a691a-129">Use este parámetro con precaución: asegúrese de saber qué versión de Cloud Connector está descargando.</span><span class="sxs-lookup"><span data-stu-id="a691a-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="a691a-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="a691a-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="a691a-131">Opcional</span><span class="sxs-lookup"><span data-stu-id="a691a-131">Optional</span></span>  <br/> |<span data-ttu-id="a691a-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a691a-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a691a-133">Omita el paso para descargar e instalar MSI desde el sitio de descarga y descargue solo los bits de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a691a-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a691a-134">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="a691a-134">Input Types</span></span>
<span data-ttu-id="a691a-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a691a-135"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="a691a-136">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a691a-136">None.</span></span> <span data-ttu-id="a691a-137">El Start-CcDownload no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="a691a-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a691a-138">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="a691a-138">Return Types</span></span>
<span data-ttu-id="a691a-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a691a-139"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a691a-140">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a691a-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a691a-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="a691a-141">See also</span></span>
<span data-ttu-id="a691a-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a691a-142"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a691a-143">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a691a-143">None</span></span>
  

