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
description: El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual en el que se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800830"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="6392e-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="6392e-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="6392e-104">El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual en el que se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="6392e-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="6392e-105">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="6392e-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="6392e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6392e-106">Parameters</span></span>

<span data-ttu-id="6392e-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="6392e-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="6392e-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6392e-108">Examples</span></span>
<span data-ttu-id="6392e-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6392e-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="6392e-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="6392e-110">Example 1</span></span>

<span data-ttu-id="6392e-111">En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los registros para el dispositivo actual del conector en la nube:</span><span class="sxs-lookup"><span data-stu-id="6392e-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="6392e-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="6392e-112">Detailed Description</span></span>
<span data-ttu-id="6392e-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6392e-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="6392e-114">El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual en el que se almacenan los registros para un dispositivo de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="6392e-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="6392e-115">La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="6392e-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="6392e-116">Puede cambiar el directorio con el cmdlet Set-CcApplianceDirectory. </span><span class="sxs-lookup"><span data-stu-id="6392e-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="6392e-117">Nota: no hay ningún cmdlet que cambie solo la ubicación de la carpeta de registros sin cambiar el directorio de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6392e-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="6392e-118">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="6392e-118">Input Types</span></span>
<span data-ttu-id="6392e-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6392e-119"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="6392e-p102">Ninguno. El cmdlet Get-CcApplianceLogDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="6392e-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6392e-122">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="6392e-122">Return Types</span></span>
<span data-ttu-id="6392e-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6392e-123"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="6392e-124">Este comando devuelve una ruta de archivo.</span><span class="sxs-lookup"><span data-stu-id="6392e-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6392e-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6392e-125">See also</span></span>
<span data-ttu-id="6392e-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6392e-126"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="6392e-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="6392e-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

