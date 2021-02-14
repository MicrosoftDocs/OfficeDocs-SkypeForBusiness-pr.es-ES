---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: El cmdlet Uninstall-CcAppliance desinstala el dispositivo de Skype Empresarial Cloud Connector Edition en ejecución del servidor host.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824144"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="c1060-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c1060-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="c1060-104">El cmdlet Uninstall-CcAppliance desinstala el dispositivo de Skype Empresarial Cloud Connector Edition en ejecución del servidor host.</span><span class="sxs-lookup"><span data-stu-id="c1060-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="c1060-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c1060-105">Examples</span></span>
<span data-ttu-id="c1060-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c1060-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c1060-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="c1060-107">Example 1</span></span>

<span data-ttu-id="c1060-108">En el siguiente ejemplo se purga y desinstala el dispositivo de Cloud Connector del servidor host:</span><span class="sxs-lookup"><span data-stu-id="c1060-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="c1060-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="c1060-109">Example 2</span></span>

<span data-ttu-id="c1060-110">En el siguiente ejemplo se purga y se desinstala por la fuerza el dispositivo de Cloud Connector en ejecución en el servidor host, incluso si se ha fallado en el proceso de purga:</span><span class="sxs-lookup"><span data-stu-id="c1060-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="c1060-111">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="c1060-111">Example 3</span></span>

<span data-ttu-id="c1060-112">En el siguiente ejemplo se desinstala una versión de copia de seguridad de Cloud Connector sin la confirmación del usuario:</span><span class="sxs-lookup"><span data-stu-id="c1060-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="c1060-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="c1060-113">Detailed Description</span></span>
<span data-ttu-id="c1060-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c1060-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c1060-115">Si va a desinstalar la versión en ejecución actual de Cloud Connector, los servicios de purga se ejecutan primero en el servidor de mediación y en el servidor perimetral para permitir que las llamadas simultáneas finalicen antes de desinstalar las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="c1060-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="c1060-116">Si va a desinstalar una versión de copia de seguridad, no se realizará la purga.</span><span class="sxs-lookup"><span data-stu-id="c1060-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c1060-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1060-117">Parameters</span></span>
<span data-ttu-id="c1060-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c1060-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="c1060-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="c1060-119">**Parameter**</span></span>|<span data-ttu-id="c1060-120">**Required**</span><span class="sxs-lookup"><span data-stu-id="c1060-120">**Required**</span></span>|<span data-ttu-id="c1060-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c1060-121">**Type**</span></span>|<span data-ttu-id="c1060-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c1060-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c1060-123">Versión</span><span class="sxs-lookup"><span data-stu-id="c1060-123">Version</span></span> <br/> | <span data-ttu-id="c1060-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="c1060-124">Optional</span></span> <br/> |<span data-ttu-id="c1060-125">System.String</span><span class="sxs-lookup"><span data-stu-id="c1060-125">System.String</span></span>  <br/> | <span data-ttu-id="c1060-126">La versión de Cloud Connector que se desinstalará del servidor host.</span><span class="sxs-lookup"><span data-stu-id="c1060-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="c1060-127">Si no se especifica, desinstale la versión en ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="c1060-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="c1060-128">Force</span><span class="sxs-lookup"><span data-stu-id="c1060-128">Force</span></span>  <br/> |<span data-ttu-id="c1060-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="c1060-129">Optional</span></span>  <br/> |<span data-ttu-id="c1060-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c1060-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c1060-131">Si desinstala la versión en ejecución actual, intente purgar los servidores del servidor de mediación y del servidor perimetral antes de desinstalar las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="c1060-131">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines.</span></span> <span data-ttu-id="c1060-132">Si especifica el modificador "Force", incluso si los servicios de purga fallan, las máquinas virtuales se desinstalarán.</span><span class="sxs-lookup"><span data-stu-id="c1060-132">If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled.</span></span> <span data-ttu-id="c1060-133">Este parámetro solo se usa para desinstalar la versión en ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="c1060-133">This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="c1060-134">Confirmar</span><span class="sxs-lookup"><span data-stu-id="c1060-134">Confirm</span></span>  <br/> |<span data-ttu-id="c1060-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="c1060-135">Optional</span></span>  <br/> |<span data-ttu-id="c1060-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c1060-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c1060-137">Pida confirmación al usuario para desinstalar las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="c1060-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="c1060-138">El valor predeterminado es TRUE.</span><span class="sxs-lookup"><span data-stu-id="c1060-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c1060-139">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="c1060-139">Input Types</span></span>
<span data-ttu-id="c1060-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c1060-140"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c1060-141">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c1060-141">None.</span></span> <span data-ttu-id="c1060-142">El Uninstall-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="c1060-142">The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c1060-143">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="c1060-143">Return Types</span></span>
<span data-ttu-id="c1060-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c1060-144"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c1060-145">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c1060-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c1060-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1060-146">See also</span></span>
<span data-ttu-id="c1060-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c1060-147"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="c1060-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c1060-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="c1060-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c1060-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="c1060-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c1060-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="c1060-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c1060-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

