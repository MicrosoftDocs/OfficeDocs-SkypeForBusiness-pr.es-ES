---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: El cmdlet Get-CcSiteDirectory muestra el directorio actual donde se almacenan los archivos de configuración de nivel de sitio. La carpeta contiene el VHD base y los archivos de instalación de Skype Empresarial Cloud Connector Edition. Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de Cloud Connector.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799870"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="7aadd-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="7aadd-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="7aadd-106">El cmdlet Get-CcSiteDirectory muestra el directorio actual donde se almacenan los archivos de configuración de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="7aadd-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="7aadd-107">La carpeta contiene el VHD base y los archivos de instalación de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="7aadd-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="7aadd-108">Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7aadd-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="7aadd-109">Este cmdlet se aplica a Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="7aadd-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="7aadd-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7aadd-110">Parameters</span></span>

<span data-ttu-id="7aadd-111">Ninguno</span><span class="sxs-lookup"><span data-stu-id="7aadd-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="7aadd-112">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7aadd-112">Examples</span></span>
<span data-ttu-id="7aadd-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7aadd-113"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="7aadd-114">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="7aadd-114">Example 1</span></span>

<span data-ttu-id="7aadd-115">En el siguiente ejemplo se muestra la carpeta actual donde se almacenan los archivos de configuración y de máquinas virtuales de los componentes de Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="7aadd-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="7aadd-116">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="7aadd-116">Detailed Description</span></span>
<span data-ttu-id="7aadd-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7aadd-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="7aadd-118">Para proporcionar afinidad de puerta de enlace y alta disponibilidad, los dispositivos de Cloud Connector se pueden combinar en sitios.</span><span class="sxs-lookup"><span data-stu-id="7aadd-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="7aadd-119">Los usuarios se asignan a sitios en lugar de dispositivos de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7aadd-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="7aadd-120">Cada sitio tiene una carpeta compartida donde se almacenan los archivos base de instalación de VHD y Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7aadd-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="7aadd-121">Los dispositivos usan esta carpeta durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="7aadd-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="7aadd-122">La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="7aadd-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="7aadd-123">Puede cambiar la ruta de acceso mediante el cmdlet Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="7aadd-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="7aadd-124">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="7aadd-124">Input Types</span></span>
<span data-ttu-id="7aadd-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7aadd-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="7aadd-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7aadd-126">None.</span></span> <span data-ttu-id="7aadd-127">El Get-CcSiteDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="7aadd-127">The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7aadd-128">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="7aadd-128">Return Types</span></span>
<span data-ttu-id="7aadd-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7aadd-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="7aadd-130">Este comando devuelve una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="7aadd-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7aadd-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="7aadd-131">See also</span></span>
<span data-ttu-id="7aadd-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7aadd-132"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="7aadd-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="7aadd-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

