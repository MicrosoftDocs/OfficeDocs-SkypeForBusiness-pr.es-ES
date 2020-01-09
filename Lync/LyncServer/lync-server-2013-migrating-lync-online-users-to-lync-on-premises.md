---
title: 'Lync Server 2013: migración de usuarios de Lync Online a Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47fb8d24a2bb112ab07d35097414141b9eaaa606
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Migrar usuarios de Lync Online a Lync local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Estos pasos solo son necesarios para migrar cuentas de usuario que se han habilitado originalmente para Lync en Lync Online, antes de implementar Lync local. Para mover los usuarios que se habilitaron originalmente para Lync local y, después, se movieron a Lync Online, vea <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">administrar usuarios en una implementación híbrida de Lync Server 2013</A>.<BR>Además, todos los usuarios que se muevan necesitarán tener cuentas en Active Directory local.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Migrar cuentas de usuario originalmente habilitadas en Lync Online a Lync local

1.  En primer lugar, asegúrese de que su organización está configurada para una implementación híbrida.
    
      - Instale la herramienta de sincronización de Azure Active Directory. Para obtener más información, <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>consulte.
    
      - Para permitir a los usuarios usar el inicio de sesión único en Lync Online, instale los servicios <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>de Federación de Active Directory.
    
      - En la implementación local, en el shell de administración de Lync Server, escriba los siguientes cmdlets para crear el proveedor de hospedaje para Lync Online:
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Confirme que, en los servidores perimetrales locales, tiene la cadena de certificados que habilita la conexión a Lync Online, como se muestra en la tabla siguiente. Puede descargar esta cadena aquí:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


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
    <td><p>CA raíz de confianza</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet Authority (nuevo certificado CA)</p></td>
    <td><p>CA intermedia</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine Auth CA2 (nueva CA2 de emisión)</p></td>
    <td><p>CA intermedia</p></td>
    </tr>
    </tbody>
    </table>

3.  En su Active Directory local, habilite las cuentas de usuario afectadas para Lync local. Para hacerlo para un usuario individual, escriba el cmdlet siguiente:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    También puede crear un script que lea los nombres de usuario de un archivo y los indique como entrada al cmdlet Enable-CsUser cmdlet:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Ejecute DirSync para sincronizar los usuarios de Lync Online con los usuarios de Lync local actualizados.

5.  Actualice algunos registros DNS para dirigir todo el tráfico SIP a Lync local:
    
      - Actualice el registro A **lyncdiscover.contoso.com** para que apunte al FQDN del servidor proxy inverso local.
    
      - Actualiza el ***\_SIP *.\_ **registro SRV de TLS.contoso.com para resolver la dirección IP pública o VIP del servicio perimetral de acceso de Lync local.
    
      - Actualice ***\_sipfederationtls *.\_ **registro SRV de TCP.contoso.com para resolver la dirección IP pública o VIP del servicio perimetral de acceso de Lync local.
    
      - Si su organización usa DNS dividido (a veces denominado “DNS de horizonte dividido”), asegúrese de que los usuarios que están convirtiendo nombres por medio de la zona de DNS interna se dirigen al conjunto front-end.

6.  Escriba el `Get-CsUser` cmdlet para comprobar algunas propiedades sobre los usuarios que va a mover. Desea asegurarse de que el HostingProviderProxyFQDN esté establecido en `"sipfed.online.lync.com"` y de que las direcciones SIP se hayan establecido correctamente.

7.  Mueva los usuarios de Lync Online a Lync local.
    
    Para mover un solo usuario, escriba lo siguiente:
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    Para mover varios usuarios, use el cmdlet **Get-CsUSer** con el parámetro –Filter para seleccionar a los usuarios con una propiedad concreta. Por ejemplo, puede seleccionar todos los usuarios de Lync Online filtrando por {proveedor de hospedaje – EQ "sipfed.online.lync.om"}. Luego, puede transferir los usuarios devueltos al cmdlet **Move-CsUSer**, como se muestra a continuación.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL del grupo en el que se está ejecutando el servicio de migración hospedada, en el siguiente formato: *https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.SVC*.
    
    Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365
    
    1.  Inicie sesión en el inquilino de Office 365 como administrador.
    
    2.  Abra el **centro de administración de Lync**.
    
    3.  Con el **centro de administración de Lync** mostrado, seleccione y copie la dirección URL en la barra de direcciones hasta **Lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación:
        
        `https://admin0a.online.lync.com`
    
    5.  Anexe la cadena siguiente a la URL: **/MigraciónHospedada/ServicioDeMigraciónHospedada.svc**.
        
        La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, necesita ser como la siguiente:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > El tamaño máximo por defecto de los archivos de registro de la transacción de la base de datos rtcxds es de 16 GB. Puede que no sea lo suficiente grande para mover un gran número de usuarios a la vez, especialmente si la creación de reflejos está habilitada. Para solucionarlo, puede aumentar el tamaño del archivo o hacer regularmente una copia de seguridad de los archivos de registro. Para obtener más información, <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>consulte.

    
    </div>

8.  Este paso es opcional. Si tiene que llevar a cabo la integración con Exchange 2013 Online, tendrá que usar un proveedor de hospedaje adicional. Para obtener información detallada, consulte [configuración de la integración de Lync Server 2013 con Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Ahora se han movido los usuarios. Para comprobar si un usuario tiene valores correctos para los atributos que se muestran en la tabla siguiente, escriba este cmdlet:
    
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
    <th>Valor correcto para usuarios locales de Lync</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>Proveedor de hospedaje</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV:</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>Dirección SIP</p></td>
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


10. Cada usuario que se haya movido necesitará cerrar sesión en Lync y, a continuación, volver a iniciar sesión. Al hacerlo, tendrán que verificar sus listas de contactos y agregar contactos si es necesario.
    
    Tenga en cuenta que las reuniones programadas no se migran de Lync Online a Lync local. Los usuarios tendrán que volver a programar las reuniones una vez movidos.
    
    Después de que se actualicen los registros DNS y de que todos los usuarios se dirijan a local, el atributo Hostingprovider manda indica al usuario de Lync que use registros SRV o los dirija al proveedor en línea "sipfed.online.lync.com".

</div>

</div>

<span> </span>

</div>

</div>

</div>

