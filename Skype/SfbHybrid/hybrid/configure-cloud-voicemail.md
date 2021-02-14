---
title: Configurar el servicio de correo de voz en la nube para usuarios locales
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instrucciones para implementar el correo de voz basado en la nube para los usuarios que están en Skype Empresarial Server.
ms.openlocfilehash: 29faba6bf092647f0c55899f013c6b4bf146304f
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552586"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="ae330-103">Configurar el servicio de correo de voz en la nube para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="ae330-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="ae330-104">Información general</span><span class="sxs-lookup"><span data-stu-id="ae330-104">Overview</span></span> 
<span data-ttu-id="ae330-105">En este artículo se describe cómo configurar el servicio de correo de voz en la nube de Microsoft para los usuarios locales de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ae330-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="ae330-106">En este artículo se presupone que Skype Empresarial Server ya está implementado en una topología compatible y que ha cumplido los requisitos previos para configurar la conectividad híbrida.</span><span class="sxs-lookup"><span data-stu-id="ae330-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="ae330-107">Para obtener más información sobre las ventajas, consideraciones de planeación y requisitos para implementar el correo de voz en la nube, consulte [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="ae330-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="ae330-108">La configuración del correo de voz en la nube implica las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="ae330-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="ae330-109">Asegúrese de que ha cumplido los requisitos previos tal como se describe en [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="ae330-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="ae330-110">Asegúrese de que ha configurado la conectividad híbrida como se describe en [Planear la conectividad híbrida](plan-hybrid-connectivity.md) y Configurar la conectividad [híbrida.](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="ae330-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="ae330-111">[Configure el correo de voz en la nube como proveedor de hospedaje en el servidor front-end,](#configure-cloud-voicemail-as-the-hosting-provider) tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ae330-111">[Configure Cloud Voicemail as the hosting provider on the Front End Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="ae330-112">[Configure una directiva de correo de voz hospedado](#configure-a-hosted-voicemail-policy) como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ae330-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="ae330-113">[Asigne una directiva de correo de voz hospedado](#assign-a-hosted-voicemail-policy) como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ae330-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="ae330-114">[Habilite a un usuario para correo de voz en la nube,](#enable-a-user-for-cloud-voicemail) tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ae330-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="ae330-115">Configurar el correo de voz en la nube como proveedor de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ae330-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="ae330-116">El correo de voz en la nube se configura como proveedor de hospedaje en un servidor front-end mediante el cmdlet New-CsHostingProvider con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="ae330-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="ae330-117">**Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando; por ejemplo, Correo de voz en la nube.</span><span class="sxs-lookup"><span data-stu-id="ae330-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="ae330-118">**Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada.</span><span class="sxs-lookup"><span data-stu-id="ae330-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="ae330-119">Este parámetro debe establecerse en True.</span><span class="sxs-lookup"><span data-stu-id="ae330-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="ae330-120">**EnabledSharedAddressSpace** indica si se usará el proveedor de hospedaje en un escenario de espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="ae330-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="ae330-121">Este parámetro debe establecerse en True.</span><span class="sxs-lookup"><span data-stu-id="ae330-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="ae330-122">**HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae330-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="ae330-123">Este parámetro debe establecerse en False.</span><span class="sxs-lookup"><span data-stu-id="ae330-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="ae330-124">**ProxyFQDN especifica** el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje; por ejemplo, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ae330-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="ae330-125">Póngase en contacto con el proveedor de hospedaje para obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="ae330-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="ae330-126">Este valor no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="ae330-126">This value cannot be modified.</span></span> <span data-ttu-id="ae330-127">Si el proveedor de hospedaje cambia su servidor proxy, tendrá que eliminar y, a continuación, volver a crear la entrada para ese proveedor.</span><span class="sxs-lookup"><span data-stu-id="ae330-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="ae330-128">**IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae330-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="ae330-129">Este parámetro debe establecerse en False.</span><span class="sxs-lookup"><span data-stu-id="ae330-129">This parameter must be set to False.</span></span>

<span data-ttu-id="ae330-130">Por ejemplo, en el Shell de administración de Skype Empresarial, el siguiente cmdlet configura el correo de voz en la nube como proveedor de hospedaje:</span><span class="sxs-lookup"><span data-stu-id="ae330-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="ae330-131">Configurar una directiva de correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="ae330-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="ae330-132">Para asegurarse de que el correo de voz de su organización se enruta al servicio de correo de voz en la nube, debe configurar una directiva de correo de voz hospedado para su organización.</span><span class="sxs-lookup"><span data-stu-id="ae330-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="ae330-133">En muchos casos, solo se necesita una directiva de correo de voz hospedado y puede modificar la directiva global para satisfacer todas sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="ae330-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="ae330-134">Si su organización requiere varias directivas de correo de voz hospedado, puede agregar directivas con el cmdlet new-cshostedvoicemailpolicy.</span><span class="sxs-lookup"><span data-stu-id="ae330-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="ae330-135">Para modificar la directiva global, ejecute el siguiente comando en el Shell de administración de Skype Empresarial Server después de actualizar la organización y tenantID:</span><span class="sxs-lookup"><span data-stu-id="ae330-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="ae330-136">**El** destino especifica el nombre de dominio completo (FQDN) del servicio de correo de voz en la nube hospedado.</span><span class="sxs-lookup"><span data-stu-id="ae330-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="ae330-137">Este valor debe establecerse en **exap.um.outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="ae330-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="ae330-138">**La** organización es el dominio predeterminado asignado a su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="ae330-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="ae330-139">Puede recuperar esta información haciendo que el administrador del espacio empresarial inicie sesión en office.com, haga clic en la aplicación Centro de administración, vaya a **Configuración** a la izquierda y haga clic en **Dominios.**</span><span class="sxs-lookup"><span data-stu-id="ae330-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="ae330-140">Por ejemplo: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="ae330-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="ae330-141">El nombre de la organización también es el nombre de dominio predeterminado en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae330-141">The Organization name is also the Default Domain name in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="ae330-142">Para asegurarse de que una directiva de correo de voz hospedado se creó correctamente, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="ae330-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="ae330-143">Asignar una directiva de correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="ae330-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="ae330-144">De forma predeterminada, la directiva global de correo de voz hospedado se asigna a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ae330-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="ae330-145">Si usa una directiva diferente, antes de habilitar a los usuarios para el correo de voz hospedado, primero debe conceder a los usuarios la directiva de correo de voz hospedada deseada mediante el cmdlet [Grant-CSHostedVoicemailPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ae330-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="ae330-146">Por ejemplo, el siguiente comando asigna una directiva de correo de voz hospedado no global a un usuario:</span><span class="sxs-lookup"><span data-stu-id="ae330-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="ae330-147">Habilitar un usuario para correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="ae330-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="ae330-148">Para permitir que las llamadas de correo de voz de un usuario se enrutan al correo de voz en la nube, use el cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) con el parámetro HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="ae330-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="ae330-149">Por ejemplo, el siguiente comando habilita una cuenta de usuario para correo de voz en la nube:</span><span class="sxs-lookup"><span data-stu-id="ae330-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="ae330-150">El cmdlet comprueba que una directiva de correo de voz en la nube (a nivel global, de sitio o de usuario) se aplica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="ae330-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="ae330-151">Si no se aplica ninguna directiva, el cmdlet no se completará correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae330-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="ae330-152">En el siguiente ejemplo se deshabilita una cuenta de usuario para correo de voz en la nube:</span><span class="sxs-lookup"><span data-stu-id="ae330-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="ae330-153">El cmdlet comprueba que ninguna directiva de correo de voz hospedado (a nivel global, de sitio o de usuario) se aplique a este usuario.</span><span class="sxs-lookup"><span data-stu-id="ae330-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="ae330-154">Si se aplica alguna directiva, el cmdlet no se completará correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae330-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="ae330-155">Los usuarios deben tener la voz empresarial habilitada para usar el servicio de correo de voz en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae330-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
