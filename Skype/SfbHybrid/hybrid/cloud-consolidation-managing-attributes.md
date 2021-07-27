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
localization_priority: Normal
description: En este artículo se describe cómo administrar atributos después de retirar el entorno local.
ms.openlocfilehash: d8c61e1a5a76206cadd8ab4ae3ed51de77badc74
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510651"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>Decidir cómo administrar atributos después de la retirada

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


De forma predeterminada, todos los usuarios que se habilitaron anteriormente para Skype Empresarial Server y posteriormente se movieron a la nube todavía tienen atributos msRTCSIP configurados en active directory local. 

Estos atributos, en particular la dirección sip (msRTCSIP-PrimaryUserAddress) y el número de teléfono potencialmente (msRTCSIP-Line), siguen sincroniciendo en Azure AD. Si se requieren cambios en cualquiera de los atributos msRTCSIP, estos cambios deben realizarse en Active Directory local y, a continuación, sincronizarse con Azure AD. Sin embargo, una vez Skype Empresarial Server implementación, las herramientas Skype Empresarial Server no estarán disponibles para administrar estos atributos.

Hay dos opciones disponibles para controlar esta situación:

1. Deje los usuarios habilitados para Skype Empresarial cuentas de servidor tal y como está y administre los atributos msRTCSIP con herramientas de Active Directory. Esto garantiza que no se pierda el servicio para los usuarios migrados y le permite quitar fácilmente la implementación de Skype Empresarial Server eliminando (por ejemplo, limpiando) los servidores, sin un desmantelamiento completo. Sin embargo, los usuarios recién con licencia no tendrán estos atributos rellenados en su Active Directory local y tendrán que administrarse en línea.

2.  Borre todos los atributos msRTCSIP de los usuarios migrados en su Active Directory local y administre estos atributos con herramientas en línea. Este método permite un enfoque de administración coherente para los usuarios existentes y nuevos, pero puede provocar una pérdida temporal del servicio durante el proceso de retirada local.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Método 1: administrar direcciones sip y números de teléfono para usuarios de Active Directory

Los administradores pueden administrar usuarios que se movieron previamente de un Skype Empresarial Server local a la nube, incluso después de retirar la implementación local. 

Si desea realizar cambios en la dirección sip de un usuario o en el número de teléfono de un usuario (y la dirección sip o el número de teléfono ya tiene un valor en Active Directory local), debe hacerlo en Active Directory local y permitir que los valores fluyan hasta Azure AD. Esto NO requiere una instalación local Skype Empresarial Server. En su lugar, puede modificar estos atributos directamente en Active Directory local, mediante el complemento MMC usuarios y equipos de Active Directory (como se muestra a continuación) o mediante PowerShell. Si usa el complemento MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque los atributos adecuados para modificar:

- Para modificar la dirección sip de un usuario, modifique `msRTCSIP-PrimaryUserAddress` el archivo .

    > [!NOTE]
    > Si el `ProxyAddresses` atributo contiene una dirección SIP, actualice también ese valor como procedimiento recomendado. Aunque O365 omite la dirección sip si está rellenada, otros componentes locales pueden `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` usarla.

- Para modificar el número de teléfono de un usuario, modifique `msRTCSIP-Line` *si ya tiene un valor*.

  ![Herramienta de equipos y usuarios de Active Directory](../media/disable-hybrid-1.png)
  
-  Si el usuario no tenía originalmente un valor para local antes del movimiento, puede modificar el número de teléfono mediante el parámetro - en el `msRTCSIP-Line` `onpremLineUri` cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) en el módulo de PowerShell de Skype Empresarial Online.

Estos pasos no son necesarios para los nuevos usuarios creados después de deshabilitar híbridos y esos usuarios se pueden administrar directamente en la nube. Si se siente cómodo con la combinación de estos métodos, así como con dejar los atributos msRTCSIP en su Active Directory local, simplemente puede volver a crear una imagen de los servidores Skype Empresarial locales. Sin embargo, si prefiere borrar todos los atributos msRTCSIP y realizar una desinstalación tradicional de Skype Empresarial Server, use el método 2.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Método 2: borrar Skype Empresarial para todos los usuarios locales de Active Directory

Esta opción requiere un esfuerzo adicional y una planeación adecuada, ya que es necesario volver a aprovisionar los usuarios que se movieron anteriormente de un Skype Empresarial Server local a la nube. Estos usuarios se pueden clasificar en dos categorías diferentes: usuarios sin Sistema telefónico y usuarios con Sistema telefónico. Los usuarios Sistema telefónico experimentarán una pérdida temporal del servicio telefónico como parte de la transición del número de teléfono desde que se administra en Active Directory local a la nube. **Se recomienda realizar un piloto en el que participen un número reducido de usuarios con Sistema telefónico antes de iniciar operaciones de usuario en masa.** Para implementaciones grandes, los usuarios pueden procesarse en grupos más pequeños en diferentes ventanas de tiempo. 

> [!NOTE] 
> Este proceso es más sencillo para los usuarios que tienen una dirección sip correspondiente y UserPrincipalName. Para las organizaciones que tienen usuarios con valores que no coinciden en estos dos atributos, se debe tener cuidado adicional como se indica a continuación para una transición sin problemas.

> [!NOTE]
> Si ha configurado puntos de conexión de aplicaciones híbridas locales para operadores automáticos o colas de llamadas, asegúrese de mover estos puntos de conexión a Microsoft 365 antes de retirar Skype Empresarial Server.


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

3. Cree un archivo con un grupo de usuarios que se usará en los pasos siguientes. Después de que el primer grupo de usuarios se haya completado correctamente, continúe con el siguiente grupo de usuarios. En el ejemplo siguiente, los grupos de usuarios se seleccionan alfabéticamente, pero puede filtrar por usuarios en función de criterios que coincidan con la forma en que desea procesar los usuarios.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Antes de continuar, abra SfbUsers.csv archivo y confirme que los datos de usuario se han exportado correctamente. Necesitará LineUri (número de teléfono), UserPrincipalName, SamAccountName y SipAddress de este archivo en un paso posterior.

4. Elimine la información de atributo relacionada con Skype Empresarial Server de Active Directory para el conjunto de usuarios que está listo para actualizar.  Hay dos pasos para este proceso, como se muestra a continuación.

   > [!Important] 
   > Después del siguiente ciclo de Sincronización de AAD después de ejecutar este paso, los usuarios con Sistema telefónico que se movieron previamente de un Skype Empresarial Server local a la nube perderán la capacidad de realizar y recibir llamadas hasta que el paso 8 se complete y confirme correctamente en el paso 9. Además, asegúrese de haber guardado los números de teléfono del usuario y la información relacionada según el paso 2, ya que esa información es necesaria para ese paso.

 
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

5. Ejecute el siguiente módulo local de Active Directory para Windows PowerShell cmdlet para agregar el valor de dirección sip de nuevo al proxy de Active Directory localAddresses. Esto evitará problemas de interoperabilidad que dependen de este atributo. 

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

7. Espere a que se complete el aprovisionamiento de usuarios. Para supervisar el progreso del aprovisionamiento de usuarios, ejecute el siguiente comando Skype Empresarial PowerShell en línea. El siguiente Skype Empresarial de PowerShell en línea devuelve un resultado vacío en cuanto se complete el proceso.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Ejecute el siguiente comando Skype Empresarial PowerShell en línea para asignar números de teléfono y habilitar a los usuarios para Sistema telefónico:
     
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
   >  Si todavía tiene Skype Empresarial extremos (ya sea Skype o teléfonos de terceros), también querrá establecer -HostedVoiceMail en $true. Si su organización solo usa puntos Teams para usuarios habilitados para voz, esta configuración no se aplica a los usuarios. 

9. Confirme que los usuarios Sistema telefónico funcionalidad se han aprovisionado correctamente. El siguiente Skype Empresarial de PowerShell en línea devuelve un resultado vacío en cuanto se complete el proceso.

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
    Skype Empresarial Comando de PowerShell en línea:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. Después de completar todos los pasos del método 2, vea Move [hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) y Remove your [on-premises Skype Empresarial Server](decommission-remove-on-prem.md) for additional steps to remove your Skype Empresarial Server on-premises deployment.


## <a name="see-also"></a>Vea también

- [Consolidación de nube para Teams y Skype Empresarial](cloud-consolidation.md)

- [Retirar el entorno local de Skype Empresarial](decommission-on-prem-overview.md)

