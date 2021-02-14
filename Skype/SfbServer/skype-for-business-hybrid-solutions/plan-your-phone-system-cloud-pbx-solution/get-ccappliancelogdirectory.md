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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual donde se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800830"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="ee2bb-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="ee2bb-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="ee2bb-104">El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual donde se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="ee2bb-105">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="ee2bb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee2bb-106">Parameters</span></span>

<span data-ttu-id="ee2bb-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ee2bb-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="ee2bb-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ee2bb-108">Examples</span></span>
<span data-ttu-id="ee2bb-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ee2bb-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ee2bb-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="ee2bb-110">Example 1</span></span>

<span data-ttu-id="ee2bb-111">En el siguiente ejemplo se muestra la carpeta actual donde se almacenan los registros del dispositivo actual de Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="ee2bb-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="ee2bb-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="ee2bb-112">Detailed Description</span></span>
<span data-ttu-id="ee2bb-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ee2bb-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="ee2bb-114">El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual donde se almacenan los registros de un dispositivo de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="ee2bb-115">La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="ee2bb-116">Puede cambiar el directorio con el cmdlet Set-CcApplianceDirectory datos.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="ee2bb-117">Nota: No hay ningún cmdlet que cambie solo la ubicación de la carpeta de registro sin cambiar el directorio del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="ee2bb-118">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="ee2bb-118">Input Types</span></span>
<span data-ttu-id="ee2bb-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ee2bb-119"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ee2bb-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-120">None.</span></span> <span data-ttu-id="ee2bb-121">El Get-CcApplianceLogDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-121">The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ee2bb-122">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="ee2bb-122">Return Types</span></span>
<span data-ttu-id="ee2bb-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ee2bb-123"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ee2bb-124">Este comando devuelve una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ee2bb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee2bb-125">See also</span></span>
<span data-ttu-id="ee2bb-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ee2bb-126"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="ee2bb-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="ee2bb-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

