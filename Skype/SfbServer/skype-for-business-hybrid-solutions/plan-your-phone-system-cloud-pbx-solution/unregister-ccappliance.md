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
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: El cmdlet Unregister-CcAppliance anula el registro del dispositivo actual de Skype Empresarial Cloud Connector Edition de un sitio RTC en la configuración del inquilino en línea.
ms.openlocfilehash: 2bd8f3a3ef4ac2b29ab9e7d766836d7a3555c0f4
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003140"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="66d92-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="66d92-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="66d92-104">El cmdlet Unregister-CcAppliance anula el registro del dispositivo actual de Skype Empresarial Cloud Connector Edition de un sitio RTC en la configuración del inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="66d92-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="66d92-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="66d92-105">Examples</span></span>
<span data-ttu-id="66d92-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="66d92-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="66d92-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="66d92-107">Example 1</span></span>

<span data-ttu-id="66d92-108">En el siguiente ejemplo se anula el registro de un dispositivo actual de la configuración del inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="66d92-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="66d92-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="66d92-109">Example 2</span></span>

<span data-ttu-id="66d92-110">En el siguiente ejemplo se comprueba la configuración para anular el registro localmente sin conectar con la configuración del inquilino en línea:</span><span class="sxs-lookup"><span data-stu-id="66d92-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="66d92-111">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="66d92-111">Example 3</span></span>

<span data-ttu-id="66d92-112">En el siguiente ejemplo se anula el registro del dispositivo actual con el nombre "Appliance1" del sitio RTC "Site1":</span><span class="sxs-lookup"><span data-stu-id="66d92-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="66d92-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="66d92-113">Detailed Description</span></span>
<span data-ttu-id="66d92-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="66d92-114"></span></span>

<span data-ttu-id="66d92-p101">Igual que con el cmdlet Register-CcAppliance, la combinación de SiteName con el FQDN externo del servidor perimetral en el archivo CloudConnector.ini file se considera una identidad de sitio RTC. Del mismo modo, la combinación de ApplianceName con el FQDN del servidor de mediación en el archivo CloudConnector.ini se considera una identidad de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66d92-p101">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="66d92-117">Una vez que el dispositivo no esté registrado, reinicie el servicio de administración de conector de nube e inicie sesión como la cuenta NetworkService.</span><span class="sxs-lookup"><span data-stu-id="66d92-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="66d92-118">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66d92-118">Parameters</span></span>
<span data-ttu-id="66d92-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="66d92-119"></span></span>

|<span data-ttu-id="66d92-120">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="66d92-120">**Parameter**</span></span>|<span data-ttu-id="66d92-121">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="66d92-121">**Required**</span></span>|<span data-ttu-id="66d92-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="66d92-122">**Type**</span></span>|<span data-ttu-id="66d92-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="66d92-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="66d92-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="66d92-124">SiteName</span></span> <br/> |<span data-ttu-id="66d92-125">Opcional </span><span class="sxs-lookup"><span data-stu-id="66d92-125">Optional</span></span>  <br/> |<span data-ttu-id="66d92-126">System.String</span><span class="sxs-lookup"><span data-stu-id="66d92-126">System.String</span></span>  <br/> |<span data-ttu-id="66d92-p102">Nombre del sitio RTC en el que está registrado el dispositivo. El valor predeterminado es SiteName en el archivo CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="66d92-p102">PSTN site name where the appliance is registered. Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="66d92-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="66d92-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="66d92-130">Opcional </span><span class="sxs-lookup"><span data-stu-id="66d92-130">Optional</span></span>  <br/> |<span data-ttu-id="66d92-131">System.String</span><span class="sxs-lookup"><span data-stu-id="66d92-131">System.String</span></span>  <br/> |<span data-ttu-id="66d92-p103">Nombre del dispositivo actual. El valor predeterminado es el nombre del equipo del servidor host.</span><span class="sxs-lookup"><span data-stu-id="66d92-p103">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="66d92-134">Local</span><span class="sxs-lookup"><span data-stu-id="66d92-134">Local</span></span>  <br/> |<span data-ttu-id="66d92-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="66d92-135">Optional</span></span>  <br/> |<span data-ttu-id="66d92-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="66d92-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="66d92-137">Se comprueba la configuración del registro localmente sin conectar con la configuración del inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="66d92-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="66d92-138">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="66d92-138">Input Types</span></span>
<span data-ttu-id="66d92-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66d92-139"></span></span>

<span data-ttu-id="66d92-p104">Ninguno. El cmdlet Unregister-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="66d92-p104">None. The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="66d92-142">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="66d92-142">Return Types</span></span>
<span data-ttu-id="66d92-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66d92-143"></span></span>

<span data-ttu-id="66d92-144">Ninguno</span><span class="sxs-lookup"><span data-stu-id="66d92-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="66d92-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66d92-145">See also</span></span>
<span data-ttu-id="66d92-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66d92-146"></span></span>

[<span data-ttu-id="66d92-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="66d92-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="66d92-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="66d92-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="66d92-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="66d92-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="66d92-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="66d92-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

