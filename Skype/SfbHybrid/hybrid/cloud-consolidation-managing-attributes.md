---
title: Decidir cómo administrar atributos después de la retirada
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
ms.localizationpriority: medium
description: En este artículo se describe cómo administrar atributos después de retirar el entorno local.
ms.openlocfilehash: 64a56b2fd5543179fbd9167721ad60699c6c4a23
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763794"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>Decidir cómo administrar atributos después de la retirada

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


De forma predeterminada, todos los usuarios que se han habilitado para Skype Empresarial Server y, a continuación, se han movido a la nube, siguen teniendo atributos msRTCSIP configurados en su Active Directory local. 

Estos atributos, en particular la dirección sip (msRTCSIP-PrimaryUserAddress) y el número de teléfono (msRTCSIP-Line), siguen sincroniendo en Azure AD. Si se requieren cambios en cualquiera de los atributos msRTCSIP, estos cambios deben realizarse en Active Directory local y, a continuación, sincronizarse con Azure AD. Sin embargo, una vez Skype Empresarial Server implementación, las herramientas Skype Empresarial Server no estarán disponibles para administrar estos atributos.

Hay dos opciones disponibles para controlar esta situación:

1. Deje los usuarios habilitados para Skype Empresarial cuentas de servidor tal y como está y administre los atributos msRTCSIP con herramientas de Active Directory. Este método garantiza que no se pierda el servicio para los usuarios migrados y le permite quitar la implementación de Skype Empresarial Server eliminando (por ejemplo, limpiando) los servidores, sin un desmantelamiento completo. Sin embargo, los usuarios recién con licencia no tendrán estos atributos rellenados en su Active Directory local y tendrán que administrarse en línea.

2.  Borre todos los atributos msRTCSIP de los usuarios migrados en su Active Directory local y administre estos atributos con herramientas en línea. Este método permite un enfoque de administración coherente para los usuarios existentes y nuevos. Sin embargo, puede provocar una pérdida temporal del servicio durante el proceso de retirada local.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Método 1: administrar direcciones sip y números de teléfono para usuarios de Active Directory

Los administradores pueden administrar los usuarios que se movieron de un Skype Empresarial Server local a la nube, incluso después de retirar la implementación local. 

Si desea realizar cambios en la dirección sip de un usuario o en el número de teléfono de un usuario (y la dirección sip o el número de teléfono ya tiene un valor en el Active Directory local), debe realizar el cambio en Active Directory local y permitir que los valores fluyan hasta Azure AD. Este método NO requiere una instalación local Skype Empresarial Server. En su lugar, puede modificar estos atributos directamente en Active Directory local, mediante el complemento MMC usuarios y equipos de Active Directory (como se muestra a continuación) o mediante PowerShell. Si usa el complemento MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque los atributos adecuados para modificar:

- Para modificar la dirección sip de un usuario, modifique el `msRTCSIP-PrimaryUserAddress`archivo .

    > [!NOTE]
    > Si el `ProxyAddresses` atributo contiene una dirección SIP, actualice también ese valor como procedimiento recomendado. Aunque O365 `msRTCSIP-PrimaryUserAddress` omite la dirección sip `ProxyAddresses` si está rellenada, otros componentes locales pueden usarla.

- Para modificar el número de teléfono de un usuario, modifique `msRTCSIP-Line` *si ya tiene un valor*.

  ![Herramienta de equipos y usuarios de Active Directory.](../media/disable-hybrid-1.png)


- Si el usuario no tenía originalmente `msRTCSIP-Line` un valor para local antes del movimiento, `-PhoneNumber` puede modificar el número de teléfono mediante el parámetro [del cmdlet Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) en el módulo de PowerShell de Teams.

Estos pasos no son necesarios para los nuevos usuarios creados después de deshabilitar híbridos y esos usuarios se pueden administrar directamente en la nube. Si se siente cómodo usando la combinación de estos métodos y dejando los atributos msRTCSIP en su Active Directory local, puede volver a crear una imagen de los servidores Skype Empresarial locales. Sin embargo, si prefiere borrar todos los atributos msRTCSIP y realizar una desinstalación tradicional de Skype Empresarial Server, use el método 2.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Método 2: borrar Skype Empresarial para todos los usuarios locales de Active Directory

Esta opción requiere más esfuerzo y una planeación adecuada, ya que los usuarios que se han movido de un Skype Empresarial Server local a la nube deben volver a aprovisionarse. Estos usuarios se pueden clasificar en dos categorías diferentes: usuarios sin Sistema telefónico y usuarios con Sistema telefónico. Los usuarios Sistema telefónico experimentarán una pérdida temporal del servicio telefónico como parte de la transición del número de teléfono desde que se administra en Active Directory local a la nube. **Se recomienda realizar un piloto en el que participen un número reducido de usuarios con Sistema telefónico antes de iniciar operaciones de usuario en masa.** Para implementaciones grandes, los usuarios pueden procesarse en grupos más pequeños en diferentes ventanas de tiempo. 

> [!NOTE] 
> Este proceso es más sencillo para los usuarios que tienen una dirección sip correspondiente y UserPrincipalName. Para las organizaciones que tienen usuarios con valores que no coinciden en estos dos atributos, se debe tener cuidado adicional como se indica a continuación para una transición sin problemas.

> [!NOTE]
> Si ha configurado puntos de conexión de aplicaciones híbridas locales para operadores automáticos o colas de llamadas, asegúrese de mover estos puntos de conexión a Microsoft 365 antes de retirar Skype Empresarial Server. Para obtener más información, consulte [Migrate hybrid application endpoints before decommissioning your on-premises environment](decommission-move-on-prem-endpoints.md).  


1. Confirme que el siguiente cmdlet local Skype Empresarial PowerShell devuelve un resultado vacío. Un resultado vacío significa que ningún usuario está internado y se ha movido a Microsoft 365 o se ha deshabilitado:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Registre el número de teléfono actual de los usuarios (LineUri), UserPrincipalName e información relacionada, ejecutando el siguiente cmdlet de PowerShell local Skype Empresarial Server para exportar datos de usuario:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Antes de continuar, abra SfbUserSettings.csv archivo y confirme que todos los datos de usuario se han exportado correctamente. Se recomienda conservar una copia de este archivo.  No use este archivo en los siguientes pasos para procesar usuarios. 

3. Cree un archivo con un grupo de usuarios que se usará en los pasos siguientes. Después de que el primer grupo de usuarios se haya completado correctamente, continúe con el siguiente grupo de usuarios. En el ejemplo siguiente, los grupos de usuarios se seleccionan alfabéticamente. Puede filtrar por usuarios en función de criterios que coincidan con el modo en que desea procesar los usuarios.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Antes de continuar, abra SfbUsers.csv archivo y confirme que los datos de usuario se han exportado correctamente. Necesitará LineUri (número de teléfono), UserPrincipalName, SamAccountName y SipAddress de este archivo en un paso posterior.

4. Elimine la información de atributo relacionada Skype Empresarial Server de active Directory para el conjunto de usuarios que está listo para actualizar.  Hay dos pasos para este proceso, como se muestra a continuación.

   > [!Important] 
   > Después del siguiente ciclo de Sincronización de AAD después de ejecutar este paso, los usuarios con Sistema telefónico que se movieron de un Skype Empresarial Server local a la nube perderán la capacidad de realizar y recibir llamadas hasta que el paso 8 se complete correctamente y se confirme en el paso 9. Además, asegúrese de haber guardado los números de teléfono del usuario y la información relacionada según el paso 2, ya que esa información es necesaria para ese paso.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   A continuación, para el mismo conjunto de usuarios, desactive el valor de msRTCSIP-DeploymentLocator con PowerShell de Active Directory local:

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Para volver a agregar el valor de dirección sip a los proxyAddresses locales de Active Directory, ejecute el siguiente módulo local de Active Directory para Windows PowerShell cmdlet. Esta acción evitará problemas de interoperabilidad que dependen de este atributo. 

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

6. Ejecute Sincronización de Azure AD

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Espere a que se complete el aprovisionamiento de usuarios. Puede supervisar el progreso del aprovisionamiento de usuarios ejecutando el siguiente Teams de PowerShell. El siguiente Teams comando de PowerShell devuelve un resultado vacío en cuanto se complete el proceso.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Para asignar números de teléfono y habilitar usuarios para Sistema telefónico, ejecute el siguiente comando Teams PowerShell:


   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
             Set-CsPhoneNumberAssignment -Identity $user.SipAddress -PhoneNumber $user.LineUri.Replace("tel:","") -PhoneNumberType DirectRouting
        }
   }
   ```

   > [!Note]
   >  Si todavía tiene Skype Empresarial de conexión (ya sea Skype clientes o teléfonos de terceros), también querrá establecer -HostedVoiceMail en $true. Si su organización solo usa puntos Teams para usuarios habilitados para voz, esta configuración no se aplica a los usuarios. 

9. Confirme que los usuarios Sistema telefónico funcionalidad se han aprovisionado correctamente. El siguiente Teams comando de PowerShell devuelve un resultado vacío en cuanto se complete el proceso.

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

10. Repita los pasos del 3 al 9 hasta que se procese a todos los usuarios.

11. Confirme que todos los usuarios se han procesado correctamente ejecutando los dos comandos de PowerShell siguientes.

    Comando de PowerShell Skype Empresarial Server local:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams de PowerShell:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 

12. Después de completar todos los pasos del método 2, vea Move [hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) y [Remove your on-premises Skype Empresarial Server](decommission-remove-on-prem.md) for additional steps to remove your Skype Empresarial Server on-premises deployment.


## <a name="see-also"></a>Vea también

- [Consolidación de nube para Teams y Skype Empresarial](cloud-consolidation.md)

- [Retirar el entorno local de Skype Empresarial](decommission-on-prem-overview.md)

