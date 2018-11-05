---
title: Migrar usuarios de Lync Online a Lync local
TOCTitle: Migrar usuarios de Lync Online a Lync local
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62247379
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar usuarios de Lync Online a Lync local

 

_**Última modificación del tema:** 2016-12-08_

> [!IMPORTANT]  
> Estos pasos solo son necesarios para migrar cuentas de usuario habilitadas originalmente para Lync en Lync Online antes de la implementación de Lync local. Para mover usuarios habilitados originalmente para Lync local y que posteriormente se movieron a Lync Online, vea <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administrar usuarios en una implementación híbrida de Lync Server 2013</a>.<br />
> Además, todos los usuarios que se muevan deberán tener cuentas en Active Directory local.


## Migrar cuentas de usuario originalmente habilitadas en Lync Online a Lync local

1.  En primer lugar, asegúrese de que su organización está configurada para implementaciones híbridas.
    
      - Instale la Herramienta de sincronización de Windows Azure Active Directory. Para obtener más información, vea <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Para habilitar a los usuarios para que usen el inicio de sesión único en Lync Online, instale los Servicios de federación de Active Directory <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.
    
      - En la implementación local, en Shell de administración de Lync Server, escriba los siguientes cmdlets para crear el proveedor de hospedaje para Lync Online:
        
        ```
        Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
        ```
        ```
        New-CSHostingProvider -Identity LyncOnline -Name LyncOnlin -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
        ```

2.  Confirme que, en sus servidores perimetrales locales, tiene la cadena de certificados que permite la conexión a Lync Online, como se muestra en la tabla siguiente. Puede descargar la cadena aquí: [https://corp.sts.microsoft.com/Onboard/ADFS\_Onboarding\_Pack/corp\_sts\_certs.zip](https://corp.sts.microsoft.com/onboard/adfs_onboarding_pack/corp_sts_certs.zip) .
    
    
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

5.  Actualice algunos registros de DNS para dirigir todo el tráfico SIP a Lync local:
    
      - Actualice el registro A **lyncdiscover.contoso.com** para que señale el FQDN del servidor proxy inverso local.
    
      - Actualice el registro SRV ***\_sip*.\_tls.contoso.com** para que se convierta en la dirección VIP o IP pública del servicio perimetral de acceso de Lync local.
    
      - Actualice el registro SRV ***\_sipfederationtls*.\_tcp.contoso.com** para que se convierta en la dirección VIP o IP pública del servicio perimetral de acceso de Lync local.
    
      - Si su organización usa DNS dividido (a veces denominado “DNS de horizonte dividido”), asegúrese de que los usuarios que están convirtiendo nombres mediante la zona de DNS interna se dirigen al conjunto front-end.

6.  Escriba el cmdlet `Get-CsUser` para comprobar algunas propiedades sobre los usuarios que va a mover. Debe asegurarse de que el FQDN del servidor proxy del proveedor de hospedaje está definido a `"sipfed.online.lync.com"` y que las direcciones SIP están bien configuradas.

7.  Mueva a los usuarios de Lync Online a Lync local.
    
    Para mover un solo usuario, escriba lo siguiente:
    
    ```
    $cred = Get-Credential
    ```
    ```
    Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
    ```
    
    Para mover varios usuarios, use el cmdlet **Get-CsUSer** con el parámetro –Filter para seleccionar a los usuarios con una propiedad concreta. Por ejemplo, para seleccionar a todos los usuarios de Lync Online, filtre por {Hosting Provider –eq “sipfed.online.lync.om”}. A continuación, puede transferir los usuarios devueltos al cmdlet **Move-CsUSer**, como se muestra a continuación.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** tiene que ser la URL del grupo en el que se está ejecutando el servicio de migración hospedada y tiene que tener el siguiente formato: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.
    
    Para determinar la URL del servicio de migración hospedada, consulte la URL del Panel de control de Lync Online de su cuenta de inquilino de Office 365.
    
    ## Para determinar la URL al servicio de migración hospedado de su inquilino Office 365
    
    1.  Inicie sesión en el inquilino de Office 365 como administrador.
    
    2.  Abra el **Centro de administración de Lync**.
    
    3.  Con el **Centro de administración de Lync** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Sustituya **webdir** en la URL por **admin**. Quedará como a continuación:
        
        `https://admin0a.online.lync.com`
    
    5.  Anexe la cadena siguiente a la URL: **/MigraciónHospedada/ServicioDeMigraciónHospedada.svc**.
        
        La URL resultante, que es el valor de **HostedMigrationOverrideUrl**, debe ser como la siguiente:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

    > [!NOTE]
    > El tamaño máximo por defecto de los archivos de registro de la transacción de la base de datos rtcxds es de 16 GB. Puede que no sea lo suficiente grande para mover un gran número de usuarios a la vez, especialmente si la creación de reflejos está habilitada. Para solucionarlo, puede aumentar el tamaño del archivo o hacer regularmente una copia de seguridad de los archivos de registro. Para obtener más información, vea <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.



8.  Este paso es opcional. Si tiene que llevar a cabo la integración con Exchange 2013 Online, tendrá que usar un proveedor de hospedaje adicional. Para obtener información, vea [Configuración de la integración local de Lync Server 2013 con Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

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
    <th>Valor correcto para los usuarios de Lync local</th>
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
    <td><p>sRTCSIP-UserEnabled</p></td>
    <td><p>Habilitado</p></td>
    <td><p>Verdadero</p></td>
    <td><p>Verdadero</p></td>
    </tr>
    </tbody>
    </table>


10. Todos los usuarios movidos tendrán que cerrar la sesión de Lync y volver a iniciar la sesión. Al hacerlo, tendrán que verificar sus listas de contactos y agregar contactos si es necesario.
    
    Tenga en cuenta que las reuniones programadas no se migran de Lync Online a Lync local. Los usuarios tendrán que volver a programar las reuniones una vez movidos.
    
    Después de actualizar los registros de DNS y de dirigir a todos los usuarios a Lync local, el atributo Proveedor de hospedaje dirige al usuario de Lync a usar los registros SRV o al proveedor en línea “sipfed.online.lync.com.”

