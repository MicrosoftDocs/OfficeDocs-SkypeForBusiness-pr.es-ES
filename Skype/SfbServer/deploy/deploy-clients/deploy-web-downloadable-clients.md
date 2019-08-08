---
title: Implementar clientes descargables en Internet en Skype empresarial Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumen: implemente la aplicación Web de Skype empresarial y la aplicación reuniones de Skype que se usan con Skype empresarial.'
ms.openlocfilehash: 8f2449fde2f270834bda50602fe163829f3b725f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234398"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="4e175-103">Implementar clientes descargables en Internet en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4e175-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="4e175-104">**Resumen:** Implementar la aplicación Web de Skype empresarial 2015 y la aplicación reuniones de Skype que se usa con Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4e175-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="4e175-105">La aplicación Web de Skype empresarial es un cliente web de Internet Information Services (IIS) instalado en el servidor que ejecuta Skype empresarial Server y, de forma predeterminada, se implementa a petición para los usuarios que aún no tienen el cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e175-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="4e175-106">Estos usuarios de reuniones son más frecuentes que los casos de usuarios que no se conectan desde fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="4e175-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="4e175-107">Siempre que un usuario haga clic en una dirección URL de la reunión pero no tenga instalado el cliente de Skype empresarial, se le presentará al usuario la opción de unirse a la reunión con la versión más reciente de la aplicación Web de Skype empresarial, la aplicación reuniones de Skype o Skype empresarial para Mac.</span><span class="sxs-lookup"><span data-stu-id="4e175-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="4e175-108">Las características de voz, vídeo y uso compartido de la aplicación Web de Skype empresarial requieren un control ActiveX de Microsoft que el explorador del usuario Use como complemento.</span><span class="sxs-lookup"><span data-stu-id="4e175-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="4e175-109">Puede instalar el control ActiveX por adelantado o permitir que los usuarios lo instalen cuando se le pida, que es la primera vez que usan la aplicación Web de Skype empresarial o la primera vez que tienen acceso a una característica que requiere el control ActiveX.</span><span class="sxs-lookup"><span data-stu-id="4e175-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="4e175-110">En las implementaciones de servidor perimetral de Skype empresarial Server, se necesita un proxy inverso HTTPS en la red perimetral para el acceso de cliente de la aplicación Web de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e175-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="4e175-111">También debe publicar direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="4e175-111">You must also publish simple URLs.</span></span> <span data-ttu-id="4e175-112">Para obtener más información, consulte [configuración de servidores proxy](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) inversos y [requisitos de DNS para direcciones URL simples en Skype empresarial Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="4e175-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="4e175-113">Habilitar la autenticación multifactor para la aplicación Web de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="4e175-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="4e175-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="4e175-114"></span></span>

<span data-ttu-id="4e175-115">La aplicación Web de Skype empresarial, la aplicación reuniones de Skype y Skype empresarial para Mac admiten la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="4e175-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="4e175-116">Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios que se unen desde redes externas cuando inician sesión en reuniones de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e175-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="4e175-117">Puede habilitar la autenticación multifactor si implementa el servidor de Federación de servicio de Federación de Active Directory (AD FS) y habilita la autenticación pasiva en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4e175-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="4e175-118">Después de configurar AD FS, los usuarios externos que intenten unirse a reuniones de Skype empresarial recibirán una página web de autenticación multifactor de AD FS que contiene el desafío de nombre de usuario y contraseña junto con los métodos de autenticación adicionales que ha configurado.</span><span class="sxs-lookup"><span data-stu-id="4e175-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e175-119">A continuación, se incluyen algunas consideraciones importantes para planear la configuración de AD FS para la autenticación multifactor:</span><span class="sxs-lookup"><span data-stu-id="4e175-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="4e175-p105">La autenticación multifactor de AD FS funciona si el usuario que participa en la reunión y el organizador están en la misma organización o si ambos provienen de una organización federada de AD FS. La autenticación multifactor de AD FS no funciona para usuarios federados de Lync porque la infraestructura web de Lync Server no lo admite en este momento.</span><span class="sxs-lookup"><span data-stu-id="4e175-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="4e175-122">Si usa equilibradores de carga de hardware, habilite la persistencia de las cookies en los equilibradores de carga para que todas las solicitudes de los clientes de la aplicación Web de Skype empresarial o de la aplicación de reuniones se controlen mediante el mismo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="4e175-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="4e175-123">Al establecer una relación de confianza para usuario autenticado entre los servidores de Skype empresarial Server y AD FS, asigne un token de duración que sea lo suficientemente largo como para abarcar la máxima duración de las reuniones de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e175-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="4e175-124">Por lo general, una duración de token de 240 minutos es suficiente.</span><span class="sxs-lookup"><span data-stu-id="4e175-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="4e175-125">Esta configuración no se aplica a los clientes móviles de Lync.</span><span class="sxs-lookup"><span data-stu-id="4e175-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="4e175-126">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="4e175-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="4e175-127">Instale un rol del servidor de federación de AD FS.</span><span class="sxs-lookup"><span data-stu-id="4e175-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="4e175-128">Para obtener más información, consulte la [Guía de implementación de servicios de Federación de active directory 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="4e175-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="4e175-129">Cree certificados para AD FS.</span><span class="sxs-lookup"><span data-stu-id="4e175-129">Create certificates for AD FS.</span></span> <span data-ttu-id="4e175-130">Para obtener más información, consulte la sección ["certificados de servidor de Federación"](https://go.microsoft.com/fwlink/p/?LinkId=285376) de los temas planear e implementar AD FS para su uso con el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="4e175-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="4e175-131">Desde la interfaz de línea de comandos de Windows PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4e175-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="4e175-132">Establezca una relación de usuario mediante la ejecución del siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4e175-132">Establish a partnership by running the following command:</span></span>

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="4e175-133">Defina las siguientes reglas de usuario de confianza:</span><span class="sxs-lookup"><span data-stu-id="4e175-133">Set the following relying party rules:</span></span>

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="4e175-134">Deshabilitar BranchCache </span><span class="sxs-lookup"><span data-stu-id="4e175-134">Disable BranchCache</span></span>
<span data-ttu-id="4e175-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="4e175-135"></span></span>

<span data-ttu-id="4e175-136">La característica BranchCache en Windows 7 y Windows Server 2008 R2 puede interferir con los componentes Web de la aplicación Web de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e175-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="4e175-137">Para evitar problemas con los usuarios de la aplicación Web de Skype empresarial, asegúrese de que BranchCache no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="4e175-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="4e175-138">Para obtener más información sobre cómo deshabilitar BranchCache, consulte la [Guía de implementación de BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span><span class="sxs-lookup"><span data-stu-id="4e175-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="4e175-139">Comprobar la implementación de la aplicación Web de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="4e175-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="4e175-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="4e175-140"></span></span>

<span data-ttu-id="4e175-141">Puede usar el cmdlet Test-CsUcwaConference para comprobar que un par de usuarios de prueba puedan participar de una conferencia con la API web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="4e175-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="4e175-142">Para obtener más información sobre este cmdlet, consulte [probar-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) en la documentación del shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4e175-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="4e175-143">Solución de problemas de instalación de complementos en Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4e175-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="4e175-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="4e175-144"></span></span>

<span data-ttu-id="4e175-145">Si se produce un error en la instalación del complemento en un equipo con Windows Server 2008 R2, es posible que tenga que modificar la configuración de seguridad de Internet Explorer o la configuración de la clave del registro DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="4e175-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="4e175-146">Modificar la configuración de seguridad de Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="4e175-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="4e175-147">Abra Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4e175-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="4e175-148">Haga clic en \*\*Herramientas \*\*, en **Opciones de Internet** y en **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="4e175-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="4e175-149">Desplácese hacia abajo hasta la sección **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="4e175-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="4e175-150">Desactive **No guardar las páginas cifradas en el disco** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4e175-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4e175-151">Si se selecciona, esta configuración también provocará un error al intentar descargar un archivo adjunto desde la aplicación Web de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e175-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="4e175-p111">Vuelva a unirse a la reunión. El complemento se debe descargar sin errores.</span><span class="sxs-lookup"><span data-stu-id="4e175-p111">Rejoin the meeting. The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="4e175-154">Modificar la configuración del Registro DisableMSI</span><span class="sxs-lookup"><span data-stu-id="4e175-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="4e175-155">Haga clic en  \*\*Inicio \*\* y en  \*\*Ejecutar \*\*.</span><span class="sxs-lookup"><span data-stu-id="4e175-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="4e175-156">Para acceder al Editor del Registro, escriba **regedit**.</span><span class="sxs-lookup"><span data-stu-id="4e175-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="4e175-157">Navegue hasta HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="4e175-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="4e175-158">Modifique o agregue la clave del Registro DisableMSI de tipo REG_DWORD, y defínala en 0.</span><span class="sxs-lookup"><span data-stu-id="4e175-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="4e175-159">Vuelva a unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="4e175-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="4e175-160">Habilitar la aplicación reuniones de Skype para reemplazar la aplicación Web de Skype empresarial (opcional, Skype empresarial Server 2015 solamente)</span><span class="sxs-lookup"><span data-stu-id="4e175-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="4e175-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="4e175-161"></span></span>

<span data-ttu-id="4e175-162">Este procedimiento es opcional y se aplica a Skype empresarial Server 2015 CU5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4e175-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="4e175-163">Si no lo usa, los usuarios externos seguirán combinando reuniones con la aplicación Web de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e175-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="4e175-164">Habilitar el método simplificado para unirse a las reuniones y la aplicación Reuniones de Skype</span><span class="sxs-lookup"><span data-stu-id="4e175-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="4e175-165">Al habilitar el acceso a la red de entrega de contenido (CDN), los usuarios podrán conectarse a la red CDN en línea y obtener la aplicación reuniones de Skype (en Windows) y Skype empresarial para Mac (en Mac), y usarán la experiencia de la combinación de reuniones simplificada.</span><span class="sxs-lookup"><span data-stu-id="4e175-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="4e175-166">Permitir la telemetría de registro del lado cliente de la Página Web de la Unión a reuniones o de la aplicación reuniones de Skype para enviarla a los servidores de Microsoft (el comando tiene el valor predeterminado falso).</span><span class="sxs-lookup"><span data-stu-id="4e175-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="4e175-167">La información enviada a Microsoft es estrictamente compatible con las [prácticas de recopilación de datos de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span><span class="sxs-lookup"><span data-stu-id="4e175-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="4e175-168">Establezca el tiempo de espera antes de volver a la experiencia de la aplicación Web de Skype empresarial hospedada localmente si CDN no está disponible.</span><span class="sxs-lookup"><span data-stu-id="4e175-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="4e175-169">El valor predeterminado es 6 segundos.</span><span class="sxs-lookup"><span data-stu-id="4e175-169">The default value is 6 seconds.</span></span> <span data-ttu-id="4e175-170">En caso de que fuese 0, no habría tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4e175-170">If this value is set to 0, there will be no timeout.</span></span>

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a><span data-ttu-id="4e175-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e175-171">See also</span></span>
<span data-ttu-id="4e175-172"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="4e175-172"></span></span>

[<span data-ttu-id="4e175-173">Planear clientes de reuniones (aplicación web y aplicación reuniones)</span><span class="sxs-lookup"><span data-stu-id="4e175-173">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="4e175-174">Configurar la página de combinación de reuniones en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4e175-174">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="4e175-175">Declaración de privacidad de Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="4e175-175">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="4e175-176">Términos de licencia y documentación</span><span class="sxs-lookup"><span data-stu-id="4e175-176">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
