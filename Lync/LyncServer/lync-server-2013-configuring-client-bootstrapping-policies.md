---
title: 'Lync Server 2013: configuración de directivas de inicio de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8258063645267fb12801548ddfdeae1b4ef7c795
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="52158-102">Configuración de directivas de inicio de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52158-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52158-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="52158-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="52158-104">La Consola de administración de directivas de grupo (GPMC) y el Editor de objetos de directiva de grupo son herramientas que puede usar para administrar directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="52158-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="52158-105">En la plantilla administrativa de la Directiva de grupo de Office se incluyen las plantillas administrativas de Lync 2013. ADMX (ADMX) y. ADML (ADML), que contienen la configuración de directiva basada en el registro que se configura para los objetos de directiva de grupo en el dominio.</span><span class="sxs-lookup"><span data-stu-id="52158-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="52158-106">Los archivos ADML son complementos específicos del idioma de los archivos ADMX.</span><span class="sxs-lookup"><span data-stu-id="52158-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="52158-107">Todos los archivos ADMX y ADML contienen la configuración de directiva de una única aplicación de Office.</span><span class="sxs-lookup"><span data-stu-id="52158-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="52158-108">Para obtener más información, consulte "archivos de plantilla administrativa (ADMX, ADML) de Office 2013" en la documentación <http://go.microsoft.com/fwlink/p/?linkid=267516>de Office 2013 en.</span><span class="sxs-lookup"><span data-stu-id="52158-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="52158-109">Para Lync 2013, hay varias directivas de inicio del cliente que debe considerar configurar antes de que los usuarios inicien sesión en el servidor por primera vez.</span><span class="sxs-lookup"><span data-stu-id="52158-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="52158-110">Por ejemplo, el modo de seguridad y los servidores predeterminados que el cliente tiene que usar hasta que se complete el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="52158-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="52158-111">Puede usar esta directiva de grupo para establecer estas configuraciones en los registros de los equipos de los usuarios antes de que inicien sesión y reciban configuraciones de aprovisionamiento dentro de banda del servidor.</span><span class="sxs-lookup"><span data-stu-id="52158-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="52158-112">En la siguiente tabla se enumeran las opciones de configuración de directiva de grupo disponibles para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="52158-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="52158-113">Configuración de directiva de grupo para Lync 2013</span><span class="sxs-lookup"><span data-stu-id="52158-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52158-114">Configuración de directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="52158-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="52158-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="52158-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52158-116">Especificar servidor</span><span class="sxs-lookup"><span data-stu-id="52158-116">Specify Server</span></span><br />
<span data-ttu-id="52158-117">(ConfigurationMode)</span><span class="sxs-lookup"><span data-stu-id="52158-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="52158-118">Especifica cómo Lync 2013 identifica el transporte y el servidor que se van a usar durante el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="52158-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="52158-119">En esta opción puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52158-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="52158-120">ServerAddressExternal: especifica el nombre del servidor o la dirección IP que utilizan los clientes y los contactos federados al conectarse desde fuera del firewall externo.</span><span class="sxs-lookup"><span data-stu-id="52158-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="52158-121">ServerAddressInternal: especifica el nombre del servidor o la dirección IP que se utilizan cuando los clientes se conectan desde dentro del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="52158-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="52158-122">Transporte: especifica el Protocolo de control de transmisión (TCP) o Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="52158-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52158-123">Versiones de servidor adicionales admitidas</span><span class="sxs-lookup"><span data-stu-id="52158-123">Additional server versions supported</span></span><br />
<span data-ttu-id="52158-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="52158-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="52158-125">Especifica una lista de nombres de versión de servidor separados por puntos y comas donde Lync Server 2013 iniciará sesión, además de las versiones de servidor que son compatibles de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="52158-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52158-126">Deshabilitar la carga automática de los registros de errores de inicio de sesión (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="52158-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="52158-127">Carga automáticamente registros de errores de inicio de sesión en Lync Server para su análisis.</span><span class="sxs-lookup"><span data-stu-id="52158-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="52158-128">No se cargan automáticamente registros si el inicio de sesión es correcto.</span><span class="sxs-lookup"><span data-stu-id="52158-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="52158-129">Si esta directiva no está configurada, ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52158-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="52158-130">Para usuarios de Lync Online: los registros de errores de inicio de sesión se cargan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="52158-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="52158-131">Para los usuarios de Lync local: se muestra un cuadro de diálogo de confirmación para el usuario antes de cargarlo.</span><span class="sxs-lookup"><span data-stu-id="52158-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="52158-132">Cuando esta configuración está deshabilitada, los registros de inicio de sesión se cargan automáticamente en el servidor de Lync para los usuarios de Lync local y Lync Online.</span><span class="sxs-lookup"><span data-stu-id="52158-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="52158-133">Cuando este parámetro está habilitado, los registros de inicio de sesión nunca se cargan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="52158-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52158-134">Deshabilitar la reserva HTTP para conexión SIP</span><span class="sxs-lookup"><span data-stu-id="52158-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="52158-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="52158-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="52158-136">Impide que Lync Server intente conectarse al servidor mediante HTTP, si TLS o TCP no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="52158-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="52158-137">De forma predeterminada, Lync primero intenta conectarse al servidor mediante TLS o TCP y, si ninguno de estos métodos de transporte se realiza correctamente, Lync intenta conectarse mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="52158-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="52158-138">Use esta directiva para deshabilitar el intento de conexión HTTP de reserva.</span><span class="sxs-lookup"><span data-stu-id="52158-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52158-139">Requerir credenciales de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="52158-139">Require logon credentials</span></span><br />
<span data-ttu-id="52158-140">(DisableNTCredentials)</span><span class="sxs-lookup"><span data-stu-id="52158-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="52158-141">Requiere que el usuario proporcione las credenciales de inicio de sesión de Lync en lugar de usar automáticamente las credenciales de Windows durante el inicio de sesión en un servidor SIP.</span><span class="sxs-lookup"><span data-stu-id="52158-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52158-142">Deshabilitar comprobación de la versión del servidor</span><span class="sxs-lookup"><span data-stu-id="52158-142">Disable server version check</span></span><br />
<span data-ttu-id="52158-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="52158-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="52158-144">Si establece esta directiva en 1, evitará que Lync Compruebe el nombre del servidor y la versión antes de iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="52158-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="52158-145">De forma predeterminada, Lync realiza estas comprobaciones antes de iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="52158-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52158-146">Habilitar el uso de BITS para descargar los archivos del servicio de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="52158-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="52158-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="52158-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="52158-148">Permite que Lync use el servicio de transferencia inteligente en segundo plano (BITS) para descargar los archivos de los servicios de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="52158-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52158-149">Configurar el modo de seguridad SIP</span><span class="sxs-lookup"><span data-stu-id="52158-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="52158-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="52158-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="52158-151">Permite a Lync enviar y recibir mensajes instantáneos de forma más segura.</span><span class="sxs-lookup"><span data-stu-id="52158-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="52158-152">Esta directiva no afecta a los servicios de Microsoft Exchange Server ni Windows .NET.</span><span class="sxs-lookup"><span data-stu-id="52158-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="52158-153">Si no establece esta configuración de Directiva, Lync puede usar cualquier transporte.</span><span class="sxs-lookup"><span data-stu-id="52158-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="52158-154">Pero si no usa TLS y el servidor autentica a los usuarios, Lync debe usar la autenticación NTLM o Kerberos.</span><span class="sxs-lookup"><span data-stu-id="52158-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52158-155">Descarga inicial de la libreta de direcciones global</span><span class="sxs-lookup"><span data-stu-id="52158-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="52158-156">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="52158-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="52158-p110">Especifica el período de tiempo que transcurrirá antes de que se produzca una descarga de la lista global de direcciones (GAL). El valor predeterminado es 60 minutos, lo que significa que el servidor retrasa la descarga del archivo GAL durante un período de tiempo aleatorio comprendido entre 0 y 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="52158-p110">Specifies the time period before a download of the global address list (GAL) occurs. The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52158-159">Impedir que los usuarios ejecuten Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="52158-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="52158-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="52158-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="52158-161">Impide que los usuarios ejecuten Lync.</span><span class="sxs-lookup"><span data-stu-id="52158-161">Prevents users from running Lync.</span></span> <span data-ttu-id="52158-162">Puede establecer esta configuración de directiva en Configuración del equipo o en Configuración de usuario, pero la configuración de directiva de Configuración del equipo tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="52158-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52158-163">Permitir el almacenamiento de contraseñas de usuario</span><span class="sxs-lookup"><span data-stu-id="52158-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="52158-164">(SavePassword)</span><span class="sxs-lookup"><span data-stu-id="52158-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="52158-165">Permite a Lync almacenar contraseñas.</span><span class="sxs-lookup"><span data-stu-id="52158-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52158-166">Configurar el modo de compresión SIP</span><span class="sxs-lookup"><span data-stu-id="52158-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="52158-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="52158-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="52158-p112">Especifica cuándo debe activarse la compresión SIP. De forma predeterminada, la compresión SIP se habilita en función de la velocidad del adaptador. Tenga en cuenta que la configuración de esta directiva puede provocar un aumento en el tiempo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="52158-p112">Specifies when to turn on SIP compression. By default, SIP compression is enabled based on the adapter speed. Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52158-171">Lista de dominios de confianza</span><span class="sxs-lookup"><span data-stu-id="52158-171">Trusted Domain List</span></span><br />
<span data-ttu-id="52158-172">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="52158-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="52158-173">Muestra los dominios de confianza que no coinciden con el prefijo del dominio SIP del cliente.</span><span class="sxs-lookup"><span data-stu-id="52158-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52158-p113">Las directivas configuradas en el servidor tienen prioridad frente a la configuración de las directivas de grupo y las opciones de cliente que configure el usuario. En la tabla siguiente se indica el orden de prioridad de la configuración cuando se produce un conflicto.</span><span class="sxs-lookup"><span data-stu-id="52158-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="52158-176">Prioridad de las directivas de grupo</span><span class="sxs-lookup"><span data-stu-id="52158-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52158-177">Prioridad</span><span class="sxs-lookup"><span data-stu-id="52158-177">Precedence</span></span></th>
<th><span data-ttu-id="52158-178">Ubicación o método de configuración</span><span class="sxs-lookup"><span data-stu-id="52158-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52158-179">1</span><span class="sxs-lookup"><span data-stu-id="52158-179">1</span></span></p></td>
<td><p><span data-ttu-id="52158-180">Aprovisionamiento en banda de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52158-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52158-181">1</span><span class="sxs-lookup"><span data-stu-id="52158-181">2</span></span></p></td>
<td><p><span data-ttu-id="52158-182">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="52158-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52158-183">3</span><span class="sxs-lookup"><span data-stu-id="52158-183">3</span></span></p></td>
<td><p><span data-ttu-id="52158-184">HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="52158-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52158-185">4</span><span class="sxs-lookup"><span data-stu-id="52158-185">4</span></span></p></td>
<td><p><span data-ttu-id="52158-186">El cuadro de diálogo Lync-opciones en Lync 2013</span><span class="sxs-lookup"><span data-stu-id="52158-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="52158-187">Para definir la configuración de directiva de grupo mediante los archivos de plantilla administrativa de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="52158-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="52158-p114">Cree una carpeta de nivel de raíz que contenga todos los archivos ADMX independientes del idioma. Por ejemplo, cree la carpeta raíz del almacén central en el controlador del dominio en esta ubicación:</span><span class="sxs-lookup"><span data-stu-id="52158-p114">Create a root-level folder to contain all language-neutral ADMX files. For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52158-p115">Este procedimiento presupone que desea administrar varios equipos en su dominio. En este caso, almacena las plantillas de un almacén central en la carpeta Sysvol del controlador del dominio principal. Así obtendrá una ubicación de almacenamiento central replicada para las plantillas administrativas del dominio.</span><span class="sxs-lookup"><span data-stu-id="52158-p115">This procedure assumes that you want to manage multiple computers in your domain. In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller. This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="52158-p116">Cree una subcarpeta para cada idioma que vaya a utilizar. Estas subcarpetas contendrán los archivos de recursos ADML específicos del idioma. Por ejemplo, cree una subcarpeta para inglés de Estados Unidos (EN-US) en esta ubicación:</span><span class="sxs-lookup"><span data-stu-id="52158-p116">Create a subfolder for each language that you’ll use. These subfolders will contain the language-specific ADML resource files. For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

