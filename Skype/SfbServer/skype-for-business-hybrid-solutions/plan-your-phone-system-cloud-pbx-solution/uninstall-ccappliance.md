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
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'El cmdlet Uninstall-CcAppliance desinstala el dispositivo en ejecución de Skype Empresarial Cloud Connector Edition desde el servidor host. '
ms.openlocfilehash: f37c3092103832c9efd3b24d2efbedf00e8f54ac
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003150"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="495a7-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="495a7-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="495a7-104">El cmdlet Uninstall-CcAppliance desinstala el dispositivo en ejecución de Skype Empresarial Cloud Connector Edition desde el servidor host. </span><span class="sxs-lookup"><span data-stu-id="495a7-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="495a7-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="495a7-105">Examples</span></span>
<span data-ttu-id="495a7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="495a7-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="495a7-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="495a7-107">Example 1</span></span>

<span data-ttu-id="495a7-108">En el ejemplo siguiente se purgan y desinstalan el dispositivo de conector de nube desde el servidor host:</span><span class="sxs-lookup"><span data-stu-id="495a7-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="495a7-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="495a7-109">Example 2</span></span>

<span data-ttu-id="495a7-110">El siguiente ejemplo purga y fuerza la desinstalación del dispositivo conector de nube en ejecución en el servidor host, incluso si se produjo un error en el proceso de drenaje:</span><span class="sxs-lookup"><span data-stu-id="495a7-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="495a7-111">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="495a7-111">Example 3</span></span>

<span data-ttu-id="495a7-112">En el siguiente ejemplo se desinstala la versión de copia de seguridad de un conector de nube sin la confirmación del usuario:</span><span class="sxs-lookup"><span data-stu-id="495a7-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="495a7-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="495a7-113">Detailed Description</span></span>
<span data-ttu-id="495a7-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="495a7-114"></span></span>

<span data-ttu-id="495a7-115">Si está desinstalando la versión de ejecución actual del conector en la nube, los servicios de drenaje se ejecutan primero en el servidor de mediación y en el servidor perimetral para permitir que las llamadas simultáneas finalicen antes de desinstalar las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="495a7-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="495a7-116">Si va a desinstalar una versión de copia de seguridad, la depuración no se lleva a cabo.</span><span class="sxs-lookup"><span data-stu-id="495a7-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="495a7-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="495a7-117">Parameters</span></span>
<span data-ttu-id="495a7-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="495a7-118"></span></span>

|<span data-ttu-id="495a7-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="495a7-119">**Parameter**</span></span>|<span data-ttu-id="495a7-120">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="495a7-120">**Required**</span></span>|<span data-ttu-id="495a7-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="495a7-121">**Type**</span></span>|<span data-ttu-id="495a7-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="495a7-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="495a7-123">Version</span><span class="sxs-lookup"><span data-stu-id="495a7-123">Version</span></span> <br/> | <span data-ttu-id="495a7-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="495a7-124">Optional</span></span> <br/> |<span data-ttu-id="495a7-125">System.String</span><span class="sxs-lookup"><span data-stu-id="495a7-125">System.String</span></span>  <br/> | <span data-ttu-id="495a7-126">La versión del conector de nube que se desinstalará del servidor host.</span><span class="sxs-lookup"><span data-stu-id="495a7-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="495a7-127">Si no se especifica, desinstale la versión en ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="495a7-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="495a7-128">Force</span><span class="sxs-lookup"><span data-stu-id="495a7-128">Force</span></span>  <br/> |<span data-ttu-id="495a7-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="495a7-129">Optional</span></span>  <br/> |<span data-ttu-id="495a7-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="495a7-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="495a7-p103">Si se va a desinstalar la versión en ejecución actual, se intenta depurar los servidores del servidor de mediación y del servidor perimetral antes de desinstalar las máquinas virtuales. Si especifica el conmutador "Force", incluso en caso de error de los servicios de depuración, las máquinas virtuales se desinstalarán. Este parámetro solo se usa para desinstalar la versión en ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="495a7-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="495a7-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="495a7-134">Confirm</span></span>  <br/> |<span data-ttu-id="495a7-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="495a7-135">Optional</span></span>  <br/> |<span data-ttu-id="495a7-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="495a7-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="495a7-137">Pida a la confirmación del usuario que desinstale las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="495a7-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="495a7-138">El valor predeterminado es TRUE.</span><span class="sxs-lookup"><span data-stu-id="495a7-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="495a7-139">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="495a7-139">Input Types</span></span>
<span data-ttu-id="495a7-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="495a7-140"></span></span>

<span data-ttu-id="495a7-p105">Ninguno. El cmdlet Uninstall-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="495a7-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="495a7-143">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="495a7-143">Return Types</span></span>
<span data-ttu-id="495a7-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="495a7-144"></span></span>

<span data-ttu-id="495a7-145">Ninguno</span><span class="sxs-lookup"><span data-stu-id="495a7-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="495a7-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="495a7-146">See also</span></span>
<span data-ttu-id="495a7-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="495a7-147"></span></span>

[<span data-ttu-id="495a7-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="495a7-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="495a7-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="495a7-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="495a7-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="495a7-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="495a7-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="495a7-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

