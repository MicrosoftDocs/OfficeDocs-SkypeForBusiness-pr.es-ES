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
ms.openlocfilehash: aaae8df4d21e3aa766bd452c5ffd697dce30660a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507487"
---
# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="9a07a-102">Implementación de la aplicación Lync de la tienda Windows en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a07a-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a07a-103">_**Última modificación del tema:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="9a07a-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="9a07a-104">Antes de poner a disposición de los usuarios la aplicación Lync de la tienda Windows, asegúrese de que la implementación cumple los [requisitos de la aplicación de Lync para Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a07a-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="9a07a-105">Para obtener más información sobre cómo configurar Lync Server 2013 para que admita la aplicación Lync de la tienda Windows, vea el artículo del blog NextHop, "Lync Server Autodiscover y la aplicación Lync Windows Store", en [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966) .</span><span class="sxs-lookup"><span data-stu-id="9a07a-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="9a07a-106">Una vez configurado correctamente el entorno de servidor, puede dirigir a los usuarios para que descarguen la aplicación Lync desde la tienda Windows buscando "Lync".</span><span class="sxs-lookup"><span data-stu-id="9a07a-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="9a07a-107">Habilitar la autenticación multifactor para la aplicación de la tienda Windows de Lync</span><span class="sxs-lookup"><span data-stu-id="9a07a-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="9a07a-108">Actualizaciones acumulativas para Lync Server 2013: el 2013 de junio agrega compatibilidad con la autenticación multifactor para los clientes de la aplicación de la tienda Windows de Lync.</span><span class="sxs-lookup"><span data-stu-id="9a07a-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="9a07a-109">Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios externos cuando inician sesión en reuniones de Lync.</span><span class="sxs-lookup"><span data-stu-id="9a07a-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="9a07a-110">Para habilitar la autenticación multifactor, debe implementar el servidor de Federación del servicio de Federación de Active Directory (AD FS) y habilitar la autenticación pasiva en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a07a-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="9a07a-111">Una vez configurado AD FS, los usuarios externos que intenten unirse a reuniones de Lync reciben una página web de autenticación multifactor de AD FS que contiene el desafío de nombre de usuario y contraseña junto con los métodos de autenticación adicionales que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="9a07a-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="9a07a-112">Las siguientes son consideraciones importantes si planea configurar AD FS para la autenticación multifactor para la aplicación de la tienda Windows de Lync:</span><span class="sxs-lookup"><span data-stu-id="9a07a-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9a07a-113">Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: se requiere junio de 2013 como mínimo.</span><span class="sxs-lookup"><span data-stu-id="9a07a-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="9a07a-114">Los clientes de escritorio de Lync 2013 no requieren actualizaciones acumulativas para Lync Server 2013: junio de 2013, por lo que puede parecer que la autenticación pasiva funciona porque los clientes de Lync 2013 pueden realizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="9a07a-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="9a07a-115">Sin embargo, el proceso de autenticación para los clientes de la aplicación de la tienda Windows Lync no se completará y no se mostrará ningún mensaje de notificación o error.</span><span class="sxs-lookup"><span data-stu-id="9a07a-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="9a07a-116">El servidor debe estar configurado para que la autenticación pasiva sea el único tipo de autenticación ofrecido.</span><span class="sxs-lookup"><span data-stu-id="9a07a-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="9a07a-117">Si usa equilibradores de carga de hardware, habilite la persistencia de las cookies en los equilibradores de carga para que todas las solicitudes del cliente de la aplicación de la tienda Windows de Lync se controlen con el mismo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="9a07a-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="9a07a-118">Cuando establezca una relación de confianza para usuario autenticado entre los servidores de Lync Server y AD FS, asigne una duración de tokens lo suficientemente larga como para extender la longitud máxima de las reuniones de Lync.</span><span class="sxs-lookup"><span data-stu-id="9a07a-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="9a07a-119">Normalmente, una duración de token de 240 minutos es suficiente.</span><span class="sxs-lookup"><span data-stu-id="9a07a-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="9a07a-120">**Para configurar la autenticación multifactor**</span><span class="sxs-lookup"><span data-stu-id="9a07a-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="9a07a-121">Instale un rol de servidor de Federación de AD FS.</span><span class="sxs-lookup"><span data-stu-id="9a07a-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="9a07a-122">Para obtener más información, consulte la guía de implementación de los servicios de Federación de Active Directory 2,0 en <https://go.microsoft.com/fwlink/p/?linkid=267511> .</span><span class="sxs-lookup"><span data-stu-id="9a07a-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="9a07a-123">Crear certificados para AD FS.</span><span class="sxs-lookup"><span data-stu-id="9a07a-123">Create certificates for AD FS.</span></span> <span data-ttu-id="9a07a-124">Para obtener más información, consulte la sección "certificados de servidor de Federación" del tema Plan for and Deploy AD FS for use with Single Sign-on [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .</span><span class="sxs-lookup"><span data-stu-id="9a07a-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="9a07a-125">Desde la interfaz de línea de comandos de Windows PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9a07a-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="9a07a-126">Establezca una asociación mediante la ejecución del siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9a07a-126">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="9a07a-127">Establezca las siguientes reglas de usuario de confianza:</span><span class="sxs-lookup"><span data-stu-id="9a07a-127">Set the following relying party rules:</span></span>
    
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

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="9a07a-128">Problemas conocidos que pueden impedir el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9a07a-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="9a07a-129">La hora y la fecha no se establecen correctamente en el dispositivo que ejecuta la aplicación Lync de la tienda Windows</span><span class="sxs-lookup"><span data-stu-id="9a07a-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="9a07a-130">La configuración de la hora en el dispositivo debe estar sincronizada con la configuración de hora en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9a07a-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="9a07a-131">Esto es especialmente importante para dispositivos como Microsoft Surface y otros dispositivos que ejecutan Windows RT que no están Unidos a un dominio.</span><span class="sxs-lookup"><span data-stu-id="9a07a-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="9a07a-132">Para establecer la hora en estos dispositivos automáticamente desde un servidor de hora, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="9a07a-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="9a07a-133">Lync la aplicación de la tienda Windows no puede acceder a Lync Server o a los servicios</span><span class="sxs-lookup"><span data-stu-id="9a07a-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="9a07a-134">Es posible que la aplicación Lync de la tienda Windows no pueda obtener acceso a Lync Server o a los servicios a través de adaptadores de red, como los módems USB de 4G LTE, que no se registran en Windows 8 como dispositivos físicos.</span><span class="sxs-lookup"><span data-stu-id="9a07a-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="9a07a-135">Lync la aplicación de la tienda Windows puede tener este problema incluso cuando las aplicaciones de escritorio y los exploradores puedan acceder a otros servidores y sitios Web.</span><span class="sxs-lookup"><span data-stu-id="9a07a-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="9a07a-136">Lync la aplicación de la tienda Windows no puede iniciar sesión con el servidor perimetral de Lync Server 2010 y Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9a07a-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="9a07a-137">Si su topología consta de Lync Server 2010 con Office Communications Server 2007 R2 Edge Server, tendrá que ejecutar la versión actualizada del generador de topologías disponible en la actualización acumulativa de Lync Server 2010: de julio de 2013.</span><span class="sxs-lookup"><span data-stu-id="9a07a-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="9a07a-138">Las versiones anteriores del generador de topologías no crean la asignación necesaria al servidor perimetral de Office Communications Server 2007, por lo que los clientes de la aplicación de la tienda Windows de Lync no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="9a07a-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="9a07a-139">Se requieren los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a07a-139">The following steps are required:</span></span>

1.  <span data-ttu-id="9a07a-140">Instale la actualización acumulativa para Lync Server 2010:2013 de julio en los grupos de servidores de Lync Server 2010 y los directores de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9a07a-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="9a07a-141">Actualice la configuración de detección automática de Lync para indicar que el punto de entrada SIP externo es la dirección del servidor perimetral; para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a07a-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="9a07a-142">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a07a-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="9a07a-143">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9a07a-143">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="9a07a-144">Lync la aplicación de la tienda Windows no puede iniciar sesión debido a un error de validación de nombre de certificado</span><span class="sxs-lookup"><span data-stu-id="9a07a-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="9a07a-145">Puede producirse un problema de inicio de sesión para los usuarios de Microsoft 365 o Office 365 que no ejecutan la versión más reciente de la aplicación de la tienda Windows de Lync.</span><span class="sxs-lookup"><span data-stu-id="9a07a-145">A sign-in issue can occur for Microsoft 365 or Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="9a07a-146">Este problema suele producirse cuando se usan varios dominios (por ejemplo, cuando el URI del SIP es **Usera@domainZ.com** pero el servidor perimetral es **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="9a07a-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="9a07a-147">Para solucionar el problema, los usuarios deben instalar la última versión de la aplicación Lync de la tienda Windows, que también requiere Windows 8,1.</span><span class="sxs-lookup"><span data-stu-id="9a07a-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="9a07a-148">Usar registros de aplicación de la tienda Windows Lync para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="9a07a-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="9a07a-149">Puede usar los registros generados en el dispositivo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="9a07a-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="9a07a-150">Los registros se almacenan en la carpeta siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a07a-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="9a07a-151">% LocalAppData% \\ Packages \\ Microsoft. LyncMX \_ 8wekyb3d8bbwe \\ LocalState \\ Tracing</span><span class="sxs-lookup"><span data-stu-id="9a07a-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="9a07a-152">Antes de obtener los registros de un usuario, asegúrese de que esté activado el registro y, a continuación, pida al usuario que guarde los registros para que toda la información almacenada en la memoria también se guarde en los archivos del disco duro.</span><span class="sxs-lookup"><span data-stu-id="9a07a-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="9a07a-153">**Para activar el registro**</span><span class="sxs-lookup"><span data-stu-id="9a07a-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="9a07a-154">Abra la aplicación Lync de la tienda Windows en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9a07a-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="9a07a-155">Deslice el dedo desde el lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="9a07a-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="9a07a-156">Si está usando un mouse, coloque el puntero en la esquina superior derecha de la pantalla y, a continuación, mueva el puntero del mouse hacia abajo en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="9a07a-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="9a07a-157">Seleccione **configuración**, seleccione **Opciones**y, después, establezca los registros **de** **diagnóstico** en activado.</span><span class="sxs-lookup"><span data-stu-id="9a07a-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="9a07a-158">Si los **registros de diagnóstico** se desactivaron anteriormente, debe reiniciar Lync.</span><span class="sxs-lookup"><span data-stu-id="9a07a-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="9a07a-159">Para reiniciar Lync, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="9a07a-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="9a07a-160">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9a07a-160">Restart the device.</span></span>
    
      - <span data-ttu-id="9a07a-161">Finalice la tarea de Lync y vuelva a iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9a07a-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="9a07a-162">Para finalizar la tarea, abra el administrador de tareas de Windows, seleccione **Lync**y, a continuación, puntee en **Finalizar tarea**.</span><span class="sxs-lookup"><span data-stu-id="9a07a-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="9a07a-163">Si Lync no aparece en la lista, pulse **más detalles** y busque Lync en **procesos en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="9a07a-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="9a07a-164">**Para guardar los registros**</span><span class="sxs-lookup"><span data-stu-id="9a07a-164">**To save the logs**</span></span>

1.  <span data-ttu-id="9a07a-165">Abra la aplicación Lync de la tienda Windows en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9a07a-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="9a07a-166">Intente iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="9a07a-166">Try signing in.</span></span>

3.  <span data-ttu-id="9a07a-167">Deslice el dedo desde el lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="9a07a-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="9a07a-168">Si está usando un mouse, coloque el puntero en la esquina superior derecha de la pantalla y, a continuación, mueva el puntero del mouse hacia abajo en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="9a07a-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="9a07a-169">Seleccione **configuración**, seleccione **acerca**de y, a continuación, seleccione **guardar registros**.</span><span class="sxs-lookup"><span data-stu-id="9a07a-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

