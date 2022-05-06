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
ms.openlocfilehash: b838b965430a007fa74320d7dbebdcf7ee36c3a9
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2022
ms.locfileid: "65249022"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>Decidir cómo administrar atributos después de la retirada

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


De forma predeterminada, todos los usuarios que se habilitaron para Skype Empresarial Server y luego se trasladaron a la nube siguen teniendo atributos msRTCSIP configurados en el Active Directory local. 

Estos atributos, en particular la dirección sip (msRTCSIP-PrimaryUserAddress) y el número de teléfono (msRTCSIP-Line), continúan sincronizándose en Azure AD. Si se requieren cambios en cualquiera de los atributos msRTCSIP, estos cambios se deben realizar en el Active Directory local y, a continuación, sincronizar con Azure AD. Sin embargo, una vez que se haya quitado la implementación de Skype Empresarial Server, las herramientas de Skype Empresarial Server no estarán disponibles para administrar estos atributos.

Hay dos opciones disponibles para controlar esta situación:

1. Deje los usuarios habilitados para Skype Empresarial cuentas de servidor tal cual y administre los atributos msRTCSIP mediante las herramientas de Active Directory. Este método garantiza que no se pierda el servicio para los usuarios migrados y permite quitar la implementación de Skype Empresarial Server mediante la eliminación (por ejemplo, la eliminación) de los servidores, sin un desmantelamiento completo. Sin embargo, los usuarios con licencia recién no tendrán estos atributos rellenados en el Active Directory local y tendrán que administrarse en línea.

2.  Borre todos los atributos msRTCSIP de los usuarios migrados en el Active Directory local y administre estos atributos mediante herramientas en línea. Este método permite un enfoque de administración coherente para los usuarios existentes y nuevos. Sin embargo, puede dar lugar a una pérdida temporal del servicio durante el proceso de retirada local.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Método 1: Administración de direcciones SIP y números de teléfono para usuarios de Active Directory

Los administradores pueden administrar los usuarios que se trasladaron de un Skype Empresarial Server local a la nube, incluso después de retirar la implementación local. 

Si desea realizar cambios en la dirección SIP de un usuario o en el número de teléfono de un usuario (y la dirección sip o el número de teléfono ya tiene un valor en el Active Directory local), debe realizar el cambio en el Active Directory local y dejar que los valores fluyan hasta Azure AD. Este método NO requiere Skype Empresarial Server locales. En su lugar, puede modificar estos atributos directamente en el Active Directory local, mediante el complemento MMC Usuarios y equipos de Active Directory (como se muestra a continuación) o mediante PowerShell. Si usa el complemento MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque los atributos adecuados para modificar:

- Para modificar la dirección SIP de un usuario, modifique .`msRTCSIP-PrimaryUserAddress`

    > [!NOTE]
    > Si el `ProxyAddresses` atributo contiene una dirección sip, actualice también ese valor como procedimiento recomendado. Aunque O365 omite la dirección sip en `ProxyAddresses` si `msRTCSIP-PrimaryUserAddress` se rellena, otros componentes locales pueden usarla.

- Para modificar el número de teléfono de un usuario, modifique `msRTCSIP-Line` *si ya tiene un valor*.

  ![Herramienta usuarios y equipos de Active Directory.](../media/disable-hybrid-1.png)


- Si el usuario no tenía originalmente un valor para `msRTCSIP-Line` el entorno local antes del traslado, puede modificar el número de teléfono mediante el `-PhoneNumber` parámetro en el [cmdlet Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) del módulo de PowerShell Teams.

Estos pasos no son necesarios para los nuevos usuarios creados después de deshabilitar el híbrido y esos usuarios se pueden administrar directamente en la nube. Si se siente cómodo con la combinación de estos métodos y con dejar los atributos msRTCSIP en su lugar en el Active Directory local, puede volver a crear una imagen de los servidores de Skype Empresarial locales. Sin embargo, si prefiere borrar todos los atributos msRTCSIP y realizar una desinstalación tradicional de Skype Empresarial Server, use el método 2.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Método 2: Borrar atributos de Skype Empresarial para todos los usuarios locales de Active Directory

Esta opción requiere más esfuerzo y un planeamiento adecuado, ya que los usuarios que se trasladaron de un Skype Empresarial Server local a la nube deben volver a aprovisionarse. Estos usuarios se pueden clasificar en dos categorías diferentes: usuarios sin Sistema telefónico y usuarios con Sistema telefónico. Los usuarios con Sistema telefónico experimentarán una pérdida temporal del servicio telefónico como parte de la transición del número de teléfono de la administración en Active Directory local a la nube. **Se recomienda realizar un piloto que implique a un pequeño número de usuarios con Sistema telefónico antes de iniciar operaciones masivas de usuarios.** Para implementaciones grandes, los usuarios se pueden procesar en grupos más pequeños en diferentes ventanas de tiempo. 

> [!NOTE] 
> Este proceso es más sencillo para los usuarios que tienen una dirección SIP coincidente y UserPrincipalName. Para las organizaciones que tienen usuarios con valores que no coinciden en estos dos atributos, se debe tener cuidado adicional como se indica a continuación para una transición fluida.

> [!NOTE]
> Si ha configurado puntos de conexión de aplicaciones híbridas locales para operadores automáticos o colas de llamadas, asegúrese de mover estos puntos de conexión a Microsoft 365 antes de retirar Skype Empresarial Server. Para obtener más información, consulte [Migración de puntos de conexión de aplicaciones híbridas antes de retirar el entorno local](decommission-move-on-prem-endpoints.md).  


1. Confirme que el siguiente cmdlet de PowerShell Skype Empresarial local devuelve un resultado vacío. Un resultado vacío significa que no hay usuarios hospedados en el entorno local y se han movido a Microsoft 365 o se han deshabilitado:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Registre el número de teléfono actual de los usuarios (LineUri), UserPrincipalName e información relacionada mediante la ejecución de los siguientes Skype Empresarial Server cmdlet de PowerShell locales para exportar datos de usuario:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Antes de continuar, abra SfbUserSettings.csv archivo y confirme que todos los datos de usuario se han exportado correctamente. Se recomienda mantener una copia de este archivo.  No use este archivo en los pasos siguientes para procesar usuarios. 

3. Cree un archivo con un grupo de usuarios que se usará en los pasos siguientes. Una vez que el primer grupo de usuarios se haya completado correctamente, continúe con el siguiente grupo de usuarios. En el ejemplo siguiente, los grupos de usuarios se seleccionan alfabéticamente. Puede filtrar por los usuarios en función de criterios que coincidan con la forma en que desea procesar a los usuarios.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Antes de continuar, abra SfbUsers.csv archivo y confirme que los datos de usuario se han exportado correctamente. Necesitará lineuri (número de teléfono), UserPrincipalName, SamAccountName y SipAddress de este archivo en un paso posterior.

4. Elimine la información de atributo relacionada con Skype Empresarial Server de Active Directory para el conjunto de usuarios que está listo para actualizar.  Hay dos pasos para este proceso, como se muestra a continuación.

   > [!Important] 
   > Después del siguiente ciclo de Sincronización de AAD después de ejecutar este paso, los usuarios con Sistema telefónico que se trasladaron de un Skype Empresarial Server local a la nube perderán la capacidad de realizar y recibir llamadas hasta que el paso 8 se complete y confirme correctamente en el paso 9. Además, asegúrese de que ha guardado los números de teléfono del usuario y la información relacionada según el paso 2, ya que esa información es necesaria para ese paso.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   A continuación, para el mismo conjunto de usuarios, borre el valor de msRTCSIP-DeploymentLocator mediante Active Directory local PowerShell:

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Para volver a agregar el valor de la dirección SIP al proxyAddresses de Active Directory local, ejecute el siguiente módulo Active Directory local para Windows PowerShell cmdlet. Esta acción impedirá los problemas de interoperabilidad que se basan en este atributo. 

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

6. Ejecutar Sincronización de Azure AD

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Espere a que se complete el aprovisionamiento de usuarios. Para supervisar el progreso del aprovisionamiento de usuarios, ejecute el siguiente comando de PowerShell Teams. El siguiente Teams comando de PowerShell devuelve un resultado vacío en cuanto se completa el proceso.

   ```PowerShell
   Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | Where UserValidationErrors -ne $null | Select SipAddress,InterpretedUserType,UserValidationErrors
   ```

8. Para asignar números de teléfono y habilitar usuarios para Sistema telefónico, ejecute el siguiente comando de PowerShell Teams:


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
   >  Si todavía tiene puntos de conexión de Skype Empresarial (ya sea Skype clientes o teléfonos de terceros), también querrá establecer -HostedVoiceMail en $true. Si su organización solo usa puntos de conexión de Teams para usuarios habilitados para voz, esta configuración no es aplicable a los usuarios. 

9. Confirme que los usuarios con Sistema telefónico funcionalidad se han aprovisionado correctamente. El siguiente Teams comando de PowerShell devuelve un resultado vacío en cuanto se completa el proceso.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled
                }
        }
   }
   ``` 

10. Repita los pasos del 3 al 9 hasta que se procesen todos los usuarios.

11. Confirme que todos los usuarios se han procesado correctamente ejecutando los dos comandos de PowerShell siguientes.

    Comando de PowerShell local Skype Empresarial Server local:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams comando de PowerShell:

    ```PowerShell
    Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | where {UserValidationErrors -ne $null} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, UserValidationErrors
    ``` 

12. Después de completar todos los pasos del Método 2, consulte [Traslado de puntos de conexión de aplicaciones híbridas del entorno local a en línea](decommission-move-on-prem-endpoints.md) y [Eliminación de la Skype Empresarial Server local](decommission-remove-on-prem.md) para ver pasos adicionales para quitar la implementación local de Skype Empresarial Server.


## <a name="see-also"></a>Consulte también

- [Consolidación de la nube para Teams y Skype Empresarial](cloud-consolidation.md)

- [Retirar el entorno local de Skype Empresarial](decommission-on-prem-overview.md)

