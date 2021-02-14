---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: El Get-CcApplianceDirectory recupera el directorio de trabajo en el servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800850"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="988a9-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="988a9-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="988a9-105">El Get-CcApplianceDirectory recupera el directorio de trabajo en el servidor host de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="988a9-105">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="988a9-106">Todos los archivos de implementación se almacenan en este directorio.</span><span class="sxs-lookup"><span data-stu-id="988a9-106">All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="988a9-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="988a9-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="988a9-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="988a9-108">Parameters</span></span>

<span data-ttu-id="988a9-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="988a9-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="988a9-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="988a9-110">Examples</span></span>
<span data-ttu-id="988a9-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="988a9-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="988a9-112">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="988a9-112">Example 1</span></span>

<span data-ttu-id="988a9-113">En el siguiente ejemplo se muestra la carpeta actual donde se almacenan los archivos de configuración y de máquina virtual de los componentes de Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="988a9-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="988a9-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="988a9-114">Detailed Description</span></span>
<span data-ttu-id="988a9-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="988a9-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="988a9-116">El cmdlet Get-CcApplianceDirectory muestra dónde se almacenan todos los archivos de configuración y máquina virtual, registros y certificados externos para el dispositivo de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="988a9-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="988a9-117">Cada dispositivo de Cloud Connector tiene cuatro componentes: servidor de mediación, almacén de administración central, servidor perimetral y controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="988a9-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="988a9-118">La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="988a9-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="988a9-119">Puede cambiar esta carpeta mediante el cmdlet Set-CCApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="988a9-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="988a9-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="988a9-120">Input Types</span></span>
<span data-ttu-id="988a9-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="988a9-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="988a9-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="988a9-122">None.</span></span> <span data-ttu-id="988a9-123">El Get-CCApplianceDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="988a9-123">The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="988a9-124">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="988a9-124">Return Types</span></span>
<span data-ttu-id="988a9-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="988a9-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="988a9-126">El comando devuelve una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="988a9-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="988a9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="988a9-127">See also</span></span>
<span data-ttu-id="988a9-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="988a9-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="988a9-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="988a9-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

