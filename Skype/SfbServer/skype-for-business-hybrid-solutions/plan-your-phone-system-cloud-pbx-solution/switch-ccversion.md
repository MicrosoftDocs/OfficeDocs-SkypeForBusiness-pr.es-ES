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
description: El cmdlet switch-CcVersion desconecta el equipo que se ejecuta y cambia a un dispositivo de copia de seguridad o recién implementado.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824154"
---
# <a name="switch-ccversion"></a><span data-ttu-id="5ee61-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="5ee61-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="5ee61-104">El cmdlet switch-CcVersion desconecta el equipo que se ejecuta y cambia a un dispositivo de copia de seguridad o recién implementado.</span><span class="sxs-lookup"><span data-stu-id="5ee61-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="5ee61-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5ee61-105">Examples</span></span>
<span data-ttu-id="5ee61-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5ee61-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="5ee61-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="5ee61-107">Example 1</span></span>

<span data-ttu-id="5ee61-108">En el ejemplo siguiente se purgan los servicios del dispositivo en ejecución actual y, a continuación, se cambia a un dispositivo recién implementado o de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="5ee61-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="5ee61-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="5ee61-109">Example 2</span></span>

<span data-ttu-id="5ee61-110">El ejemplo siguiente drena los servicios del dispositivo en ejecución actual y detiene la fuerza de los servicios si se produce un error al agotar los servicios.</span><span class="sxs-lookup"><span data-stu-id="5ee61-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="5ee61-111">El comando cambia entonces a un dispositivo de copia de seguridad o recién implementado:</span><span class="sxs-lookup"><span data-stu-id="5ee61-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="5ee61-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="5ee61-112">Detailed Description</span></span>
<span data-ttu-id="5ee61-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5ee61-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="5ee61-114">El cmdlet switch-CcVersion drena los servicios del conector de nube en el servidor de mediación y en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="5ee61-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="5ee61-115">Todas las llamadas en curso se completarán, pero el dispositivo rechazará las llamadas nuevas.</span><span class="sxs-lookup"><span data-stu-id="5ee61-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="5ee61-116">Después del agotamiento, el cmdlet desconecta el dispositivo en ejecución de las redes corporativas y de Internet, apaga todas las máquinas virtuales que pertenecen al dispositivo y, a continuación, conecta el dispositivo de copia de seguridad a las redes corporativas y de Internet.</span><span class="sxs-lookup"><span data-stu-id="5ee61-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="5ee61-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ee61-117">Parameters</span></span>
<span data-ttu-id="5ee61-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5ee61-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="5ee61-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="5ee61-119">**Parameter**</span></span>|<span data-ttu-id="5ee61-120">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="5ee61-120">**Required**</span></span>|<span data-ttu-id="5ee61-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5ee61-121">**Type**</span></span>|<span data-ttu-id="5ee61-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5ee61-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5ee61-123">Force</span><span class="sxs-lookup"><span data-stu-id="5ee61-123">Force</span></span> <br/> | <span data-ttu-id="5ee61-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="5ee61-124">Optional</span></span> <br/> |<span data-ttu-id="5ee61-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5ee61-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="5ee61-126">Detiene la fuerza de los servicios si se produce un error al agotar los servicios.</span><span class="sxs-lookup"><span data-stu-id="5ee61-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5ee61-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="5ee61-127">Input Types</span></span>
<span data-ttu-id="5ee61-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ee61-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="5ee61-129">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5ee61-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5ee61-130">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="5ee61-130">Return Types</span></span>
<span data-ttu-id="5ee61-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ee61-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5ee61-132">Ninguno </span><span class="sxs-lookup"><span data-stu-id="5ee61-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5ee61-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ee61-133">See also</span></span>
<span data-ttu-id="5ee61-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ee61-134"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5ee61-135">Ninguno</span><span class="sxs-lookup"><span data-stu-id="5ee61-135">None</span></span>
  

