---
title: CcAppliance desinstalar
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'El cmdlet Uninstall-CcAppliance desinstala el dispositivo en ejecución de Skype Empresarial Cloud Connector Edition desde el servidor host. '
ms.openlocfilehash: 325e21d28ef87f9d27e87721452bc3d67d197169
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="361d1-103">CcAppliance desinstalar</span><span class="sxs-lookup"><span data-stu-id="361d1-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="361d1-104">El cmdlet Uninstall-CcAppliance desinstala el dispositivo en ejecución de Skype Empresarial Cloud Connector Edition desde el servidor host. </span><span class="sxs-lookup"><span data-stu-id="361d1-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="361d1-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="361d1-105">Examples</span></span>
<span data-ttu-id="361d1-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="361d1-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="361d1-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="361d1-107">Example 1</span></span>

<span data-ttu-id="361d1-108">En el ejemplo siguiente se agota y desinstala el dispositivo conector de nube desde el servidor host:</span><span class="sxs-lookup"><span data-stu-id="361d1-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="361d1-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="361d1-109">Example 2</span></span>

<span data-ttu-id="361d1-110">En el ejemplo siguiente se purga y forzosamente desinstala el dispositivo conector de nube ejecutando en el servidor host, incluso si ha fallado el proceso de drenaje:</span><span class="sxs-lookup"><span data-stu-id="361d1-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="361d1-111">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="361d1-111">Example 3</span></span>

<span data-ttu-id="361d1-112">En el ejemplo siguiente se desinstala una versión de copia de seguridad de nube conector sin pedir confirmación del usuario:</span><span class="sxs-lookup"><span data-stu-id="361d1-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="361d1-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="361d1-113">Detailed Description</span></span>
<span data-ttu-id="361d1-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="361d1-114"></span></span>

<span data-ttu-id="361d1-115">Si está desinstalando la versión actual de ejecución del conector de la nube, servicios de drenaje primero se ejecutan en el servidor de mediación y un servidor perimetral para permitir las llamadas simultáneas a finalizar antes de desinstalar las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="361d1-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="361d1-116">Si va a desinstalar una versión de copia de seguridad, la depuración no se lleva a cabo.</span><span class="sxs-lookup"><span data-stu-id="361d1-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="361d1-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="361d1-117">Parameters</span></span>
<span data-ttu-id="361d1-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="361d1-118"></span></span>

|<span data-ttu-id="361d1-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="361d1-119">**Parameter**</span></span>|<span data-ttu-id="361d1-120">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="361d1-120">**Required**</span></span>|<span data-ttu-id="361d1-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="361d1-121">**Type**</span></span>|<span data-ttu-id="361d1-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="361d1-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="361d1-123">Version</span><span class="sxs-lookup"><span data-stu-id="361d1-123">Version</span></span> <br/> | <span data-ttu-id="361d1-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="361d1-124">Optional</span></span> <br/> |<span data-ttu-id="361d1-125">System.String</span><span class="sxs-lookup"><span data-stu-id="361d1-125">System.String</span></span>  <br/> | <span data-ttu-id="361d1-126">La versión del conector de nube que se van a desinstalar desde el servidor host.</span><span class="sxs-lookup"><span data-stu-id="361d1-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="361d1-127">Si no se especifica, desinstale la versión en ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="361d1-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="361d1-128">Force</span><span class="sxs-lookup"><span data-stu-id="361d1-128">Force</span></span>  <br/> |<span data-ttu-id="361d1-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="361d1-129">Optional</span></span>  <br/> |<span data-ttu-id="361d1-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="361d1-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="361d1-p103">Si se va a desinstalar la versión en ejecución actual, se intenta depurar los servidores del servidor de mediación y del servidor perimetral antes de desinstalar las máquinas virtuales. Si especifica el conmutador "Force", incluso en caso de error de los servicios de depuración, las máquinas virtuales se desinstalarán. Este parámetro solo se usa para desinstalar la versión en ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="361d1-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="361d1-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="361d1-134">Confirm</span></span>  <br/> |<span data-ttu-id="361d1-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="361d1-135">Optional</span></span>  <br/> |<span data-ttu-id="361d1-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="361d1-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="361d1-137">Pedir confirmación del usuario para desinstalar las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="361d1-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="361d1-138">El valor predeterminado es TRUE.</span><span class="sxs-lookup"><span data-stu-id="361d1-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="361d1-139">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="361d1-139">Input Types</span></span>
<span data-ttu-id="361d1-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="361d1-140"></span></span>

<span data-ttu-id="361d1-p105">Ninguno. El cmdlet Uninstall-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="361d1-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="361d1-143">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="361d1-143">Return Types</span></span>
<span data-ttu-id="361d1-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="361d1-144"></span></span>

<span data-ttu-id="361d1-145">Ninguno</span><span class="sxs-lookup"><span data-stu-id="361d1-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="361d1-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="361d1-146">See also</span></span>
<span data-ttu-id="361d1-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="361d1-147"></span></span>

[<span data-ttu-id="361d1-148">Instalar CcAppliance</span><span class="sxs-lookup"><span data-stu-id="361d1-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="361d1-149">CcAppliance publicar</span><span class="sxs-lookup"><span data-stu-id="361d1-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="361d1-150">Registro CcAppliance</span><span class="sxs-lookup"><span data-stu-id="361d1-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="361d1-151">Anular el registro de CcAppliance</span><span class="sxs-lookup"><span data-stu-id="361d1-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

