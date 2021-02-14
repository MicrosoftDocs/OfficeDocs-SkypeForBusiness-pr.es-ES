---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: El cmdlet Register-CcAppliance registra la información del dispositivo en un sitio RTC en una configuración de inquilino en línea. Un dispositivo debe registrarse para poder implementarse y administrarse mediante el servicio de administración de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824306"
---
# <a name="register-ccappliance"></a><span data-ttu-id="ee47b-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="ee47b-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="ee47b-105">El cmdlet Register-CcAppliance registra la información del dispositivo en un sitio RTC en una configuración de inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="ee47b-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="ee47b-106">Un dispositivo debe registrarse para poder implementarse y administrarse mediante el servicio de administración de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="ee47b-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="ee47b-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ee47b-107">Examples</span></span>
<span data-ttu-id="ee47b-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ee47b-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ee47b-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="ee47b-109">Example 1</span></span>

<span data-ttu-id="ee47b-110">En el siguiente ejemplo se registra la información del dispositivo actual en una configuración de inquilino en línea:</span><span class="sxs-lookup"><span data-stu-id="ee47b-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="ee47b-111">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="ee47b-111">Example 2</span></span>

<span data-ttu-id="ee47b-112">En el siguiente ejemplo se comprueba la configuración del registro localmente sin conectarse a una configuración de inquilino en línea:</span><span class="sxs-lookup"><span data-stu-id="ee47b-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="ee47b-113">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="ee47b-113">Example 3</span></span>

<span data-ttu-id="ee47b-114">En el siguiente ejemplo se registra el dispositivo actual con el nombre "Appliance1" en el sitio RTC "Site1":</span><span class="sxs-lookup"><span data-stu-id="ee47b-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="ee47b-115">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="ee47b-115">Detailed Description</span></span>
<span data-ttu-id="ee47b-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ee47b-116"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="ee47b-117">Debe proporcionar el nombre y la contraseña de la cuenta de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ee47b-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="ee47b-118">Use la cuenta que ha creado para la administración en línea de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ee47b-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="ee47b-119">En la versión 1.4.2 y anteriores, siga las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de administrador de modo seguro, la contraseña de administrador de dominio y la contraseña de administrador de máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="ee47b-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="ee47b-120">En la versión 2.0 y posteriores, siga las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de CceService y la contraseña caBackupFile.</span><span class="sxs-lookup"><span data-stu-id="ee47b-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="ee47b-121">Al final del registro, reinicie el servicio de administración de Cloud Connector e inicie sesión en los servicios como cuenta CceService.</span><span class="sxs-lookup"><span data-stu-id="ee47b-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="ee47b-122">SiteName combinado con el FQDN externo del servidor perimetral en el CloudConnector.ini se considera una identidad de sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="ee47b-122">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="ee47b-123">Si no se ha usado ni siteName ni el FQDN externo del servidor perimetral para registrar un sitio, se creará un nuevo sitio para este dispositivo en una configuración de inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="ee47b-123">If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration.</span></span> <span data-ttu-id="ee47b-124">Si se encuentra una identidad de sitio RTC, un sitio RTC usará esta identidad y el dispositivo se registrará en este sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="ee47b-124">If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="ee47b-125">En la siguiente situación, se producirá un error en el cmdlet e indicará que Site1 ya está registrado:</span><span class="sxs-lookup"><span data-stu-id="ee47b-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="ee47b-126">SiteName es Site1 y el FQDN externo del servidor perimetral es edgserver1.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ee47b-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="ee47b-127">Un sitio RTC cuyo SiteName es Site1 y el FQDN externo del servidor perimetral es edgserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ee47b-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="ee47b-128">Se ha registrado un sitio RTC cuyo SiteName es NewSite y el FQDN externo edgserver1.contoso.com servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="ee47b-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="ee47b-129">ApplianceName combinado con el FQDN del servidor de mediación en CloudConnector.ini archivo se considera una identidad de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ee47b-129">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity.</span></span> <span data-ttu-id="ee47b-130">Si no se han usado ni el ApplianceName ni el FQDN del servidor de mediación para registrar un dispositivo, se creará un nuevo dispositivo en la configuración del inquilino en línea.</span><span class="sxs-lookup"><span data-stu-id="ee47b-130">If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration.</span></span> <span data-ttu-id="ee47b-131">Si el dispositivo ya está registrado, se producirá un error en el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee47b-131">If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="ee47b-132">En la siguiente situación, se producirá un error en el cmdlet e indicará que el dispositivo ya está registrado:</span><span class="sxs-lookup"><span data-stu-id="ee47b-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="ee47b-133">ApplianceName es Appliance1 y el FQDN del servidor de mediación es ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="ee47b-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="ee47b-134">En el sitio RTC actual, si un dispositivo cuyo nombre es Appliance1 y FQDN del servidor de mediación es ms.vdomain.com o un dispositivo cuyo nombre es NewAppliance y FQDN del servidor de mediación ms1.vdomain.com se ha registrado.</span><span class="sxs-lookup"><span data-stu-id="ee47b-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="ee47b-135">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee47b-135">Parameters</span></span>
<span data-ttu-id="ee47b-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ee47b-136"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="ee47b-137">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="ee47b-137">**Parameter**</span></span>|<span data-ttu-id="ee47b-138">**Required**</span><span class="sxs-lookup"><span data-stu-id="ee47b-138">**Required**</span></span>|<span data-ttu-id="ee47b-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ee47b-139">**Type**</span></span>|<span data-ttu-id="ee47b-140">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ee47b-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ee47b-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="ee47b-141">SiteName</span></span>  <br/> |<span data-ttu-id="ee47b-142">Opcional</span><span class="sxs-lookup"><span data-stu-id="ee47b-142">Optional</span></span>  <br/> |<span data-ttu-id="ee47b-143">System.String</span><span class="sxs-lookup"><span data-stu-id="ee47b-143">System.String</span></span>  <br/> |<span data-ttu-id="ee47b-144">Nombre del sitio RTC en el que está registrado el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ee47b-144">PSTN site name to which the appliance is registered.</span></span> <span data-ttu-id="ee47b-145">El valor predeterminado es SiteName en el CloudConnector.ini archivo.</span><span class="sxs-lookup"><span data-stu-id="ee47b-145">Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="ee47b-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="ee47b-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="ee47b-147">Opcional</span><span class="sxs-lookup"><span data-stu-id="ee47b-147">Optional</span></span>  <br/> |<span data-ttu-id="ee47b-148">System.String</span><span class="sxs-lookup"><span data-stu-id="ee47b-148">System.String</span></span>  <br/> |<span data-ttu-id="ee47b-149">Nombre del dispositivo actual.</span><span class="sxs-lookup"><span data-stu-id="ee47b-149">Name of the current appliance.</span></span> <span data-ttu-id="ee47b-150">El valor predeterminado es el nombre de equipo del servidor host.</span><span class="sxs-lookup"><span data-stu-id="ee47b-150">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="ee47b-151">Local</span><span class="sxs-lookup"><span data-stu-id="ee47b-151">Local</span></span>  <br/> |<span data-ttu-id="ee47b-152">Opcional</span><span class="sxs-lookup"><span data-stu-id="ee47b-152">Optional</span></span>  <br/> |<span data-ttu-id="ee47b-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="ee47b-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="ee47b-154">Compruebe las configuraciones para el registro localmente sin conectarse a la configuración de inquilinos en línea.</span><span class="sxs-lookup"><span data-stu-id="ee47b-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ee47b-155">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="ee47b-155">Input Types</span></span>
<span data-ttu-id="ee47b-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ee47b-156"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ee47b-157">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ee47b-157">None.</span></span> <span data-ttu-id="ee47b-158">El Register-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="ee47b-158">The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ee47b-159">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="ee47b-159">Return Types</span></span>
<span data-ttu-id="ee47b-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ee47b-160"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ee47b-161">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ee47b-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ee47b-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee47b-162">See also</span></span>
<span data-ttu-id="ee47b-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ee47b-163"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="ee47b-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="ee47b-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="ee47b-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="ee47b-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="ee47b-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="ee47b-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="ee47b-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="ee47b-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

