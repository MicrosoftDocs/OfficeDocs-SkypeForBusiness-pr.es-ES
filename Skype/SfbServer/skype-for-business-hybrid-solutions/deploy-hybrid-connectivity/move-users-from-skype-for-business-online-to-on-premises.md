---
title: Mover usuarios de Skype para empresarial en línea para local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Resumen: Obtenga información sobre cómo mover las cuentas de usuario de en línea para localmente en Skype para Business Server.'
ms.openlocfilehash: 098dc36e6551839d599042993b156073197753ec
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21025684"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a>Mover usuarios de Skype para empresarial en línea para local
 
**Resumen:** Obtenga información sobre cómo mover las cuentas de usuario de en línea para localmente en Skype para Business Server.
  
Debe mover las cuentas de usuario de en línea para local para asegurarse de que los usuarios alojados en línea y local son detectables entre sí. Para ser detectable entre sí, todos los usuarios deben tener una presencia en el Active Directory local. Para obtener más información, consulte [Plan de conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md). Es posible que desee mover los usuarios en línea en local, por ejemplo, si: 
  
- Tener nuevos usuarios que necesiten ser creado en local y, a continuación, se mueve a la nube.
    
- Su organización implementa Skype para en línea de negocio antes de que implemente Skype para Business Server. Por lo tanto, tiene los usuarios que se crearon en la nube en primer lugar y ahora necesita va a mover a local antes de mover a Skype para profesionales en línea. 
    
En este tema se describe dos escenarios:
  
- [Mover usuarios en línea, que estaba conectado originalmente — a local](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)
    
- [Mover en línea a los usuarios (que eran originalmente en local) local](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)
    
## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a>Mover usuarios en línea, que estaba conectado originalmente — a local
<a name="BKMK_originallyonline"> </a>

En esta sección se aplica sólo a los usuarios que se han creado y habilitado en línea, pero que no tienen una cuenta en las instalaciones en Active Directory. 
  
Antes de empezar a mover usuarios en línea a su entorno local, compruebe que se cumplan las condiciones siguientes:
  
- Su entorno local necesita estar completamente implementado y validado. Para obtener más información, vea [implementación de Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) o [Implementar Skype para Business Server 2015](../../deploy/deploy.md), dependiendo de la versión que está utilizando en local. 
    
- El inquilino online debe configurarse para el acceso remoto de PowerShell.
    
    Para ello, instale primero la Skype para el módulo del conector en línea de negocio para Windows PowerShell, que se puede obtener aquí: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
    
    Después de instalar el módulo, puede establecer una sesión remota escribiendo los siguientes cmdlets en el Skype para Shell de administración de servidor empresarial:
    
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

    Para obtener más información acerca del uso de PowerShell con Skype para profesionales en línea, vea [Configurar el equipo de Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
- El inquilino online debe configurarse para un espacio de direcciones SIP compartido. Para ello, inicie primero una sesión remota de Powershell con Skype para profesionales en línea. Luego, ejecute el cmdlet siguiente:
    
  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > Las necesidades de atributo SharedSipAddressSpace permanezca "True" hasta que mover a en línea es final y no a los usuarios permanecen en local. 
  
Una vez que haya terminado de estos pasos, puede migrar las cuentas de usuario tal como se describe en el procedimiento siguiente:
  
### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a>Mover cuentas de usuario originalmente habilitadas en línea para una implementación local

1. En primer lugar, asegúrese de que su organización está configurada para implementaciones híbridas, incluidos Azure Active Directory Connect y las herramientas de sincronización. Para obtener más información, consulte [Plan de conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
    
  - En la implementación local, en la Skype para Shell de administración de servidor empresarial, escriba los siguientes cmdlets para crear el proveedor de hospedaje de Skype para profesionales en línea. Puede usar cualquier valor que desee para los parámetros Identidad y Nombre.
    
  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. Confirme que en los servidores perimetrales local, tiene la cadena de certificados que permite la conexión a Skype para en línea de negocio, tal como se muestra en la siguiente tabla. Puede descargar esta cadena aquí: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).
    
|**Certificado**|**Almacén de certificado**|
|:-----|:-----|
|Baltimore CyberTrust Root  <br/> |CA raíz de confianza  <br/> |
|Microsoft Internet Authority (nuevo certificado CA)  <br/> |CA intermedia  <br/> |
|MSIT Machine Auth CA2 (nueva CA2 de emisión)  <br/> |CA intermedia  <br/> |
   
3. En su Active Directory local, habilite las cuentas de usuario afectado de Skype para Business Server 2015 local. Para hacerlo para un usuario individual, escriba el cmdlet siguiente: 
    
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

4. Sincronización de los usuarios en línea con los usuarios actualizado local. Para obtener más información, vea [Herramientas de integración de Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=530320).
    
5. Actualizar los siguientes registros DNS para dirigir todo el tráfico SIP a la implementación local:
    
  - Actualice el registro A **lyncdiscover.contoso.com** para que apunte al FQDN del servidor proxy inverso local.
    
  - Actualización de la ** *_sip* . _tls.contoso.com** registro SRV para resolver en la dirección IP o la dirección VIP pública del servicio de servidor perimetral de acceso de Lync local.
    
  - Actualización de la ** *_sipfederationtls* . _tcp.contoso.com** registro SRV para resolver en la dirección IP o la dirección VIP pública del servicio de servidor perimetral de acceso de Skype para Business Server 2015 local.
    
  - Si su organización utiliza divididas de DNS (a veces denominado "split-brain DNS"), asegúrese de que se dirigen a los usuarios resolución de nombres a través de la zona DNS interna para el grupo de servidores Front-End.
    
6. Tipo de la `Get-CsUser` cmdlet para comprobar algunas propiedades acerca de los usuarios que se va a mover. Necesita asegurarse de que el FQDN del servidor proxy del proveedor de hospedaje está definido a `"sipfed.online.lync.com"` y que las direcciones SIP están bien configuradas.
    
7. Mover los usuarios en línea en local.
    
    Para mover un solo usuario, escriba lo siguiente:
    
  ```
  $cred = Get-Credential
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    Puede mover varios usuarios mediante el cmdlet **Get-CsUSer** -el parámetro Filter para seleccionar los usuarios con una propiedad concreta. Por ejemplo, puede seleccionar todos los usuarios en línea mediante el filtrado para {proveedor de hospedaje - eq "sipfed.online.lync.om"}. A continuación, se pueden canalizar los usuarios devueltos al cmdlet **Move-CsUSer** , tal y como se muestra a continuación.
    
  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL para el grupo de servidores donde se ejecuta el servicio de migración hospedado, en el siguiente formato: _Https://\<FQDN del grupo de servidores\>/HostedMigration/ hostedmigrationService.svc_.
    
    Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.
    
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365

1. Inicie sesión en el inquilino de Office 365 como administrador.
    
2. Abra el **Centro de administración de Skype Empresarial**.
    
3. Con el **Centro de administración de Skype Empresarial** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación: 
    
     `https://admin0a.online.lync.com`
    
5. Anexe la cadena siguiente a la URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    La dirección URL resultante, que es el valor de la **HostedMigrationOverrideUrl**, debe tener un aspecto similar al siguiente:
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]
    > El tamaño máximo por defecto de los archivos de registro de la transacción de la base de datos rtcxds es de 16 GB. Esto no sea lo suficientemente grande si va a mover un gran número de usuarios a la vez, especialmente si dispone de la creación de reflejos habilitado. Para solucionarlo, puede aumentar el tamaño del archivo o hacer regularmente una copia de seguridad de los archivos de registro. Para obtener más información, consulte [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725). 
  
8. Este paso es opcional. Si tiene que llevar a cabo la integración con Exchange 2013 Online, tendrá que usar un proveedor de hospedaje adicional. Para obtener información detallada, vea [Configurar la integración entre local Skype para Business Server 2015 y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).
    
9. Ahora se han movido los usuarios. Para comprobar si un usuario tiene valores correctos para los atributos que se muestran en la tabla siguiente, escriba este cmdlet: 
    
  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|**Atributo de Active Directory**|**Nombre del atributo**|**Valor correcto para el usuario en línea**|**Valor correcto para los usuarios locales**|
|:-----|:-----|:-----|:-----|
|msRTCSIP-DeploymentLocator  <br/> |HostingProvider  <br/> |sipfed.Online.Lync.com  <br/> |SRV:  <br/> |
|msRTCSIP-PrimaryUserAddress  <br/> |Dirección SIP  <br/> |SIP:username@contoso.com  <br/> |SIP:username@contoso.com  <br/> |
|sRTCSIP-UserEnabled  <br/> |Habilitado  <br/> |True  <br/> |True  <br/> |
   
10. Todos los usuarios movidos tendrán que cerrar la sesión y volver a iniciar la sesión. Al hacerlo, tendrán que verificar sus listas de contactos y agregar contactos si es necesario.
    
    Tenga en cuenta que las reuniones programadas no se migran del modo en línea al local. Los usuarios tendrán que volver a programar las reuniones una vez movidos.
    
    Una vez que se actualizan los registros DNS y todos los usuarios se dirigen a local, el atributo HostingProvider dirige al usuario a utilizar registros SRV o dirigirlos al proveedor en línea "sipfed.online.lync.com."
    
## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a>Mover en línea a los usuarios (que eran originalmente en local) local
<a name="BKMK_originallyonprem"> </a>

En esta sección se aplica sólo a los usuarios que se han creado y habilitados para una implementación local y, a continuación, se mueve de una implementación de local a en línea. 
  
- Ejecute los siguientes cmdlets para mover un usuario de Skype para profesionales en línea de vuelta a local, reemplazando el valor de los parámetros **Identity** y **destino** corregir los valores para el entorno:
    
  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL para el grupo de servidores donde se ejecuta el servicio de migración hospedado, en el siguiente formato:
  
 _Https://\<FQDN de grupo de\>/HostedMigration/hostedmigrationService.svc_. Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365

1. Inicie sesión en el inquilino de Office 365 como administrador.
    
2. Abra el **Centro de administración de Skype Empresarial**.
    
3. Con el **Centro de administración de Skype Empresarial** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación: 
    
     `https://admin0a.online.lync.com`
    
5. Anexe la cadena siguiente a la URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    La dirección URL resultante, que es el valor de la **HostedMigrationOverrideUrl**, debe tener un aspecto similar al siguiente:
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

