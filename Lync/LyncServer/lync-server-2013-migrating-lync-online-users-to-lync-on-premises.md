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

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="ff893-102">Migrar usuarios de Lync Online a Lync local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff893-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff893-103">_**Última modificación del tema:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="ff893-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="ff893-104">Estos pasos solo son necesarios para migrar cuentas de usuario habilitadas originalmente para Lync en Lync Online, antes de implementar Lync local.</span><span class="sxs-lookup"><span data-stu-id="ff893-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="ff893-105">Para mover los usuarios que se habilitaron originalmente para Lync local y, posteriormente, se movieron a Lync Online, consulte <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a Hybrid Lync Server 2013 Deployment</A>.</span><span class="sxs-lookup"><span data-stu-id="ff893-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="ff893-106">Además, todos los usuarios que se van a mover deben tener cuentas en Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="ff893-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="ff893-107">Migrar cuentas de usuario habilitadas originalmente en Lync Online a Lync local</span><span class="sxs-lookup"><span data-stu-id="ff893-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="ff893-108">En primer lugar, asegúrese de que su organización está configurada para entornos híbridos.</span><span class="sxs-lookup"><span data-stu-id="ff893-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="ff893-109">Instale la herramienta de sincronización de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff893-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="ff893-110">Para más información, vea <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span><span class="sxs-lookup"><span data-stu-id="ff893-110">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="ff893-111">Para permitir que los usuarios usen el inicio de sesión único para Lync Online, instale los servicios <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>de Federación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff893-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="ff893-112">En la implementación local, en Shell de administración de Lync Server, escriba los siguientes cmdlets para crear el proveedor de hospedaje para Lync Online:</span><span class="sxs-lookup"><span data-stu-id="ff893-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="ff893-113">Confirme que, en los servidores perimetrales locales, tiene la cadena de certificados que permite la conexión con Lync Online, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="ff893-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="ff893-114">Puede descargar esta cadena aquí:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="ff893-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ff893-115">Certificado</span><span class="sxs-lookup"><span data-stu-id="ff893-115">Certificate</span></span></th>
    <th><span data-ttu-id="ff893-116">Almacén de certificado</span><span class="sxs-lookup"><span data-stu-id="ff893-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ff893-117">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="ff893-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="ff893-118">Entidad de certificación raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="ff893-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ff893-119">Entidad de Microsoft Internet (nuevo certificado de CA)</span><span class="sxs-lookup"><span data-stu-id="ff893-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="ff893-120">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="ff893-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ff893-121">MSIT CA2 de autenticación del equipo (nueva CA2 de emisión)</span><span class="sxs-lookup"><span data-stu-id="ff893-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="ff893-122">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="ff893-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="ff893-123">En su Active Directory local, habilite las cuentas de usuario afectadas para Lync local.</span><span class="sxs-lookup"><span data-stu-id="ff893-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="ff893-124">Puede hacerlo para un usuario individual; para ello, escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ff893-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="ff893-125">O bien, puede crear un script que lea los nombres de usuario de un archivo y los proporcione como entrada al cmdlet enable-CsUser:</span><span class="sxs-lookup"><span data-stu-id="ff893-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="ff893-126">Ejecute DirSync para sincronizar los usuarios de Lync Online con los usuarios locales de Lync actualizados.</span><span class="sxs-lookup"><span data-stu-id="ff893-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="ff893-127">Actualice algunos registros DNS para dirigir todo el tráfico SIP a Lync local:</span><span class="sxs-lookup"><span data-stu-id="ff893-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="ff893-128">Actualice el registro a de **lyncdiscover.contoso.com** para que apunte al FQDN del servidor proxy inverso local.</span><span class="sxs-lookup"><span data-stu-id="ff893-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="ff893-129">Actualice el \*\**\_SIP *.\_ tls.contoso.com** registro SRV para resolver la dirección IP o VIP pública del servicio perimetral de acceso de Lync local.</span><span class="sxs-lookup"><span data-stu-id="ff893-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="ff893-130">Actualice \*\**\_sipfederationtls *.\_ tcp.contoso.com** registro SRV para resolver la dirección IP o VIP pública del servicio perimetral de acceso de Lync local.</span><span class="sxs-lookup"><span data-stu-id="ff893-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="ff893-131">Si su organización usa DNS dividido (a veces denominado "DNS de horizonte dividido"), asegúrese de que los usuarios que resuelven nombres a través de la zona DNS interna se dirigen al grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="ff893-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="ff893-132">Escriba el `Get-CsUser` cmdlet para comprobar algunas propiedades sobre los usuarios que va a mover.</span><span class="sxs-lookup"><span data-stu-id="ff893-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="ff893-133">Desea asegurarse de que FQDN se establece en `"sipfed.online.lync.com"` y que las direcciones SIP se establecen correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff893-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="ff893-134">Mueva los usuarios de Lync Online a Lync local.</span><span class="sxs-lookup"><span data-stu-id="ff893-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="ff893-135">Para mover un solo usuario, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff893-135">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="ff893-136">Puede mover varios usuarios mediante el cmdlet **Get-CsUSer** con el parámetro – filter para seleccionar los usuarios con una propiedad específica.</span><span class="sxs-lookup"><span data-stu-id="ff893-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="ff893-137">Por ejemplo, puede seleccionar todos los usuarios de Lync Online filtrando {Hosting Provider – EQ "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="ff893-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="ff893-138">A continuación, puede canalizar los usuarios devueltos al cmdlet **Move-CsUSer** , tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="ff893-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="ff893-139">El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la URL del grupo en el que se ejecuta el servicio de migración hospedado, con el siguiente formato: *https://\<grupo de FQDN\>/HostedMigration/hostedmigrationService.SVC*.</span><span class="sxs-lookup"><span data-stu-id="ff893-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="ff893-140">Para determinar la dirección URL del servicio de migración hospedado, vea la dirección URL del panel de control de Lync Online para su cuenta de inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ff893-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="ff893-141">Para determinar la dirección URL del servicio de migración hospedado de su inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="ff893-141">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>
    
    1.  <span data-ttu-id="ff893-142">Inicie sesión en su inquilino de Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="ff893-142">Login to your Office 365 tenant as an administrator.</span></span>
    
    2.  <span data-ttu-id="ff893-143">Abra el **centro de administración de Lync**.</span><span class="sxs-lookup"><span data-stu-id="ff893-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="ff893-144">Con el **centro de administración de Lync** mostrado, seleccione y copie la dirección URL en la barra de direcciones hasta **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="ff893-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="ff893-145">Una dirección URL de ejemplo tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff893-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="ff893-146">Reemplace **webdir** en la dirección URL con **admin**, lo que dará como resultado lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff893-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="ff893-147">Anexe la cadena siguiente a la dirección URL: **/HostedMigration/hostedmigrationservice.SVC**.</span><span class="sxs-lookup"><span data-stu-id="ff893-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="ff893-148">La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff893-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="ff893-149">El tamaño máximo predeterminado para los archivos de registro de transacciones de la base de datos rtcxds es de 16 GB.</span><span class="sxs-lookup"><span data-stu-id="ff893-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="ff893-150">Es posible que esto no sea lo suficientemente grande como para mover un gran número de usuarios a la vez, especialmente si está habilitada la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="ff893-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="ff893-151">Para solucionarlo, puede aumentar el tamaño del archivo o hacer una copia de seguridad de los archivos de registro con regularidad.</span><span class="sxs-lookup"><span data-stu-id="ff893-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="ff893-152">Para obtener más información, <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>consulte.</span><span class="sxs-lookup"><span data-stu-id="ff893-152">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="ff893-153">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="ff893-153">This is an optional step.</span></span> <span data-ttu-id="ff893-154">Si necesita integrarse con Exchange 2013 online, debe usar un proveedor de hospedaje adicional.</span><span class="sxs-lookup"><span data-stu-id="ff893-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="ff893-155">Para obtener más información, consulte [Configuring on-premises Lync Server 2013 Integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="ff893-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="ff893-156">Los usuarios se moverán ahora.</span><span class="sxs-lookup"><span data-stu-id="ff893-156">The users are now moved.</span></span> <span data-ttu-id="ff893-157">Para comprobar que un usuario tiene los valores correctos para los atributos que se muestran en la tabla siguiente, escriba este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ff893-157">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
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
    <th><span data-ttu-id="ff893-158">Atributo de Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff893-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="ff893-159">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="ff893-159">Attribute name</span></span></th>
    <th><span data-ttu-id="ff893-160">Valor correcto para el usuario de Lync Online</span><span class="sxs-lookup"><span data-stu-id="ff893-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="ff893-161">Valor correcto para los usuarios de Lync local</span><span class="sxs-lookup"><span data-stu-id="ff893-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ff893-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="ff893-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="ff893-163">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="ff893-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="ff893-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff893-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="ff893-165">SRV</span><span class="sxs-lookup"><span data-stu-id="ff893-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ff893-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="ff893-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="ff893-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="ff893-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="ff893-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff893-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="ff893-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff893-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ff893-170">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="ff893-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="ff893-171">Habilitado</span><span class="sxs-lookup"><span data-stu-id="ff893-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="ff893-172">True</span><span class="sxs-lookup"><span data-stu-id="ff893-172">True</span></span></p></td>
    <td><p><span data-ttu-id="ff893-173">True</span><span class="sxs-lookup"><span data-stu-id="ff893-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="ff893-174">Cada usuario que se haya movido tendrá que cerrar sesión en Lync y, a continuación, volver a iniciarla.</span><span class="sxs-lookup"><span data-stu-id="ff893-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="ff893-175">Cuando inicien sesión, deben comprobar sus listas de contactos y agregar contactos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ff893-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="ff893-176">Tenga en cuenta que las reuniones programadas no se migran de Lync Online a Lync local.</span><span class="sxs-lookup"><span data-stu-id="ff893-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="ff893-177">Los usuarios tendrán que volver a programar estas reuniones después de que se muevan.</span><span class="sxs-lookup"><span data-stu-id="ff893-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="ff893-178">Una vez que se actualizan los registros DNS y todos los usuarios se dirigen a su estado local, el atributo hospedaje dirige al usuario de Lync para que use los registros SRV o los dirija al proveedor en línea "sipfed.online.lync.com".</span><span class="sxs-lookup"><span data-stu-id="ff893-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

