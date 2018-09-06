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
ms.openlocfilehash: 655c037fc2299044aa3799d06e0d231784248d7e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260149"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a><span data-ttu-id="50dbf-103">Mover usuarios de Skype para empresarial en línea para local</span><span class="sxs-lookup"><span data-stu-id="50dbf-103">Move users from Skype for Business Online to on premises</span></span>

<span data-ttu-id="50dbf-104">**Resumen:** Obtenga información sobre cómo mover las cuentas de usuario de en línea para localmente en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="50dbf-104">**Summary:** Learn how to move user accounts from online to on premises in Skype for Business Server.</span></span>

<span data-ttu-id="50dbf-105">Debe mover las cuentas de usuario de en línea para local para asegurarse de que los usuarios alojados en línea y local son detectables entre sí.</span><span class="sxs-lookup"><span data-stu-id="50dbf-105">You might need to move user accounts from online to on premises to ensure that users homed online and on premises are discoverable to one another.</span></span> <span data-ttu-id="50dbf-106">Para ser detectable entre sí, todos los usuarios deben tener una presencia en el Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="50dbf-106">To be discoverable to one another, all users must have a presence in the on-premises Active Directory.</span></span> <span data-ttu-id="50dbf-107">Para obtener más información, consulte [Plan de conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="50dbf-107">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span> <span data-ttu-id="50dbf-108">Es posible que desee mover los usuarios en línea en local, por ejemplo, si:</span><span class="sxs-lookup"><span data-stu-id="50dbf-108">You might want to move online users to on premises, for example, if:</span></span>

- <span data-ttu-id="50dbf-109">Tener nuevos usuarios que necesiten ser creado en local y, a continuación, se mueve a la nube.</span><span class="sxs-lookup"><span data-stu-id="50dbf-109">You have new users who need to be created on premises and then moved to the cloud.</span></span>

- <span data-ttu-id="50dbf-110">Su organización implementa Skype para en línea de negocio antes de que implemente Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="50dbf-110">Your organization deployed Skype for Business Online before it deployed Skype for Business Server.</span></span> <span data-ttu-id="50dbf-111">Por lo tanto, tiene los usuarios que se crearon en la nube en primer lugar y ahora necesita va a mover a local antes de mover a Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="50dbf-111">Therefore, you have users who were created in the cloud first, and now need to be moved to on premises before they are move to Skype for Business Online.</span></span>

<span data-ttu-id="50dbf-112">En este tema se describe dos escenarios:</span><span class="sxs-lookup"><span data-stu-id="50dbf-112">This topic describes two scenarios:</span></span>

- [<span data-ttu-id="50dbf-113">Mover usuarios en línea, que estaba conectado originalmente — a local</span><span class="sxs-lookup"><span data-stu-id="50dbf-113">Move online users—who were originally online—to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)

- [<span data-ttu-id="50dbf-114">Mover en línea a los usuarios (que eran originalmente en local) local</span><span class="sxs-lookup"><span data-stu-id="50dbf-114">Move online users (who were originally on premises) to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)

## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a><span data-ttu-id="50dbf-115">Mover usuarios en línea, que estaba conectado originalmente — a local</span><span class="sxs-lookup"><span data-stu-id="50dbf-115">Move online users—who were originally online—to on premises</span></span>
<span data-ttu-id="50dbf-116"><a name="BKMK_originallyonline"> </a></span><span class="sxs-lookup"><span data-stu-id="50dbf-116"></span></span>

<span data-ttu-id="50dbf-117">En esta sección se aplica sólo a los usuarios que se han creado y habilitado en línea, pero que no tienen una cuenta en las instalaciones en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="50dbf-117">This section applies only to users who were created and enabled online, but who do not have an account in the on premises Active Directory.</span></span>

<span data-ttu-id="50dbf-118">Antes de empezar a mover usuarios en línea a su entorno local, compruebe que se cumplan las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="50dbf-118">Before you start moving online users to your on-premises environment, check that all of the following are true:</span></span>

- <span data-ttu-id="50dbf-119">Su entorno local necesita estar completamente implementado y validado.</span><span class="sxs-lookup"><span data-stu-id="50dbf-119">Your on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="50dbf-120">Para obtener más información, vea [implementación de Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) o [Implementar Skype para Business Server 2015](../../deploy/deploy.md), dependiendo de la versión que está utilizando en local.</span><span class="sxs-lookup"><span data-stu-id="50dbf-120">For more information, see [Deploying Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) or [Deploy Skype for Business Server 2015](../../deploy/deploy.md), depending on which version you are using on premises.</span></span>

- <span data-ttu-id="50dbf-121">El inquilino online debe configurarse para el acceso remoto de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50dbf-121">Your online tenant must be configured for remote PowerShell access.</span></span>

    <span data-ttu-id="50dbf-122">Para ello, instale primero la Skype para el módulo del conector en línea de negocio para Windows PowerShell, que se puede obtener aquí: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="50dbf-122">To do this, first install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>

    <span data-ttu-id="50dbf-123">Después de instalar el módulo, puede establecer una sesión remota escribiendo los siguientes cmdlets en el Skype para Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="50dbf-123">After you install the module, you can establish a remote session by typing the following cmdlets in the Skype for Business Server Management Shell:</span></span>

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

    <span data-ttu-id="50dbf-124">Para obtener más información acerca del uso de PowerShell con Skype para profesionales en línea, vea [Configurar el equipo de Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="50dbf-124">For more information about using PowerShell with Skype for Business Online, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>

- <span data-ttu-id="50dbf-125">El inquilino online debe configurarse para un espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="50dbf-125">Your online tenant must be configured for a shared SIP address space.</span></span> <span data-ttu-id="50dbf-126">Para ello, inicie primero una sesión remota de Powershell con Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="50dbf-126">To do this, first start a remote Powershell session with Skype for Business Online.</span></span> <span data-ttu-id="50dbf-127">Luego, ejecute el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="50dbf-127">Then run the following cmdlet:</span></span>

  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > <span data-ttu-id="50dbf-128">Las necesidades de atributo SharedSipAddressSpace permanezca "True" hasta que mover a en línea es final y no a los usuarios permanecen en local.</span><span class="sxs-lookup"><span data-stu-id="50dbf-128">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on premises.</span></span>

<span data-ttu-id="50dbf-129">Una vez que haya terminado de estos pasos, puede migrar las cuentas de usuario tal como se describe en el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="50dbf-129">After you've finished these steps, you can migrate user accounts as described in the following procedure:</span></span>

### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a><span data-ttu-id="50dbf-130">Mover cuentas de usuario originalmente habilitadas en línea para una implementación local</span><span class="sxs-lookup"><span data-stu-id="50dbf-130">Move user accounts originally enabled online to an on-premises deployment</span></span>

1. <span data-ttu-id="50dbf-131">En primer lugar, asegúrese de que su organización está configurada para implementaciones híbridas, incluidos Azure Active Directory Connect y las herramientas de sincronización.</span><span class="sxs-lookup"><span data-stu-id="50dbf-131">First, make sure that your organization is configured for hybrid, including Azure Active Directory Connect and sync tools.</span></span> <span data-ttu-id="50dbf-132">Para obtener más información, consulte [Plan de conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="50dbf-132">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>

  - <span data-ttu-id="50dbf-133">En la implementación local, en la Skype para Shell de administración de servidor empresarial, escriba los siguientes cmdlets para crear el proveedor de hospedaje de Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="50dbf-133">On your on-premises deployment, in the Skype for Business Server Management Shell, type the following cmdlets to create the hosting provider for Skype for Business Online.</span></span> <span data-ttu-id="50dbf-134">Puede usar cualquier valor que desee para los parámetros Identidad y Nombre.</span><span class="sxs-lookup"><span data-stu-id="50dbf-134">You can use whatever value you want for the Identity and Name parameters.</span></span>

  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. <span data-ttu-id="50dbf-135">Confirme que en los servidores perimetrales local, tiene la cadena de certificados que permite la conexión a Skype para en línea de negocio, tal como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="50dbf-135">Confirm that on your on-premises Edge Servers, you have the certificate chain that enables connection to Skype for Business Online, as shown in the following table.</span></span> <span data-ttu-id="50dbf-136">Puede descargar esta cadena aquí: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span><span class="sxs-lookup"><span data-stu-id="50dbf-136">You can download this chain here: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span></span>

|<span data-ttu-id="50dbf-137">**Certificado**</span><span class="sxs-lookup"><span data-stu-id="50dbf-137">**Certificate**</span></span>|<span data-ttu-id="50dbf-138">**Almacén de certificado**</span><span class="sxs-lookup"><span data-stu-id="50dbf-138">**Certificate Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="50dbf-139">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="50dbf-139">Baltimore CyberTrust Root</span></span>  <br/> |<span data-ttu-id="50dbf-140">CA raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="50dbf-140">Trusted Root CA</span></span>  <br/> |
|<span data-ttu-id="50dbf-141">Microsoft Internet Authority (nuevo certificado CA)</span><span class="sxs-lookup"><span data-stu-id="50dbf-141">Microsoft Internet Authority (New CA certificate)</span></span>  <br/> |<span data-ttu-id="50dbf-142">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="50dbf-142">Intermediate CA</span></span>  <br/> |
|<span data-ttu-id="50dbf-143">MSIT Machine Auth CA2 (nueva CA2 de emisión)</span><span class="sxs-lookup"><span data-stu-id="50dbf-143">MSIT Machine Auth CA2 (New Issuing CA2)</span></span>  <br/> |<span data-ttu-id="50dbf-144">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="50dbf-144">Intermediate CA</span></span>  <br/> |

3. <span data-ttu-id="50dbf-145">En su Active Directory local, habilite las cuentas de usuario afectado de Skype para Business Server 2015 local.</span><span class="sxs-lookup"><span data-stu-id="50dbf-145">In your on-premises Active Directory, enable the affected user accounts for Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="50dbf-146">Para hacerlo para un usuario individual, escriba el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="50dbf-146">You can do this for an individual user by typing the following cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity "username "
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    <span data-ttu-id="50dbf-147">También puede crear un script que lea los nombres de usuario de un archivo y los indique como entrada al cmdlet Enable-CsUser cmdlet:</span><span class="sxs-lookup"><span data-stu-id="50dbf-147">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity $Identity
-SipAddress $SipAddress
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. <span data-ttu-id="50dbf-148">Sincronización de los usuarios en línea con los usuarios actualizado local.</span><span class="sxs-lookup"><span data-stu-id="50dbf-148">Synchronize the online users with the updated on-premises users.</span></span> <span data-ttu-id="50dbf-149">Para obtener más información, vea [Herramientas de integración de Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span><span class="sxs-lookup"><span data-stu-id="50dbf-149">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>

5. <span data-ttu-id="50dbf-150">Actualizar los siguientes registros DNS para dirigir todo el tráfico SIP a la implementación local:</span><span class="sxs-lookup"><span data-stu-id="50dbf-150">Update the following DNS records to direct all SIP traffic to your on-premises deployment:</span></span>

  - <span data-ttu-id="50dbf-151">Actualice el registro A **lyncdiscover.contoso.com** para que apunte al FQDN del servidor proxy inverso local.</span><span class="sxs-lookup"><span data-stu-id="50dbf-151">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>

  - <span data-ttu-id="50dbf-152">Actualización de la \*\* *_sip* . _tls.contoso.com\*\* registro SRV para resolver en la dirección IP o la dirección VIP pública del servicio de servidor perimetral de acceso de Lync local.</span><span class="sxs-lookup"><span data-stu-id="50dbf-152">Update the ***_sip*  ._tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>

  - <span data-ttu-id="50dbf-153">Actualización de la \*\* *_sipfederationtls* . _tcp.contoso.com\*\* registro SRV para resolver en la dirección IP o la dirección VIP pública del servicio de servidor perimetral de acceso de Skype para Business Server 2015 local.</span><span class="sxs-lookup"><span data-stu-id="50dbf-153">Update the ***_sipfederationtls*  ._tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Skype for Business Server 2015 on-premises.</span></span>

  - <span data-ttu-id="50dbf-154">Si su organización utiliza divididas de DNS (a veces denominado "split-brain DNS"), asegúrese de que se dirigen a los usuarios resolución de nombres a través de la zona DNS interna para el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="50dbf-154">If your organization uses split DNS (sometimes called "split-brain DNS"), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6. <span data-ttu-id="50dbf-155">Tipo de la `Get-CsUser` cmdlet para comprobar algunas propiedades acerca de los usuarios que se va a mover.</span><span class="sxs-lookup"><span data-stu-id="50dbf-155">Type the  `Get-CsUser` cmdlet to check some properties about the users you'll be moving.</span></span> <span data-ttu-id="50dbf-156">Necesita asegurarse de que el FQDN del servidor proxy del proveedor de hospedaje está definido a `"sipfed.online.lync.com"` y que las direcciones SIP están bien configuradas.</span><span class="sxs-lookup"><span data-stu-id="50dbf-156">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7. <span data-ttu-id="50dbf-157">Mover los usuarios en línea en local.</span><span class="sxs-lookup"><span data-stu-id="50dbf-157">Move online users to on premises.</span></span>

    <span data-ttu-id="50dbf-158">Para mover un solo usuario, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50dbf-158">To move a single user, type this:</span></span>

  ```
  $cred = Get-Credential
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="50dbf-159">Puede mover varios usuarios mediante el cmdlet **Get-CsUSer** -el parámetro Filter para seleccionar los usuarios con una propiedad concreta.</span><span class="sxs-lookup"><span data-stu-id="50dbf-159">You can move multiple users by using the **Get-CsUSer** cmdlet with the -Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="50dbf-160">Por ejemplo, puede seleccionar todos los usuarios en línea mediante el filtrado para {proveedor de hospedaje - eq "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="50dbf-160">For example, you could select all Online users by filtering for {Hosting Provider -eq "sipfed.online.lync.om"}.</span></span> <span data-ttu-id="50dbf-161">A continuación, se pueden canalizar los usuarios devueltos al cmdlet **Move-CsUSer** , tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="50dbf-161">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>

  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="50dbf-162">El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL para el grupo de servidores donde se ejecuta el servicio de migración hospedado, en el siguiente formato: _Https://\<FQDN del grupo de servidores\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="50dbf-162">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>

    <span data-ttu-id="50dbf-163">Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="50dbf-163">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="50dbf-164">Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365</span><span class="sxs-lookup"><span data-stu-id="50dbf-164">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="50dbf-165">Inicie sesión en el inquilino de Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="50dbf-165">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="50dbf-166">Abra el **Centro de administración de Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="50dbf-166">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="50dbf-p112">Con el **Centro de administración de Skype Empresarial** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="50dbf-p112">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="50dbf-169">Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación:</span><span class="sxs-lookup"><span data-stu-id="50dbf-169">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="50dbf-170">Anexe la cadena siguiente a la URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="50dbf-170">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="50dbf-171">La dirección URL resultante, que es el valor de la **HostedMigrationOverrideUrl**, debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="50dbf-171">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

    > [!NOTE]
    > <span data-ttu-id="50dbf-172">El tamaño máximo por defecto de los archivos de registro de la transacción de la base de datos rtcxds es de 16 GB.</span><span class="sxs-lookup"><span data-stu-id="50dbf-172">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="50dbf-173">Esto no sea lo suficientemente grande si va a mover un gran número de usuarios a la vez, especialmente si dispone de la creación de reflejos habilitado.</span><span class="sxs-lookup"><span data-stu-id="50dbf-173">This might not be big enough if you're moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="50dbf-174">Para solucionarlo, puede aumentar el tamaño del archivo o hacer regularmente una copia de seguridad de los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="50dbf-174">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="50dbf-175">Para obtener más información, consulte [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span><span class="sxs-lookup"><span data-stu-id="50dbf-175">For more information, see [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span></span>

8. <span data-ttu-id="50dbf-176">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="50dbf-176">This is an optional step.</span></span> <span data-ttu-id="50dbf-177">Si tiene que llevar a cabo la integración con Exchange 2013 Online, tendrá que usar un proveedor de hospedaje adicional.</span><span class="sxs-lookup"><span data-stu-id="50dbf-177">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="50dbf-178">Para obtener información detallada, vea [Configurar la integración entre local Skype para Business Server 2015 y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="50dbf-178">For details, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span></span>

9. <span data-ttu-id="50dbf-p115">Ahora se han movido los usuarios. Para comprobar si un usuario tiene valores correctos para los atributos que se muestran en la tabla siguiente, escriba este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="50dbf-p115">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>

  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|<span data-ttu-id="50dbf-181">**Atributo de Active Directory**</span><span class="sxs-lookup"><span data-stu-id="50dbf-181">**Active Directory attribute**</span></span>|<span data-ttu-id="50dbf-182">**Nombre del atributo**</span><span class="sxs-lookup"><span data-stu-id="50dbf-182">**Attribute name**</span></span>|<span data-ttu-id="50dbf-183">**Valor correcto para el usuario en línea**</span><span class="sxs-lookup"><span data-stu-id="50dbf-183">**Correct value for Online user**</span></span>|<span data-ttu-id="50dbf-184">**Valor correcto para los usuarios locales**</span><span class="sxs-lookup"><span data-stu-id="50dbf-184">**Correct value for on-premises users**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="50dbf-185">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="50dbf-185">msRTCSIP-DeploymentLocator</span></span>  <br/> |<span data-ttu-id="50dbf-186">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="50dbf-186">HostingProvider</span></span>  <br/> |<span data-ttu-id="50dbf-187">sipfed.Online.Lync.com</span><span class="sxs-lookup"><span data-stu-id="50dbf-187">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="50dbf-188">SRV:</span><span class="sxs-lookup"><span data-stu-id="50dbf-188">SRV:</span></span>  <br/> |
|<span data-ttu-id="50dbf-189">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="50dbf-189">msRTCSIP-PrimaryUserAddress</span></span>  <br/> |<span data-ttu-id="50dbf-190">Dirección SIP</span><span class="sxs-lookup"><span data-stu-id="50dbf-190">SIPAddress</span></span>  <br/> |<span data-ttu-id="50dbf-191">SIP:username@contoso.com</span><span class="sxs-lookup"><span data-stu-id="50dbf-191">sip:userName@contoso.com</span></span>  <br/> |<span data-ttu-id="50dbf-192">SIP:username@contoso.com</span><span class="sxs-lookup"><span data-stu-id="50dbf-192">sip:userName@contoso.com</span></span>  <br/> |
|<span data-ttu-id="50dbf-193">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="50dbf-193">msRTCSIP-UserEnabled</span></span>  <br/> |<span data-ttu-id="50dbf-194">Habilitado</span><span class="sxs-lookup"><span data-stu-id="50dbf-194">Enabled</span></span>  <br/> |<span data-ttu-id="50dbf-195">True</span><span class="sxs-lookup"><span data-stu-id="50dbf-195">True</span></span>  <br/> |<span data-ttu-id="50dbf-196">True</span><span class="sxs-lookup"><span data-stu-id="50dbf-196">True</span></span>  <br/> |

10. <span data-ttu-id="50dbf-p116">Todos los usuarios movidos tendrán que cerrar la sesión y volver a iniciar la sesión. Al hacerlo, tendrán que verificar sus listas de contactos y agregar contactos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="50dbf-p116">Each user who has been moved will need to log out, then log back in. When they log in they should verify their contact lists, and add contacts if needed.</span></span>

    <span data-ttu-id="50dbf-p117">Tenga en cuenta que las reuniones programadas no se migran del modo en línea al local. Los usuarios tendrán que volver a programar las reuniones una vez movidos.</span><span class="sxs-lookup"><span data-stu-id="50dbf-p117">Note that scheduled meetings are not migrated from online to on-premises. Users will need to reschedule these meetings after being moved.</span></span>

    <span data-ttu-id="50dbf-201">Una vez que se actualizan los registros DNS y todos los usuarios se dirigen a local, el atributo HostingProvider dirige al usuario a utilizar registros SRV o dirigirlos al proveedor en línea "sipfed.online.lync.com."</span><span class="sxs-lookup"><span data-stu-id="50dbf-201">After the DNS records are updated and all users are directed to On-premises, the HostingProvider attribute directs the user to either use SRV records or direct them to the Online provider "sipfed.online.lync.com."</span></span>

## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a><span data-ttu-id="50dbf-202">Mover en línea a los usuarios (que eran originalmente en local) local</span><span class="sxs-lookup"><span data-stu-id="50dbf-202">Move online users (who were originally on premises) to on premises</span></span>
<span data-ttu-id="50dbf-203"><a name="BKMK_originallyonprem"> </a></span><span class="sxs-lookup"><span data-stu-id="50dbf-203"></span></span>

<span data-ttu-id="50dbf-204">En esta sección se aplica sólo a los usuarios que se han creado y habilitados para una implementación local y, a continuación, se mueve de una implementación de local a en línea.</span><span class="sxs-lookup"><span data-stu-id="50dbf-204">This section applies only to users who were created and enabled for an on-premises deployment and then moved from an on-premises deployment to online.</span></span>

- <span data-ttu-id="50dbf-205">Ejecute los siguientes cmdlets para mover un usuario de Skype para profesionales en línea de vuelta a local, reemplazando el valor de los parámetros **Identity** y **destino** corregir los valores para el entorno:</span><span class="sxs-lookup"><span data-stu-id="50dbf-205">Run the following cmdlets to move a user from Skype for Business Online back to on-premises, replacing the value for the **Identity** and **Target** parameters to correct values for your environment:</span></span>

  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

<span data-ttu-id="50dbf-206">El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL para el grupo de servidores donde se ejecuta el servicio de migración hospedado, en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="50dbf-206">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

 <span data-ttu-id="50dbf-207">_Https://\<FQDN de grupo de\>/HostedMigration/hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="50dbf-207">_Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span> <span data-ttu-id="50dbf-208">Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="50dbf-208">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="50dbf-209">Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365</span><span class="sxs-lookup"><span data-stu-id="50dbf-209">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="50dbf-210">Inicie sesión en el inquilino de Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="50dbf-210">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="50dbf-211">Abra el **Centro de administración de Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="50dbf-211">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="50dbf-p119">Con el **Centro de administración de Skype Empresarial** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="50dbf-p119">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="50dbf-214">Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación:</span><span class="sxs-lookup"><span data-stu-id="50dbf-214">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="50dbf-215">Anexe la cadena siguiente a la URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="50dbf-215">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="50dbf-216">La dirección URL resultante, que es el valor de la **HostedMigrationOverrideUrl**, debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="50dbf-216">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`


