---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: El cmdlet Set-CcSiteDirectory establece el directorio en el que se almacenarán los archivos de configuración del nivel de sitio para Skype Empresarial Cloud Connector Edition. La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.
ms.openlocfilehash: 1c03d0f91b3a724df6ce61d216138bb281fb0b87
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885585"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="93f13-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="93f13-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="93f13-105">El cmdlet Set-CcSiteDirectory establece el directorio en el que se almacenarán los archivos de configuración del nivel de sitio para Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="93f13-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="93f13-106">La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="93f13-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="93f13-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="93f13-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="93f13-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="93f13-108">Examples</span></span>
<span data-ttu-id="93f13-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="93f13-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="93f13-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="93f13-110">Example 1</span></span>

<span data-ttu-id="93f13-111">En el ejemplo siguiente se establece el directorio raíz del sitio en \\SiteShare\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="93f13-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="93f13-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="93f13-112">Detailed Description</span></span>
<span data-ttu-id="93f13-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="93f13-113"></span></span>

<span data-ttu-id="93f13-114">Para proporcionar alta disponibilidad y la afinidad de puerta de enlace, se pueden combinar dispositivos de conector en la nube en sitios.</span><span class="sxs-lookup"><span data-stu-id="93f13-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="93f13-115">Los usuarios se asignan a sitios en lugar de dispositivos de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="93f13-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="93f13-116">Cada sitio tiene una carpeta compartida donde se almacenan los archivos de instalación bases VHD y el conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="93f13-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="93f13-117">Dispositivos utilizan esta carpeta durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="93f13-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="93f13-118">Esta carpeta se debe compartir con todos los otros equipos en un sitio de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="93f13-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="93f13-119">La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="93f13-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="93f13-120">La ruta se puede ver mediante el cmdlet Get-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="93f13-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="93f13-121">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93f13-121">Parameters</span></span>
<span data-ttu-id="93f13-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="93f13-122"></span></span>

|<span data-ttu-id="93f13-123">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="93f13-123">**Parameter**</span></span>|<span data-ttu-id="93f13-124">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="93f13-124">**Required**</span></span>|<span data-ttu-id="93f13-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="93f13-125">**Type**</span></span>|<span data-ttu-id="93f13-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="93f13-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="93f13-127"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="93f13-127">Path</span></span> <br/> | <span data-ttu-id="93f13-128">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="93f13-128">Required</span></span> <br/> | <span data-ttu-id="93f13-129">System.String</span><span class="sxs-lookup"><span data-stu-id="93f13-129">System.String</span></span> <br/> |<span data-ttu-id="93f13-130">Proporciona la ruta de acceso a la carpeta donde se almacenarán los archivos de sitio de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="93f13-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="93f13-131">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="93f13-131">Input Types</span></span>
<span data-ttu-id="93f13-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="93f13-132"></span></span>

<span data-ttu-id="93f13-133">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="93f13-133">None.</span></span> <span data-ttu-id="93f13-134">El cmdlet Set-CcSiteDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="93f13-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="93f13-135">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="93f13-135">Return Types</span></span>
<span data-ttu-id="93f13-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="93f13-136"></span></span>

<span data-ttu-id="93f13-137">Ninguno</span><span class="sxs-lookup"><span data-stu-id="93f13-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="93f13-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93f13-138">See also</span></span>
<span data-ttu-id="93f13-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="93f13-139"></span></span>

[<span data-ttu-id="93f13-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="93f13-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

