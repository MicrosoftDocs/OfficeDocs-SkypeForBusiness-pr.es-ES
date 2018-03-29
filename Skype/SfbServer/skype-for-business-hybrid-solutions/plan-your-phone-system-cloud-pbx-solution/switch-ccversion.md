---
title: Conmutador CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: El cmdlet CcVersion de Switch desconecta el dispositivo ejecutando y cambia a un dispositivo recién implementado o copia de seguridad.
ms.openlocfilehash: 651dad80ef5c9907eb6c182527b646da7aa5acc8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="switch-ccversion"></a><span data-ttu-id="fb938-103">Conmutador CcVersion</span><span class="sxs-lookup"><span data-stu-id="fb938-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="fb938-104">El cmdlet CcVersion de Switch desconecta el dispositivo ejecutando y cambia a un dispositivo recién implementado o copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb938-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="fb938-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fb938-105">Examples</span></span>
<span data-ttu-id="fb938-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fb938-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="fb938-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="fb938-107">Example 1</span></span>

<span data-ttu-id="fb938-108">En el ejemplo siguiente se agota los servicios del equipo de ejecución actual y, a continuación, cambia a un dispositivo recién implementado o copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="fb938-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="fb938-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="fb938-109">Example 2</span></span>

<span data-ttu-id="fb938-110">En el ejemplo siguiente se purgan los servicios del equipo de ejecución actual y detiene los servicios forzosamente si no purga los servicios.</span><span class="sxs-lookup"><span data-stu-id="fb938-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="fb938-111">A continuación, cambia el comando a un dispositivo recién implementado o copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="fb938-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="fb938-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="fb938-112">Detailed Description</span></span>
<span data-ttu-id="fb938-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fb938-113"></span></span>

<span data-ttu-id="fb938-114">El cmdlet CcVersion de conmutador purga los servicios de nube de conector en el servidor de mediación y servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="fb938-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="fb938-115">Todas las llamadas de ejecución se completará, pero el dispositivo rechazará todas las llamadas nuevas.</span><span class="sxs-lookup"><span data-stu-id="fb938-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="fb938-116">Tras el drenaje, el cmdlet desconecta el dispositivo ejecución de corporativa y redes de Internet, desactiva todas las máquinas virtuales que pertenecen al dispositivo y, a continuación, conecta el dispositivo de copia de seguridad a la empresa y las redes de Internet.</span><span class="sxs-lookup"><span data-stu-id="fb938-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="fb938-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb938-117">Parameters</span></span>
<span data-ttu-id="fb938-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fb938-118"></span></span>

|<span data-ttu-id="fb938-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="fb938-119">**Parameter**</span></span>|<span data-ttu-id="fb938-120">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="fb938-120">**Required**</span></span>|<span data-ttu-id="fb938-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fb938-121">**Type**</span></span>|<span data-ttu-id="fb938-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fb938-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="fb938-123">Force</span><span class="sxs-lookup"><span data-stu-id="fb938-123">Force</span></span> <br/> | <span data-ttu-id="fb938-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="fb938-124">Optional</span></span> <br/> |<span data-ttu-id="fb938-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fb938-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="fb938-126">Detiene los servicios forzosamente si purga los servicios se produce un error.</span><span class="sxs-lookup"><span data-stu-id="fb938-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="fb938-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="fb938-127">Input Types</span></span>
<span data-ttu-id="fb938-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fb938-128"></span></span>

<span data-ttu-id="fb938-129">Ninguno</span><span class="sxs-lookup"><span data-stu-id="fb938-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fb938-130">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="fb938-130">Return Types</span></span>
<span data-ttu-id="fb938-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fb938-131"></span></span>

<span data-ttu-id="fb938-132">Ninguno</span><span class="sxs-lookup"><span data-stu-id="fb938-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fb938-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb938-133">See also</span></span>
<span data-ttu-id="fb938-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fb938-134"></span></span>

<span data-ttu-id="fb938-135">Ninguno</span><span class="sxs-lookup"><span data-stu-id="fb938-135">None</span></span>
  

