---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual en el que se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 675e89f49c7c1384edc7cfa5944c8aee3f236c79
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287373"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="a8534-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="a8534-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="a8534-104">El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual en el que se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="a8534-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="a8534-105">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="a8534-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="a8534-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8534-106">Parameters</span></span>

<span data-ttu-id="a8534-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a8534-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="a8534-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a8534-108">Examples</span></span>
<span data-ttu-id="a8534-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a8534-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="a8534-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a8534-110">Example 1</span></span>

<span data-ttu-id="a8534-111">En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los registros para el dispositivo actual del conector en la nube:</span><span class="sxs-lookup"><span data-stu-id="a8534-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="a8534-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="a8534-112">Detailed Description</span></span>
<span data-ttu-id="a8534-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a8534-113"></span></span>

<span data-ttu-id="a8534-114">El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual en el que se almacenan los registros para un dispositivo de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="a8534-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="a8534-115">La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="a8534-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="a8534-116">Puede cambiar el directorio con el cmdlet Set-CcApplianceDirectory. </span><span class="sxs-lookup"><span data-stu-id="a8534-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="a8534-117">Nota: no hay ningún cmdlet que cambie solo la ubicación de la carpeta de registros sin cambiar el directorio de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a8534-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="a8534-118">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="a8534-118">Input Types</span></span>
<span data-ttu-id="a8534-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a8534-119"></span></span>

<span data-ttu-id="a8534-p102">Ninguno. El cmdlet Get-CcApplianceLogDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="a8534-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a8534-122">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="a8534-122">Return Types</span></span>
<span data-ttu-id="a8534-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a8534-123"></span></span>

<span data-ttu-id="a8534-124">Este comando devuelve una ruta de archivo.</span><span class="sxs-lookup"><span data-stu-id="a8534-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a8534-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8534-125">See also</span></span>
<span data-ttu-id="a8534-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a8534-126"></span></span>

[<span data-ttu-id="a8534-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="a8534-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

