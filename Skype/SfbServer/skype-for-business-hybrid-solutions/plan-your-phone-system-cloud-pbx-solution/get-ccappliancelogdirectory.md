---
title: Get-CcApplianceLogDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual en el que se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 9b7d4853deb9ab16c7ae61279a20a30778774072
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="4005d-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="4005d-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="4005d-104">El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual en el que se almacenan los registros de un dispositivo de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="4005d-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="4005d-105">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4005d-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="4005d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4005d-106">Parameters</span></span>

<span data-ttu-id="4005d-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4005d-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="4005d-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4005d-108">Examples</span></span>
<span data-ttu-id="4005d-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4005d-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="4005d-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="4005d-110">Example 1</span></span>

<span data-ttu-id="4005d-111">En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los registros para el dispositivo actual del conector de la nube:</span><span class="sxs-lookup"><span data-stu-id="4005d-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="4005d-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="4005d-112">Detailed Description</span></span>
<span data-ttu-id="4005d-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4005d-113"></span></span>

<span data-ttu-id="4005d-114">El cmdlet Get-CcApplianceLogDirectory muestra el directorio actual donde se almacenan los registros para un dispositivo conector de nube.</span><span class="sxs-lookup"><span data-stu-id="4005d-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="4005d-115">La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="4005d-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="4005d-116">Puede cambiar el directorio con el cmdlet Set-CcApplianceDirectory. </span><span class="sxs-lookup"><span data-stu-id="4005d-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="4005d-117">Nota: no hay ningún cmdlet que cambie solo la ubicación de la carpeta de registros sin cambiar el directorio de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4005d-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="4005d-118">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="4005d-118">Input Types</span></span>
<span data-ttu-id="4005d-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4005d-119"></span></span>

<span data-ttu-id="4005d-p102">Ninguno. El cmdlet Get-CcApplianceLogDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="4005d-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4005d-122">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="4005d-122">Return Types</span></span>
<span data-ttu-id="4005d-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4005d-123"></span></span>

<span data-ttu-id="4005d-124">Este comando devuelve una ruta de archivo.</span><span class="sxs-lookup"><span data-stu-id="4005d-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4005d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4005d-125">See also</span></span>
<span data-ttu-id="4005d-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4005d-126"></span></span>

[<span data-ttu-id="4005d-127">Conjunto de CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="4005d-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

