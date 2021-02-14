---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: El cmdlet Switch-CcVersion desconecta el dispositivo en ejecución y cambia a un dispositivo recién implementado o de copia de seguridad.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824154"
---
# <a name="switch-ccversion"></a><span data-ttu-id="1b6e1-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="1b6e1-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="1b6e1-104">El cmdlet Switch-CcVersion desconecta el dispositivo en ejecución y cambia a un dispositivo recién implementado o de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="1b6e1-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1b6e1-105">Examples</span></span>
<span data-ttu-id="1b6e1-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1b6e1-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="1b6e1-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="1b6e1-107">Example 1</span></span>

<span data-ttu-id="1b6e1-108">En el siguiente ejemplo se purgan los servicios del dispositivo en ejecución actual y, a continuación, se cambia a un dispositivo recién implementado o de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="1b6e1-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="1b6e1-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="1b6e1-109">Example 2</span></span>

<span data-ttu-id="1b6e1-110">En el siguiente ejemplo se purgan los servicios del dispositivo en ejecución actual y se detienen los servicios por la fuerza si se produce un error al purgar los servicios.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="1b6e1-111">A continuación, el comando cambia a un dispositivo recién implementado o de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="1b6e1-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="1b6e1-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="1b6e1-112">Detailed Description</span></span>
<span data-ttu-id="1b6e1-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1b6e1-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="1b6e1-114">El cmdlet Switch-CcVersion purga los servicios de Cloud Connector en el servidor de mediación y el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="1b6e1-115">Todas las llamadas en ejecución se completarán, pero el dispositivo rechazará las llamadas nuevas.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="1b6e1-116">Después de purgar, el cmdlet desconecta el dispositivo en ejecución de las redes corporativas e Internet, desactiva todas las máquinas virtuales que pertenecen al dispositivo y, a continuación, conecta el dispositivo de copia de seguridad a las redes corporativas e Internet.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1b6e1-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b6e1-117">Parameters</span></span>
<span data-ttu-id="1b6e1-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1b6e1-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="1b6e1-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="1b6e1-119">**Parameter**</span></span>|<span data-ttu-id="1b6e1-120">**Required**</span><span class="sxs-lookup"><span data-stu-id="1b6e1-120">**Required**</span></span>|<span data-ttu-id="1b6e1-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1b6e1-121">**Type**</span></span>|<span data-ttu-id="1b6e1-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1b6e1-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1b6e1-123">Force</span><span class="sxs-lookup"><span data-stu-id="1b6e1-123">Force</span></span> <br/> | <span data-ttu-id="1b6e1-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="1b6e1-124">Optional</span></span> <br/> |<span data-ttu-id="1b6e1-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1b6e1-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="1b6e1-126">Detiene los servicios por la fuerza si se produce un error al purgar los servicios.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1b6e1-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="1b6e1-127">Input Types</span></span>
<span data-ttu-id="1b6e1-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1b6e1-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="1b6e1-129">Ninguno</span><span class="sxs-lookup"><span data-stu-id="1b6e1-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1b6e1-130">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="1b6e1-130">Return Types</span></span>
<span data-ttu-id="1b6e1-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1b6e1-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1b6e1-132">Ninguno</span><span class="sxs-lookup"><span data-stu-id="1b6e1-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1b6e1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b6e1-133">See also</span></span>
<span data-ttu-id="1b6e1-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1b6e1-134"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1b6e1-135">Ninguno</span><span class="sxs-lookup"><span data-stu-id="1b6e1-135">None</span></span>
  

