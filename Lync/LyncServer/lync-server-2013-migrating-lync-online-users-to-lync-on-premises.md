---
title: 'Lync Server 2013: migración de usuarios de Lync Online a Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07a333eeb794a27ca78b1f6d8c9bf71c386c8a92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Migrar usuarios de Lync Online a Lync local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Estos pasos solo son necesarios para migrar cuentas de usuario habilitadas originalmente para Lync en Lync Online, antes de implementar Lync local. Para mover los usuarios que se habilitaron originalmente para Lync local y, posteriormente, se movieron a Lync Online, consulte <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a Hybrid Lync Server 2013 Deployment</A>.<BR>Además, todos los usuarios que se van a mover deben tener cuentas en Active Directory local.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Migrar cuentas de usuario habilitadas originalmente en Lync Online a Lync local

1.  En primer lugar, asegúrese de que su organización está configurada para entornos híbridos.
    
      - Instale la herramienta de sincronización de Azure Active Directory. Para más información, vea <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Para permitir que los usuarios usen el inicio de sesión único para Lync Online, instale los servicios <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>de Federación de Active Directory.
    
      - En la implementación local, en Shell de administración de Lync Server, escriba los siguientes cmdlets para crear el proveedor de hospedaje para Lync Online:
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Confirme que, en los servidores perimetrales locales, tiene la cadena de certificados que permite la conexión con Lync Online, como se muestra en la siguiente tabla. Puede descargar esta cadena aquí:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Certificado</th>
    <th>Almacén de certificado</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>Entidad de certificación raíz de confianza</p></td>
    </tr>
    <tr class="even">
    <td><p>Entidad de Microsoft Internet (nuevo certificado de CA)</p></td>
    <td><p>CA intermedia</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT CA2 de autenticación del equipo (nueva CA2 de emisión)</p></td>
    <td><p>CA intermedia</p></td>
    </tr>
    </tbody>
    </table>

3.  En su Active Directory local, habilite las cuentas de usuario afectadas para Lync local. Puede hacerlo para un usuario individual; para ello, escriba el siguiente cmdlet:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    O bien, puede crear un script que lea los nombres de usuario de un archivo y los proporcione como entrada al cmdlet enable-CsUser:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Ejecute DirSync para sincronizar los usuarios de Lync Online con los usuarios locales de Lync actualizados.

5.  Actualice algunos registros DNS para dirigir todo el tráfico SIP a Lync local:
    
      - Actualice el registro a de **lyncdiscover.contoso.com** para que apunte al FQDN del servidor proxy inverso local.
    
      - Actualice el ***\_SIP *.\_ tls.contoso.com** registro SRV para resolver la dirección IP o VIP pública del servicio perimetral de acceso de Lync local.
    
      - Actualice ***\_sipfederationtls *.\_ tcp.contoso.com** registro SRV para resolver la dirección IP o VIP pública del servicio perimetral de acceso de Lync local.
    
      - Si su organización usa DNS dividido (a veces denominado "DNS de horizonte dividido"), asegúrese de que los usuarios que resuelven nombres a través de la zona DNS interna se dirigen al grupo de servidores front-end.

6.  Escriba el `Get-CsUser` cmdlet para comprobar algunas propiedades sobre los usuarios que va a mover. Desea asegurarse de que FQDN se establece en `"sipfed.online.lync.com"` y que las direcciones SIP se establecen correctamente.

7.  Mueva los usuarios de Lync Online a Lync local.
    
    Para mover un solo usuario, escriba lo siguiente:
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    Puede mover varios usuarios mediante el cmdlet **Get-CsUSer** con el parámetro – filter para seleccionar los usuarios con una propiedad específica. Por ejemplo, puede seleccionar todos los usuarios de Lync Online filtrando {Hosting Provider – EQ "sipfed.online.lync.om"}. A continuación, puede canalizar los usuarios devueltos al cmdlet **Move-CsUSer** , tal como se muestra a continuación.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la URL del grupo en el que se ejecuta el servicio de migración hospedado, con el siguiente formato: *https://\<grupo de FQDN\>/HostedMigration/hostedmigrationService.SVC*.
    
    Para determinar la dirección URL del servicio de migración hospedado, vea la dirección URL del panel de control de Lync Online para su cuenta de inquilino de Office 365.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Para determinar la dirección URL del servicio de migración hospedado de su inquilino de Office 365
    
    1.  Inicie sesión en su inquilino de Office 365 como administrador.
    
    2.  Abra el **centro de administración de Lync**.
    
    3.  Con el **centro de administración de Lync** mostrado, seleccione y copie la dirección URL en la barra de direcciones hasta **Lync.com**. Una dirección URL de ejemplo tiene un aspecto similar al siguiente:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Reemplace **webdir** en la dirección URL con **admin**, lo que dará como resultado lo siguiente:
        
        `https://admin0a.online.lync.com`
    
    5.  Anexe la cadena siguiente a la dirección URL: **/HostedMigration/hostedmigrationservice.SVC**.
        
        La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, debe ser similar a la siguiente:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > El tamaño máximo predeterminado para los archivos de registro de transacciones de la base de datos rtcxds es de 16 GB. Es posible que esto no sea lo suficientemente grande como para mover un gran número de usuarios a la vez, especialmente si está habilitada la creación de reflejo. Para solucionarlo, puede aumentar el tamaño del archivo o hacer una copia de seguridad de los archivos de registro con regularidad. Para obtener más información, <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>consulte.

    
    </div>

8.  Este paso es opcional. Si necesita integrarse con Exchange 2013 online, debe usar un proveedor de hospedaje adicional. Para obtener más información, consulte [Configuring on-premises Lync Server 2013 Integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Los usuarios se moverán ahora. Para comprobar que un usuario tiene los valores correctos para los atributos que se muestran en la tabla siguiente, escriba este cmdlet:
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Atributo de Active Directory</th>
    <th>Nombre del atributo</th>
    <th>Valor correcto para el usuario de Lync Online</th>
    <th>Valor correcto para los usuarios de Lync local</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>Hospedaje</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP-UserEnabled</p></td>
    <td><p>Habilitado</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. Cada usuario que se haya movido tendrá que cerrar sesión en Lync y, a continuación, volver a iniciarla. Cuando inicien sesión, deben comprobar sus listas de contactos y agregar contactos si es necesario.
    
    Tenga en cuenta que las reuniones programadas no se migran de Lync Online a Lync local. Los usuarios tendrán que volver a programar estas reuniones después de que se muevan.
    
    Una vez que se actualizan los registros DNS y todos los usuarios se dirigen a su estado local, el atributo hospedaje dirige al usuario de Lync para que use los registros SRV o los dirija al proveedor en línea "sipfed.online.lync.com".

</div>

</div>

<span> </span>

</div>

</div>

</div>

