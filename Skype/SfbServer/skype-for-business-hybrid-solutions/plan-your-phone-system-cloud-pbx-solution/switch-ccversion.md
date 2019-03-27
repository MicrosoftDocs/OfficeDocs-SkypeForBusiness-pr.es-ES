---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: El cmdlet de modificador CcVersion desconecta el dispositivo que se está ejecutando y cambia a un dispositivo recién implementado o copia de seguridad.
ms.openlocfilehash: 73ae9b4f93a2488dea29f3271565ac3d25759fd1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872862"
---
# <a name="switch-ccversion"></a><span data-ttu-id="44eb9-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="44eb9-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="44eb9-104">El cmdlet de modificador CcVersion desconecta el dispositivo que se está ejecutando y cambia a un dispositivo recién implementado o copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="44eb9-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="44eb9-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="44eb9-105">Examples</span></span>
<span data-ttu-id="44eb9-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="44eb9-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="44eb9-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="44eb9-107">Example 1</span></span>

<span data-ttu-id="44eb9-108">En el siguiente ejemplo se purga los servicios de la aplicación actual que se está ejecutando y, a continuación, se pasa a un dispositivo recién implementado o copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="44eb9-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="44eb9-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="44eb9-109">Example 2</span></span>

<span data-ttu-id="44eb9-110">En el ejemplo siguiente se purga los servicios de la aplicación actual que se está ejecutando y detiene los servicios forzosamente si purga de los servicios se produce un error.</span><span class="sxs-lookup"><span data-stu-id="44eb9-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="44eb9-111">A continuación, cambia el comando a un dispositivo recién implementado o copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="44eb9-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="44eb9-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="44eb9-112">Detailed Description</span></span>
<span data-ttu-id="44eb9-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="44eb9-113"></span></span>

<span data-ttu-id="44eb9-114">El cmdlet de modificador CcVersion purga los servicios del conector de nube en el servidor de mediación y el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="44eb9-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="44eb9-115">Se completará todas las llamadas que se está ejecutando, pero el dispositivo rechazará las llamadas nuevo.</span><span class="sxs-lookup"><span data-stu-id="44eb9-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="44eb9-116">Después de purga, el cmdlet desconecta el dispositivo que se está ejecutando desde la corporativa y las redes de Internet, desactiva todas las máquinas virtuales que pertenecen al dispositivo y, a continuación, conecta el dispositivo de copia de seguridad a la empresa y las redes de Internet.</span><span class="sxs-lookup"><span data-stu-id="44eb9-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="44eb9-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44eb9-117">Parameters</span></span>
<span data-ttu-id="44eb9-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="44eb9-118"></span></span>

|<span data-ttu-id="44eb9-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="44eb9-119">**Parameter**</span></span>|<span data-ttu-id="44eb9-120">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="44eb9-120">**Required**</span></span>|<span data-ttu-id="44eb9-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="44eb9-121">**Type**</span></span>|<span data-ttu-id="44eb9-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="44eb9-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="44eb9-123">Force</span><span class="sxs-lookup"><span data-stu-id="44eb9-123">Force</span></span> <br/> | <span data-ttu-id="44eb9-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="44eb9-124">Optional</span></span> <br/> |<span data-ttu-id="44eb9-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="44eb9-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="44eb9-126">Detiene los servicios forzosamente si purga de los servicios se produce un error.</span><span class="sxs-lookup"><span data-stu-id="44eb9-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="44eb9-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="44eb9-127">Input Types</span></span>
<span data-ttu-id="44eb9-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="44eb9-128"></span></span>

<span data-ttu-id="44eb9-129">Ninguno</span><span class="sxs-lookup"><span data-stu-id="44eb9-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="44eb9-130">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="44eb9-130">Return Types</span></span>
<span data-ttu-id="44eb9-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="44eb9-131"></span></span>

<span data-ttu-id="44eb9-132">Ninguno </span><span class="sxs-lookup"><span data-stu-id="44eb9-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="44eb9-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44eb9-133">See also</span></span>
<span data-ttu-id="44eb9-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="44eb9-134"></span></span>

<span data-ttu-id="44eb9-135">Ninguno</span><span class="sxs-lookup"><span data-stu-id="44eb9-135">None</span></span>
  

