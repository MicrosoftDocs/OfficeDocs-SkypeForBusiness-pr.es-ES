---
title: 'Lync Server 2013: implementación de la aplicación de la tienda Windows de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49fcea107a4613ca78661a21d492612f82d9775f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="1495e-102">Implementación de la aplicación de la tienda Windows de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1495e-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1495e-103">_**Última modificación del tema:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="1495e-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="1495e-104">Antes de hacer que la aplicación de la tienda Windows de Lync esté disponible para los usuarios, asegúrese de que la implementación cumple los [requisitos de la aplicación de la tienda Windows de Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1495e-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="1495e-105">Para obtener más información sobre cómo configurar Lync Server 2013 para admitir la aplicación de la tienda Windows de Lync, consulte el artículo del blog de NextHop, "detección automática de Lync [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)Server y la aplicación de la tienda Windows de Lync", en.</span><span class="sxs-lookup"><span data-stu-id="1495e-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="1495e-106">Una vez que el entorno de servidor esté configurado correctamente, puede dirigir a los usuarios para que descarguen la aplicación de Lync desde la tienda Windows buscando "Lync".</span><span class="sxs-lookup"><span data-stu-id="1495e-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="1495e-107">Habilitar la autenticación multifactor para la aplicación de la tienda Windows de Lync</span><span class="sxs-lookup"><span data-stu-id="1495e-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="1495e-108">Actualizaciones acumulativas para Lync Server 2013: el 2013 de junio agrega compatibilidad con la autenticación multifactor para los clientes de la aplicación de la tienda Windows de Lync.</span><span class="sxs-lookup"><span data-stu-id="1495e-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="1495e-109">Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar usuarios externos cuando inician sesión en reuniones de Lync.</span><span class="sxs-lookup"><span data-stu-id="1495e-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="1495e-110">Para habilitar la autenticación multifactor, debe implementar el servidor de Federación de servicio de Federación de Active Directory (AD FS) y habilitar la autenticación pasiva en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1495e-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="1495e-111">Después de configurar AD FS, los usuarios externos que intenten unirse a reuniones de Lync se presentan con una página web de autenticación multifactor de AD FS que contiene el desafío de nombre de usuario y contraseña, junto con los métodos de autenticación adicionales que haya configurado. .</span><span class="sxs-lookup"><span data-stu-id="1495e-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="1495e-112">A continuación se indican algunas consideraciones importantes si tiene previsto configurar AD FS para la autenticación multifactor para la aplicación de la tienda Windows de Lync:</span><span class="sxs-lookup"><span data-stu-id="1495e-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1495e-113">Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: se necesita, como mínimo, el 2013 de junio.</span><span class="sxs-lookup"><span data-stu-id="1495e-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="1495e-114">Los clientes de escritorio de Lync 2013 no requieren actualizaciones acumulativas para Lync Server 2013:2013 de junio, por lo que podría parecer que la autenticación pasiva funciona correctamente porque los clientes de Lync 2013 pueden autenticarse.</span><span class="sxs-lookup"><span data-stu-id="1495e-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="1495e-115">Sin embargo, el proceso de autenticación para los clientes de la aplicación de la tienda Windows Lync no se completará y no se mostrará ninguna notificación o mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="1495e-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="1495e-116">El servidor debe estar configurado de modo que la autenticación pasiva sea el único tipo de autenticación ofrecido.</span><span class="sxs-lookup"><span data-stu-id="1495e-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="1495e-117">Si usa equilibradores de carga de hardware, habilite la persistencia de las cookies en los equilibradores de carga para que todas las solicitudes del cliente de la aplicación de la tienda Windows de Lync se controlen mediante el mismo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1495e-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="1495e-118">Al establecer una relación de confianza para usuario autenticado entre Lync Server y los servidores AD FS, asigne un símbolo de vida que sea lo suficientemente largo para que se extienda la longitud máxima de las reuniones de Lync.</span><span class="sxs-lookup"><span data-stu-id="1495e-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="1495e-119">Por lo general, una duración de token de 240 minutos es suficiente.</span><span class="sxs-lookup"><span data-stu-id="1495e-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="1495e-120">**Para configurar la autenticación multifactor**</span><span class="sxs-lookup"><span data-stu-id="1495e-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="1495e-121">Instale un rol del servidor de federación de AD FS.</span><span class="sxs-lookup"><span data-stu-id="1495e-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="1495e-122">Para obtener más información, consulte la guía de implementación de servicios de <http://go.microsoft.com/fwlink/p/?linkid=267511>Federación de active directory 2,0 en.</span><span class="sxs-lookup"><span data-stu-id="1495e-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="1495e-123">Cree certificados para AD FS.</span><span class="sxs-lookup"><span data-stu-id="1495e-123">Create certificates for AD FS.</span></span> <span data-ttu-id="1495e-124">Para obtener más información, consulte la sección "certificados de servidor de Federación" de los temas planear e implementar AD FS para su uso con el inicio [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)de sesión único en.</span><span class="sxs-lookup"><span data-stu-id="1495e-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="1495e-125">Desde la interfaz de línea de comandos de Windows PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1495e-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="1495e-126">Establezca una relación de usuario mediante la ejecución del siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1495e-126">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="1495e-127">Defina las siguientes reglas de usuario de confianza:</span><span class="sxs-lookup"><span data-stu-id="1495e-127">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="1495e-128">Problemas conocidos que pueden impedir el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="1495e-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="1495e-129">La fecha y la hora no se establecen correctamente en el dispositivo que ejecuta la aplicación de la tienda Windows de Lync</span><span class="sxs-lookup"><span data-stu-id="1495e-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="1495e-130">La configuración de hora del dispositivo debe estar sincronizada con la configuración de hora del servidor.</span><span class="sxs-lookup"><span data-stu-id="1495e-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="1495e-131">Esto es especialmente importante para dispositivos como Microsoft Surface y otros dispositivos que ejecutan Windows RT que no están Unidos a un dominio.</span><span class="sxs-lookup"><span data-stu-id="1495e-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="1495e-132">Para establecer la hora en estos dispositivos de forma automática desde un servidor de hora, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="1495e-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="1495e-133">Aplicación de la tienda Windows de Lync no se puede acceder al servidor o servicios de Lync</span><span class="sxs-lookup"><span data-stu-id="1495e-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="1495e-134">Es posible que la aplicación Lync Windows Store no pueda acceder al servidor o los servicios de Lync a través de adaptadores de red, como los módems 4G LTE USB, que no se registran en Windows 8 como dispositivos físicos.</span><span class="sxs-lookup"><span data-stu-id="1495e-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="1495e-135">Es posible que la aplicación de la tienda Windows de Lync tenga este problema incluso cuando las aplicaciones de escritorio y los exploradores puedan acceder a otros servidores y sitios Web.</span><span class="sxs-lookup"><span data-stu-id="1495e-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="1495e-136">Aplicación de la tienda Windows de Lync no se puede iniciar sesión con Lync Server 2010 y el servidor perimetral de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1495e-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="1495e-137">Si su topología consta de Lync Server 2010 con el servidor perimetral R2 de Office Communications Server 2007, tendrá que ejecutar la versión actualizada de Topology Builder disponible en la actualización acumulativa para Lync Server 2010: de 2013 julio.</span><span class="sxs-lookup"><span data-stu-id="1495e-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="1495e-138">Las versiones anteriores de Topology Builder no crean la asignación requerida para Office Communications Server 2007 Edge Server, por lo que los clientes de la aplicación de la tienda Windows Lync no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="1495e-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="1495e-139">Los pasos siguientes son necesarios:</span><span class="sxs-lookup"><span data-stu-id="1495e-139">The following steps are required:</span></span>

1.  <span data-ttu-id="1495e-140">Instale la actualización acumulativa para Lync Server 2010:2013 de julio en los grupos de Lync Server 2010 y los directores de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1495e-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="1495e-141">Actualice la configuración de detección automática de Lync para indicar que el punto de entrada SIP externo es la dirección del servidor perimetral haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1495e-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="1495e-142">Abra el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1495e-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="1495e-143">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1495e-143">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="1495e-144">La aplicación de la tienda Windows de Lync no puede iniciar sesión debido a un error de validación de nombre de certificado</span><span class="sxs-lookup"><span data-stu-id="1495e-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="1495e-145">Puede producirse un problema de inicio de sesión para los usuarios de Office 365 que no ejecutan la versión más reciente de la aplicación de la tienda Windows de Lync.</span><span class="sxs-lookup"><span data-stu-id="1495e-145">A sign-in issue can occur for Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="1495e-146">Este problema suele ocurrir cuando se usan varios dominios (por ejemplo, cuando el URI del SIP es **Usera@domainZ.com** pero el servidor perimetral es **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="1495e-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="1495e-147">Para solucionar el problema, los usuarios deben instalar la última versión de la aplicación Lync de la tienda Windows, que también requiere Windows 8,1.</span><span class="sxs-lookup"><span data-stu-id="1495e-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="1495e-148">Usar los registros de la aplicación Lync Windows Store para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="1495e-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="1495e-149">Puede usar los registros generados en el dispositivo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="1495e-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="1495e-150">Los registros se almacenan en la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="1495e-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="1495e-151">% LocalAppData%\\Packages\\Microsoft.\_LyncMX\\8wekyb3d8bbwe\\LocalState Tracing</span><span class="sxs-lookup"><span data-stu-id="1495e-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="1495e-152">Antes de obtener los registros de un usuario, asegúrese de que el registro esté activado y, a continuación, pida al usuario que guarde los registros para que toda la información almacenada en la memoria también se guarde en los archivos del disco duro.</span><span class="sxs-lookup"><span data-stu-id="1495e-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="1495e-153">**Para activar el registro**</span><span class="sxs-lookup"><span data-stu-id="1495e-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="1495e-154">Abra la aplicación de la tienda Windows de Lync en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1495e-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="1495e-155">Deslice el dedo desde el lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="1495e-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="1495e-156">Si usa un mouse, apunte a la esquina superior derecha de la pantalla y, a continuación, mueva el puntero del mouse hacia abajo en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="1495e-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="1495e-157">Seleccione **configuración**, seleccione **Opciones**y, a continuación, establezca registros **de** **diagnóstico** en activado.</span><span class="sxs-lookup"><span data-stu-id="1495e-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="1495e-158">Si los **registros de diagnóstico** estaban deshabilitados anteriormente, debe reiniciar Lync.</span><span class="sxs-lookup"><span data-stu-id="1495e-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="1495e-159">Para reiniciar Lync, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="1495e-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="1495e-160">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1495e-160">Restart the device.</span></span>
    
      - <span data-ttu-id="1495e-161">Finalice la tarea de Lync y vuelva a iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1495e-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="1495e-162">Para finalizar la tarea, abra el administrador de tareas de Windows, seleccione **Lync**y, a continuación, puntee en **Finalizar tarea**.</span><span class="sxs-lookup"><span data-stu-id="1495e-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="1495e-163">Si Lync no aparece en la lista, pulse **más detalles** y busque Lync en **procesos en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="1495e-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="1495e-164">**Para guardar los registros**</span><span class="sxs-lookup"><span data-stu-id="1495e-164">**To save the logs**</span></span>

1.  <span data-ttu-id="1495e-165">Abra la aplicación de la tienda Windows de Lync en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1495e-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="1495e-166">Intente iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="1495e-166">Try signing in.</span></span>

3.  <span data-ttu-id="1495e-167">Deslice el dedo desde el lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="1495e-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="1495e-168">Si usa un mouse, apunte a la esquina superior derecha de la pantalla y, a continuación, mueva el puntero del mouse hacia abajo en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="1495e-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="1495e-169">Seleccione **configuración**, seleccione **acerca**de y, a continuación, haga clic en **guardar registros**.</span><span class="sxs-lookup"><span data-stu-id="1495e-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

