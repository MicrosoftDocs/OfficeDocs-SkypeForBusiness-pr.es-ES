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
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 'El cmdlet Get-CcSiteLogDirectory muestra el directorio actual en el que se almacenan los registros a nivel de sitio de Skype Empresarial Cloud Connector Edition. '
ms.openlocfilehash: bc47c2ea2d81e70538305daa98f97a35cf3d9e0a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287289"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="e19b5-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="e19b5-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="e19b5-104">El cmdlet Get-CcSiteLogDirectory muestra el directorio actual en el que se almacenan los registros a nivel de sitio de Skype Empresarial Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="e19b5-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="e19b5-105">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="e19b5-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="e19b5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e19b5-106">Parameters</span></span>

<span data-ttu-id="e19b5-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e19b5-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e19b5-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e19b5-108">Examples</span></span>
<span data-ttu-id="e19b5-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e19b5-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="e19b5-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e19b5-110">Example 1</span></span>

<span data-ttu-id="e19b5-111">En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los archivos de registro del sitio del conector de la nube:</span><span class="sxs-lookup"><span data-stu-id="e19b5-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="e19b5-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="e19b5-112">Detailed Description</span></span>
<span data-ttu-id="e19b5-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e19b5-113"></span></span>

<span data-ttu-id="e19b5-114">La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="e19b5-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="e19b5-115">Para cambiar la carpeta, ejecute el cmdlet Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="e19b5-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="e19b5-116">No hay un cmdlet aparte que cambie solo la ubicación de la carpeta de registros sin cambiar el directorio de sitios.</span><span class="sxs-lookup"><span data-stu-id="e19b5-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e19b5-117">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="e19b5-117">Input Types</span></span>
<span data-ttu-id="e19b5-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e19b5-118"></span></span>

<span data-ttu-id="e19b5-p102">Ninguno. El cmdlet Get-CcSiteLogDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="e19b5-p102">None. The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e19b5-121">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="e19b5-121">Return Types</span></span>
<span data-ttu-id="e19b5-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e19b5-122"></span></span>

<span data-ttu-id="e19b5-123">El comando devuelve una ruta de archivo.</span><span class="sxs-lookup"><span data-stu-id="e19b5-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e19b5-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e19b5-124">See also</span></span>
<span data-ttu-id="e19b5-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e19b5-125"></span></span>

[<span data-ttu-id="e19b5-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="e19b5-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

