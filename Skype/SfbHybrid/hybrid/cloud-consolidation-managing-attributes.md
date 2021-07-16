---
title: Decidir cómo administrar atributos después del desmantelamiento
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: En este artículo se describe cómo administrar atributos después de retirar el entorno local.
ms.openlocfilehash: 1c862e8c0055fc2eb40efcc7d26bb9a1166ae550
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53459008"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a><span data-ttu-id="42ae5-103">Decidir cómo administrar atributos después del desmantelamiento</span><span class="sxs-lookup"><span data-stu-id="42ae5-103">Decide how to manage attributes after decommissioning</span></span>

<span data-ttu-id="42ae5-104">De forma predeterminada, todos los usuarios que se habilitaron anteriormente para Skype Empresarial Server y posteriormente se movieron a la nube todavía tienen atributos msRTCSIP configurados en active directory local.</span><span class="sxs-lookup"><span data-stu-id="42ae5-104">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> 

<span data-ttu-id="42ae5-105">Estos atributos, en particular la dirección sip (msRTCSIP-PrimaryUserAddress) y el número de teléfono potencialmente (msRTCSIP-Line), siguen sincroniciendo en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="42ae5-105">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="42ae5-106">Si se requieren cambios en cualquiera de los atributos msRTCSIP, estos cambios deben realizarse en Active Directory local y, a continuación, sincronizarse con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="42ae5-106">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="42ae5-107">Sin embargo, una vez Skype Empresarial Server implementación, las herramientas Skype Empresarial Server no estarán disponibles para administrar estos atributos.</span><span class="sxs-lookup"><span data-stu-id="42ae5-107">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="42ae5-108">Hay dos opciones disponibles para controlar esta situación:</span><span class="sxs-lookup"><span data-stu-id="42ae5-108">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="42ae5-109">Deje los usuarios habilitados para Skype Empresarial cuentas de servidor tal y como está y administre los atributos msRTCSIP con herramientas de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42ae5-109">Leave users that were enabled for Skype for Business server accounts as is, and manage the msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="42ae5-110">Esto garantiza que no se pierda el servicio para los usuarios migrados y le permite quitar fácilmente la implementación de Skype Empresarial Server eliminando (por ejemplo, limpiando) los servidores, sin un desmantelamiento completo.</span><span class="sxs-lookup"><span data-stu-id="42ae5-110">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="42ae5-111">Sin embargo, los usuarios recién con licencia no tendrán estos atributos rellenados en su Active Directory local y tendrán que administrarse en línea.</span><span class="sxs-lookup"><span data-stu-id="42ae5-111">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="42ae5-112">Borre todos los atributos msRTCSIP de los usuarios migrados en su Active Directory local y administre estos atributos con herramientas en línea.</span><span class="sxs-lookup"><span data-stu-id="42ae5-112">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="42ae5-113">Este método permite un enfoque de administración coherente para los usuarios existentes y nuevos, pero puede provocar una pérdida temporal del servicio durante el proceso de retirada local.</span><span class="sxs-lookup"><span data-stu-id="42ae5-113">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="42ae5-114">Método 1: administrar direcciones sip y números de teléfono para usuarios de Active Directory</span><span class="sxs-lookup"><span data-stu-id="42ae5-114">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="42ae5-115">Los administradores pueden administrar usuarios que se movieron previamente de un Skype Empresarial Server local a la nube, incluso después de retirar la implementación local.</span><span class="sxs-lookup"><span data-stu-id="42ae5-115">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> 

<span data-ttu-id="42ae5-116">Si desea realizar cambios en la dirección sip de un usuario o en el número de teléfono de un usuario (y la dirección sip o el número de teléfono ya tiene un valor en Active Directory local), debe hacerlo en Active Directory local y permitir que los valores fluyan hasta Azure AD.</span><span class="sxs-lookup"><span data-stu-id="42ae5-116">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="42ae5-117">Esto NO requiere una instalación local Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="42ae5-117">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="42ae5-118">En su lugar, puede modificar estos atributos directamente en Active Directory local, mediante el complemento MMC usuarios y equipos de Active Directory (como se muestra a continuación) o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42ae5-118">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="42ae5-119">Si usa el complemento MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque los atributos adecuados para modificar:</span><span class="sxs-lookup"><span data-stu-id="42ae5-119">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="42ae5-120">Para modificar la dirección sip de un usuario, modifique `msRTCSIP-PrimaryUserAddress` el archivo .</span><span class="sxs-lookup"><span data-stu-id="42ae5-120">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="42ae5-121">Si el `ProxyAddresses` atributo contiene una dirección SIP, actualice también ese valor como procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="42ae5-121">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="42ae5-122">Aunque O365 omite la dirección sip si está rellenada, otros componentes locales pueden `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` usarla.</span><span class="sxs-lookup"><span data-stu-id="42ae5-122">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="42ae5-123">Para modificar el número de teléfono de un usuario, modifique `msRTCSIP-Line` *si ya tiene un valor*.</span><span class="sxs-lookup"><span data-stu-id="42ae5-123">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Herramienta de equipos y usuarios de Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="42ae5-125">Si el usuario no tenía originalmente un valor para local antes del movimiento, puede modificar el número de teléfono mediante el parámetro - en el `msRTCSIP-Line` `onpremLineUri` cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) en el módulo de PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="42ae5-125">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="42ae5-126">Estos pasos no son necesarios para los nuevos usuarios creados después de deshabilitar híbridos y esos usuarios se pueden administrar directamente en la nube.</span><span class="sxs-lookup"><span data-stu-id="42ae5-126">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="42ae5-127">Si se siente cómodo con la combinación de estos métodos, así como con dejar los atributos msRTCSIP en su Active Directory local, simplemente puede volver a crear una imagen de los servidores Skype Empresarial locales.</span><span class="sxs-lookup"><span data-stu-id="42ae5-127">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="42ae5-128">Sin embargo, si prefiere borrar todos los atributos msRTCSIP y realizar una desinstalación tradicional de Skype Empresarial Server, use el método 2.</span><span class="sxs-lookup"><span data-stu-id="42ae5-128">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="42ae5-129">Método 2: borrar Skype Empresarial para todos los usuarios locales de Active Directory</span><span class="sxs-lookup"><span data-stu-id="42ae5-129">Method 2 - Clear Skype for Business attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="42ae5-130">Esta opción requiere un esfuerzo adicional y una planeación adecuada, ya que es necesario volver a aprovisionar los usuarios que se movieron anteriormente de un Skype Empresarial Server local a la nube.</span><span class="sxs-lookup"><span data-stu-id="42ae5-130">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="42ae5-131">Estos usuarios se pueden clasificar en dos categorías diferentes: usuarios sin Sistema telefónico y usuarios con Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="42ae5-131">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="42ae5-132">Los usuarios Sistema telefónico experimentarán una pérdida temporal del servicio telefónico como parte de la transición del número de teléfono desde que se administra en Active Directory local a la nube.</span><span class="sxs-lookup"><span data-stu-id="42ae5-132">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="42ae5-133">**Se recomienda realizar un piloto en el que participen un número reducido de usuarios con Sistema telefónico antes de iniciar operaciones de usuario en masa.**</span><span class="sxs-lookup"><span data-stu-id="42ae5-133">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="42ae5-134">Para implementaciones grandes, los usuarios pueden procesarse en grupos más pequeños en diferentes ventanas de tiempo.</span><span class="sxs-lookup"><span data-stu-id="42ae5-134">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="42ae5-135">Este proceso es más sencillo para los usuarios que tienen una dirección sip correspondiente y UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="42ae5-135">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="42ae5-136">Para las organizaciones que tienen usuarios con valores que no coinciden en estos dos atributos, se debe tener cuidado adicional como se indica a continuación para una transición sin problemas.</span><span class="sxs-lookup"><span data-stu-id="42ae5-136">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="42ae5-137">Si ha configurado puntos de conexión de aplicaciones híbridas locales para operadores automáticos o colas de llamadas, asegúrese de mover estos puntos de conexión a Microsoft 365 antes de retirar Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="42ae5-137">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="42ae5-138">Confirme que el siguiente cmdlet local Skype Empresarial PowerShell devuelve un resultado vacío.</span><span class="sxs-lookup"><span data-stu-id="42ae5-138">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="42ae5-139">Un resultado vacío significa que ningún usuario está internado y se ha movido a Microsoft 365 o se ha deshabilitado:</span><span class="sxs-lookup"><span data-stu-id="42ae5-139">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="42ae5-140">Registre el número de teléfono actual de los usuarios (LineUri), UserPrincipalName e información relacionada, ejecutando el siguiente cmdlet de PowerShell local Skype Empresarial Server para exportar datos de usuario:</span><span class="sxs-lookup"><span data-stu-id="42ae5-140">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="42ae5-141">Antes de continuar, abra SfbUserSettings.csv archivo y confirme que todos los datos de usuario se han exportado correctamente.</span><span class="sxs-lookup"><span data-stu-id="42ae5-141">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="42ae5-142">Se recomienda conservar una copia de este archivo.</span><span class="sxs-lookup"><span data-stu-id="42ae5-142">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="42ae5-143">No use este archivo en los siguientes pasos para procesar usuarios.</span><span class="sxs-lookup"><span data-stu-id="42ae5-143">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="42ae5-144">Cree un archivo con un grupo de usuarios que se usará en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="42ae5-144">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="42ae5-145">Después de que el primer grupo de usuarios se haya completado correctamente, continúe con el siguiente grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="42ae5-145">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="42ae5-146">En el ejemplo siguiente, los grupos de usuarios se seleccionan alfabéticamente, pero puede filtrar por usuarios en función de criterios que coincidan con la forma en que desea procesar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="42ae5-146">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="42ae5-147">Antes de continuar, abra SfbUsers.csv archivo y confirme que los datos de usuario se han exportado correctamente.</span><span class="sxs-lookup"><span data-stu-id="42ae5-147">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="42ae5-148">Necesitará LineUri (número de teléfono), UserPrincipalName, SamAccountName y SipAddress de este archivo en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="42ae5-148">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="42ae5-149">Elimine la información de atributo relacionada con Skype Empresarial Server de Active Directory para el conjunto de usuarios que está listo para actualizar.</span><span class="sxs-lookup"><span data-stu-id="42ae5-149">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="42ae5-150">Hay dos pasos para este proceso, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="42ae5-150">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="42ae5-151">Después del siguiente ciclo de Sincronización de AAD después de ejecutar este paso, los usuarios con Sistema telefónico que se movieron previamente de un Skype Empresarial Server local a la nube perderán la capacidad de realizar y recibir llamadas hasta que el paso 8 se complete y confirme correctamente en el paso 9.</span><span class="sxs-lookup"><span data-stu-id="42ae5-151">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="42ae5-152">Además, asegúrese de haber guardado los números de teléfono del usuario y la información relacionada según el paso 2, ya que esa información es necesaria para ese paso.</span><span class="sxs-lookup"><span data-stu-id="42ae5-152">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="42ae5-153">A continuación, para el mismo conjunto de usuarios, desactive el valor de msRTCSIP-DeploymentLocator con PowerShell de Active Directory local:</span><span class="sxs-lookup"><span data-stu-id="42ae5-153">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="42ae5-154">Ejecute el siguiente módulo local de Active Directory para Windows PowerShell cmdlet para agregar el valor de dirección sip de nuevo al proxy de Active Directory localAddresses.</span><span class="sxs-lookup"><span data-stu-id="42ae5-154">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="42ae5-155">Esto evitará problemas de interoperabilidad que dependen de este atributo.</span><span class="sxs-lookup"><span data-stu-id="42ae5-155">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="42ae5-156">Ejecute Sincronización de Azure AD</span><span class="sxs-lookup"><span data-stu-id="42ae5-156">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="42ae5-157">Espere a que se complete el aprovisionamiento de usuarios.</span><span class="sxs-lookup"><span data-stu-id="42ae5-157">Wait for user provisioning to complete.</span></span> <span data-ttu-id="42ae5-158">Para supervisar el progreso del aprovisionamiento de usuarios, ejecute el siguiente comando Skype Empresarial PowerShell en línea.</span><span class="sxs-lookup"><span data-stu-id="42ae5-158">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="42ae5-159">El siguiente Skype Empresarial de PowerShell en línea devuelve un resultado vacío en cuanto se complete el proceso.</span><span class="sxs-lookup"><span data-stu-id="42ae5-159">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="42ae5-160">Ejecute el siguiente comando Skype Empresarial PowerShell en línea para asignar números de teléfono y habilitar a los usuarios para Sistema telefónico:</span><span class="sxs-lookup"><span data-stu-id="42ae5-160">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="42ae5-161">Si todavía tiene Skype Empresarial extremos (ya sea Skype o teléfonos de terceros), también querrá establecer -HostedVoiceMail en $true.</span><span class="sxs-lookup"><span data-stu-id="42ae5-161">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="42ae5-162">Si su organización solo usa puntos Teams para usuarios habilitados para voz, esta configuración no se aplica a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="42ae5-162">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="42ae5-163">Confirme que los usuarios Sistema telefónico funcionalidad se han aprovisionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="42ae5-163">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="42ae5-164">El siguiente Skype Empresarial de PowerShell en línea devuelve un resultado vacío en cuanto se complete el proceso.</span><span class="sxs-lookup"><span data-stu-id="42ae5-164">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="42ae5-165">Repita los pasos del 3 al 9 hasta que se procese a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="42ae5-165">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="42ae5-166">Confirme que todos los usuarios se han procesado correctamente ejecutando los dos comandos de PowerShell siguientes.</span><span class="sxs-lookup"><span data-stu-id="42ae5-166">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="42ae5-167">Comando de PowerShell Skype Empresarial Server local:</span><span class="sxs-lookup"><span data-stu-id="42ae5-167">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="42ae5-168">Skype Empresarial Comando de PowerShell en línea:</span><span class="sxs-lookup"><span data-stu-id="42ae5-168">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="42ae5-169">Después de completar todos los pasos del método 2, vea Move [hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) y Remove your [on-premises Skype Empresarial Server](decommission-remove-on-prem.md) for additional steps to remove your Skype Empresarial Server on-premises deployment.</span><span class="sxs-lookup"><span data-stu-id="42ae5-169">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="42ae5-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="42ae5-170">See also</span></span>

- [<span data-ttu-id="42ae5-171">Consolidación de nube para Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="42ae5-171">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="42ae5-172">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="42ae5-172">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

