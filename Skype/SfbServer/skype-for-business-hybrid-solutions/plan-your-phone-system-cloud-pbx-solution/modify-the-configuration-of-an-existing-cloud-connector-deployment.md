---
title: Modificar la configuración de una implementación de Cloud Connector existente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Siga los pasos descritos en este tema para modificar la configuración de un Skype existente de conector de nube de Business Edition 1.4.1 o implementación posterior.
ms.openlocfilehash: be3c7cbbc1395000dbb84bab0c9be0a866fb4403
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375375"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="8cfb2-103">Modificar la configuración de una implementación de Cloud Connector existente</span><span class="sxs-lookup"><span data-stu-id="8cfb2-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="8cfb2-104">Siga los pasos descritos en este tema para modificar la configuración de un Skype existente de conector de nube de Business Edition 1.4.1 o implementación posterior.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="8cfb2-105">Modificar la configuración de un único sitio</span><span class="sxs-lookup"><span data-stu-id="8cfb2-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="8cfb2-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="8cfb2-106"></span></span>

<span data-ttu-id="8cfb2-107">Si solo hay una aplicación en el sitio, cuando desee cambiar la configuración después de haber implementado la aplicación, puede modificar el archivo CloudConnector.ini e iniciar la implementación de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="8cfb2-108">Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el servidor host: </span><span class="sxs-lookup"><span data-stu-id="8cfb2-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="8cfb2-109">Ejecute el siguiente cmdlet para anular el registro del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="8cfb2-110">Actualice el archivo CloudConnector.ini en el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="8cfb2-111">Ejecute el cmdlet siguiente para actualizar la configuración: (este paso sólo es aplicable para la versión 2; para las versiones anteriores, vaya al paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="8cfb2-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="8cfb2-112">Ejecute el siguiente cmdlet para volver a registrar el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```
   Register-CcAppliance
   ```

6. <span data-ttu-id="8cfb2-113">Ejecute el siguiente cmdlet para instalar Skype Empresarial Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```
   Install-CcAppliance
   ```

<span data-ttu-id="8cfb2-114">Si hay más de un dispositivo en el sitio, tendrá que seguir estos pasos, modificar el archivo CloudConnector.ini y volver a implementar los dispositivos uno a uno.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="8cfb2-115">Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el dispositivo actual:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="8cfb2-116">Ejecute el siguiente cmdlet para anular el registro del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="8cfb2-117">Actualice el archivo CloudConnector.ini en el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="8cfb2-118">Ejecute el cmdlet siguiente para actualizar la configuración: (este paso sólo es aplicable para la versión 2; para las versiones anteriores, vaya al paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="8cfb2-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="8cfb2-119">Ejecute el siguiente cmdlet para volver a registrar el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```
   Register-CcAppliance
   ```

6. <span data-ttu-id="8cfb2-120">Ejecute el siguiente cmdlet en todos los demás dispositivos del sitio para recoger la última configuración:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```
   Publish-CcAppliance
   ```

7. <span data-ttu-id="8cfb2-121">Ejecute el cmdlet siguiente para volver a implementar el conector de nube en el dispositivo actual:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="8cfb2-122">Modificar la configuración de varios sitios</span><span class="sxs-lookup"><span data-stu-id="8cfb2-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="8cfb2-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="8cfb2-123"></span></span>

<span data-ttu-id="8cfb2-124">Para modificar la configuración para varios sitios en una implementación, siga los pasos de un solo sitio, actualizar un sitio a la vez.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="8cfb2-125">Modificar la configuración de su inquilino de Office 365 para habilitar las actualizaciones automáticas</span><span class="sxs-lookup"><span data-stu-id="8cfb2-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="8cfb2-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="8cfb2-126"></span></span>

<span data-ttu-id="8cfb2-127">Para habilitar las actualizaciones automáticas de sistema operativo y las actualizaciones automáticas de Bits, debe usar el Skype para la cuenta de administrador de inquilinos empresarial para la administración en línea y usar PowerShell remoto de inquilinos como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="8cfb2-128">Si deshabilita las actualizaciones automáticas de sistema operativo o las actualizaciones automáticas de Bits, el host y la máquina virtual es posible que se pierda importantes actualizaciones de Windows y en la nube conector no se actualiza automáticamente a la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="8cfb2-129">Las actualizaciones automáticas son altamente recomendables.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="8cfb2-130">La propiedad EnableAutoUpdate del sitio debe establecerse en true (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="8cfb2-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="8cfb2-131">Ejecute el siguiente cmdlet para asegurarse de que EnableAutoUpdate esté establecida en true:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="8cfb2-132">Cree un intervalo de actualización automática para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="8cfb2-p103">El intervalo de tiempo puede ser diario, semanal o mensual. En todos los casos se necesita una hora de inicio y una duración.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-p103">The time window can be daily, weekly and monthly. All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="8cfb2-135">Para los intervalos diarios, solo se necesita la hora de inicio y la duración. </span><span class="sxs-lookup"><span data-stu-id="8cfb2-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="8cfb2-136">Para los intervalos semanales, se necesitan los días de la semana, que pueden ser un solo día o varios días.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="8cfb2-p104">Los intervalos mensuales pueden ser de dos tipos. El primer tipo consiste en especificar un día del mes, que puede ser un solo día. El segunda tipo consiste en especificar las semanas del mes, junto con los días de la semana. Ambos elementos pueden ser únicos o múltiples.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-p104">For a monthly time window, there can be two types. The first type is to specify the day of the month, which can be a single day. The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="8cfb2-p105">Cada inquilino puede tener 20 intervalos definidos. El intervalo predeterminado se creará para un nuevo inquilino como intervalo predeterminado para actualizaciones del sistema operativo y de Bits. Ejecute los siguientes cmdlets para establecer un intervalo diario, semanal o mensual:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-p105">Each tenant can have 20 time windows defined. The default time window will be created for a new tenant as the default time window for operating system update and Bits update. Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="8cfb2-143">Asignar tiempo de actualización de windows para el sitio.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="8cfb2-144">Los intervalos de actualización de Bits y del sistema operativo se configuran por separado.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="8cfb2-145">A ambos se les puede asignar un solo intervalo o varios.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="8cfb2-146">Además, cada intervalo se puede asignar a distintos sitios y distintos fines (actualización de Bits o del sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="8cfb2-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="8cfb2-147">Ejecute el cmdlet siguiente para establecer la ventana de tiempo para el sitio:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="8cfb2-148">Actualizar las credenciales de administrador de inquilinos dedicado </span><span class="sxs-lookup"><span data-stu-id="8cfb2-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="8cfb2-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="8cfb2-149"></span></span>

<span data-ttu-id="8cfb2-150">Se realizan cambios administrativos en el inquilino de Office 365 para el conector de nube desde una cuenta con los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="8cfb2-151">En las versiones de conector en la nube antes de 2.0, esa cuenta es una cuenta de administrador de inquilinos global dedicado.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="8cfb2-152">En las versiones 2.0 y versiones posteriores de conector en la nube, esa cuenta puede ser una cuenta de Office 365 con Skype para derechos de administrador empresarial.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="8cfb2-153">Si cambian sus credenciales de cuenta de administrador en Office 365, debe actualizar las credenciales en caché local en la nube Connector ejecutando el siguiente comando de PowerShell de administrador en cada dispositivo de conector en la nube que haya implementado:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="8cfb2-154">Actualizar la contraseña del servidor host </span><span class="sxs-lookup"><span data-stu-id="8cfb2-154">Update the password for the host server</span></span>
<span data-ttu-id="8cfb2-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="8cfb2-155"></span></span>

> [!NOTE]
> <span data-ttu-id="8cfb2-156">En esta sección es aplicable a la versión 2.0 de conector en la nube y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="8cfb2-157">Todas las credenciales del conector en la nube se almacenan en el siguiente archivo: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".</span><span class="sxs-lookup"><span data-stu-id="8cfb2-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="8cfb2-158">Cuando se cambia la contraseña en el servidor de host, debe actualizar las credenciales almacenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="8cfb2-159">Para actualizar las credenciales almacenadas localmente en el dispositivo de conector en la nube, use los cmdlets [Get-CcCredential](get-cccredential.md) y [Set-CcCredential](set-cccredential.md) y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="8cfb2-160">Ejecute los siguientes comandos para recuperar las contraseñas que necesitará más adelante:  </span><span class="sxs-lookup"><span data-stu-id="8cfb2-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="8cfb2-161">Get-CcCredential - AccountType del administrador del dominio - DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="8cfb2-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="8cfb2-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="8cfb2-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="8cfb2-163">Get-CcCredential - AccountType CceService - DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="8cfb2-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="8cfb2-164">Cambie la contraseña de su cuenta en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="8cfb2-165">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="8cfb2-166">Elimine el archivo siguiente: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".</span><span class="sxs-lookup"><span data-stu-id="8cfb2-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="8cfb2-167">Iniciar una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-Local" para volver a escribir las contraseñas que sigue a la descripción.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="8cfb2-168">Asegúrese de que escribir la misma contraseña que escribió antes de la implementación del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="8cfb2-p110">De forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService. Si las contraseñas de DomainAdmin, VMAdmin y CceService que se devolvieron en el paso 1 son diferentes, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-p110">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="8cfb2-171">Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="8cfb2-172">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="8cfb2-173">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña que devolvió la contraseña de DomainAdmin en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="8cfb2-174">Ejecute Set-CcCredential -AccountType VmAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="8cfb2-175">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="8cfb2-176">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña que devolvió la contraseña de VmAdmin en el paso 1. </span><span class="sxs-lookup"><span data-stu-id="8cfb2-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="8cfb2-177">Actualizar la contraseña de la cuenta de CceService</span><span class="sxs-lookup"><span data-stu-id="8cfb2-177">Update the password for the CceService account</span></span>
<span data-ttu-id="8cfb2-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="8cfb2-178"></span></span>

> [!NOTE]
> <span data-ttu-id="8cfb2-179">En esta sección es aplicable a la versión 2.0.1 de conector en la nube y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="8cfb2-180">El servicio de conector en la nube ejecuta el servicio de administración del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="8cfb2-181">La cuenta de CceService se creados durante la implementación en la nube conector Edition y se almacena en los siguientes archivos: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml "y"% SystemDrive%\Programdata\Cloudconnector\credentials... CceService.xml".</span><span class="sxs-lookup"><span data-stu-id="8cfb2-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="8cfb2-182">Para asegurarse de que todos los dispositivos pueden obtener acceso el recurso compartido de directorio de sitios, la contraseña de la cuenta de CceService debe ser el mismo en todos los dispositivos que se implementan en el sitio.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="8cfb2-183">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="8cfb2-184">De forma predeterminada, la cuenta de CceService se configura como "La contraseña nunca caduca".</span><span class="sxs-lookup"><span data-stu-id="8cfb2-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="8cfb2-185">Al actualizar la contraseña, Microsoft recomienda mantener esta configuración.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="8cfb2-186">Debe actualizar la contraseña durante períodos de uso máximo que no sean internos y externos a las ventanas de tiempo de actualización automática para bits o actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="8cfb2-187">Al actualizar la contraseña, el dispositivo debe vaciar y reiniciar, que tarda algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="8cfb2-188">Reiniciar el dispositivo se interrumpen las operaciones de actualización automática.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="8cfb2-189">Cuando se cambia la contraseña de la cuenta CceService, debe especificar todas las credenciales y actualizarlos en el archivo almacenado localmente.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="8cfb2-190">Para cada dispositivo que pertenece al mismo sitio de RTC, debe especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="8cfb2-191">Ejecute los comandos siguientes para recuperar los nombres de cuenta y contraseñas que va a usar más adelante:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```
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

2. <span data-ttu-id="8cfb2-192">Ejecute el cmdlet de entrar CcUpdate para purgar el dispositivo y mover en modo de mantenimiento manual.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="8cfb2-193">Actualizar la contraseña de la cuenta de CceService en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="8cfb2-194">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="8cfb2-195">Ejecute el cmdlet Restore-CcCredentials para volver a escribir las contraseñas que sigue a la descripción.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="8cfb2-196">Asegúrese de que escribir la misma contraseña que escribió antes de la implementación de nube conector excepto para la cuenta de CceService.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="8cfb2-197">Para la cuenta de CceService, escriba la nueva contraseña.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="8cfb2-198">Asegúrese de que la nueva contraseña para la cuenta de CceService es el mismo para todos los dispositivos en el sitio de RTC.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="8cfb2-p116">De forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService. Si las contraseñas de DomainAdmin, VMAdmin y CceService que se devolvieron en el paso 1 son diferentes, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-p116">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="8cfb2-201">Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="8cfb2-202">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="8cfb2-203">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña que devolvió la contraseña de DomainAdmin en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="8cfb2-204">Ejecute Set-CcCredential -AccountType VmAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="8cfb2-205">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="8cfb2-206">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña que devolvió la contraseña de VmAdmin en el paso 1. </span><span class="sxs-lookup"><span data-stu-id="8cfb2-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="8cfb2-207">Ejecute el cmdlet de Exit CcUpdate para mover el dispositivo del modo de mantenimiento manual.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="8cfb2-208">Después de completar estos pasos en todos los dispositivos en el mismo sitio de RTC, elimine los archivos siguientes en el directorio raíz del sitio:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="8cfb2-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="8cfb2-209">CcLockFile</span></span>
    
    - <span data-ttu-id="8cfb2-210">Site_\<fqdn del grupo de servidores Sip externo perimetrales\></span><span class="sxs-lookup"><span data-stu-id="8cfb2-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="8cfb2-211">Tenant_\<fqdn del grupo de servidores Sip externo perimetrales\></span><span class="sxs-lookup"><span data-stu-id="8cfb2-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="8cfb2-212">TenantConfigLock_\<fqdn del grupo de servidores Sip externo perimetrales\></span><span class="sxs-lookup"><span data-stu-id="8cfb2-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="8cfb2-213">Agregar un nuevo dominio SIP </span><span class="sxs-lookup"><span data-stu-id="8cfb2-213">Add a new SIP domain</span></span>
<span data-ttu-id="8cfb2-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="8cfb2-214"></span></span>

<span data-ttu-id="8cfb2-215">Para agregar un nuevo dominio SIP (o varios dominios SIP) a la implementación existente de conector en la nube, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="8cfb2-216">Asegúrese de que haya completado los pasos para actualizar su dominio en Office 365 y tienen la capacidad de agregar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="8cfb2-217">Para obtener más información acerca de cómo configurar el dominio en Office 365, vea [Agregar un dominio a Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="8cfb2-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="8cfb2-218">Actualizar el archivo de configuración del conector en la nube con el nuevo dominio SIP o dominios.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="8cfb2-219">Solicitar un nuevo certificado externo de borde con nombres de SAN adicionales para SIP.dominio para cada dominio SIP definido en la configuración del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="8cfb2-220">Establezca la ruta de acceso del nuevo certificado perimetral externo como sigue:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="8cfb2-221">Siga las instrucciones de [Modificar la configuración de un único sitio](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o [Modificar la configuración de varios sitios](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="8cfb2-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="8cfb2-222">Modificar el dominio SIP principal</span><span class="sxs-lookup"><span data-stu-id="8cfb2-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="8cfb2-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="8cfb2-223"></span></span>

<span data-ttu-id="8cfb2-224">Si necesita cambiar el dominio SIP principal en la implementación del conector de la nube, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="8cfb2-225">Asegúrese de que haya completado los pasos para actualizar su dominio en Office 365 y tienen la capacidad de agregar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="8cfb2-226">Para obtener más información acerca de cómo configurar el dominio en Office 365, vea [Agregar un dominio a Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="8cfb2-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="8cfb2-227">Actualice el archivo de configuración del conector en la nube con el nuevo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="8cfb2-228">Solicitar un nuevo certificado externo de borde con nombres de SAN adicionales para SIP.dominio para cada dominio SIP definido en la configuración del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="8cfb2-229">Establezca la ruta de acceso del nuevo certificado perimetral externo como sigue:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="8cfb2-230">Quitar el registro del inquilino para cada dispositivo en un sitio ejecutando el siguiente cmdlet en Administrador de PowerShell en la nube conector:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="8cfb2-231">Quite el registro de sitios para cada sitio mediante la ejecución del siguiente cmdlet en el PowerShell de Skype Empresarial Online :

</span><span class="sxs-lookup"><span data-stu-id="8cfb2-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="8cfb2-232">Desinstalación de cada dispositivo ejecutando el siguiente cmdlet en Administrador de PowerShell en la nube conector:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="8cfb2-233">Registrar cada dispositivo ejecutando el siguiente cmdlet en Administrador de PowerShell en la nube conector:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="8cfb2-234">Instalar cada dispositivo, uno por uno, ejecutando el siguiente cmdlet en Administrador de PowerShell en la nube conector:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="8cfb2-235">Reemplazar el certificado externo del borde con un nuevo certificado</span><span class="sxs-lookup"><span data-stu-id="8cfb2-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="8cfb2-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="8cfb2-236"></span></span>

<span data-ttu-id="8cfb2-237">Cuando se necesita reemplazar el certificado externo del borde en los dispositivos de conector en la nube, debe obtener un nuevo certificado de servidor perimetral, preparar el archivo PFX que contiene la clave privada y la cadena de certificados completa y, a continuación, realice lo siguiente en cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="8cfb2-238">Coloque el dispositivo en modo de mantenimiento mediante el cmdlet ENTRAR CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="8cfb2-239">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="8cfb2-239">Run the following command:</span></span> 
    
   ```
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="8cfb2-240">Si la contraseña del certificado nuevo es el mismo que el anterior, la importación se completará correctamente.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="8cfb2-241">Si la contraseña es diferente, recibirá un error que la contraseña es incorrecta, y tendrá que restablecer la contraseña ejecutando el cmdlet Register-CcAppliance con el parámetro - Local, y de repetición, a continuación, el paso 2.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="8cfb2-242">Tomar el dispositivo del modo de mantenimiento mediante el cmdlet Exit - CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="8cfb2-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

