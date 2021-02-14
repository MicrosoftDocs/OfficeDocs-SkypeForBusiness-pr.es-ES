---
title: Unregister-CcAppliance
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
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: El Unregister-CcAppliance cmdlet anula el registro del dispositivo actual de Skype Empresarial Cloud Connector Edition de un sitio RTC en la configuración del espacio empresarial en línea.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824134"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="426d7-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="426d7-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="426d7-104">El Unregister-CcAppliance cmdlet anula el registro del dispositivo actual de Skype Empresarial Cloud Connector Edition de un sitio RTC en la configuración del espacio empresarial en línea.</span><span class="sxs-lookup"><span data-stu-id="426d7-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="426d7-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="426d7-105">Examples</span></span>
<span data-ttu-id="426d7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="426d7-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="426d7-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="426d7-107">Example 1</span></span>

<span data-ttu-id="426d7-108">En el siguiente ejemplo se anula el registro de un dispositivo actual de la configuración de inquilino en línea:</span><span class="sxs-lookup"><span data-stu-id="426d7-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="426d7-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="426d7-109">Example 2</span></span>

<span data-ttu-id="426d7-110">En el siguiente ejemplo se comprueba la configuración para anular el registro localmente sin conectarse a la configuración de inquilino en línea:</span><span class="sxs-lookup"><span data-stu-id="426d7-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="426d7-111">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="426d7-111">Example 3</span></span>

<span data-ttu-id="426d7-112">En el siguiente ejemplo se anula el registro del dispositivo actual con el nombre "Appliance1" en el sitio RTC "Site1":</span><span class="sxs-lookup"><span data-stu-id="426d7-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="426d7-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="426d7-113">Detailed Description</span></span>
<span data-ttu-id="426d7-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="426d7-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="426d7-115">Al igual que el cmdlet Register-CcAppliance, SiteName combinado con el FQDN externo del servidor perimetral en el archivo CloudConnector.ini se considera una identidad de sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="426d7-115">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="426d7-116">Del mismo modo, ApplianceName combinado con el FQDN del servidor de mediación en el CloudConnector.ini se considera una identidad de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="426d7-116">Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="426d7-117">Una vez anulado el registro del dispositivo, reinicie el servicio de administración de Cloud Connector e inicie sesión como la cuenta NetworkService.</span><span class="sxs-lookup"><span data-stu-id="426d7-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="426d7-118">Parámetros</span><span class="sxs-lookup"><span data-stu-id="426d7-118">Parameters</span></span>
<span data-ttu-id="426d7-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="426d7-119"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="426d7-120">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="426d7-120">**Parameter**</span></span>|<span data-ttu-id="426d7-121">**Required**</span><span class="sxs-lookup"><span data-stu-id="426d7-121">**Required**</span></span>|<span data-ttu-id="426d7-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="426d7-122">**Type**</span></span>|<span data-ttu-id="426d7-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="426d7-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="426d7-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="426d7-124">SiteName</span></span> <br/> |<span data-ttu-id="426d7-125">Opcional</span><span class="sxs-lookup"><span data-stu-id="426d7-125">Optional</span></span>  <br/> |<span data-ttu-id="426d7-126">System.String</span><span class="sxs-lookup"><span data-stu-id="426d7-126">System.String</span></span>  <br/> |<span data-ttu-id="426d7-127">Nombre del sitio RTC donde está registrado el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="426d7-127">PSTN site name where the appliance is registered.</span></span> <span data-ttu-id="426d7-128">El valor predeterminado es SiteName en CloudConnector.ini archivo.</span><span class="sxs-lookup"><span data-stu-id="426d7-128">Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="426d7-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="426d7-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="426d7-130">Opcional</span><span class="sxs-lookup"><span data-stu-id="426d7-130">Optional</span></span>  <br/> |<span data-ttu-id="426d7-131">System.String</span><span class="sxs-lookup"><span data-stu-id="426d7-131">System.String</span></span>  <br/> |<span data-ttu-id="426d7-132">Nombre del dispositivo actual.</span><span class="sxs-lookup"><span data-stu-id="426d7-132">Name of the current appliance.</span></span> <span data-ttu-id="426d7-133">El valor predeterminado es el nombre de equipo del servidor host.</span><span class="sxs-lookup"><span data-stu-id="426d7-133">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="426d7-134">Local</span><span class="sxs-lookup"><span data-stu-id="426d7-134">Local</span></span>  <br/> |<span data-ttu-id="426d7-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="426d7-135">Optional</span></span>  <br/> |<span data-ttu-id="426d7-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="426d7-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="426d7-137">Compruebe la configuración del registro localmente sin conectarse a una configuración de inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="426d7-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="426d7-138">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="426d7-138">Input Types</span></span>
<span data-ttu-id="426d7-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="426d7-139"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="426d7-140">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="426d7-140">None.</span></span> <span data-ttu-id="426d7-141">El Unregister-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="426d7-141">The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="426d7-142">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="426d7-142">Return Types</span></span>
<span data-ttu-id="426d7-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="426d7-143"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="426d7-144">Ninguno</span><span class="sxs-lookup"><span data-stu-id="426d7-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="426d7-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="426d7-145">See also</span></span>
<span data-ttu-id="426d7-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="426d7-146"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="426d7-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="426d7-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="426d7-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="426d7-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="426d7-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="426d7-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="426d7-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="426d7-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

