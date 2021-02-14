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
description: El cmdlet Set-CcSiteDirectory establece el directorio donde se almacenarán los archivos de configuración de nivel de sitio para Skype Empresarial Cloud Connector Edition. La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824194"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="d716f-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="d716f-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="d716f-105">El cmdlet Set-CcSiteDirectory establece el directorio donde se almacenarán los archivos de configuración de nivel de sitio para Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="d716f-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="d716f-106">La carpeta contendrá el VHD base y los archivos de configuración de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d716f-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="d716f-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="d716f-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="d716f-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d716f-108">Examples</span></span>
<span data-ttu-id="d716f-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d716f-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d716f-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="d716f-110">Example 1</span></span>

<span data-ttu-id="d716f-111">En el siguiente ejemplo se establece el directorio raíz del sitio \\ en SiteShare\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="d716f-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="d716f-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="d716f-112">Detailed Description</span></span>
<span data-ttu-id="d716f-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d716f-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="d716f-114">Para proporcionar afinidad de puerta de enlace y alta disponibilidad, los dispositivos de Cloud Connector se pueden combinar en sitios.</span><span class="sxs-lookup"><span data-stu-id="d716f-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="d716f-115">Los usuarios se asignan a sitios en lugar de dispositivos de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d716f-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="d716f-116">Cada sitio tiene una carpeta compartida donde se almacenan los archivos base de instalación de VHD y Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d716f-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="d716f-117">Los dispositivos usan esta carpeta durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="d716f-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="d716f-118">Esta carpeta debe compartirse con todos los demás dispositivos de un sitio de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d716f-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="d716f-119">La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="d716f-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="d716f-120">La ruta de acceso se puede ver con el cmdlet Get-CcSiteDirectory búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d716f-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d716f-121">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d716f-121">Parameters</span></span>
<span data-ttu-id="d716f-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d716f-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="d716f-123">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="d716f-123">**Parameter**</span></span>|<span data-ttu-id="d716f-124">**Required**</span><span class="sxs-lookup"><span data-stu-id="d716f-124">**Required**</span></span>|<span data-ttu-id="d716f-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d716f-125">**Type**</span></span>|<span data-ttu-id="d716f-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d716f-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d716f-127">Path</span><span class="sxs-lookup"><span data-stu-id="d716f-127">Path</span></span> <br/> | <span data-ttu-id="d716f-128">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d716f-128">Required</span></span> <br/> | <span data-ttu-id="d716f-129">System.String</span><span class="sxs-lookup"><span data-stu-id="d716f-129">System.String</span></span> <br/> |<span data-ttu-id="d716f-130">Proporciona la ruta de acceso a la carpeta donde se almacenarán los archivos del sitio de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d716f-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d716f-131">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="d716f-131">Input Types</span></span>
<span data-ttu-id="d716f-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d716f-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="d716f-133">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d716f-133">None.</span></span> <span data-ttu-id="d716f-134">El Set-CcSiteDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="d716f-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d716f-135">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="d716f-135">Return Types</span></span>
<span data-ttu-id="d716f-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d716f-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d716f-137">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d716f-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d716f-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d716f-138">See also</span></span>
<span data-ttu-id="d716f-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d716f-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="d716f-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="d716f-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

