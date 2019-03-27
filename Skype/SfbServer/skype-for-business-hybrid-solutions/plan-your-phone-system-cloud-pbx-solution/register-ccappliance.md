---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: El cmdlet Register-CcAppliance registra la información de los dispositivos en un sitio RTC en una configuración de inquilinos en línea. Los dispositivos deben registrarse antes de que el servicio de administración de Skype Empresarial Cloud Connector Edition pueda implementarlos y administrarlos.
ms.openlocfilehash: e753f92c84b880da6aac060b65726bda5f9ba1ae
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892276"
---
# <a name="register-ccappliance"></a><span data-ttu-id="a7c8e-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a7c8e-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="a7c8e-105">El cmdlet Register-CcAppliance registra la información de los dispositivos en un sitio RTC en una configuración de inquilinos en línea.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="a7c8e-106">Los dispositivos deben registrarse antes de que el servicio de administración de Skype Empresarial Cloud Connector Edition pueda implementarlos y administrarlos.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="a7c8e-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a7c8e-107">Examples</span></span>
<span data-ttu-id="a7c8e-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a7c8e-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="a7c8e-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a7c8e-109">Example 1</span></span>

<span data-ttu-id="a7c8e-110">En el siguiente ejemplo se registra la información del dispositivo actual a una configuración de inquilino en línea:</span><span class="sxs-lookup"><span data-stu-id="a7c8e-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="a7c8e-111">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="a7c8e-111">Example 2</span></span>

<span data-ttu-id="a7c8e-112">En el siguiente ejemplo se comprueba la configuración del registro localmente sin conectar con una configuración de inquilino en línea:</span><span class="sxs-lookup"><span data-stu-id="a7c8e-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="a7c8e-113">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="a7c8e-113">Example 3</span></span>

<span data-ttu-id="a7c8e-114">En el siguiente ejemplo se registra el dispositivo actual con el nombre "Appliance1" en el sitio RTC "Site1":</span><span class="sxs-lookup"><span data-stu-id="a7c8e-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="a7c8e-115">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="a7c8e-115">Detailed Description</span></span>
<span data-ttu-id="a7c8e-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a7c8e-116"></span></span>

<span data-ttu-id="a7c8e-117">Deberá proporcionar el nombre y la contraseña de la cuenta de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="a7c8e-118">Use la cuenta que creó para la administración en línea de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="a7c8e-119">En la versión 1.4.2 y versiones anteriores, siga las instrucciones para proporcionar la contraseña de certificado externo, contraseña de administrador de modo seguro, contraseña de administrador de dominio y contraseña de administrador de la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="a7c8e-120">En la versión 2.0 y versiones posteriores, siga las instrucciones para proporcionar la contraseña de certificado externo, contraseña CceService y CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="a7c8e-121">Al final del registro, reinicie el servicio de administración de conector en la nube y los servicios de inicio de sesión como cuenta de CceService.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="a7c8e-p104">El SiteName combinado con el FQDN externo del servidor perimetral en el archivo CloudConnector.ini file se considera la identidad del sitio RTC. Si no se han usado ni el SiteName ni el FQDN externo del servidor perimetral para registrar un sitio, se creará un sitio nuevo para este dispositivo en una configuración de inquilino en línea. Si se encuentra una identidad de sitio RTC, un sitio RTC usará esta identidad y el dispositivo se registrará en este sitio RTC. </span><span class="sxs-lookup"><span data-stu-id="a7c8e-p104">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration. If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="a7c8e-125">En la siguiente situación, se producirá un error del cmdlet, que indicará que Site1 ya está registrado: </span><span class="sxs-lookup"><span data-stu-id="a7c8e-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="a7c8e-126">El SiteName es Site1 y el FQDN externo del servidor perimetral es edgserver1.contoso.com. </span><span class="sxs-lookup"><span data-stu-id="a7c8e-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="a7c8e-127">Un sitio RTC cuyo SiteName es Site1 y cuyo FQDN externo del servidor perimetral es edgserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="a7c8e-128">Se ha registrado un sitio RTC cuyo SiteName es NewSite y cuyo FQDN externo del servidor perimetral es edgserver1.contoso.com. </span><span class="sxs-lookup"><span data-stu-id="a7c8e-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="a7c8e-p105">El ApplianceName combinado con el FQDN del servidor de mediación en el archivo CloudConnector.ini file se considera la identidad de un dispositivo. Si no se han usado ni el ApplianceName ni el FQDN del servidor de mediación para registrar un dispositivo, se creará un dispositivo nuevo en la configuración de inquilino en línea. Si el dispositivo ya se ha registrado, se producirá un error del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-p105">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity. If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration. If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="a7c8e-132">En la siguiente situación, se producirá un error del cmdlet, que indicará que el dispositivo ya está registrado: </span><span class="sxs-lookup"><span data-stu-id="a7c8e-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="a7c8e-133">El ApplianceName es Appliance1 y el FQDN del servidor de mediación es ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="a7c8e-134">En el sitio RTC actual, si un dispositivo cuyo nombre es Appliance1 y cuyo FQDN del servidor de mediación es ms.vdomain.com, o el dispositivo cuyo nombre es NewAppliance y el FQDN del servidor de mediación es ms1.vdomain.com ya se ha registrado.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="a7c8e-135">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7c8e-135">Parameters</span></span>
<span data-ttu-id="a7c8e-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a7c8e-136"></span></span>

|<span data-ttu-id="a7c8e-137">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="a7c8e-137">**Parameter**</span></span>|<span data-ttu-id="a7c8e-138">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="a7c8e-138">**Required**</span></span>|<span data-ttu-id="a7c8e-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a7c8e-139">**Type**</span></span>|<span data-ttu-id="a7c8e-140">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a7c8e-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7c8e-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="a7c8e-141">SiteName</span></span>  <br/> |<span data-ttu-id="a7c8e-142">Opcional </span><span class="sxs-lookup"><span data-stu-id="a7c8e-142">Optional</span></span>  <br/> |<span data-ttu-id="a7c8e-143">System.String</span><span class="sxs-lookup"><span data-stu-id="a7c8e-143">System.String</span></span>  <br/> |<span data-ttu-id="a7c8e-p106">Nombre del sitio RTC en el que está registrado el dispositivo. El valor predeterminado es SiteName en el archivo CloudConnector.ini. </span><span class="sxs-lookup"><span data-stu-id="a7c8e-p106">PSTN site name to which the appliance is registered. Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="a7c8e-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="a7c8e-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="a7c8e-147">Opcional </span><span class="sxs-lookup"><span data-stu-id="a7c8e-147">Optional</span></span>  <br/> |<span data-ttu-id="a7c8e-148">System.String</span><span class="sxs-lookup"><span data-stu-id="a7c8e-148">System.String</span></span>  <br/> |<span data-ttu-id="a7c8e-p107">Nombre del dispositivo actual. El valor predeterminado es el nombre del equipo del servidor host.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-p107">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="a7c8e-151">Local</span><span class="sxs-lookup"><span data-stu-id="a7c8e-151">Local</span></span>  <br/> |<span data-ttu-id="a7c8e-152">Opcional</span><span class="sxs-lookup"><span data-stu-id="a7c8e-152">Optional</span></span>  <br/> |<span data-ttu-id="a7c8e-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a7c8e-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a7c8e-154">Se comprueba la configuración del registro localmente sin conectar con la configuración del inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a7c8e-155">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="a7c8e-155">Input Types</span></span>
<span data-ttu-id="a7c8e-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a7c8e-156"></span></span>

<span data-ttu-id="a7c8e-p108">Ninguno. El cmdlet Register-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="a7c8e-p108">None. The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a7c8e-159">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="a7c8e-159">Return Types</span></span>
<span data-ttu-id="a7c8e-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a7c8e-160"></span></span>

<span data-ttu-id="a7c8e-161">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a7c8e-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7c8e-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7c8e-162">See also</span></span>
<span data-ttu-id="a7c8e-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a7c8e-163"></span></span>

[<span data-ttu-id="a7c8e-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a7c8e-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="a7c8e-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a7c8e-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="a7c8e-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a7c8e-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="a7c8e-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a7c8e-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

