---
title: Mover usuarios de Skype para los negocios en línea a en instalaciones
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Resumen: Conozca cómo mover cuentas de usuario de en línea para local en Skype para Business Server.'
ms.openlocfilehash: e429aebc6847146ad5bef2b34d6ccfa7d2997ec6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a>Mover usuarios de Skype para los negocios en línea a en instalaciones
 
**Resumen:** Obtenga información acerca de cómo mover cuentas de usuario de en línea para local en Skype para Business Server.
  
Debe mover las cuentas de usuario de en línea a en locales para garantizar que los usuarios alojados en línea y en locales, son reconocibles entre sí. Para que sea reconocible entre sí, todos los usuarios deben tener una presencia en el Active Directory local. Para obtener más información, consulte [Plan conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md). Desee mover usuarios conectados en locales, por ejemplo, si: 
  
- Tiene nuevos usuarios que necesitan crearse en locales y, a continuación, se mueve a la nube.
    
- La organización implementa Skype para los negocios en línea antes de que implemente Skype para Business Server. Por lo tanto, hay usuarios que se han creado en la nube en primer lugar y ahora tiene que moverse a locales antes de mover a Skype para los negocios en línea. 
    
En este tema se describe dos escenarios:
  
- [Mover usuarios en línea, que estaban originalmente en línea: a en instalaciones](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)
    
- [Mover los usuarios en línea (que eran originalmente en instalaciones) en locales](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)
    
## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a>Mover usuarios en línea, que estaban originalmente en línea: a en instalaciones
<a name="BKMK_originallyonline"> </a>

Esta sección sólo se aplica a los usuarios que se han creado y habilitado en línea, pero que no tienen una cuenta en las instalaciones de Active Directory. 
  
Antes de empezar a mover usuarios en línea a su entorno local, compruebe que se cumplan las condiciones siguientes:
  
- Su entorno local necesita estar completamente implementado y validado. Para obtener más información, vea [implementación de Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) o [Implementar Skype para Business Server 2015](../../deploy/deploy.md), dependiendo de la versión que está utilizando en instalaciones. 
    
- El arrendatario en línea debe configurarse para el acceso remoto de PowerShell.
    
    Para ello, instale primero el Skype para el módulo del conector de negocios en línea para Windows PowerShell, que se puede obtener aquí: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
    
    Después de instalar el módulo, puede establecer una sesión remota escribiendo los siguientes cmdlets en el Skype para el Shell de administración de servidor de negocios:
    
  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype para los negocios en línea, vea [conectarse a Lync Online por utilizando Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).
    
    Para obtener más información acerca de cómo utilizar el Skype para el módulo de PowerShell de conector negocios en línea, consulte [Uso de Windows PowerShell para administrar Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).
    
- El arrendatario en línea debe configurarse para un espacio de direcciones compartido de SIP. Para ello, inicie primero una sesión remota de Powershell con Skype para los negocios en línea. Luego, ejecute el cmdlet siguiente:
    
  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > Las necesidades de atributo SharedSipAddressSpace permanezca "True" hasta mover a en línea es final y no hay usuarios permanecen en las instalaciones. 
  
Cuando termine estos pasos, puede migrar las cuentas de usuario como se describe en el procedimiento siguiente:
  
### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a>Mover cuentas de usuario que originalmente habilitadas en línea a una implementación local

1. En primer lugar, asegúrese de que su organización está configurada para implementaciones híbridas, incluidos Azure Active Directory Connect y las herramientas de sincronización. Para obtener más información, consulte [Plan conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
    
  - En la implementación local, en el Skype para el Shell de administración de servidor empresarial, escriba los siguientes cmdlets para crear el proveedor de hospedaje de Skype para los negocios en línea. Puede usar cualquier valor que desee para los parámetros Identidad y Nombre.
    
  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. Confirmar que en los servidores de borde local, dispone de la cadena de certificados que permite la conexión a Skype para los negocios en línea, como se muestra en la siguiente tabla. Puede descargar aquí esta cadena: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).
    
|**Certificado**|**Almacén de certificados**|
|:-----|:-----|
|Baltimore CyberTrust Root  <br/> |CA raíz de confianza  <br/> |
|Microsoft Internet Authority (nuevo certificado CA)  <br/> |CA intermedia  <br/> |
|MSIT Machine Auth CA2 (nueva CA2 de emisión)  <br/> |CA intermedia  <br/> |
   
3. En el Active Directory local, habilitar las cuentas de usuario afectado para Skype para Business Server 2015 en locales. Para hacerlo para un usuario individual, escriba el cmdlet siguiente: 
    
  ```
  Enable-CsUser
-Identity "username " 
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    También puede crear un script que lea los nombres de usuario de un archivo y los indique como entrada al cmdlet Enable-CsUser cmdlet:
    
  ```
  Enable-CsUser
-Identity $Identity 
-SipAddress $SipAddress 
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. Sincronizar los usuarios en línea con los usuarios locales actualizados. Para obtener más información, vea [Herramientas de integración de directorio](https://go.microsoft.com/fwlink/p/?LinkId=530320).
    
5. Actualizar los siguientes registros DNS para dirigir todo el tráfico SIP para su implementación local:
    
  - Actualice el registro A **lyncdiscover.contoso.com** para que apunte al FQDN del servidor proxy inverso local.
    
  - Actualización de la ** *_sip* . grabar _tls.contoso.com** SRV para resolver la dirección pública IP o VIP del servicio acceso perimetral de Lync en locales.
    
  - Actualización de la ** *_sipfederationtls* . _tcp.contoso.com** SRV grabar para resolver las direcciones IP o VIP públicas del servicio de servidor perimetral de acceso de Skype para Business Server 2015 local.
    
  - Si su organización utiliza divide DNS (a veces denominado "Brain DNS"), asegúrese de que se dirijan a los usuarios resolver los nombres de la zona DNS interna para el grupo de servidores frontales.
    
6. Tipo de la `Get-CsUser` cmdlet para comprobar algunas propiedades acerca de los usuarios que va a mover. Necesita asegurarse de que el FQDN del servidor proxy del proveedor de hospedaje está definido a `"sipfed.online.lync.com"` y que las direcciones SIP están bien configuradas.
    
7. Mover los usuarios en línea en locales.
    
    Para mover un solo usuario, escriba lo siguiente:
    
  ```
  $cred = Get-Credential
  ```

  ```
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    Puede mover varios usuarios mediante el cmdlet **Get-CsUSer** -el parámetro Filter para seleccionar los usuarios con una propiedad específica. Por ejemplo, puede seleccionar todos los usuarios conectados por un filtro de {proveedor de hospedaje - eq "sipfed.online.lync.om"}. A continuación, puede canalizar los usuarios devueltos al cmdlet **Move-CsUSer** , como se muestra a continuación.
    
  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL para el grupo de servidores donde se ejecuta el servicio alojado de migración, en el formato siguiente: _Https://\<Pool FQDN\>/HostedMigration/ hostedmigrationService.svc_.
    
    Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.
    
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365

1. Inicie sesión en el inquilino de Office 365 como administrador.
    
2. Abra el **Centro de administración de Skype Empresarial**.
    
3. Con el **Centro de administración de Skype Empresarial** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación: 
    
     `https://admin0a.online.lync.com`
    
5. Anexe la cadena siguiente a la URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    La dirección URL resultante, que es el valor de la **HostedMigrationOverrideUrl**, debe tener el siguiente aspecto:
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]
    > El tamaño máximo por defecto de los archivos de registro de la transacción de la base de datos rtcxds es de 16 GB. Esto no puede suficientemente grande si va a mover un gran número de usuarios a la vez, especialmente si se ha habilitado un reflejo. Para solucionarlo, puede aumentar el tamaño del archivo o hacer regularmente una copia de seguridad de los archivos de registro. Para obtener más información, consulte [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725). 
  
8. Este paso es opcional. Si tiene que llevar a cabo la integración con Exchange 2013 Online, tendrá que usar un proveedor de hospedaje adicional. Para obtener información detallada, vea [Configurar la integración entre locales Skype para Business Server 2015 y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).
    
9. Ahora se han movido los usuarios. Para comprobar si un usuario tiene valores correctos para los atributos que se muestran en la tabla siguiente, escriba este cmdlet: 
    
  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|**Atributo de Active Directory**|**Nombre del atributo**|**Valor correcto para el usuario en línea**|**Valor correcto para usuarios locales**|
|:-----|:-----|:-----|:-----|
|msRTCSIP-DeploymentLocator  <br/> |HostingProvider  <br/> |sipfed.Online.Lync.com  <br/> |SRV:  <br/> |
|msRTCSIP-PrimaryUserAddress  <br/> |Dirección SIP  <br/> |SIP:username@contoso.com  <br/> |SIP:username@contoso.com  <br/> |
|sRTCSIP-UserEnabled  <br/> |Habilitado  <br/> |True  <br/> |True  <br/> |
   
10. Todos los usuarios movidos tendrán que cerrar la sesión y volver a iniciar la sesión. Al hacerlo, tendrán que verificar sus listas de contactos y agregar contactos si es necesario.
    
    Tenga en cuenta que las reuniones programadas no se migran del modo en línea al local. Los usuarios tendrán que volver a programar las reuniones una vez movidos.
    
    Una vez que se actualizan los registros DNS y todos los usuarios se dirigen a los locales, el atributo HostingProvider dirige al usuario a utilizar registros SRV o dirigirlos al proveedor en línea "sipfed.online.lync.com".
    
## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a>Mover los usuarios en línea (que eran originalmente en instalaciones) en locales
<a name="BKMK_originallyonprem"> </a>

Esta sección sólo se aplica a los usuarios que se crearon y habilitados para una implementación local y pasarlos de una implementación de local a en línea. 
  
- Ejecute los siguientes cmdlets para mover un usuario de Skype para los negocios en línea a locales, reemplazando el valor de los parámetros de **identidad** y **destino** corregir valores para su entorno:
    
  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL para el grupo de servidores donde se ejecuta el servicio alojado de migración, en el formato siguiente:
  
 _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_. Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365

1. Inicie sesión en el inquilino de Office 365 como administrador.
    
2. Abra el **Centro de administración de Skype Empresarial**.
    
3. Con el **Centro de administración de Skype Empresarial** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación: 
    
     `https://admin0a.online.lync.com`
    
5. Anexe la cadena siguiente a la URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    La dirección URL resultante, que es el valor de la **HostedMigrationOverrideUrl**, debe tener el siguiente aspecto:
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

