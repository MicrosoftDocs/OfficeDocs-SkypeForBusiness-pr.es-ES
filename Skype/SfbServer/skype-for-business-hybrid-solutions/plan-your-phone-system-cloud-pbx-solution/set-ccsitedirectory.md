---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: El cmdlet Set-CcSiteDirectory establece el directorio en el que se almacenarán los archivos de configuración del nivel de sitio para Skype Empresarial Cloud Connector Edition. La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824194"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="4460e-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="4460e-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="4460e-105">El cmdlet Set-CcSiteDirectory establece el directorio en el que se almacenarán los archivos de configuración del nivel de sitio para Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="4460e-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="4460e-106">La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4460e-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="4460e-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4460e-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="4460e-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4460e-108">Examples</span></span>
<span data-ttu-id="4460e-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4460e-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="4460e-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="4460e-110">Example 1</span></span>

<span data-ttu-id="4460e-111">En el ejemplo siguiente se establece el directorio raíz \\del sitio en SiteShare\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="4460e-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="4460e-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="4460e-112">Detailed Description</span></span>
<span data-ttu-id="4460e-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4460e-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="4460e-114">Para proporcionar afinidad de puerta de enlace y alta disponibilidad, los dispositivos del conector de nube se pueden combinar en sitios.</span><span class="sxs-lookup"><span data-stu-id="4460e-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="4460e-115">Los usuarios se asignan a sitios en lugar de a los dispositivos de conexión de la nube.</span><span class="sxs-lookup"><span data-stu-id="4460e-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="4460e-116">Cada sitio tiene una carpeta compartida en la que se almacenan los archivos de instalación del VHD básico y del conector de nube.</span><span class="sxs-lookup"><span data-stu-id="4460e-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="4460e-117">Los dispositivos usan esta carpeta durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="4460e-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="4460e-118">Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="4460e-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="4460e-119">La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="4460e-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="4460e-120">La ruta se puede ver mediante el cmdlet Get-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="4460e-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="4460e-121">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4460e-121">Parameters</span></span>
<span data-ttu-id="4460e-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4460e-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="4460e-123">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="4460e-123">**Parameter**</span></span>|<span data-ttu-id="4460e-124">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="4460e-124">**Required**</span></span>|<span data-ttu-id="4460e-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4460e-125">**Type**</span></span>|<span data-ttu-id="4460e-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4460e-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4460e-127"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="4460e-127">Path</span></span> <br/> | <span data-ttu-id="4460e-128">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="4460e-128">Required</span></span> <br/> | <span data-ttu-id="4460e-129">System.String</span><span class="sxs-lookup"><span data-stu-id="4460e-129">System.String</span></span> <br/> |<span data-ttu-id="4460e-130">Proporciona la ruta de acceso a la carpeta donde se almacenarán los archivos del sitio del conector de nube.</span><span class="sxs-lookup"><span data-stu-id="4460e-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4460e-131">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="4460e-131">Input Types</span></span>
<span data-ttu-id="4460e-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4460e-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="4460e-133">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4460e-133">None.</span></span> <span data-ttu-id="4460e-134">El cmdlet Set-CcSiteDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="4460e-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4460e-135">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="4460e-135">Return Types</span></span>
<span data-ttu-id="4460e-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4460e-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="4460e-137">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4460e-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4460e-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4460e-138">See also</span></span>
<span data-ttu-id="4460e-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4460e-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="4460e-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="4460e-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

