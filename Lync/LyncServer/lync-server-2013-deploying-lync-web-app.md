---
title: 'Lync Server 2013: implementación de Lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8babb6bf37e3dd75f2051dd08f0b2ebf3a4f093b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="36bfa-102">Implementación de Lync Web App en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36bfa-102">Deploying Lync Web App in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36bfa-103">_**Última modificación del tema:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="36bfa-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="36bfa-104">Lync Web App es un cliente web de Internet Information Services (IIS) que se instala con Lync Server 2013 y está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="36bfa-104">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="36bfa-105">No es necesario realizar ningún paso adicional para habilitar Lync Web App en el servidor o para implementar el cliente web en los usuarios.</span><span class="sxs-lookup"><span data-stu-id="36bfa-105">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="36bfa-106">Cada vez que un usuario hace clic en una dirección URL de una reunión pero no tiene instalado el cliente de Lync 2013, se le presenta la opción de unirse a la reunión con la versión más reciente de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="36bfa-106">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="36bfa-107">Las características de voz, vídeo y uso compartido de Lync Web App requieren un control ActiveX de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36bfa-107">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="36bfa-108">Puede instalar el control ActiveX con antelación o permitir a los usuarios que lo instalen cuando se le solicite, lo que ocurre la primera vez que usan Lync Web App o la primera vez que tienen acceso a una característica que requiere el control ActiveX.</span><span class="sxs-lookup"><span data-stu-id="36bfa-108">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="36bfa-109">En las implementaciones del servidor perimetral 2013 de Lync Server, se requiere un proxy inverso HTTPS en la red perimetral para el acceso de cliente de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="36bfa-109">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="36bfa-110">También debe publicar direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="36bfa-110">You must also publish simple URLs.</span></span> <span data-ttu-id="36bfa-111">Para obtener más información, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuración de servidores proxy inversos para Lync server 2013</A> y <A href="lync-server-2013-planning-for-simple-urls.md">planeación de direcciones URL sencillas en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="36bfa-111">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="36bfa-112">Habilitación de multi-factor Authentication para Lync Web App</span><span class="sxs-lookup"><span data-stu-id="36bfa-112">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="36bfa-113">La versión de Lync Server 2013 de Lync Web App admite la autenticación de varios factores.</span><span class="sxs-lookup"><span data-stu-id="36bfa-113">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="36bfa-114">Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios que se unen desde redes externas cuando inician sesión en reuniones de Lync.</span><span class="sxs-lookup"><span data-stu-id="36bfa-114">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="36bfa-115">Puede habilitar la autenticación multifactor mediante la implementación del servidor de Federación del servicio de Federación de Active Directory (AD FS) y la habilitación de la autenticación pasiva en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36bfa-115">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="36bfa-116">Una vez configurado AD FS, los usuarios externos que intenten unirse a reuniones de Lync reciben una página web de autenticación multifactor de AD FS con el nombre de usuario y la contraseña, junto con los métodos de autenticación adicionales que haya configurado. .</span><span class="sxs-lookup"><span data-stu-id="36bfa-116">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="36bfa-117">A continuación, se indican algunas consideraciones importantes que debe tener en cuenta si tiene previsto configurar AD FS para la autenticación multifactor:</span><span class="sxs-lookup"><span data-stu-id="36bfa-117">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="36bfa-118">La autenticación multifactor de ADFS funciona si el participante de la reunión y el organizador están en la misma organización o son de una organización federada de AD FS.</span><span class="sxs-lookup"><span data-stu-id="36bfa-118">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="36bfa-119">La autenticación multifactor de ADFS no funciona para los usuarios federados de Lync porque la infraestructura Web de Lync Server no lo admite en este momento.</span><span class="sxs-lookup"><span data-stu-id="36bfa-119">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="36bfa-120">Si usa equilibradores de carga de hardware, habilite la persistencia de las cookies en los equilibradores de carga para que todas las solicitudes del cliente de Lync Web App se controlen con el mismo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="36bfa-120">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="36bfa-121">Cuando establezca una relación de confianza para usuario autenticado entre los servidores de Lync Server y AD FS, asigne una duración de tokens lo suficientemente larga como para extender la longitud máxima de las reuniones de Lync.</span><span class="sxs-lookup"><span data-stu-id="36bfa-121">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="36bfa-122">Normalmente, una duración de token de 240 minutos es suficiente.</span><span class="sxs-lookup"><span data-stu-id="36bfa-122">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="36bfa-123">Esta configuración no se aplica a los clientes móviles de Lync.</span><span class="sxs-lookup"><span data-stu-id="36bfa-123">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="36bfa-124">**Para configurar la autenticación multifactor**</span><span class="sxs-lookup"><span data-stu-id="36bfa-124">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="36bfa-125">Instale un rol de servidor de Federación de AD FS.</span><span class="sxs-lookup"><span data-stu-id="36bfa-125">Install an AD FS federation server role.</span></span> <span data-ttu-id="36bfa-126">Para obtener más información, consulte la guía de implementación de los servicios de Federación de Active Directory 2,0 en<https://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="36bfa-126">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="36bfa-127">Crear certificados para AD FS.</span><span class="sxs-lookup"><span data-stu-id="36bfa-127">Create certificates for AD FS.</span></span> <span data-ttu-id="36bfa-128">Para obtener más información, consulte la sección "certificados de servidor de Federación" del tema Plan for and Deploy AD FS for use with Single Sign- [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376)on.</span><span class="sxs-lookup"><span data-stu-id="36bfa-128">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="36bfa-129">Desde la interfaz de línea de comandos de Windows PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="36bfa-129">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="36bfa-130">Establezca una asociación mediante la ejecución del siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="36bfa-130">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="36bfa-131">Establezca las siguientes reglas de usuario de confianza:</span><span class="sxs-lookup"><span data-stu-id="36bfa-131">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a><span data-ttu-id="36bfa-132">Configuración de BranchCache</span><span class="sxs-lookup"><span data-stu-id="36bfa-132">BranchCache Configuration</span></span>

<span data-ttu-id="36bfa-133">La característica BranchCache en Windows 7 y Windows Server 2008 R2 puede interferir con los componentes Web de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="36bfa-133">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="36bfa-134">Para evitar problemas con los usuarios de Lync Web App, asegúrese de que BranchCache no esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="36bfa-134">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="36bfa-135">Para obtener más información acerca de cómo deshabilitar BranchCache, consulte la guía de implementación de BranchCache, que está disponible en formato de [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) Word en el centro de descarga de Microsoft, en formato HTML en [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789)la biblioteca técnica de Windows Server 2008 R2, en.</span><span class="sxs-lookup"><span data-stu-id="36bfa-135">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="36bfa-136">Comprobación de la implementación de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="36bfa-136">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="36bfa-137">Puede usar el cmdlet test-CsUcwaConference para comprobar que un par de usuarios de prueba pueden participar en una conferencia mediante la API Web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="36bfa-137">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="36bfa-138">Para obtener más información sobre este cmdlet, vea [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36bfa-138">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="36bfa-139">Solución de problemas de instalación de complementos en Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="36bfa-139">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="36bfa-140">Si se produce un error en la instalación del complemento en un equipo que ejecuta Windows Server 2008 R2, es posible que deba modificar la configuración de seguridad de Internet Explorer o la configuración de la clave del registro DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="36bfa-140">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="36bfa-141">**Para modificar la configuración de seguridad en Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="36bfa-141">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="36bfa-142">Abra Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="36bfa-142">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="36bfa-143">Haga clic en **herramientas**, en **Opciones de Internet**y, a continuación, en **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="36bfa-143">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="36bfa-144">Desplácese hacia abajo hasta la sección **seguridad** .</span><span class="sxs-lookup"><span data-stu-id="36bfa-144">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="36bfa-145">Desactive no **guardar las páginas cifradas en el disco**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="36bfa-145">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="36bfa-146">Si esta opción está activada, también se producirá un error al intentar descargar datos adjuntos de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="36bfa-146">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="36bfa-147">Vuelva a unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="36bfa-147">Rejoin the meeting.</span></span> <span data-ttu-id="36bfa-148">El complemento debe descargarse sin errores.</span><span class="sxs-lookup"><span data-stu-id="36bfa-148">The plug-in should download without errors.</span></span>

<span data-ttu-id="36bfa-149">**Para modificar la configuración del registro DisableMSI**</span><span class="sxs-lookup"><span data-stu-id="36bfa-149">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="36bfa-150">Haga clic en **Inicio** y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="36bfa-150">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="36bfa-151">Para obtener acceso al editor del registro, escriba **regedit**.</span><span class="sxs-lookup"><span data-stu-id="36bfa-151">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="36bfa-152">Vaya a HKEY\_local\_Machine\\software\\\\Policies\\Microsoft\\Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="36bfa-152">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="36bfa-153">Edite o agregue la clave del registro DisableMSI de\_tipo REG DWORD y establézcalo en 0.</span><span class="sxs-lookup"><span data-stu-id="36bfa-153">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="36bfa-154">Vuelva a unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="36bfa-154">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36bfa-155">Consulta también</span><span class="sxs-lookup"><span data-stu-id="36bfa-155">See Also</span></span>


[<span data-ttu-id="36bfa-156">Configuración de la página de participación en la reunión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36bfa-156">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="36bfa-157">Plataformas compatibles con Lync Web App para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36bfa-157">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

