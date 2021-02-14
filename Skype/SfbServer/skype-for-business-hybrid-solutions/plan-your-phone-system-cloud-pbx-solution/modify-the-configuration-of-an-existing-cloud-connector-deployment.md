---
title: Modificar la configuración de una implementación de Cloud Connector existente
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
description: Siga los pasos de este tema para modificar la configuración de una implementación existente de Skype Empresarial Cloud Connector Edition 1.4.1 o posterior.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359116"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="72379-103">Modificar la configuración de una implementación de Cloud Connector existente</span><span class="sxs-lookup"><span data-stu-id="72379-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="72379-104">Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="72379-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="72379-105">Una vez que su organización haya actualizado a Teams, obtenga información sobre cómo conectar su red de telefonía local a Teams mediante [el enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="72379-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="72379-106">Siga los pasos de este tema para modificar la configuración de una implementación existente de Skype Empresarial Cloud Connector Edition 1.4.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="72379-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="72379-107">Modificar la configuración de un solo sitio</span><span class="sxs-lookup"><span data-stu-id="72379-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="72379-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="72379-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="72379-109">Si solo hay un dispositivo en el sitio, cuando desee cambiar las opciones de configuración después de implementar el dispositivo, puede modificar el archivo CloudConnector.ini e iniciar la implementación de nuevo.</span><span class="sxs-lookup"><span data-stu-id="72379-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="72379-110">Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el servidor host:</span><span class="sxs-lookup"><span data-stu-id="72379-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="72379-111">Ejecute el siguiente cmdlet para anular el registro del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="72379-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="72379-112">Actualice el CloudConnector.ini en el Directorio de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="72379-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="72379-113">Ejecute el siguiente cmdlet para actualizar la configuración: (Este paso solo es aplicable para la versión 2; para versiones anteriores, vaya al paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="72379-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="72379-114">Ejecute el siguiente cmdlet para volver a registrar el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="72379-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="72379-115">Ejecute el siguiente cmdlet para instalar Skype Empresarial Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="72379-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="72379-116">Si hay más de un dispositivo en el sitio, deberá seguir estos pasos, modificar el archivo CloudConnector.ini y volver a implementar los dispositivos uno por uno.</span><span class="sxs-lookup"><span data-stu-id="72379-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="72379-117">Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el dispositivo actual:</span><span class="sxs-lookup"><span data-stu-id="72379-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="72379-118">Ejecute el siguiente cmdlet para anular el registro del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="72379-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="72379-119">Actualice el CloudConnector.ini en el Directorio de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="72379-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="72379-120">Ejecute el siguiente cmdlet para actualizar la configuración: (Este paso solo es aplicable para la versión 2; para versiones anteriores, vaya al paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="72379-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="72379-121">Ejecute el siguiente cmdlet para volver a registrar el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="72379-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="72379-122">Ejecute el siguiente cmdlet en todos los demás dispositivos del sitio para obtener la configuración más reciente:</span><span class="sxs-lookup"><span data-stu-id="72379-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="72379-123">Ejecute el siguiente cmdlet para volver a implementar Cloud Connector en el dispositivo actual:</span><span class="sxs-lookup"><span data-stu-id="72379-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="72379-124">Modificar la configuración de varios sitios</span><span class="sxs-lookup"><span data-stu-id="72379-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="72379-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="72379-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="72379-126">Para modificar la configuración de varios sitios en una implementación, siga los pasos para un único sitio, actualizando un sitio cada vez.</span><span class="sxs-lookup"><span data-stu-id="72379-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="72379-127">Modificar la configuración de su organización de Microsoft 365 u Office 365 para habilitar las actualizaciones automáticas</span><span class="sxs-lookup"><span data-stu-id="72379-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="72379-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="72379-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="72379-129">Para habilitar las actualizaciones automáticas del sistema operativo y las actualizaciones automáticas de Bits, debe usar la cuenta de administrador de inquilinos de Skype Empresarial para la administración en línea y usar PowerShell remoto de inquilino de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="72379-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="72379-130">Si deshabilitó las actualizaciones automáticas del sistema operativo o las actualizaciones automáticas de Bits, es posible que el host y la máquina virtual pierdan actualizaciones importantes de Windows y Cloud Connector no se actualizará a la nueva versión automáticamente.</span><span class="sxs-lookup"><span data-stu-id="72379-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="72379-131">Se recomienda encarecidamente habilitar las actualizaciones automáticas.</span><span class="sxs-lookup"><span data-stu-id="72379-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="72379-132">La propiedad EnableAutoUpdate del sitio debe establecerse en true (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="72379-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="72379-133">Ejecute el siguiente cmdlet para asegurarse de que EnableAutoUpdate está establecido en true:</span><span class="sxs-lookup"><span data-stu-id="72379-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="72379-134">Cree una ventana de tiempo de actualización automática para el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="72379-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="72379-135">El período de tiempo puede ser diario, semanal y mensual.</span><span class="sxs-lookup"><span data-stu-id="72379-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="72379-136">Todas las ventanas de tiempo necesitan una hora de inicio y una duración.</span><span class="sxs-lookup"><span data-stu-id="72379-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="72379-137">Para una ventana de hora diaria, solo se necesita la hora de inicio y la duración.</span><span class="sxs-lookup"><span data-stu-id="72379-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="72379-138">Para un período de tiempo semanal, se necesitan días de la semana, que pueden ser un solo día o varios días.</span><span class="sxs-lookup"><span data-stu-id="72379-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="72379-139">Para un período de tiempo mensual, puede haber dos tipos.</span><span class="sxs-lookup"><span data-stu-id="72379-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="72379-140">El primer tipo es especificar el día del mes, que puede ser un solo día.</span><span class="sxs-lookup"><span data-stu-id="72379-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="72379-141">El segundo tipo es especificar las semanas del mes, junto con los días de la semana, que pueden ser un solo elemento o varios elementos.</span><span class="sxs-lookup"><span data-stu-id="72379-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="72379-142">Cada inquilino puede tener 20 ventanas definidas.</span><span class="sxs-lookup"><span data-stu-id="72379-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="72379-143">Se creará la ventana de tiempo predeterminada para un nuevo inquilino como la ventana de tiempo predeterminada para la actualización del sistema operativo y la actualización de Bits.</span><span class="sxs-lookup"><span data-stu-id="72379-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="72379-144">Ejecute los cmdlets siguientes para establecer la ventana de tiempo diaria, semanal o mensual:</span><span class="sxs-lookup"><span data-stu-id="72379-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="72379-145">Asignar ventanas de tiempo de actualización al sitio.</span><span class="sxs-lookup"><span data-stu-id="72379-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="72379-146">El tiempo de actualización de Bits y las ventanas de tiempo de actualización del sistema operativo se configuran por separado.</span><span class="sxs-lookup"><span data-stu-id="72379-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="72379-147">A ambos se les puede asignar una o varias ventanas de tiempo.</span><span class="sxs-lookup"><span data-stu-id="72379-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="72379-148">Cada ventana de tiempo se puede asignar a diferentes sitios y finalidades diferentes (actualización de bits y actualización del sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="72379-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="72379-149">Ejecute el siguiente cmdlet para establecer la ventana de tiempo para el sitio:</span><span class="sxs-lookup"><span data-stu-id="72379-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="72379-150">Actualizar las credenciales de administrador de inquilinos dedicadas</span><span class="sxs-lookup"><span data-stu-id="72379-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="72379-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="72379-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="72379-152">Los cambios administrativos en la organización de Microsoft 365 u Office 365 para Cloud Connector se realizan desde una cuenta con los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="72379-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="72379-153">En las versiones de Cloud Connector anteriores a la 2.0, esa cuenta es una cuenta de administrador de inquilinos global dedicada.</span><span class="sxs-lookup"><span data-stu-id="72379-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="72379-154">En Cloud Connector versión 2.0 y versiones posteriores, esa cuenta puede ser una cuenta de Microsoft 365 u Office 365 con derechos de administrador de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="72379-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="72379-155">Si las credenciales de la cuenta de administrador cambian en Microsoft 365 u Office 365, también debe actualizar las credenciales almacenadas localmente en caché en Cloud Connector ejecutando el siguiente comando de PowerShell de administrador en cada dispositivo de Cloud Connector que haya implementado:</span><span class="sxs-lookup"><span data-stu-id="72379-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="72379-156">Actualizar la contraseña del servidor host</span><span class="sxs-lookup"><span data-stu-id="72379-156">Update the password for the host server</span></span>
<span data-ttu-id="72379-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="72379-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="72379-158">Esta sección es aplicable a Cloud Connector versión 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="72379-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="72379-159">Todas las credenciales de Cloud Connector se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".</span><span class="sxs-lookup"><span data-stu-id="72379-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="72379-160">Cuando cambie la contraseña del servidor host, deberá actualizar las credenciales almacenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="72379-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="72379-161">Para actualizar las credenciales almacenadas localmente en el dispositivo de Cloud Connector, use los cmdlets [Get-CcCredential](get-cccredential.md) y [Set-CcCredential](set-cccredential.md) y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="72379-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="72379-162">Ejecute los siguientes comandos para recuperar las contraseñas que necesitará más adelante:</span><span class="sxs-lookup"><span data-stu-id="72379-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="72379-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="72379-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="72379-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="72379-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="72379-165">Get-CcCredential -AccountType CceService -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="72379-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="72379-166">Cambie la contraseña de su cuenta en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="72379-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="72379-167">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="72379-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="72379-168">Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".</span><span class="sxs-lookup"><span data-stu-id="72379-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="72379-169">Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance -Local" para volver a escribir las contraseñas después de la descripción.</span><span class="sxs-lookup"><span data-stu-id="72379-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="72379-170">Asegúrese de escribir la misma contraseña que escribió antes para la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="72379-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="72379-171">De forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService.</span><span class="sxs-lookup"><span data-stu-id="72379-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="72379-172">Si las contraseñas domainAdmin, VMAdmin y CceService devueltas en el paso 1 son diferentes, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="72379-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="72379-173">Ejecute Set-CcCredential -AccountType DomainAdmin de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="72379-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="72379-174">Cuando se le solicite la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="72379-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="72379-175">Cuando se le solicite la credencial de la nueva cuenta, escriba la contraseña de la contraseña de DomainAdmin devuelta en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="72379-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="72379-176">Ejecute Set-CcCredential -AccountType VmAdmin de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="72379-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="72379-177">Cuando se le solicite la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="72379-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="72379-178">Cuando se le solicite la nueva credencial de cuenta, escriba la contraseña de la contraseña de VmAdmin devuelta en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="72379-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="72379-179">Actualizar la contraseña de la cuenta CceService</span><span class="sxs-lookup"><span data-stu-id="72379-179">Update the password for the CceService account</span></span>
<span data-ttu-id="72379-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="72379-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="72379-181">Esta sección es aplicable a Cloud Connector versión 2.0.1 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="72379-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="72379-182">El servicio de Cloud Connector ejecuta el servicio de administración de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="72379-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="72379-183">La cuenta CceService se crea durante la implementación de Cloud Connector Edition y se almacena en los siguientes archivos: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" y "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span><span class="sxs-lookup"><span data-stu-id="72379-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="72379-184">Para garantizar que todos los dispositivos puedan tener acceso al recurso compartido del directorio de sitios, la contraseña de la cuenta CceService debe ser la misma en todos los dispositivos implementados en el sitio.</span><span class="sxs-lookup"><span data-stu-id="72379-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="72379-185">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72379-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="72379-186">De forma predeterminada, la cuenta CceService está configurada como "La contraseña nunca expira".</span><span class="sxs-lookup"><span data-stu-id="72379-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="72379-187">Al actualizar la contraseña, Microsoft recomienda mantener esta configuración.</span><span class="sxs-lookup"><span data-stu-id="72379-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="72379-188">Debes actualizar la contraseña durante períodos de uso no pico y fuera de las ventanas de tiempo de actualización automática para bits o actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="72379-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="72379-189">Al actualizar la contraseña, el dispositivo debe purgarse y reiniciarse, lo que lleva algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="72379-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="72379-190">El reinicio del dispositivo interrumpirá las operaciones de actualización automática.</span><span class="sxs-lookup"><span data-stu-id="72379-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="72379-191">Al cambiar la contraseña de la cuenta CceService, deberá especificar todas las credenciales y actualizarlas en el archivo almacenado localmente.</span><span class="sxs-lookup"><span data-stu-id="72379-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="72379-192">Para cada dispositivo que pertenece al mismo sitio RTC, deberá especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72379-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="72379-193">Ejecute los siguientes comandos para recuperar los nombres de cuenta y contraseñas que usará más adelante:</span><span class="sxs-lookup"><span data-stu-id="72379-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="72379-194">Ejecute el cmdlet Enter-CcUpdate para purgar el dispositivo y moverlo al modo de mantenimiento manual.</span><span class="sxs-lookup"><span data-stu-id="72379-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="72379-195">Actualice la contraseña de la cuenta CceService en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="72379-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="72379-196">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="72379-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="72379-197">Ejecute el cmdlet Restore-CcCredentials para volver a escribir las contraseñas después de la descripción.</span><span class="sxs-lookup"><span data-stu-id="72379-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="72379-198">Asegúrese de escribir la misma contraseña que escribió antes para la implementación de Cloud Connector excepto para la cuenta de CceService.</span><span class="sxs-lookup"><span data-stu-id="72379-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="72379-199">Para la cuenta de CceService, escriba la nueva contraseña.</span><span class="sxs-lookup"><span data-stu-id="72379-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="72379-200">Asegúrese de que la nueva contraseña de la cuenta CceService sea la misma para todos los dispositivos del sitio RTC.</span><span class="sxs-lookup"><span data-stu-id="72379-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="72379-201">De forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService.</span><span class="sxs-lookup"><span data-stu-id="72379-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="72379-202">Si las contraseñas domainAdmin, VMAdmin y CceService devueltas en el paso 1 son diferentes, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="72379-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="72379-203">Ejecute Set-CcCredential -AccountType DomainAdmin de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="72379-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="72379-204">Cuando se le solicite la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="72379-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="72379-205">Cuando se le solicite la credencial de la nueva cuenta, escriba la contraseña de la contraseña de DomainAdmin devuelta en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="72379-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="72379-206">Ejecute Set-CcCredential -AccountType VmAdmin de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="72379-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="72379-207">Cuando se le solicite la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="72379-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="72379-208">Cuando se le solicite la nueva credencial de cuenta, escriba la contraseña de la contraseña de VmAdmin devuelta en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="72379-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="72379-209">Ejecute el cmdlet Exit-CcUpdate para sacar el dispositivo del modo de mantenimiento manual.</span><span class="sxs-lookup"><span data-stu-id="72379-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="72379-210">Después de completar estos pasos en todos los dispositivos del mismo sitio RTC, elimine los siguientes archivos en el directorio raíz del sitio:</span><span class="sxs-lookup"><span data-stu-id="72379-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="72379-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="72379-211">CcLockFile</span></span>
    
    - <span data-ttu-id="72379-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="72379-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="72379-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="72379-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="72379-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="72379-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="72379-215">Agregar un nuevo dominio SIP</span><span class="sxs-lookup"><span data-stu-id="72379-215">Add a new SIP domain</span></span>
<span data-ttu-id="72379-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="72379-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="72379-217">Para agregar un nuevo dominio SIP (o varios dominios SIP) a la implementación existente de Cloud Connector, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72379-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="72379-218">Asegúrese de que ha completado los pasos para actualizar su dominio en Microsoft 365 u Office 365 y tiene la capacidad de agregar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="72379-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="72379-219">Para obtener más información acerca de cómo configurar su dominio en Microsoft 365 u Office 365, vea Agregar un dominio [a Microsoft 365 u Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="72379-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="72379-220">Actualice el archivo de configuración de Cloud Connector con los nuevos dominios o dominios SIP.</span><span class="sxs-lookup"><span data-stu-id="72379-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="72379-221">Solicite un nuevo certificado externo perimetral con nombres SAN adicionales para sip.domain para cada dominio SIP definido en la configuración de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="72379-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="72379-222">Establezca la ruta de acceso para el nuevo certificado externo perimetral de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="72379-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="72379-223">Siga las instrucciones para [modificar la configuración de un único sitio](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o modificar la configuración de varios [sitios.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)</span><span class="sxs-lookup"><span data-stu-id="72379-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="72379-224">Modificar el dominio SIP principal</span><span class="sxs-lookup"><span data-stu-id="72379-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="72379-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="72379-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="72379-226">Si necesita cambiar el dominio SIP principal en la implementación de Cloud Connector, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72379-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="72379-227">Asegúrese de que ha completado los pasos para actualizar su dominio en Microsoft 365 u Office 365 y tiene la capacidad de agregar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="72379-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="72379-228">Para obtener más información acerca de cómo configurar su dominio en Microsoft 365 u Office 365, vea Agregar un dominio [a Microsoft 365 u Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="72379-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="72379-229">Actualice el archivo de configuración de Cloud Connector con el nuevo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="72379-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="72379-230">Solicite un nuevo certificado externo perimetral con nombres SAN adicionales para sip.domain para cada dominio SIP definido en la configuración de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="72379-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="72379-231">Establezca la ruta de acceso para el nuevo certificado externo perimetral de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="72379-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="72379-232">Quite el registro de inquilino para cada dispositivo de un sitio ejecutando el siguiente cmdlet en el administrador de PowerShell en Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="72379-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="72379-233">Quite el registro del sitio para cada sitio ejecutando el siguiente cmdlet en PowerShell de Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="72379-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="72379-234">Desinstale cada dispositivo ejecutando el siguiente cmdlet en el Administrador de PowerShell en Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="72379-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="72379-235">Registre cada dispositivo ejecutando el siguiente cmdlet en el Administrador de PowerShell en Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="72379-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="72379-236">Instale cada dispositivo, uno a uno, ejecutando el siguiente cmdlet en el administrador de PowerShell en Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="72379-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="72379-237">Reemplazar el certificado perimetral externo con un certificado nuevo</span><span class="sxs-lookup"><span data-stu-id="72379-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="72379-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="72379-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="72379-239">Cuando necesite reemplazar el certificado perimetral externo en los dispositivos de Cloud Connector, deberá obtener un nuevo certificado perimetral, preparar el archivo PFX que contiene la clave privada y la cadena de certificados completa y, a continuación, hacer lo siguiente en cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="72379-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="72379-240">Ponga el dispositivo en modo de mantenimiento mediante el cmdlet Enter-CcUpdate de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="72379-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="72379-241">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="72379-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="72379-242">Si la contraseña del nuevo certificado es la misma que la anterior, la importación se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="72379-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="72379-243">Si la contraseña es diferente, recibirá un error de que la contraseña es incorrecta y tendrá que restablecerla ejecutando el cmdlet Register-CcAppliance con el parámetro -Local y, a continuación, repitiendo el paso 2.</span><span class="sxs-lookup"><span data-stu-id="72379-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="72379-244">Sacar el dispositivo del modo de mantenimiento mediante el cmdlet Exit -CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="72379-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

