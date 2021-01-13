---
title: Implementar clientes web descargables en Skype Empresarial Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumen: implemente la aplicación web de Skype Empresarial y la aplicación reuniones de Skype que se usa con Skype Empresarial.'
ms.openlocfilehash: afab5d0977adb8749fb514f946b676598d42ea32
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805930"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="ecd6a-103">Implementar clientes web descargables en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ecd6a-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="ecd6a-104">**Resumen:** Implemente la aplicación web de Skype Empresarial 2015 y la aplicación reuniones de Skype que se usa con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="ecd6a-105">Skype Empresarial Web App es un cliente web de Internet Information Services (IIS) que está instalado en el servidor que ejecuta Skype Empresarial Server y, de forma predeterminada, se implementa a petición para los usuarios que aún no tienen el cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="ecd6a-106">Estos usuarios de reuniones suelen no conectarse desde fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="ecd6a-107">Cuando un usuario hace clic en una dirección URL de la reunión pero no tiene instalado el cliente de Skype Empresarial, se le ofrece la opción de unirse a la reunión con la versión más reciente de Skype Empresarial Web App, la aplicación Reuniones de Skype o Skype Empresarial para Mac.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="ecd6a-108">Las características de voz, vídeo y uso compartido de Skype Empresarial Web App requieren un control de Microsoft ActiveX que el explorador del usuario usa como complemento.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="ecd6a-109">Puede instalar el control ActiveX por adelantado o permitir a los usuarios instalarlo cuando se le pida, lo que ocurre la primera vez que usan Skype Empresarial Web App o la primera vez que acceden a una característica que requiere el control ActiveX.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="ecd6a-110">En las implementaciones del servidor perimetral de Skype Empresarial Server, se necesita un proxy inverso HTTPS en la red perimetral para el acceso de cliente de Skype Empresarial Web App.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="ecd6a-111">También debe publicar direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-111">You must also publish simple URLs.</span></span> <span data-ttu-id="ecd6a-112">Para obtener más información, consulte [Configuración de servidores proxy inversos](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) y requisitos dns para direcciones URL [sencillas en Skype Empresarial Server.](../../plan-your-deployment/network-requirements/simple-urls.md)</span><span class="sxs-lookup"><span data-stu-id="ecd6a-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="ecd6a-113">Habilitar la autenticación multifactor para la aplicación web de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ecd6a-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="ecd6a-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="ecd6a-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="ecd6a-115">La aplicación web de Skype Empresarial, la aplicación reuniones de Skype y Skype Empresarial para Mac admiten la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="ecd6a-116">Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios que se unen desde redes externas cuando inician sesión en reuniones de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="ecd6a-117">Puede habilitar la autenticación multifactor implementando el servidor de federación del Servicio de federación de Active Directory (AD FS) y habilitando la autenticación pasiva en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="ecd6a-118">Después de configurar AD FS, los usuarios externos que intentan unirse a reuniones de Skype Empresarial se presentan con una página web de autenticación multifactor de AD FS que contiene el nombre de usuario y el desafío de contraseña junto con los métodos de autenticación adicionales que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ecd6a-119">Las siguientes son consideraciones importantes si planea configurar AD FS para la autenticación multifactor:</span><span class="sxs-lookup"><span data-stu-id="ecd6a-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="ecd6a-120">La autenticación multifactor ADFS funciona si el participante y el organizador de la reunión están en la misma organización o si ambos son de una organización federada de AD FS.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="ecd6a-121">La autenticación ADFS multifactor no funciona para los usuarios federados de Lync porque la infraestructura web de Lync Server no la admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="ecd6a-122">Si usa equilibradores de carga de hardware, habilite la persistencia de cookies en los equilibradores de carga para que el mismo servidor front-end controle todas las solicitudes de los clientes de la aplicación web de Skype Empresarial o de la aplicación Meetings.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="ecd6a-123">Cuando establezca una relación de confianza para usuario autenticado entre los servidores de Skype Empresarial Server y AD FS, asigne una vida de token lo suficientemente larga como para abarcar la duración máxima de las reuniones de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="ecd6a-124">Normalmente, una vida de token de 240 minutos es suficiente.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="ecd6a-125">Esta configuración no se aplica a los clientes móviles de Lync.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="ecd6a-126">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="ecd6a-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="ecd6a-127">Instalar un rol de servidor de federación de AD FS.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="ecd6a-128">Para obtener más información, consulte la Guía de implementación de Servicios de federación [de Active Directory 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="ecd6a-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="ecd6a-129">Crear certificados para AD FS.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-129">Create certificates for AD FS.</span></span> <span data-ttu-id="ecd6a-130">Para obtener más información, [vea la sección "Certificados](https://go.microsoft.com/fwlink/p/?LinkId=285376) de servidor de federación" del tema Planear e implementar AD FS para su uso con el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="ecd6a-131">Desde la Windows PowerShell de línea de comandos, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="ecd6a-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="ecd6a-132">Para establecer una asociación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="ecd6a-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="ecd6a-133">Establezca las siguientes reglas de usuario de confianza:</span><span class="sxs-lookup"><span data-stu-id="ecd6a-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="ecd6a-134">Deshabilitar BranchCache</span><span class="sxs-lookup"><span data-stu-id="ecd6a-134">Disable BranchCache</span></span>
<span data-ttu-id="ecd6a-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="ecd6a-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="ecd6a-136">La característica BranchCache de Windows 7 y Windows Server 2008 R2 puede interferir con los componentes web de Skype Empresarial Web App.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="ecd6a-137">Para evitar problemas para los usuarios de Skype Empresarial Web App, asegúrese de que BranchCache no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="ecd6a-138">Para obtener más información sobre cómo deshabilitar BranchCache, consulta la [Guía de implementación de BranchCache.](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="ecd6a-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="ecd6a-139">Comprobar la implementación de aplicaciones web de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ecd6a-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="ecd6a-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="ecd6a-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="ecd6a-141">Puede usar el cmdlet Test-CsUcwaConference para comprobar que un par de usuarios de prueba pueden participar en una conferencia mediante la API web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="ecd6a-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="ecd6a-142">Para obtener más información sobre este cmdlet, [consulte Test-CsUcwaConference en](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) la documentación del Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="ecd6a-143">Solución de problemas de la instalación de complementos en Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ecd6a-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="ecd6a-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="ecd6a-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="ecd6a-145">Si se produce un error en la instalación del complemento en un equipo que ejecuta Windows Server 2008 R2, es posible que deba modificar la configuración de seguridad de Internet Explorer o la configuración de la clave del Registro DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="ecd6a-146">Modificar la configuración de seguridad en Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="ecd6a-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="ecd6a-147">Abra Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="ecd6a-148">Haga **clic en Herramientas,** **opciones de Internet** y, a continuación, haga clic en **Opciones avanzadas.**</span><span class="sxs-lookup"><span data-stu-id="ecd6a-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="ecd6a-149">Desplácese hacia abajo hasta la **sección** Seguridad.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="ecd6a-150">Desactive **No guardar páginas cifradas en el disco** y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="ecd6a-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ecd6a-151">Si se selecciona, esta configuración también provocará un error al intentar descargar datos adjuntos de la aplicación web de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="ecd6a-152">Vuelva a unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-152">Rejoin the meeting.</span></span> <span data-ttu-id="ecd6a-153">El complemento debe descargarse sin errores.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="ecd6a-154">Modificar la configuración del Registro DisableMSI</span><span class="sxs-lookup"><span data-stu-id="ecd6a-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="ecd6a-155">Haga clic en **Inicio** y luego en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="ecd6a-156">Para obtener acceso al Editor del Registro, **escriba regedit**.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="ecd6a-157">Vaya a HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="ecd6a-158">Edita o agrega la clave del Registro DisableMSI del tipo REG_DWORD y esta establece en 0.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="ecd6a-159">Vuelva a unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="ecd6a-160">Habilitar la aplicación Reuniones de Skype para reemplazar la aplicación web de Skype Empresarial (opcional, solo Skype Empresarial Server 2015)</span><span class="sxs-lookup"><span data-stu-id="ecd6a-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="ecd6a-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="ecd6a-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="ecd6a-162">Este procedimiento es opcional y se aplica a Skype Empresarial Server 2015 CU5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="ecd6a-163">Si no lo usa, los usuarios externos seguirán unirse a las reuniones con Skype Empresarial Web App.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="ecd6a-164">Habilitar la participación en reuniones simplificada y la aplicación Reuniones de Skype</span><span class="sxs-lookup"><span data-stu-id="ecd6a-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="ecd6a-165">Cuando habilite el acceso a la red de entrega de contenido (CDN), los usuarios podrán conectarse a la red CDN en línea y obtener la aplicación Reuniones de Skype (en Windows) y Skype Empresarial para Mac (en Mac), y usarán la experiencia de participación en reuniones simplificada.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="ecd6a-166">Permitir que la telemetría de registro del lado cliente desde la página web de participación en la reunión o la aplicación reuniones de Skype se envíe a los servidores de Microsoft (el comando predeterminado es false).</span><span class="sxs-lookup"><span data-stu-id="ecd6a-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="ecd6a-167">La información enviada a Microsoft se cumple estrictamente con las [prácticas de recopilación](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)de datos de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="ecd6a-168">Establezca el tiempo de espera antes de volver a la experiencia de Skype Empresarial Web App hospedada localmente si la red CDN no está disponible.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="ecd6a-169">El valor predeterminado es 6 segundos.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-169">The default value is 6 seconds.</span></span> <span data-ttu-id="ecd6a-170">Si este valor se establece en 0, no habrá tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="ecd6a-171">Con MeetingUxUseCdn en la actualización acumulativa 5 de Skype Empresarial Server 2015, el valor predeterminado se establece en False.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="ecd6a-172">Esto provoca un problema por el que el cliente de Skype Empresarial para Mac no puede unirse a reuniones de socios no federados como invitado, incluso si el administrador de Skype Empresarial ha establecido MeetingUxUseCdn en True.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="ecd6a-173">Para que esto funcione, Skype Empresarial Server 2015 debe tener la actualización acumulativa 7, 6.0.9319.534 o posterior.</span><span class="sxs-lookup"><span data-stu-id="ecd6a-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="ecd6a-174">Consulte Habilitar la aplicación Reuniones de Skype para reemplazar la aplicación web de Skype Empresarial [en Skype Empresarial Server 2015.](https://support.microsoft.com/kb/4132312)</span><span class="sxs-lookup"><span data-stu-id="ecd6a-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="ecd6a-175">Ver también</span><span class="sxs-lookup"><span data-stu-id="ecd6a-175">See also</span></span>
<span data-ttu-id="ecd6a-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="ecd6a-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="ecd6a-177">Planeación de clientes de reuniones (aplicación web y aplicación de reuniones)</span><span class="sxs-lookup"><span data-stu-id="ecd6a-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="ecd6a-178">Configurar la página de participación en la reunión en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ecd6a-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="ecd6a-179">Declaración de privacidad de servicios en línea Microsoft</span><span class="sxs-lookup"><span data-stu-id="ecd6a-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="ecd6a-180">Términos y documentación de licencias</span><span class="sxs-lookup"><span data-stu-id="ecd6a-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
