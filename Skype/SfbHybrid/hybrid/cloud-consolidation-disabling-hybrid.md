---
title: Deshabilitar la implementación híbrida para completar la migración a la nube
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
description: En este artículo se incluyen pasos detallados para deshabilitar la implementación híbrida como parte de la consolidación de la nube para Teams y Skype Empresarial.
ms.openlocfilehash: 18bda898563e10dbf964ba149f27202372fbcceb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656706"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-the-cloud"></a>Deshabilitar la configuración híbrida para completar la migración a la nube

En este artículo se describe cómo deshabilitar la configuración híbrida antes de retirar el entorno local de Skype Empresarial. Este es el paso 2 de los siguientes pasos para retirar el entorno local:

- Paso 1. [Mueva todos los usuarios necesarios de local a en línea.](decommission-move-on-prem-users.md)

- **Paso 2. Deshabilite la configuración híbrida.** (Este artículo)

- Paso 3. [Mover extremos de aplicación híbrida de local a en línea.](decommission-move-on-prem-endpoints.md)

- Paso 4. [Quite la implementación local de Skype Empresarial](decommission-remove-on-prem.md).


## <a name="overview"></a>Información general

Después de actualizar todos los usuarios de Skype Empresarial local a Teams Solo en Microsoft 365, puede retirar la implementación local de Skype Empresarial. Antes de retirar la implementación local de Skype Empresarial y quitar cualquier hardware, debe separar lógicamente la implementación local de Microsoft 365 deshabilitando la implementación híbrida. La deshabilitación híbrida consta de los tres pasos siguientes:

1. Actualizar los registros DNS para que apunten a Microsoft 365.

2. Deshabilite el espacio de direcciones sip compartido (también conocido como "dominio dividido") en la organización de Microsoft 365.

3. Deshabilite la capacidad de comunicarse localmente con Microsoft 365.

Estos pasos separan lógicamente la implementación local de Skype Empresarial Server de Microsoft 365 y deben realizarse conjuntamente como una unidad. Los detalles de cada paso se proporcionan en este artículo. Una vez completado, puede retirar la implementación local de Skype Empresarial mediante uno de los dos métodos a los que se hace referencia a continuación.

> [!Important] 
> Una vez completada esta separación lógica, los atributos msRTCSIP de su Active Directory local siguen teniendo valores y seguirán sincroniciendo a través de Azure AD Connect en Azure AD. La forma de retirar el entorno local depende de si desea dejar estos atributos en su lugar o, en primer lugar, borrarlos de su Active Directory local. Tenga en cuenta que borrar los atributos msRTCSIP locales después de migrar desde local podría provocar la pérdida de servicio para los usuarios. Más adelante, se describen los detalles y las transacciones de los dos enfoques de retirada.

## <a name="detailed-steps"></a>Pasos detallados

1. *Actualice DNS para que apunte a Microsoft 365.* El DNS externo de la organización para la organización local debe actualizarse para que los registros de Skype Empresarial apunten a Microsoft 365 en lugar de a la implementación local. En particular:

    |Tipo de registro|Nombre|TTL|Valor|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|

    Además, se pueden eliminar los registros CNAME para meet o dialin (si están presentes). Por último, se deben quitar los registros DNS de Skype Empresarial en la red interna.

    > [!Note] 
    > En raras ocasiones, cambiar DNS de apuntar localmente a Microsoft 365 para su organización puede provocar que la federación con otras organizaciones deje de funcionar hasta que otra organización actualice su configuración de federación:
    >
    > - Las organizaciones federadas que usan el modelo de federación directa anterior (también conocido como Servidor de partners permitidos) tendrán que actualizar las entradas de dominio permitidas para su organización para quitar el FQDN de proxy. Este modelo de federación heredado no se basa en registros SRV de DNS, por lo que dicha configuración se desatendrán una vez que la organización se mueva a la nube.
    > 
    > - Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed.online.lync. <span> com tendrá que actualizar su configuración para habilitarlo. Esta situación solo es posible si la organización federada es puramente local y nunca se ha federado con ningún inquilino híbrido o en línea. En tal caso, la federación con estas organizaciones no funcionará hasta que habiliten su proveedor de hospedaje.
    >
    > Si sospecha que alguno de sus socios federados puede estar usando Direct Federation o no haber federado con ninguna organización híbrida o en línea, le sugerimos que envíe una comunicación al respecto mientras se prepara para completar la migración a la nube.


2.  *Deshabilitar el espacio de direcciones sip compartido en la organización de Microsoft 365.* El siguiente comando debe realizarse desde una ventana de PowerShell de Skype Empresarial Online.

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  *Deshabilite la capacidad de comunicarse localmente con Microsoft 365.* El siguiente comando debe realizarse desde una ventana de PowerShell local:

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>Administración de atributos después de mover usuarios de local a la nube

De forma predeterminada, todos los usuarios que se habilitaron anteriormente para Skype Empresarial Server y que posteriormente se movieron a la nube aún tienen atributos msRTCSIP configurados en active directory local. Estos atributos, en particular la dirección sip (msRTCSIP-PrimaryUserAddress) y el número de teléfono potencialmente (msRTCSIP-Line), siguen sincroniciendo en Azure AD. Si se requieren cambios en cualquiera de los atributos msRTCSIP, estos cambios deben realizarse en Active Directory local y, a continuación, sincronizarse con Azure AD. Sin embargo, una vez que se haya quitado la implementación de Skype Empresarial Server, las herramientas de Skype Empresarial Server no estarán disponibles para administrar estos atributos.

Hay dos opciones disponibles para controlar esta situación:

1. Deje los usuarios habilitados para cuentas de servidor de Skype Empresarial tal como están y administre los atributos msRTCSIP con herramientas de Active Directory. Esto garantiza que no se pierda el servicio para los usuarios migrados y le permite quitar fácilmente la implementación de Skype Empresarial Server eliminando (por ejemplo, limpiando) los servidores, sin un desmantelamiento completo. Sin embargo, los usuarios recién con licencia no tendrán estos atributos rellenados en su Active Directory local y tendrán que administrarse en línea.

2.  Borre todos los atributos msRTCSIP de los usuarios migrados en su Active Directory local y administre estos atributos con herramientas en línea. Este método permite un enfoque de administración coherente para los usuarios existentes y nuevos, pero puede provocar una pérdida temporal del servicio durante el proceso de retirada local.


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Método 1: administrar direcciones sip y números de teléfono para usuarios de Active Directory

Los administradores pueden administrar usuarios que se movieron anteriormente de un Skype Empresarial Server local a la nube, incluso después de retirar la implementación local. Si desea realizar cambios en la dirección sip de un usuario o en el número de teléfono de un usuario (y la dirección sip o el número de teléfono ya tiene un valor en Active Directory local), debe hacerlo en Active Directory local y permitir que los valores fluyan hasta Azure AD. Esto NO requiere Skype Empresarial Server local. En su lugar, puede modificar estos atributos directamente en Active Directory local, mediante el complemento MMC usuarios y equipos de Active Directory (como se muestra a continuación) o mediante PowerShell. Si usa el complemento MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque los atributos adecuados para modificar:

- Para modificar la dirección sip de un usuario, modifique `msRTCSIP-PrimaryUserAddress` el archivo . Tenga en cuenta que si el atributo contiene una dirección sip, actualice `ProxyAddresses` también ese valor como procedimiento recomendado. Aunque O365 omite la dirección sip si está rellenada, otros componentes locales pueden `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` usarla.

- Para modificar el número de teléfono de un usuario, modifique `msRTCSIP-Line` *si ya tiene un valor*.

  ![Herramienta de equipos y usuarios de Active Directory](../media/disable-hybrid-1.png)
  
-  Si el usuario no tenía originalmente un valor para local antes del movimiento, puede modificar el número de teléfono mediante el parámetro - en el `msRTCSIP-Line` `onpremLineUri` cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) del módulo PowerShell de Skype Empresarial Online.

Estos pasos no son necesarios para los nuevos usuarios creados después de deshabilitar híbridos y esos usuarios se pueden administrar directamente en la nube. Si se siente cómodo con la combinación de estos métodos, así como con dejar los atributos msRTCSIP en su Active Directory local, simplemente puede volver a crear una imagen de los servidores locales de Skype Empresarial. Sin embargo, si prefiere borrar todos los atributos msRTCSIP y realizar una desinstalación tradicional de Skype Empresarial Server, use el método 2.


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Método 2: Borrar atributos de Skype Empresarial para todos los usuarios locales de Active Directory

Esta opción requiere un esfuerzo adicional y una planeación adecuada, ya que los usuarios que se movieron previamente de un Skype Empresarial Server local a la nube deben volver a aprovisionarse. Estos usuarios se pueden clasificar en dos categorías diferentes: usuarios sin sistema telefónico y usuarios con sistema telefónico. Los usuarios con sistema telefónico experimentarán una pérdida temporal del servicio telefónico como parte de la transición del número de teléfono desde que se administra en Active Directory local a la nube. **Se recomienda realizar un piloto en el que participen un número reducido de usuarios con sistema telefónico antes de iniciar operaciones masivas de usuario.** Para implementaciones grandes, los usuarios pueden procesarse en grupos más pequeños en diferentes ventanas de tiempo. 

> [!NOTE] 
> Este proceso es más sencillo para los usuarios que tienen una dirección sip correspondiente y UserPrincipalName. Para las organizaciones que tienen usuarios con valores que no coinciden en estos dos atributos, se debe tener cuidado adicional como se indica a continuación para una transición sin problemas.

> [!NOTE]
> Si ha configurado puntos de conexión de aplicaciones híbridas locales para operadores automáticos o colas de llamadas, asegúrese de mover estos extremos a Microsoft 365 antes de retirar Skype Empresarial Server.


1. Confirme que el siguiente cmdlet local de PowerShell de Skype Empresarial devuelve un resultado vacío. Un resultado vacío significa que ningún usuario está internamente y se ha movido a Microsoft 365 o se ha deshabilitado:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Registre el número de teléfono actual de los usuarios (LineUri), UserPrincipalName e información relacionada, ejecutando el siguiente cmdlet local de PowerShell de Skype Empresarial Server para exportar datos de usuario:

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
   > Después del siguiente ciclo de sincronización de AAD después de ejecutar este paso, los usuarios con sistema telefónico que se movieron previamente de un Skype Empresarial Server local a la nube perderán la capacidad de realizar y recibir llamadas hasta que el paso 8 se complete correctamente y se confirme en el paso 9. Además, asegúrese de haber guardado los números de teléfono del usuario y la información relacionada según el paso 2, ya que esa información es necesaria para ese paso.

 
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

5. Ejecute el siguiente cmdlet local de PowerShell de Skype Empresarial para agregar el valor de la dirección sip al proxy de Active Directory localAddresses. Esto evitará problemas de interoperabilidad que dependen de este atributo. 

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

6. Ejecutar Azure AD Sync

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Espere a que se complete el aprovisionamiento de usuarios. Puede supervisar el progreso del aprovisionamiento de usuarios ejecutando el siguiente comando de PowerShell de Skype Empresarial Online. El siguiente comando de PowerShell de Skype Empresarial Online devuelve un resultado vacío en cuanto se complete el proceso.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Ejecute el siguiente comando de PowerShell de Skype Empresarial Online para asignar números de teléfono y habilitar a los usuarios para el sistema telefónico:
     
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
   >  Si todavía tiene puntos de conexión de Skype Empresarial (ya sea clientes de Skype o teléfonos de terceros), también querrá establecer -HostedVoiceMail en $true. Si su organización solo usa puntos de conexión de Teams para usuarios habilitados para voz, esta configuración no se aplica a los usuarios. 

9. Confirme que los usuarios con funcionalidad del sistema telefónico se han aprovisionado correctamente. El siguiente comando de PowerShell de Skype Empresarial Online devuelve un resultado vacío en cuanto se complete el proceso.

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

    Comando de PowerShell local de Skype Empresarial Server local:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    Comando de PowerShell de Skype Empresarial Online:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. Después de completar todos los pasos del método 2, vea Move [hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) y Remove your [on-premises Skype for Business Server](decommission-remove-on-prem.md) para obtener pasos adicionales para quitar la implementación local de Skype Empresarial Server.


## <a name="see-also"></a>Recursos adicionales

- [Consolidación en la nube para Teams y Skype Empresarial](cloud-consolidation.md)

- [Retirar el entorno local de Skype Empresarial](decommission-on-prem-overview.md)

