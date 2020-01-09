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

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="c72a5-102">Migrar usuarios de Lync Online a Lync local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c72a5-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c72a5-103">_**Última modificación del tema:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="c72a5-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="c72a5-104">Estos pasos solo son necesarios para migrar cuentas de usuario que se han habilitado originalmente para Lync en Lync Online, antes de implementar Lync local.</span><span class="sxs-lookup"><span data-stu-id="c72a5-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="c72a5-105">Para mover los usuarios que se habilitaron originalmente para Lync local y, después, se movieron a Lync Online, vea <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">administrar usuarios en una implementación híbrida de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c72a5-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="c72a5-106">Además, todos los usuarios que se muevan necesitarán tener cuentas en Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="c72a5-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="c72a5-107">Migrar cuentas de usuario originalmente habilitadas en Lync Online a Lync local</span><span class="sxs-lookup"><span data-stu-id="c72a5-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="c72a5-108">En primer lugar, asegúrese de que su organización está configurada para una implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="c72a5-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="c72a5-109">Instale la herramienta de sincronización de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c72a5-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="c72a5-110">Para obtener más información, <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>consulte.</span><span class="sxs-lookup"><span data-stu-id="c72a5-110">For more information, see <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="c72a5-111">Para permitir a los usuarios usar el inicio de sesión único en Lync Online, instale los servicios <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>de Federación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c72a5-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="c72a5-112">En la implementación local, en el shell de administración de Lync Server, escriba los siguientes cmdlets para crear el proveedor de hospedaje para Lync Online:</span><span class="sxs-lookup"><span data-stu-id="c72a5-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="c72a5-113">Confirme que, en los servidores perimetrales locales, tiene la cadena de certificados que habilita la conexión a Lync Online, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c72a5-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="c72a5-114">Puede descargar esta cadena aquí:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="c72a5-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c72a5-115">Certificado</span><span class="sxs-lookup"><span data-stu-id="c72a5-115">Certificate</span></span></th>
    <th><span data-ttu-id="c72a5-116">Almacén de certificado</span><span class="sxs-lookup"><span data-stu-id="c72a5-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c72a5-117">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="c72a5-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-118">CA raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="c72a5-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c72a5-119">Microsoft Internet Authority (nuevo certificado CA)</span><span class="sxs-lookup"><span data-stu-id="c72a5-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-120">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="c72a5-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c72a5-121">MSIT Machine Auth CA2 (nueva CA2 de emisión)</span><span class="sxs-lookup"><span data-stu-id="c72a5-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-122">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="c72a5-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="c72a5-123">En su Active Directory local, habilite las cuentas de usuario afectadas para Lync local.</span><span class="sxs-lookup"><span data-stu-id="c72a5-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="c72a5-124">Para hacerlo para un usuario individual, escriba el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="c72a5-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="c72a5-125">También puede crear un script que lea los nombres de usuario de un archivo y los indique como entrada al cmdlet Enable-CsUser cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c72a5-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="c72a5-126">Ejecute DirSync para sincronizar los usuarios de Lync Online con los usuarios de Lync local actualizados.</span><span class="sxs-lookup"><span data-stu-id="c72a5-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="c72a5-127">Actualice algunos registros DNS para dirigir todo el tráfico SIP a Lync local:</span><span class="sxs-lookup"><span data-stu-id="c72a5-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="c72a5-128">Actualice el registro A **lyncdiscover.contoso.com** para que apunte al FQDN del servidor proxy inverso local.</span><span class="sxs-lookup"><span data-stu-id="c72a5-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="c72a5-129">Actualiza el \*\*\*\_SIP \*.\_ \*\*registro SRV de TLS.contoso.com para resolver la dirección IP pública o VIP del servicio perimetral de acceso de Lync local.</span><span class="sxs-lookup"><span data-stu-id="c72a5-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="c72a5-130">Actualice \*\*\*\_sipfederationtls \*.\_ \*\*registro SRV de TCP.contoso.com para resolver la dirección IP pública o VIP del servicio perimetral de acceso de Lync local.</span><span class="sxs-lookup"><span data-stu-id="c72a5-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="c72a5-131">Si su organización usa DNS dividido (a veces denominado “DNS de horizonte dividido”), asegúrese de que los usuarios que están convirtiendo nombres por medio de la zona de DNS interna se dirigen al conjunto front-end.</span><span class="sxs-lookup"><span data-stu-id="c72a5-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="c72a5-132">Escriba el `Get-CsUser` cmdlet para comprobar algunas propiedades sobre los usuarios que va a mover.</span><span class="sxs-lookup"><span data-stu-id="c72a5-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="c72a5-133">Desea asegurarse de que el HostingProviderProxyFQDN esté establecido en `"sipfed.online.lync.com"` y de que las direcciones SIP se hayan establecido correctamente.</span><span class="sxs-lookup"><span data-stu-id="c72a5-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="c72a5-134">Mueva los usuarios de Lync Online a Lync local.</span><span class="sxs-lookup"><span data-stu-id="c72a5-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="c72a5-135">Para mover un solo usuario, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c72a5-135">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="c72a5-136">Para mover varios usuarios, use el cmdlet **Get-CsUSer** con el parámetro –Filter para seleccionar a los usuarios con una propiedad concreta.</span><span class="sxs-lookup"><span data-stu-id="c72a5-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="c72a5-137">Por ejemplo, puede seleccionar todos los usuarios de Lync Online filtrando por {proveedor de hospedaje – EQ "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="c72a5-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="c72a5-138">Luego, puede transferir los usuarios devueltos al cmdlet **Move-CsUSer**, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="c72a5-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="c72a5-139">El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL del grupo en el que se está ejecutando el servicio de migración hospedada, en el siguiente formato: *https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.SVC*.</span><span class="sxs-lookup"><span data-stu-id="c72a5-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="c72a5-140">Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c72a5-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="c72a5-141">Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365</span><span class="sxs-lookup"><span data-stu-id="c72a5-141">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>
    
    1.  <span data-ttu-id="c72a5-142">Inicie sesión en el inquilino de Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="c72a5-142">Login to your Office 365 tenant as an administrator.</span></span>
    
    2.  <span data-ttu-id="c72a5-143">Abra el **centro de administración de Lync**.</span><span class="sxs-lookup"><span data-stu-id="c72a5-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="c72a5-144">Con el **centro de administración de Lync** mostrado, seleccione y copie la dirección URL en la barra de direcciones hasta **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="c72a5-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="c72a5-145">Una dirección URL de ejemplo es muy similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c72a5-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="c72a5-146">Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación:</span><span class="sxs-lookup"><span data-stu-id="c72a5-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="c72a5-147">Anexe la cadena siguiente a la URL: **/MigraciónHospedada/ServicioDeMigraciónHospedada.svc**.</span><span class="sxs-lookup"><span data-stu-id="c72a5-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="c72a5-148">La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, necesita ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c72a5-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="c72a5-149">El tamaño máximo por defecto de los archivos de registro de la transacción de la base de datos rtcxds es de 16 GB.</span><span class="sxs-lookup"><span data-stu-id="c72a5-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="c72a5-150">Puede que no sea lo suficiente grande para mover un gran número de usuarios a la vez, especialmente si la creación de reflejos está habilitada.</span><span class="sxs-lookup"><span data-stu-id="c72a5-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="c72a5-151">Para solucionarlo, puede aumentar el tamaño del archivo o hacer regularmente una copia de seguridad de los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="c72a5-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="c72a5-152">Para obtener más información, <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>consulte.</span><span class="sxs-lookup"><span data-stu-id="c72a5-152">For more information, see <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="c72a5-153">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="c72a5-153">This is an optional step.</span></span> <span data-ttu-id="c72a5-154">Si tiene que llevar a cabo la integración con Exchange 2013 Online, tendrá que usar un proveedor de hospedaje adicional.</span><span class="sxs-lookup"><span data-stu-id="c72a5-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="c72a5-155">Para obtener información detallada, consulte [configuración de la integración de Lync Server 2013 con Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="c72a5-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="c72a5-p110">Ahora se han movido los usuarios. Para comprobar si un usuario tiene valores correctos para los atributos que se muestran en la tabla siguiente, escriba este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c72a5-p110">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
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
    <th><span data-ttu-id="c72a5-158">Atributo de Active Directory</span><span class="sxs-lookup"><span data-stu-id="c72a5-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="c72a5-159">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="c72a5-159">Attribute name</span></span></th>
    <th><span data-ttu-id="c72a5-160">Valor correcto para el usuario de Lync Online</span><span class="sxs-lookup"><span data-stu-id="c72a5-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="c72a5-161">Valor correcto para usuarios locales de Lync</span><span class="sxs-lookup"><span data-stu-id="c72a5-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c72a5-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="c72a5-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-163">Proveedor de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c72a5-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c72a5-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-165">SRV:</span><span class="sxs-lookup"><span data-stu-id="c72a5-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c72a5-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="c72a5-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-167">Dirección SIP</span><span class="sxs-lookup"><span data-stu-id="c72a5-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c72a5-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c72a5-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c72a5-170">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="c72a5-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-171">Habilitado</span><span class="sxs-lookup"><span data-stu-id="c72a5-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-172">True</span><span class="sxs-lookup"><span data-stu-id="c72a5-172">True</span></span></p></td>
    <td><p><span data-ttu-id="c72a5-173">True</span><span class="sxs-lookup"><span data-stu-id="c72a5-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="c72a5-174">Cada usuario que se haya movido necesitará cerrar sesión en Lync y, a continuación, volver a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="c72a5-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="c72a5-175">Al hacerlo, tendrán que verificar sus listas de contactos y agregar contactos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="c72a5-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="c72a5-176">Tenga en cuenta que las reuniones programadas no se migran de Lync Online a Lync local.</span><span class="sxs-lookup"><span data-stu-id="c72a5-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="c72a5-177">Los usuarios tendrán que volver a programar las reuniones una vez movidos.</span><span class="sxs-lookup"><span data-stu-id="c72a5-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="c72a5-178">Después de que se actualicen los registros DNS y de que todos los usuarios se dirijan a local, el atributo Hostingprovider manda indica al usuario de Lync que use registros SRV o los dirija al proveedor en línea "sipfed.online.lync.com".</span><span class="sxs-lookup"><span data-stu-id="c72a5-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

