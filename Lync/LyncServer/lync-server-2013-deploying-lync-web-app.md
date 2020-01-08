---
title: 'Lync Server 2013: implementación de Lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c355be1c1709cede9c032d59790d6beefb337ff6
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="5be47-102">Implementar Lync Web App en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5be47-102">Deploying Lync Web App in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5be47-103">_**Última modificación del tema:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="5be47-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="5be47-104">Lync Web App es un cliente web de Internet Information Services (IIS) que se instala con Lync Server 2013 y está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5be47-104">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="5be47-105">No se necesitan pasos adicionales para habilitar Lync Web App en el servidor o para implementar el cliente web a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5be47-105">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="5be47-106">Siempre que un usuario haga clic en una dirección URL de la reunión pero no tenga instalado el cliente 2013 de Lync, se le presentará al usuario la opción de unirse a la reunión con la versión más reciente de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="5be47-106">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="5be47-107">Las características de voz, vídeo y uso compartido de Lync Web App requieren un control ActiveX de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5be47-107">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="5be47-108">Puede instalar el control ActiveX por adelantado o permitir que los usuarios lo instalen cuando se le pida, lo que sucede la primera vez que usa Lync Web App o la primera vez que accede a una característica que requiere el control ActiveX.</span><span class="sxs-lookup"><span data-stu-id="5be47-108">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="5be47-109">En las implementaciones de servidor perimetral de Lync Server 2013, se requiere un proxy inverso HTTPS en la red perimetral para el acceso de cliente de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="5be47-109">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="5be47-110">También debe publicar direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="5be47-110">You must also publish simple URLs.</span></span> <span data-ttu-id="5be47-111">Para obtener más información, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuración de servidores proxy inversos para Lync server 2013</A> y <A href="lync-server-2013-planning-for-simple-urls.md">planeamiento de direcciones URL simples en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5be47-111">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="5be47-112">Habilitar la autenticación multifactor para Lync Web App</span><span class="sxs-lookup"><span data-stu-id="5be47-112">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="5be47-113">La versión de Lync Server 2013 de Lync Web App admite la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="5be47-113">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="5be47-114">Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar usuarios que se unan desde redes externas cuando inicien sesión en reuniones de Lync.</span><span class="sxs-lookup"><span data-stu-id="5be47-114">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="5be47-115">Puede habilitar la autenticación multifactor si implementa el servidor de Federación de servicio de Federación de Active Directory (AD FS) y habilita la autenticación pasiva en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5be47-115">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="5be47-116">Después de configurar AD FS, los usuarios externos que intenten unirse a reuniones de Lync se presentan con una página web de autenticación multifactor de AD FS que contiene el desafío de nombre de usuario y contraseña, junto con los métodos de autenticación adicionales que haya configurado. .</span><span class="sxs-lookup"><span data-stu-id="5be47-116">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="5be47-117">A continuación, se incluyen algunas consideraciones importantes para planear la configuración de AD FS para la autenticación multifactor:</span><span class="sxs-lookup"><span data-stu-id="5be47-117">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="5be47-p105">La autenticación multifactor de AD FS funciona si el usuario que participa en la reunión y el organizador están en la misma organización o si ambos provienen de una organización federada de AD FS. La autenticación multifactor de AD FS no funciona para usuarios federados de Lync porque la infraestructura web de Lync Server no lo admite en este momento.</span><span class="sxs-lookup"><span data-stu-id="5be47-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="5be47-120">Si usa equilibradores de carga de hardware, habilite la persistencia de las cookies en los equilibradores de carga para que todas las solicitudes del cliente de Lync Web App se controlen mediante el mismo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="5be47-120">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="5be47-121">Al establecer una relación de confianza para usuario autenticado entre Lync Server y los servidores AD FS, asigne un símbolo de vida que sea lo suficientemente largo para que se extienda la longitud máxima de las reuniones de Lync.</span><span class="sxs-lookup"><span data-stu-id="5be47-121">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="5be47-122">Por lo general, una duración de token de 240 minutos es suficiente.</span><span class="sxs-lookup"><span data-stu-id="5be47-122">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="5be47-123">Esta configuración no se aplica a los clientes móviles de Lync.</span><span class="sxs-lookup"><span data-stu-id="5be47-123">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="5be47-124">**Para configurar la autenticación multifactor**</span><span class="sxs-lookup"><span data-stu-id="5be47-124">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="5be47-125">Instale un rol del servidor de federación de AD FS.</span><span class="sxs-lookup"><span data-stu-id="5be47-125">Install an AD FS federation server role.</span></span> <span data-ttu-id="5be47-126">Para obtener más información, consulte la guía de implementación de servicios de Federación de Active Directory 2,0 en<http://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="5be47-126">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="5be47-127">Cree certificados para AD FS.</span><span class="sxs-lookup"><span data-stu-id="5be47-127">Create certificates for AD FS.</span></span> <span data-ttu-id="5be47-128">Para obtener más información, consulte la sección "certificados de servidor de Federación" de los temas planear e implementar AD FS para su uso con el inicio [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)de sesión único en.</span><span class="sxs-lookup"><span data-stu-id="5be47-128">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="5be47-129">Desde la interfaz de línea de comandos de Windows PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5be47-129">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="5be47-130">Establezca una relación de usuario mediante la ejecución del siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5be47-130">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="5be47-131">Defina las siguientes reglas de usuario de confianza:</span><span class="sxs-lookup"><span data-stu-id="5be47-131">Set the following relying party rules:</span></span>
    
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

## <a name="branchcache-configuration"></a><span data-ttu-id="5be47-132">Configuración de BranchCache</span><span class="sxs-lookup"><span data-stu-id="5be47-132">BranchCache Configuration</span></span>

<span data-ttu-id="5be47-133">La característica BranchCache en Windows 7 y Windows Server 2008 R2 puede interferir con los componentes Web de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="5be47-133">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="5be47-134">Para evitar problemas con los usuarios de Lync Web App, asegúrese de que BranchCache no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="5be47-134">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="5be47-135">Para más información sobre cómo deshabilitar BranchCache, consulte la guía de implementación de BranchCache, que está disponible en formato de Word en [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) el centro de descarga de Microsoft, en formato HTML, en la [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)biblioteca técnica de Windows Server 2008 R2 en.</span><span class="sxs-lookup"><span data-stu-id="5be47-135">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="5be47-136">Comprobar la implementación de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="5be47-136">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="5be47-137">Puede usar el cmdlet Test-CsUcwaConference para comprobar que un par de usuarios de prueba puedan participar de una conferencia con la API web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="5be47-137">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="5be47-138">Para obtener más información sobre este cmdlet, vea [probar-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5be47-138">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="5be47-139">Solución de problemas de instalación de complementos en Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5be47-139">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="5be47-140">Si se produce un error en la instalación del complemento en un equipo con Windows Server 2008 R2, es posible que tenga que modificar la configuración de seguridad de Internet Explorer o la configuración de la clave del registro DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="5be47-140">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="5be47-141">**Para modificar la configuración de seguridad en Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="5be47-141">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="5be47-142">Abra Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="5be47-142">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="5be47-143">Haga clic en \*\*Herramientas \*\*, en **Opciones de Internet** y en **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="5be47-143">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="5be47-144">Desplácese hacia abajo hasta la sección **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="5be47-144">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="5be47-145">Desactive **No guardar las páginas cifradas en el disco** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5be47-145">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="5be47-146">Si se selecciona, esta configuración también provocará un error al intentar descargar datos adjuntos desde Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="5be47-146">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="5be47-147">Vuelva a unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="5be47-147">Rejoin the meeting.</span></span> <span data-ttu-id="5be47-148">El complemento se debe descargar sin errores.</span><span class="sxs-lookup"><span data-stu-id="5be47-148">The plug-in should download without errors.</span></span>

<span data-ttu-id="5be47-149">**Para modificar la configuración del registro DisableMSI**</span><span class="sxs-lookup"><span data-stu-id="5be47-149">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="5be47-150">Haga clic en  \*\*Inicio \*\* y en  \*\*Ejecutar \*\*.</span><span class="sxs-lookup"><span data-stu-id="5be47-150">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="5be47-151">Para acceder al Editor del Registro, escriba **regedit**.</span><span class="sxs-lookup"><span data-stu-id="5be47-151">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="5be47-152">Vaya a HKEY\_local\_Machine\\software\\\\Policies\\Microsoft\\Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="5be47-152">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="5be47-153">Edite o agregue la clave del registro DisableMSI de\_escriba REG DWORD y establézcalo en 0.</span><span class="sxs-lookup"><span data-stu-id="5be47-153">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="5be47-154">Vuelva a unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="5be47-154">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5be47-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="5be47-155">See Also</span></span>


[<span data-ttu-id="5be47-156">Configuración de la página de participación en reuniones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5be47-156">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="5be47-157">Plataformas compatibles con Lync Web App para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5be47-157">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

