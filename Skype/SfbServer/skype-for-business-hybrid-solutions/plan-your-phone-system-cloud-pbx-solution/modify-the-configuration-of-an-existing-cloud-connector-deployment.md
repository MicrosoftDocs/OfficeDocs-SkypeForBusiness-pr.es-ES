---
title: Modificación de la configuración de una implementación existente de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Siga los pasos de este tema para modificar la configuración de una implementación existente de Skype empresarial Cloud Connector Edition 1.4.1 o posterior.
ms.openlocfilehash: 77e9940e10cc356afbade5592bf41a0cdba66b0f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779386"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="f6801-103">Modificación de la configuración de una implementación existente de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="f6801-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="f6801-104">Siga los pasos de este tema para modificar la configuración de una implementación existente de Skype empresarial Cloud Connector Edition 1.4.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f6801-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="f6801-105">Modificar la configuración de un sitio único</span><span class="sxs-lookup"><span data-stu-id="f6801-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="f6801-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="f6801-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="f6801-107">Si solo hay un dispositivo en el sitio, cuando desee cambiar las opciones de configuración una vez implementado el dispositivo, puede modificar el archivo CloudConnector. ini e iniciar la implementación de nuevo.</span><span class="sxs-lookup"><span data-stu-id="f6801-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="f6801-108">Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el servidor host:</span><span class="sxs-lookup"><span data-stu-id="f6801-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="f6801-109">Ejecute el siguiente cmdlet para anular el registro del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="f6801-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="f6801-110">Actualice el archivo CloudConnector. ini en el directorio de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f6801-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="f6801-111">Ejecute el siguiente cmdlet para actualizar la configuración: (este paso solo es aplicable a la versión 2; para versiones anteriores, vaya al paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="f6801-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="f6801-112">Ejecute el siguiente cmdlet para volver a registrar el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="f6801-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="f6801-113">Ejecute el siguiente cmdlet para instalar Skype empresarial Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="f6801-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="f6801-114">Si hay más de un dispositivo en el sitio, tendrá que seguir estos pasos, modificar el archivo CloudConnector. ini y volver a implementar los dispositivos uno a uno.</span><span class="sxs-lookup"><span data-stu-id="f6801-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="f6801-115">Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el dispositivo actual:</span><span class="sxs-lookup"><span data-stu-id="f6801-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="f6801-116">Ejecute el siguiente cmdlet para anular el registro del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="f6801-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="f6801-117">Actualice el archivo CloudConnector. ini en el directorio de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f6801-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="f6801-118">Ejecute el siguiente cmdlet para actualizar la configuración: (este paso solo es aplicable a la versión 2; para versiones anteriores, vaya al paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="f6801-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="f6801-119">Ejecute el siguiente cmdlet para volver a registrar el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="f6801-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="f6801-120">Ejecute el siguiente cmdlet en el resto de los dispositivos del sitio para seleccionar la última configuración:</span><span class="sxs-lookup"><span data-stu-id="f6801-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="f6801-121">Ejecute el siguiente cmdlet para volver a implementar Cloud Connector en el dispositivo actual:</span><span class="sxs-lookup"><span data-stu-id="f6801-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="f6801-122">Modificación de la configuración de varios sitios</span><span class="sxs-lookup"><span data-stu-id="f6801-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="f6801-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="f6801-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="f6801-124">Para modificar la configuración de varios sitios en una implementación, siga los pasos de un sitio único, actualizando un sitio cada vez.</span><span class="sxs-lookup"><span data-stu-id="f6801-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="f6801-125">Modificar la configuración de la organización de Office 365 para habilitar las actualizaciones automáticas</span><span class="sxs-lookup"><span data-stu-id="f6801-125">Modify the configuration of your Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="f6801-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="f6801-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="f6801-127">Para habilitar las actualizaciones automáticas del sistema operativo y las actualizaciones automáticas de bits, debe usar la cuenta de administrador de inquilinos de Skype empresarial para la administración en línea y usar PowerShell remoto del inquilino de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="f6801-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="f6801-128">Si deshabilitó las actualizaciones automáticas del sistema operativo o actualizaciones automáticas de bits, el host y la máquina virtual podrían perderse actualizaciones de Windows importantes y Cloud Connector no se actualizará automáticamente a la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="f6801-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="f6801-129">Se recomienda encarecidamente habilitar las actualizaciones automáticas.</span><span class="sxs-lookup"><span data-stu-id="f6801-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="f6801-130">La propiedad EnableAutoUpdate del sitio debe establecerse en true (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f6801-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="f6801-131">Ejecute el siguiente cmdlet para asegurarse de que EnableAutoUpdate está establecido en true:</span><span class="sxs-lookup"><span data-stu-id="f6801-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="f6801-132">Crear ventana de tiempo de actualización automática para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="f6801-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="f6801-133">La ventana de tiempo puede ser diaria, semanal o mensual.</span><span class="sxs-lookup"><span data-stu-id="f6801-133">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="f6801-134">Siempre que Windows necesite una hora de inicio y una duración.</span><span class="sxs-lookup"><span data-stu-id="f6801-134">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="f6801-135">Para un período de tiempo diario, solo se necesita la hora de inicio y la duración.</span><span class="sxs-lookup"><span data-stu-id="f6801-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="f6801-136">Para un intervalo de tiempo semanal, se necesitan días de la semana, que pueden ser un solo día o varios días.</span><span class="sxs-lookup"><span data-stu-id="f6801-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="f6801-137">Para un intervalo mensual, puede haber dos tipos.</span><span class="sxs-lookup"><span data-stu-id="f6801-137">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="f6801-138">El primer tipo es especificar el día del mes, que puede ser un solo día.</span><span class="sxs-lookup"><span data-stu-id="f6801-138">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="f6801-139">El segundo tipo es especificar las semanas del mes, junto con los días de la semana, que ambos pueden ser un único elemento o varios elementos.</span><span class="sxs-lookup"><span data-stu-id="f6801-139">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="f6801-140">Cada inquilino puede tener 20 ventanas de tiempo definidas.</span><span class="sxs-lookup"><span data-stu-id="f6801-140">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="f6801-141">Se creará la ventana de tiempo predeterminada para un nuevo inquilino como ventana de tiempo predeterminada para la actualización del sistema operativo y la actualización de bits.</span><span class="sxs-lookup"><span data-stu-id="f6801-141">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="f6801-142">Ejecute los cmdlets siguientes para establecer el intervalo de tiempo diario, semanal o mensual:</span><span class="sxs-lookup"><span data-stu-id="f6801-142">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="f6801-143">Asignar ventanas de tiempo de actualización al sitio.</span><span class="sxs-lookup"><span data-stu-id="f6801-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="f6801-144">Las ventanas hora de actualización de bits y hora de actualización del sistema operativo se configuran por separado.</span><span class="sxs-lookup"><span data-stu-id="f6801-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="f6801-145">Ambos se pueden asignar a una o varias ventanas de tiempo.</span><span class="sxs-lookup"><span data-stu-id="f6801-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="f6801-146">Cada ventana de tiempo se puede asignar a distintos sitios y a diferentes propósitos (actualización de bits y actualización del sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="f6801-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="f6801-147">Ejecute el siguiente cmdlet para establecer el período de tiempo para el sitio:</span><span class="sxs-lookup"><span data-stu-id="f6801-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="f6801-148">Actualizar las credenciales de administrador del espacio dedicado</span><span class="sxs-lookup"><span data-stu-id="f6801-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="f6801-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="f6801-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="f6801-150">Los cambios administrativos en la organización de Office 365 para Cloud Connector se realizan desde una cuenta con los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="f6801-150">Administrative changes in the Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="f6801-151">En la versión de Cloud Connector anterior a 2,0, esa cuenta es una cuenta de administrador de inquilino global dedicada.</span><span class="sxs-lookup"><span data-stu-id="f6801-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="f6801-152">En Cloud Connector versiones 2,0 y posteriores, esa cuenta puede ser una cuenta de Office 365 con derechos de administrador de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="f6801-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="f6801-153">Si las credenciales de la cuenta de administrador cambian en Office 365, también deberá actualizar las credenciales almacenadas en caché local en Cloud Connector mediante la ejecución del siguiente comando de PowerShell de administrador en cada dispositivo de Cloud Connector que haya implementado:</span><span class="sxs-lookup"><span data-stu-id="f6801-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="f6801-154">Actualizar la contraseña del servidor host</span><span class="sxs-lookup"><span data-stu-id="f6801-154">Update the password for the host server</span></span>
<span data-ttu-id="f6801-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="f6801-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="f6801-156">Esta sección se aplica a Cloud Connector versión 2,0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f6801-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="f6801-157">Todas las credenciales de Cloud Connector se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="f6801-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="f6801-158">Cuando cambie la contraseña en el servidor host, tendrá que actualizar las credenciales almacenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="f6801-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="f6801-159">Para actualizar las credenciales almacenadas localmente en el dispositivo de Cloud Connector, use los cmdlets [Get-CcCredential](get-cccredential.md) y [set-CcCredential](set-cccredential.md) y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f6801-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="f6801-160">Ejecute los siguientes comandos para recuperar las contraseñas que necesitará más adelante:</span><span class="sxs-lookup"><span data-stu-id="f6801-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="f6801-161">Get-CcCredential-AccountType-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="f6801-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="f6801-162">Get-CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="f6801-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="f6801-163">Get-CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="f6801-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="f6801-164">Cambie la contraseña de su cuenta en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="f6801-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="f6801-165">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="f6801-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="f6801-166">Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="f6801-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="f6801-167">Inicie una consola de PowerShell como administrador y, después, ejecute "Register-CcAppliance-local" para volver a escribir las contraseñas después de la descripción.</span><span class="sxs-lookup"><span data-stu-id="f6801-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="f6801-168">Asegúrese de escribir la misma contraseña que escribió antes para la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f6801-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="f6801-169">De forma predeterminada, VmAdmin y valor detor usan la misma contraseña que CceService.</span><span class="sxs-lookup"><span data-stu-id="f6801-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="f6801-170">Si las contraseñas del usuario, la VMAdmin y la CceService devueltas en el paso 1 son diferentes, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="f6801-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="f6801-171">Ejecute Set-CcCredential-AccountType preestablecido de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f6801-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="f6801-172">Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="f6801-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="f6801-173">Cuando se le soliciten las credenciales de cuenta nuevas, escriba la contraseña de la contraseña del ID de usuario devuelta en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f6801-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="f6801-174">Ejecute Set-CcCredential-AccountType VmAdmin de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f6801-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="f6801-175">Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="f6801-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="f6801-176">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de VmAdmin devuelta en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f6801-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="f6801-177">Actualizar la contraseña de la cuenta CceService</span><span class="sxs-lookup"><span data-stu-id="f6801-177">Update the password for the CceService account</span></span>
<span data-ttu-id="f6801-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="f6801-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="f6801-179">Esta sección se aplica a Cloud Connector versión 2.0.1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f6801-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="f6801-180">El servicio de Cloud Connector ejecuta el servicio de administración de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f6801-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="f6801-181">La cuenta CceService se crea durante la implementación de Cloud Connector Edition y se almacena en los siguientes archivos: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "y"%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService. xml ".</span><span class="sxs-lookup"><span data-stu-id="f6801-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="f6801-182">Para asegurarse de que todos los dispositivos puedan acceder al directorio compartido de sitios, la contraseña de la cuenta CceService debe ser la misma en todos los dispositivos que se hayan implementado en el sitio.</span><span class="sxs-lookup"><span data-stu-id="f6801-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="f6801-183">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6801-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="f6801-184">De forma predeterminada, la cuenta CceService está configurada como "la contraseña nunca expira".</span><span class="sxs-lookup"><span data-stu-id="f6801-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="f6801-185">Al actualizar la contraseña, Microsoft recomienda conservar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="f6801-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="f6801-186">Debe actualizar la contraseña durante los períodos de uso no máximos y fuera de las ventanas de tiempo de actualización automáticas para bits o actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="f6801-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="f6801-187">Al actualizar la contraseña, el dispositivo debe purgarse y reiniciarse, lo que lleva algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="f6801-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="f6801-188">Si reinicia el dispositivo, se interrumpirán las operaciones de actualización automática.</span><span class="sxs-lookup"><span data-stu-id="f6801-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="f6801-189">Al cambiar la contraseña de la cuenta CceService, tendrá que especificar todas las credenciales y actualizarlas en el archivo almacenado localmente.</span><span class="sxs-lookup"><span data-stu-id="f6801-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="f6801-190">Para cada dispositivo que pertenezca al mismo sitio de RTC, tendrá que especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6801-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="f6801-191">Ejecute los siguientes comandos para recuperar los nombres de cuenta y las contraseñas que usará más adelante:</span><span class="sxs-lookup"><span data-stu-id="f6801-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. <span data-ttu-id="f6801-192">Ejecute el cmdlet Enter-CcUpdate para purgar el dispositivo y moverlo al modo de mantenimiento manual.</span><span class="sxs-lookup"><span data-stu-id="f6801-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="f6801-193">Actualice la contraseña de la cuenta CceService en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="f6801-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="f6801-194">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="f6801-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="f6801-195">Ejecute el cmdlet restore-CcCredentials para volver a escribir las contraseñas a continuación de la descripción.</span><span class="sxs-lookup"><span data-stu-id="f6801-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="f6801-196">Asegúrese de escribir la misma contraseña que escribió antes para la implementación de Cloud Connector, excepto para la cuenta CceService.</span><span class="sxs-lookup"><span data-stu-id="f6801-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="f6801-197">Para la cuenta CceService, escriba la nueva contraseña.</span><span class="sxs-lookup"><span data-stu-id="f6801-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="f6801-198">Asegúrese de que la nueva contraseña de la cuenta CceService es la misma para todos los dispositivos del sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="f6801-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="f6801-199">De forma predeterminada, VmAdmin y valor detor usan la misma contraseña que CceService.</span><span class="sxs-lookup"><span data-stu-id="f6801-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="f6801-200">Si las contraseñas del usuario, la VMAdmin y la CceService devueltas en el paso 1 son diferentes, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="f6801-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="f6801-201">Ejecute Set-CcCredential-AccountType preestablecido de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f6801-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="f6801-202">Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="f6801-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="f6801-203">Cuando se le soliciten las credenciales de cuenta nuevas, escriba la contraseña de la contraseña del ID de usuario devuelta en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f6801-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="f6801-204">Ejecute Set-CcCredential-AccountType VmAdmin de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f6801-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="f6801-205">Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="f6801-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="f6801-206">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de VmAdmin devuelta en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f6801-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="f6801-207">Ejecute el cmdlet Exit-CcUpdate para desplazar el dispositivo fuera del modo de mantenimiento manual.</span><span class="sxs-lookup"><span data-stu-id="f6801-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="f6801-208">Después de completar estos pasos en todos los dispositivos del mismo sitio RTC, elimine los siguientes archivos del directorio raíz del sitio:</span><span class="sxs-lookup"><span data-stu-id="f6801-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="f6801-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="f6801-209">CcLockFile</span></span>
    
    - <span data-ttu-id="f6801-210">FQDN\<del grupo de SIP externo de Site_ perimetral\></span><span class="sxs-lookup"><span data-stu-id="f6801-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="f6801-211">FQDN\<del grupo de SIP externo de Tenant_ perimetral\></span><span class="sxs-lookup"><span data-stu-id="f6801-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="f6801-212">FQDN\<del grupo de SIP externo de TenantConfigLock_ perimetral\></span><span class="sxs-lookup"><span data-stu-id="f6801-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="f6801-213">Adición de un nuevo dominio SIP</span><span class="sxs-lookup"><span data-stu-id="f6801-213">Add a new SIP domain</span></span>
<span data-ttu-id="f6801-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="f6801-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="f6801-215">Para agregar un nuevo dominio SIP (o varios dominios SIP) a la implementación existente de Cloud Connector, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6801-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="f6801-216">Asegúrese de que ha completado los pasos para actualizar el dominio en Office 365 y de que tiene la capacidad de agregar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="f6801-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="f6801-217">Para obtener más información acerca de cómo configurar su dominio en Office 365, consulte [Agregar un dominio a office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="f6801-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="f6801-218">Actualice el archivo de configuración de Cloud Connector con el nuevo dominio o dominios SIP.</span><span class="sxs-lookup"><span data-stu-id="f6801-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="f6801-219">Solicite un nuevo certificado externo perimetral con nombres SAN adicionales para SIP. domain para cada dominio SIP definido en la configuración de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f6801-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="f6801-220">Establezca la ruta de acceso para el nuevo certificado externo perimetral de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f6801-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="f6801-221">Siga las instrucciones para [modificar la configuración de un único sitio](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o [modificar la configuración de varios sitios](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="f6801-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="f6801-222">Modificar el dominio SIP principal</span><span class="sxs-lookup"><span data-stu-id="f6801-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="f6801-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="f6801-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="f6801-224">Si necesita cambiar el dominio SIP principal en su implementación de Cloud Connector, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6801-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="f6801-225">Asegúrese de que ha completado los pasos para actualizar el dominio en Office 365 y de que tiene la capacidad de agregar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="f6801-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="f6801-226">Para obtener más información acerca de cómo configurar su dominio en Office 365, consulte [Agregar un dominio a office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="f6801-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="f6801-227">Actualice el archivo de configuración de Cloud Connector con el nuevo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="f6801-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="f6801-228">Solicite un nuevo certificado externo perimetral con nombres SAN adicionales para SIP. domain para cada dominio SIP definido en la configuración de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f6801-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="f6801-229">Establezca la ruta de acceso para el nuevo certificado externo perimetral de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f6801-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="f6801-230">Quite el registro de inquilino de cada dispositivo en un sitio mediante la ejecución del siguiente cmdlet en el PowerShell del administrador en Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="f6801-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="f6801-231">Quite el registro de sitios para cada sitio mediante la ejecución del siguiente cmdlet en PowerShell de Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="f6801-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="f6801-232">Para desinstalar cada dispositivo, ejecute el siguiente cmdlet en el administrador de PowerShell de Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="f6801-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="f6801-233">Registre cada dispositivo mediante la ejecución del siguiente cmdlet en el PowerShell del administrador en Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="f6801-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="f6801-234">Instale cada dispositivo, uno a uno, mediante la ejecución del siguiente cmdlet en el PowerShell del administrador en Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="f6801-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="f6801-235">Reemplazar el certificado perimetral externo por un certificado nuevo</span><span class="sxs-lookup"><span data-stu-id="f6801-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="f6801-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="f6801-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="f6801-237">Cuando necesite reemplazar el certificado perimetral externo en los dispositivos de Cloud Connector, tendrá que obtener un nuevo certificado perimetral, preparar el archivo PFX que contiene la clave privada y la cadena de certificados completa y, a continuación, hacer lo siguiente en cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="f6801-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="f6801-238">Coloque el dispositivo en modo de mantenimiento mediante el cmdlet Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="f6801-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="f6801-239">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f6801-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="f6801-240">Si la contraseña del nuevo certificado es la misma que la antigua, la importación se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="f6801-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="f6801-241">Si la contraseña es diferente, recibirá un error que le informará de que la contraseña es incorrecta y tendrá que restablecer la contraseña si ejecuta el cmdlet Register-CcAppliance con el parámetro-local y, a continuación, se repite el paso 2.</span><span class="sxs-lookup"><span data-stu-id="f6801-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="f6801-242">Saque el dispositivo del modo de mantenimiento mediante el cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="f6801-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

