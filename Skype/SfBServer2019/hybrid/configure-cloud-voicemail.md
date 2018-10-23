---
title: Configurar el servicio de correo de voz en la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instrucciones de implementación de voz basados en la nube para los usuarios alojados en Skype para Business Server.
ms.openlocfilehash: 80f154a7fa8e34b7912ebf5762e5d0390e21fd22
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696187"
---
# <a name="configure-cloud-voicemail-service"></a><span data-ttu-id="bcc1d-103">Configurar el servicio de correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="bcc1d-103">Configure Cloud Voicemail service</span></span>

## <a name="overview"></a><span data-ttu-id="bcc1d-104">Información general</span><span class="sxs-lookup"><span data-stu-id="bcc1d-104">Overview</span></span> 
<span data-ttu-id="bcc1d-105">En este artículo se describe cómo configurar el servicio de correo de voz de Microsoft en la nube para su Skype para los usuarios empresariales locales.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="bcc1d-106">En este artículo se supone que ya dispone de Skype para Business Server implementado en una topología admitida y que cumplen los requisitos previos para la configuración de conectividad híbrida.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="bcc1d-107">Para obtener más información acerca de las ventajas, planeación, requisitos y consideraciones para la implementación de correo de voz en la nube, vea [servicio de planeación de correo de voz en la nube](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="bcc1d-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="bcc1d-108">Configuración de correo de voz en la nube implica las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="bcc1d-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="bcc1d-109">Asegúrese de que se cumplen los requisitos previos tal como se describe en el [servicio de planeación de correo de voz en la nube](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="bcc1d-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="bcc1d-110">Asegúrese de que ha configurado la conectividad híbrida tal como se describe en [conectividad híbrida de Plan](plan-hybrid-connectivity.md) y [conectividad de la configuración híbrida](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="bcc1d-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="bcc1d-111">[Configuración de correo de voz en la nube como el proveedor de hospedaje en el servidor perimetral](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="bcc1d-112">[Configure una directiva de correo de voz hospedado](#configure-a-hosted-voicemail-policy) como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="bcc1d-113">[Asignar una directiva de correo de voz hospedado](#assign-a-hosted-voicemail-policy) como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="bcc1d-114">[Habilitar a un usuario de correo de voz en la nube](#enable-a-user-for-cloud-voicemail) tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="bcc1d-115">Configurar el correo de voz en la nube como el proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="bcc1d-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="bcc1d-116">Configurar el correo de voz en la nube como el proveedor de hospedaje en el servidor perimetral mediante el cmdlet New-CsHostingProvider con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="bcc1d-116">You configure Cloud Voicemail as the hosting provider on the Edge Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="bcc1d-117">**Identidad** especifica un identificador de valor de cadena único para el proveedor de hospedaje que va a crear; Por ejemplo, en la nube correo de voz.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="bcc1d-118">\*\*Habilitada \*\* indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="bcc1d-119">Este parámetro debe establecerse en True.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="bcc1d-120">**EnabledSharedAddressSpace** indica si el proveedor de hospedaje se usará en un escenario de espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="bcc1d-121">Este parámetro debe establecerse en True.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="bcc1d-122">**HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Skype para las cuentas de Business Server.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="bcc1d-123">Este parámetro debe establecerse en False.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="bcc1d-124">**ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy utilizado por el proveedor de hospedaje; Por ejemplo, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="bcc1d-125">Para obtener esta información, póngase en contacto con su proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="bcc1d-126">Este valor no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-126">This value cannot be modified.</span></span> <span data-ttu-id="bcc1d-127">Si el proveedor de hospedaje cambia su servidor proxy, debe eliminar y, a continuación, volver a crear la entrada de ese proveedor.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="bcc1d-128">**IsLocal** indica si el servidor proxy utilizado por el proveedor de hospedaje está dentro de su Skype de topología de servidores de negocio.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="bcc1d-129">Este parámetro debe establecerse en False.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-129">This parameter must be set to False.</span></span>

<span data-ttu-id="bcc1d-130">Por ejemplo, en Skype para el shell de administración de negocio, el siguiente cmdlet configura el correo de voz en la nube como el proveedor de hospedaje:</span><span class="sxs-lookup"><span data-stu-id="bcc1d-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="bcc1d-131">Configurar una directiva de correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="bcc1d-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="bcc1d-132">Para asegurarse de que correo de voz para su organización se enruta al servicio de correo de voz en la nube, debe configurar una directiva de correo de voz hospedado para su organización.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="bcc1d-133">En muchos casos, solo un correo de voz hospedado directiva es necesario y se puede modificar la directiva global para satisfacer todas sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="bcc1d-134">Si la organización requiere varias directivas de correo de voz hospedado, puede agregar las directivas mediante el cmdlet new-cshostedvoicemailpolicy.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="bcc1d-135">Para modificar la directiva global, ejecute el siguiente comando en el Skype para Business Server shell de administración de después de actualizar la organización y TenantID:</span><span class="sxs-lookup"><span data-stu-id="bcc1d-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="bcc1d-136">**Destino** especifica el nombre de dominio completo (FQDN) del servicio hospedado de correo de voz en la nube.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="bcc1d-137">Este valor debe establecerse en **exap.um.outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="bcc1d-138">**Organización** es el dominio predeterminado asignado a su inquilino.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="bcc1d-139">Puede recuperar esta información mediante la necesidad de la administración de inquilinos inicie sesión office.com, haga clic en la aplicación de centro de administración, navegue hasta **el programa de instalación** de la izquierda y haga clic en **dominios**.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="bcc1d-140">Por ejemplo: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="bcc1d-141">El nombre de la organización también es el nombre de dominio predeterminado en Office 365.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="bcc1d-142">**TenantID** se usa para identificar al inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-142">**TenantID** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="bcc1d-143">Para obtener más información, vea [encontrar el identificador del inquilino de Office 365](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span><span class="sxs-lookup"><span data-stu-id="bcc1d-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="bcc1d-144">Para asegurarse de que una directiva de correo de voz hospedado se creó correctamente, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bcc1d-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="bcc1d-145">Asignar una directiva de correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="bcc1d-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="bcc1d-146">De forma predeterminada, la Global hospedada directiva de correo de voz se asigna a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="bcc1d-147">Si utiliza una directiva diferente, antes de habilitar a los usuarios para correo de voz hospedado, primero debe conceder a los usuarios la directiva de correo de voz hospedado que desee mediante el cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="bcc1d-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="bcc1d-148">Por ejemplo, el comando siguiente asigna una directiva de correo de voz hospedado no Global a un usuario:</span><span class="sxs-lookup"><span data-stu-id="bcc1d-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="bcc1d-149">Habilitar a un usuario de correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="bcc1d-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="bcc1d-150">Para habilitar las llamadas de correo de voz de un usuario deben enrutarse al correo de voz en la nube, usar el cmdlet [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) con el parámetro HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="bcc1d-151">Por ejemplo, el siguiente comando permite una cuenta de usuario de correo de voz en la nube:</span><span class="sxs-lookup"><span data-stu-id="bcc1d-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="bcc1d-152">El cmdlet comprueba que una directiva de correo de voz en la nube--a nivel global, nivel de sitio o usuario--se aplica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="bcc1d-153">Si no se aplica ninguna directiva, se produce un error en el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="bcc1d-154">En el ejemplo siguiente se deshabilita una cuenta de usuario de correo de voz en la nube:</span><span class="sxs-lookup"><span data-stu-id="bcc1d-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="bcc1d-155">El cmdlet comprueba que no hay ninguna directiva de correo de voz hospedado--a nivel global, nivel de sitio o usuario--se aplica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="bcc1d-156">Si se aplica una directiva, se produce un error en el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="bcc1d-157">Los usuarios deben ser habilitada para usar el servicio de correo de voz de Microsoft en la nube de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="bcc1d-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>