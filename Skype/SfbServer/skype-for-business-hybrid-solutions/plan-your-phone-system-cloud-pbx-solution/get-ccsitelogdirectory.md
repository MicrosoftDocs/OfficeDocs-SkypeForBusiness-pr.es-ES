---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: El cmdlet Get-CcSiteLogDirectory muestra el directorio actual donde se almacenan los registros de nivel de sitio para Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: cace3ce3757294adbb3c55db24c619925f55ce5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799890"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="47607-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="47607-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="47607-104">El cmdlet Get-CcSiteLogDirectory muestra el directorio actual donde se almacenan los registros de nivel de sitio para Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="47607-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="47607-105">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="47607-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="47607-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47607-106">Parameters</span></span>

<span data-ttu-id="47607-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="47607-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="47607-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="47607-108">Examples</span></span>
<span data-ttu-id="47607-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47607-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="47607-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="47607-110">Example 1</span></span>

<span data-ttu-id="47607-111">En el siguiente ejemplo se muestra la carpeta actual donde se almacenan los archivos de registro del sitio de Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="47607-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="47607-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="47607-112">Detailed Description</span></span>
<span data-ttu-id="47607-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="47607-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="47607-114">La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="47607-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="47607-115">Puede cambiar la carpeta ejecutando el cmdlet Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="47607-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="47607-116">No hay ningún cmdlet independiente que cambie solo la ubicación de la carpeta de registro sin cambiar el directorio del sitio.</span><span class="sxs-lookup"><span data-stu-id="47607-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="47607-117">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="47607-117">Input Types</span></span>
<span data-ttu-id="47607-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="47607-118"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="47607-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="47607-119">None.</span></span> <span data-ttu-id="47607-120">El Get-CcSiteLogDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="47607-120">The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="47607-121">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="47607-121">Return Types</span></span>
<span data-ttu-id="47607-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="47607-122"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="47607-123">El comando devuelve una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="47607-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="47607-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="47607-124">See also</span></span>
<span data-ttu-id="47607-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="47607-125"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="47607-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="47607-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

