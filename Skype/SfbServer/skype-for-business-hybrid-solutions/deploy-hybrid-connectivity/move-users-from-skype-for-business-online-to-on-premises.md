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
ms.openlocfilehash: 7e0400a0a77a50253e6932c8255c64eb58574229
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569480"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a><span data-ttu-id="8132b-103">Mover usuarios de Skype para empresarial en línea para local</span><span class="sxs-lookup"><span data-stu-id="8132b-103">Move users from Skype for Business Online to on premises</span></span>
 
<span data-ttu-id="8132b-104">**Resumen:** Obtenga información sobre cómo mover las cuentas de usuario de en línea para localmente en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8132b-104">**Summary:** Learn how to move user accounts from online to on premises in Skype for Business Server.</span></span>
  
<span data-ttu-id="8132b-105">Debe mover las cuentas de usuario de en línea para local para asegurarse de que los usuarios alojados en línea y local son detectables entre sí.</span><span class="sxs-lookup"><span data-stu-id="8132b-105">You might need to move user accounts from online to on premises to ensure that users homed online and on premises are discoverable to one another.</span></span> <span data-ttu-id="8132b-106">Para ser detectable entre sí, todos los usuarios deben tener una presencia en el Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="8132b-106">To be discoverable to one another, all users must have a presence in the on-premises Active Directory.</span></span> <span data-ttu-id="8132b-107">Para obtener más información, consulte [Plan de conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8132b-107">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span> <span data-ttu-id="8132b-108">Es posible que desee mover los usuarios en línea en local, por ejemplo, si:</span><span class="sxs-lookup"><span data-stu-id="8132b-108">You might want to move online users to on premises, for example, if:</span></span> 
  
- <span data-ttu-id="8132b-109">Tener nuevos usuarios que necesiten ser creado en local y, a continuación, se mueve a la nube.</span><span class="sxs-lookup"><span data-stu-id="8132b-109">You have new users who need to be created on premises and then moved to the cloud.</span></span>
    
- <span data-ttu-id="8132b-110">Su organización implementa Skype para en línea de negocio antes de que implemente Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8132b-110">Your organization deployed Skype for Business Online before it deployed Skype for Business Server.</span></span> <span data-ttu-id="8132b-111">Por lo tanto, tiene los usuarios que se crearon en la nube en primer lugar y ahora necesita va a mover a local antes de mover a Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="8132b-111">Therefore, you have users who were created in the cloud first, and now need to be moved to on premises before they are move to Skype for Business Online.</span></span> 
    
<span data-ttu-id="8132b-112">En este tema se describe dos escenarios:</span><span class="sxs-lookup"><span data-stu-id="8132b-112">This topic describes two scenarios:</span></span>
  
- [<span data-ttu-id="8132b-113">Mover usuarios en línea, que estaba conectado originalmente — a local</span><span class="sxs-lookup"><span data-stu-id="8132b-113">Move online users—who were originally online—to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)
    
- [<span data-ttu-id="8132b-114">Mover en línea a los usuarios (que eran originalmente en local) local</span><span class="sxs-lookup"><span data-stu-id="8132b-114">Move online users (who were originally on premises) to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)
    
## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a><span data-ttu-id="8132b-115">Mover usuarios en línea, que estaba conectado originalmente — a local</span><span class="sxs-lookup"><span data-stu-id="8132b-115">Move online users—who were originally online—to on premises</span></span>
<span data-ttu-id="8132b-116"><a name="BKMK_originallyonline"> </a></span><span class="sxs-lookup"><span data-stu-id="8132b-116"></span></span>

<span data-ttu-id="8132b-117">En esta sección se aplica sólo a los usuarios que se han creado y habilitado en línea, pero que no tienen una cuenta en las instalaciones en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8132b-117">This section applies only to users who were created and enabled online, but who do not have an account in the on premises Active Directory.</span></span> 
  
<span data-ttu-id="8132b-118">Antes de empezar a mover usuarios en línea a su entorno local, compruebe que se cumplan las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8132b-118">Before you start moving online users to your on-premises environment, check that all of the following are true:</span></span>
  
- <span data-ttu-id="8132b-119">Su entorno local necesita estar completamente implementado y validado.</span><span class="sxs-lookup"><span data-stu-id="8132b-119">Your on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="8132b-120">Para obtener más información, vea [implementación de Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) o [Implementar Skype para Business Server 2015](../../deploy/deploy.md), dependiendo de la versión que está utilizando en local.</span><span class="sxs-lookup"><span data-stu-id="8132b-120">For more information, see [Deploying Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) or [Deploy Skype for Business Server 2015](../../deploy/deploy.md), depending on which version you are using on premises.</span></span> 
    
- <span data-ttu-id="8132b-121">El inquilino online debe configurarse para el acceso remoto de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8132b-121">Your online tenant must be configured for remote PowerShell access.</span></span>
    
    <span data-ttu-id="8132b-122">Para ello, instale primero la Skype para el módulo del conector en línea de negocio para Windows PowerShell, que se puede obtener aquí: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="8132b-122">To do this, first install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
    
    <span data-ttu-id="8132b-123">Después de instalar el módulo, puede establecer una sesión remota escribiendo los siguientes cmdlets en el Skype para Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="8132b-123">After you install the module, you can establish a remote session by typing the following cmdlets in the Skype for Business Server Management Shell:</span></span>
    
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

    <span data-ttu-id="8132b-124">Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype para profesionales en línea, consulte [Connecting to Lync Online por Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span><span class="sxs-lookup"><span data-stu-id="8132b-124">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Lync Online By Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span></span>
    
    <span data-ttu-id="8132b-125">Para obtener más información acerca del uso de la Skype para el módulo de PowerShell de conector en línea de negocio, vea [Using Windows PowerShell para administrar Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span><span class="sxs-lookup"><span data-stu-id="8132b-125">For more information about using the Skype for Business Online connector PowerShell module, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
    
- <span data-ttu-id="8132b-126">El inquilino online debe configurarse para un espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="8132b-126">Your online tenant must be configured for a shared SIP address space.</span></span> <span data-ttu-id="8132b-127">Para ello, inicie primero una sesión remota de Powershell con Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="8132b-127">To do this, first start a remote Powershell session with Skype for Business Online.</span></span> <span data-ttu-id="8132b-128">Luego, ejecute el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="8132b-128">Then run the following cmdlet:</span></span>
    
  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > <span data-ttu-id="8132b-129">Las necesidades de atributo SharedSipAddressSpace permanezca "True" hasta que mover a en línea es final y no a los usuarios permanecen en local.</span><span class="sxs-lookup"><span data-stu-id="8132b-129">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on premises.</span></span> 
  
<span data-ttu-id="8132b-130">Una vez que haya terminado de estos pasos, puede migrar las cuentas de usuario tal como se describe en el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="8132b-130">After you've finished these steps, you can migrate user accounts as described in the following procedure:</span></span>
  
### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a><span data-ttu-id="8132b-131">Mover cuentas de usuario originalmente habilitadas en línea para una implementación local</span><span class="sxs-lookup"><span data-stu-id="8132b-131">Move user accounts originally enabled online to an on-premises deployment</span></span>

1. <span data-ttu-id="8132b-132">En primer lugar, asegúrese de que su organización está configurada para implementaciones híbridas, incluidos Azure Active Directory Connect y las herramientas de sincronización.</span><span class="sxs-lookup"><span data-stu-id="8132b-132">First, make sure that your organization is configured for hybrid, including Azure Active Directory Connect and sync tools.</span></span> <span data-ttu-id="8132b-133">Para obtener más información, consulte [Plan de conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8132b-133">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>
    
  - <span data-ttu-id="8132b-134">En la implementación local, en la Skype para Shell de administración de servidor empresarial, escriba los siguientes cmdlets para crear el proveedor de hospedaje de Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="8132b-134">On your on-premises deployment, in the Skype for Business Server Management Shell, type the following cmdlets to create the hosting provider for Skype for Business Online.</span></span> <span data-ttu-id="8132b-135">Puede usar cualquier valor que desee para los parámetros Identidad y Nombre.</span><span class="sxs-lookup"><span data-stu-id="8132b-135">You can use whatever value you want for the Identity and Name parameters.</span></span>
    
  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. <span data-ttu-id="8132b-136">Confirme que en los servidores perimetrales local, tiene la cadena de certificados que permite la conexión a Skype para en línea de negocio, tal como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="8132b-136">Confirm that on your on-premises Edge Servers, you have the certificate chain that enables connection to Skype for Business Online, as shown in the following table.</span></span> <span data-ttu-id="8132b-137">Puede descargar esta cadena aquí: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span><span class="sxs-lookup"><span data-stu-id="8132b-137">You can download this chain here: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span></span>
    
|<span data-ttu-id="8132b-138">**Certificado**</span><span class="sxs-lookup"><span data-stu-id="8132b-138">**Certificate**</span></span>|<span data-ttu-id="8132b-139">**Almacén de certificados**</span><span class="sxs-lookup"><span data-stu-id="8132b-139">**Certificate Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8132b-140">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="8132b-140">Baltimore CyberTrust Root</span></span>  <br/> |<span data-ttu-id="8132b-141">CA raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="8132b-141">Trusted Root CA</span></span>  <br/> |
|<span data-ttu-id="8132b-142">Microsoft Internet Authority (nuevo certificado CA)</span><span class="sxs-lookup"><span data-stu-id="8132b-142">Microsoft Internet Authority (New CA certificate)</span></span>  <br/> |<span data-ttu-id="8132b-143">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="8132b-143">Intermediate CA</span></span>  <br/> |
|<span data-ttu-id="8132b-144">MSIT Machine Auth CA2 (nueva CA2 de emisión)</span><span class="sxs-lookup"><span data-stu-id="8132b-144">MSIT Machine Auth CA2 (New Issuing CA2)</span></span>  <br/> |<span data-ttu-id="8132b-145">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="8132b-145">Intermediate CA</span></span>  <br/> |
   
3. <span data-ttu-id="8132b-146">En su Active Directory local, habilite las cuentas de usuario afectado de Skype para Business Server 2015 local.</span><span class="sxs-lookup"><span data-stu-id="8132b-146">In your on-premises Active Directory, enable the affected user accounts for Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="8132b-147">Para hacerlo para un usuario individual, escriba el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="8132b-147">You can do this for an individual user by typing the following cmdlet:</span></span> 
    
  ```
  Enable-CsUser
-Identity "username " 
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    <span data-ttu-id="8132b-148">También puede crear un script que lea los nombres de usuario de un archivo y los indique como entrada al cmdlet Enable-CsUser cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8132b-148">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
  ```
  Enable-CsUser
-Identity $Identity 
-SipAddress $SipAddress 
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. <span data-ttu-id="8132b-149">Sincronización de los usuarios en línea con los usuarios actualizado local.</span><span class="sxs-lookup"><span data-stu-id="8132b-149">Synchronize the online users with the updated on-premises users.</span></span> <span data-ttu-id="8132b-150">Para obtener más información, vea [Herramientas de integración de Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span><span class="sxs-lookup"><span data-stu-id="8132b-150">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>
    
5. <span data-ttu-id="8132b-151">Actualizar los siguientes registros DNS para dirigir todo el tráfico SIP a la implementación local:</span><span class="sxs-lookup"><span data-stu-id="8132b-151">Update the following DNS records to direct all SIP traffic to your on-premises deployment:</span></span>
    
  - <span data-ttu-id="8132b-152">Actualice el registro A **lyncdiscover.contoso.com** para que apunte al FQDN del servidor proxy inverso local.</span><span class="sxs-lookup"><span data-stu-id="8132b-152">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
  - <span data-ttu-id="8132b-153">Actualización de la ** *_sip* . _tls.contoso.com** SRV se registre para resolver a la dirección IP o la dirección VIP pública del servicio de servidor perimetral de acceso de Lync local.</span><span class="sxs-lookup"><span data-stu-id="8132b-153">Update the ** *_sip*  ._tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
  - <span data-ttu-id="8132b-154">Actualización de la ** *_sipfederationtls* . SRV _tcp.contoso.com** registrar para resolver a la dirección IP o la dirección VIP pública del servicio de servidor perimetral de acceso de Skype para Business Server 2015 local.</span><span class="sxs-lookup"><span data-stu-id="8132b-154">Update the ** *_sipfederationtls*  ._tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Skype for Business Server 2015 on-premises.</span></span>
    
  - <span data-ttu-id="8132b-155">Si su organización utiliza divididas de DNS (a veces denominado "split-brain DNS"), asegúrese de que se dirigen a los usuarios resolución de nombres a través de la zona DNS interna para el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="8132b-155">If your organization uses split DNS (sometimes called "split-brain DNS"), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>
    
6. <span data-ttu-id="8132b-156">Tipo de la `Get-CsUser` cmdlet para comprobar algunas propiedades acerca de los usuarios que se va a mover.</span><span class="sxs-lookup"><span data-stu-id="8132b-156">Type the  `Get-CsUser` cmdlet to check some properties about the users you'll be moving.</span></span> <span data-ttu-id="8132b-157">Necesita asegurarse de que el FQDN del servidor proxy del proveedor de hospedaje está definido a `"sipfed.online.lync.com"` y que las direcciones SIP están bien configuradas.</span><span class="sxs-lookup"><span data-stu-id="8132b-157">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>
    
7. <span data-ttu-id="8132b-158">Mover los usuarios en línea en local.</span><span class="sxs-lookup"><span data-stu-id="8132b-158">Move online users to on premises.</span></span>
    
    <span data-ttu-id="8132b-159">Para mover un solo usuario, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8132b-159">To move a single user, type this:</span></span>
    
  ```
  $cred = Get-Credential
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="8132b-160">Puede mover varios usuarios mediante el cmdlet **Get-CsUSer** -el parámetro Filter para seleccionar los usuarios con una propiedad concreta.</span><span class="sxs-lookup"><span data-stu-id="8132b-160">You can move multiple users by using the **Get-CsUSer** cmdlet with the -Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="8132b-161">Por ejemplo, puede seleccionar todos los usuarios en línea mediante el filtrado para {proveedor de hospedaje - eq "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="8132b-161">For example, you could select all Online users by filtering for {Hosting Provider -eq "sipfed.online.lync.om"}.</span></span> <span data-ttu-id="8132b-162">A continuación, se pueden canalizar los usuarios devueltos al cmdlet **Move-CsUSer** , tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="8132b-162">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="8132b-163">El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL para el grupo de servidores donde se ejecuta el servicio de migración hospedado, en el siguiente formato: _Https://\<FQDN del grupo de servidores\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="8132b-163">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>
    
    <span data-ttu-id="8132b-164">Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8132b-164">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="8132b-165">Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365</span><span class="sxs-lookup"><span data-stu-id="8132b-165">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="8132b-166">Inicie sesión en el inquilino de Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="8132b-166">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="8132b-167">Abra el **Centro de administración de Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="8132b-167">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="8132b-p112">Con el **Centro de administración de Skype Empresarial** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8132b-p112">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="8132b-170">Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación:</span><span class="sxs-lookup"><span data-stu-id="8132b-170">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="8132b-171">Anexe la cadena siguiente a la URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="8132b-171">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="8132b-172">La dirección URL resultante, que es el valor de la **HostedMigrationOverrideUrl**, debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="8132b-172">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]
    > <span data-ttu-id="8132b-173">El tamaño máximo por defecto de los archivos de registro de la transacción de la base de datos rtcxds es de 16 GB.</span><span class="sxs-lookup"><span data-stu-id="8132b-173">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="8132b-174">Esto no sea lo suficientemente grande si va a mover un gran número de usuarios a la vez, especialmente si dispone de la creación de reflejos habilitado.</span><span class="sxs-lookup"><span data-stu-id="8132b-174">This might not be big enough if you're moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="8132b-175">Para solucionarlo, puede aumentar el tamaño del archivo o hacer regularmente una copia de seguridad de los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="8132b-175">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="8132b-176">Para obtener más información, consulte [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span><span class="sxs-lookup"><span data-stu-id="8132b-176">For more information, see [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span></span> 
  
8. <span data-ttu-id="8132b-177">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="8132b-177">This is an optional step.</span></span> <span data-ttu-id="8132b-178">Si tiene que llevar a cabo la integración con Exchange 2013 Online, tendrá que usar un proveedor de hospedaje adicional.</span><span class="sxs-lookup"><span data-stu-id="8132b-178">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="8132b-179">Para obtener información detallada, vea [Configurar la integración entre local Skype para Business Server 2015 y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="8132b-179">For details, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span></span>
    
9. <span data-ttu-id="8132b-p115">Ahora se han movido los usuarios. Para comprobar si un usuario tiene valores correctos para los atributos que se muestran en la tabla siguiente, escriba este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8132b-p115">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span> 
    
  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|<span data-ttu-id="8132b-182">**Atributo de Active Directory**</span><span class="sxs-lookup"><span data-stu-id="8132b-182">**Active Directory attribute**</span></span>|<span data-ttu-id="8132b-183">**Nombre de atributo**</span><span class="sxs-lookup"><span data-stu-id="8132b-183">**Attribute name**</span></span>|<span data-ttu-id="8132b-184">**Valor correcto para el usuario en línea**</span><span class="sxs-lookup"><span data-stu-id="8132b-184">**Correct value for Online user**</span></span>|<span data-ttu-id="8132b-185">**Valor correcto para los usuarios locales**</span><span class="sxs-lookup"><span data-stu-id="8132b-185">**Correct value for on-premises users**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8132b-186">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="8132b-186">msRTCSIP-DeploymentLocator</span></span>  <br/> |<span data-ttu-id="8132b-187">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="8132b-187">HostingProvider</span></span>  <br/> |<span data-ttu-id="8132b-188">sipfed.Online.Lync.com</span><span class="sxs-lookup"><span data-stu-id="8132b-188">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="8132b-189">SRV:</span><span class="sxs-lookup"><span data-stu-id="8132b-189">SRV:</span></span>  <br/> |
|<span data-ttu-id="8132b-190">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="8132b-190">msRTCSIP-PrimaryUserAddress</span></span>  <br/> |<span data-ttu-id="8132b-191">Dirección SIP</span><span class="sxs-lookup"><span data-stu-id="8132b-191">SIPAddress</span></span>  <br/> |<span data-ttu-id="8132b-192">SIP:username@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8132b-192">sip:userName@contoso.com</span></span>  <br/> |<span data-ttu-id="8132b-193">SIP:username@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8132b-193">sip:userName@contoso.com</span></span>  <br/> |
|<span data-ttu-id="8132b-194">sRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="8132b-194">sRTCSIP-UserEnabled</span></span>  <br/> |<span data-ttu-id="8132b-195">Habilitado</span><span class="sxs-lookup"><span data-stu-id="8132b-195">Enabled</span></span>  <br/> |<span data-ttu-id="8132b-196">True</span><span class="sxs-lookup"><span data-stu-id="8132b-196">True</span></span>  <br/> |<span data-ttu-id="8132b-197">True</span><span class="sxs-lookup"><span data-stu-id="8132b-197">True</span></span>  <br/> |
   
10. <span data-ttu-id="8132b-p116">Todos los usuarios movidos tendrán que cerrar la sesión y volver a iniciar la sesión. Al hacerlo, tendrán que verificar sus listas de contactos y agregar contactos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="8132b-p116">Each user who has been moved will need to log out, then log back in. When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="8132b-p117">Tenga en cuenta que las reuniones programadas no se migran del modo en línea al local. Los usuarios tendrán que volver a programar las reuniones una vez movidos.</span><span class="sxs-lookup"><span data-stu-id="8132b-p117">Note that scheduled meetings are not migrated from online to on-premises. Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="8132b-202">Una vez que se actualizan los registros DNS y todos los usuarios se dirigen a local, el atributo HostingProvider dirige al usuario a utilizar registros SRV o dirigirlos al proveedor en línea "sipfed.online.lync.com."</span><span class="sxs-lookup"><span data-stu-id="8132b-202">After the DNS records are updated and all users are directed to On-premises, the HostingProvider attribute directs the user to either use SRV records or direct them to the Online provider "sipfed.online.lync.com."</span></span>
    
## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a><span data-ttu-id="8132b-203">Mover en línea a los usuarios (que eran originalmente en local) local</span><span class="sxs-lookup"><span data-stu-id="8132b-203">Move online users (who were originally on premises) to on premises</span></span>
<span data-ttu-id="8132b-204"><a name="BKMK_originallyonprem"> </a></span><span class="sxs-lookup"><span data-stu-id="8132b-204"></span></span>

<span data-ttu-id="8132b-205">En esta sección se aplica sólo a los usuarios que se han creado y habilitados para una implementación local y, a continuación, se mueve de una implementación de local a en línea.</span><span class="sxs-lookup"><span data-stu-id="8132b-205">This section applies only to users who were created and enabled for an on-premises deployment and then moved from an on-premises deployment to online.</span></span> 
  
- <span data-ttu-id="8132b-206">Ejecute los siguientes cmdlets para mover un usuario de Skype para profesionales en línea de vuelta a local, reemplazando el valor de los parámetros **Identity** y **destino** corregir los valores para el entorno:</span><span class="sxs-lookup"><span data-stu-id="8132b-206">Run the following cmdlets to move a user from Skype for Business Online back to on-premises, replacing the value for the **Identity** and **Target** parameters to correct values for your environment:</span></span>
    
  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

<span data-ttu-id="8132b-207">El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL para el grupo de servidores donde se ejecuta el servicio de migración hospedado, en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="8132b-207">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>
  
 <span data-ttu-id="8132b-208">_Https://\<FQDN de grupo de\>/HostedMigration/hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="8132b-208">_Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span> <span data-ttu-id="8132b-209">Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8132b-209">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="8132b-210">Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365</span><span class="sxs-lookup"><span data-stu-id="8132b-210">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="8132b-211">Inicie sesión en el inquilino de Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="8132b-211">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="8132b-212">Abra el **Centro de administración de Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="8132b-212">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="8132b-p119">Con el **Centro de administración de Skype Empresarial** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8132b-p119">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="8132b-215">Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación:</span><span class="sxs-lookup"><span data-stu-id="8132b-215">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="8132b-216">Anexe la cadena siguiente a la URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="8132b-216">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="8132b-217">La dirección URL resultante, que es el valor de la **HostedMigrationOverrideUrl**, debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="8132b-217">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

