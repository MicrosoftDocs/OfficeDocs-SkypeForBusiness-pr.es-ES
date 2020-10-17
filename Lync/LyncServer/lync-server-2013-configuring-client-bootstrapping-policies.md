---
title: 'Lync Server 2013: configuración de directivas de arranque de cliente'
description: 'Lync Server 2013: configuración de directivas de arranque de cliente.'
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
ms.openlocfilehash: 3c03a9f7954d42f128dd6ae96296069ae5a515e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545636"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="46e76-103">Configuración de directivas de arranque de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46e76-103">Configuring client bootstrapping policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46e76-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="46e76-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="46e76-105">La consola de administración de directivas de grupo (GPMC) y el editor de objetos de directiva de grupo son herramientas que se usan para administrar la Directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="46e76-105">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="46e76-106">En la plantilla administrativa de la Directiva de grupo de Office se incluyen plantillas administrativas de Lync 2013. ADMX (ADMX) y. ADML (ADML), que contienen las opciones de directiva basadas en el registro que se configuran para los objetos de directiva de grupo en el dominio.</span><span class="sxs-lookup"><span data-stu-id="46e76-106">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="46e76-107">Los archivos ADML son complementos específicos de idioma para archivos ADMX.</span><span class="sxs-lookup"><span data-stu-id="46e76-107">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="46e76-108">Cada archivo ADMX y ADML contiene la configuración de directiva para una sola aplicación de Office.</span><span class="sxs-lookup"><span data-stu-id="46e76-108">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="46e76-109">Para obtener más información, consulte "Office 2013 Administrative template files (ADMX, ADML)" en la documentación de Office 2013 en <https://go.microsoft.com/fwlink/p/?linkid=267516> .</span><span class="sxs-lookup"><span data-stu-id="46e76-109">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="46e76-110">Para Lync 2013, hay varias directivas de arranque de cliente que debe considerar configurar antes de que los usuarios inicien sesión en el servidor por primera vez.</span><span class="sxs-lookup"><span data-stu-id="46e76-110">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="46e76-111">Por ejemplo, el modo de seguridad y los servidores predeterminados que el cliente debe usar hasta que se complete el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="46e76-111">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="46e76-112">Puede usar la Directiva de grupo para establecer estas opciones en los registros del equipo de los usuarios antes de iniciar sesión y comenzar a recibir la configuración de aprovisionamiento en banda del servidor.</span><span class="sxs-lookup"><span data-stu-id="46e76-112">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="46e76-113">En la siguiente tabla se enumeran las opciones de configuración de directiva de grupo que están disponibles para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="46e76-113">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="46e76-114">Configuración de directiva de grupo para Lync 2013</span><span class="sxs-lookup"><span data-stu-id="46e76-114">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46e76-115">Configuración de directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="46e76-115">Group Policy setting</span></span></th>
<th><span data-ttu-id="46e76-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="46e76-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46e76-117">Especificar servidor</span><span class="sxs-lookup"><span data-stu-id="46e76-117">Specify Server</span></span><br />
<span data-ttu-id="46e76-118">ConfigurationMode</span><span class="sxs-lookup"><span data-stu-id="46e76-118">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="46e76-119">Especifica cómo Lync 2013 identifica el transporte y el servidor que se deben usar durante el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="46e76-119">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="46e76-120">En esta configuración, debe especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="46e76-120">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="46e76-121">ServerAddressExternal: especifica el nombre del servidor o la dirección IP que usan los clientes y los contactos federados cuando se conectan desde fuera del firewall externo.</span><span class="sxs-lookup"><span data-stu-id="46e76-121">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="46e76-122">ServerAddressInternal: especifica el nombre del servidor o la dirección IP que se usa cuando los clientes se conectan desde dentro del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="46e76-122">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="46e76-123">Transport: especifica el protocolo de control de transmisión (TCP) o la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="46e76-123">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e76-124">Versiones de servidor adicionales admitidas</span><span class="sxs-lookup"><span data-stu-id="46e76-124">Additional server versions supported</span></span><br />
<span data-ttu-id="46e76-125">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="46e76-125">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="46e76-126">Especifica una lista de nombres de versiones de servidor separados por punto y coma en los que Lync Server 2013 iniciará sesión, además de las versiones de servidor admitidas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="46e76-126">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e76-127">Deshabilitar la carga automática de registros de error de inicio de sesión (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="46e76-127">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="46e76-128">Carga automáticamente los registros de error de inicio de sesión en Lync Server para su análisis.</span><span class="sxs-lookup"><span data-stu-id="46e76-128">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="46e76-129">Si el inicio de sesión se realiza correctamente, no se cargará automáticamente ningún registro.</span><span class="sxs-lookup"><span data-stu-id="46e76-129">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="46e76-130">Si esta Directiva no está configurada, ocurrirá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="46e76-130">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="46e76-131">Para los usuarios de Lync Online: los registros de error de inicio de sesión se cargan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="46e76-131">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="46e76-132">Para los usuarios de Lync local: se muestra un cuadro de diálogo de confirmación al usuario antes de cargarlo.</span><span class="sxs-lookup"><span data-stu-id="46e76-132">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="46e76-133">Cuando esta configuración está deshabilitada, los registros de inicio de sesión se cargan automáticamente en el servidor Lync para los usuarios de Lync local y Lync Online.</span><span class="sxs-lookup"><span data-stu-id="46e76-133">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="46e76-134">Cuando esta configuración está habilitada, los registros de inicio de sesión nunca se cargan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="46e76-134">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e76-135">Deshabilitar la reserva HTTP para la conexión SIP</span><span class="sxs-lookup"><span data-stu-id="46e76-135">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="46e76-136">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="46e76-136">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="46e76-137">Impide que Lync Server intente conectarse al servidor mediante HTTP, si TLS o TCP no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="46e76-137">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="46e76-138">De forma predeterminada, Lync intenta primero conectar con el servidor mediante TLS o TCP y, si ninguno de estos métodos de transporte funciona correctamente, Lync intenta conectarse mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="46e76-138">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="46e76-139">Use esta directiva para deshabilitar el intento de conexión HTTP de reserva.</span><span class="sxs-lookup"><span data-stu-id="46e76-139">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e76-140">Requerir credenciales de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="46e76-140">Require logon credentials</span></span><br />
<span data-ttu-id="46e76-141">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="46e76-141">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="46e76-142">Requiere que el usuario proporcione credenciales de inicio de sesión para Lync en lugar de usar automáticamente las credenciales de Windows durante el inicio de sesión en un servidor SIP.</span><span class="sxs-lookup"><span data-stu-id="46e76-142">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e76-143">Deshabilitar la comprobación de la versión del servidor</span><span class="sxs-lookup"><span data-stu-id="46e76-143">Disable server version check</span></span><br />
<span data-ttu-id="46e76-144">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="46e76-144">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="46e76-145">Si establece esta directiva en 1, impide que Lync Compruebe el nombre del servidor y la versión antes de iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="46e76-145">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="46e76-146">De forma predeterminada, Lync realiza estas comprobaciones antes de iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="46e76-146">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e76-147">Habilitar el uso de BITS para descargar archivos del servicio de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="46e76-147">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="46e76-148">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="46e76-148">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="46e76-149">Permite que Lync use el servicio de transferencia inteligente en segundo plano (BITS) para descargar los archivos de los servicios de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="46e76-149">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e76-150">Configurar el modo de seguridad SIP</span><span class="sxs-lookup"><span data-stu-id="46e76-150">Configure SIP security mode</span></span><br />
<span data-ttu-id="46e76-151">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="46e76-151">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="46e76-152">Permite a Lync enviar y recibir mensajes instantáneos de forma más segura.</span><span class="sxs-lookup"><span data-stu-id="46e76-152">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="46e76-153">Esta directiva no se aplica a los servicios de Windows .NET o Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="46e76-153">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="46e76-154">Si no establece esta configuración de Directiva, Lync puede usar cualquier transporte.</span><span class="sxs-lookup"><span data-stu-id="46e76-154">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="46e76-155">Pero si no usa TLS y el servidor autentica a los usuarios, Lync debe usar la autenticación NTLM o Kerberos.</span><span class="sxs-lookup"><span data-stu-id="46e76-155">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e76-156">Retraso inicial de descarga de libreta de direcciones global</span><span class="sxs-lookup"><span data-stu-id="46e76-156">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="46e76-157">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="46e76-157">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="46e76-158">Especifica el período de tiempo que debe transcurrir antes de que se produzca una descarga de la lista global de direcciones (GAL).</span><span class="sxs-lookup"><span data-stu-id="46e76-158">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="46e76-159">El valor predeterminado es de 60 minutos, lo que significa que el servidor retrasa la descarga del archivo GAL durante un período aleatorio comprendido entre 0 y 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="46e76-159">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e76-160">Impedir que los usuarios ejecuten Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="46e76-160">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="46e76-161">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="46e76-161">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="46e76-162">Impide que los usuarios ejecuten Lync.</span><span class="sxs-lookup"><span data-stu-id="46e76-162">Prevents users from running Lync.</span></span> <span data-ttu-id="46e76-163">Puede configurar esta opción de directiva en Configuración del equipo y Configuración de usuario, si bien la configuración de directiva establecida en Configuración del equipo tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="46e76-163">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e76-164">Permitir el almacenamiento de contraseñas de usuario</span><span class="sxs-lookup"><span data-stu-id="46e76-164">Allow storage of user passwords</span></span><br />
<span data-ttu-id="46e76-165">SavePassword</span><span class="sxs-lookup"><span data-stu-id="46e76-165">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="46e76-166">Permite que Lync almacene contraseñas.</span><span class="sxs-lookup"><span data-stu-id="46e76-166">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e76-167">Configurar el modo de compresión SIP</span><span class="sxs-lookup"><span data-stu-id="46e76-167">Configure SIP compression mode</span></span><br />
<span data-ttu-id="46e76-168">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="46e76-168">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="46e76-169">Especifica cuándo se debe activar la compresión SIP.</span><span class="sxs-lookup"><span data-stu-id="46e76-169">Specifies when to turn on SIP compression.</span></span> <span data-ttu-id="46e76-170">De forma predeterminada, la compresión SIP está habilitada en función de la velocidad del adaptador.</span><span class="sxs-lookup"><span data-stu-id="46e76-170">By default, SIP compression is enabled based on the adapter speed.</span></span> <span data-ttu-id="46e76-171">Tenga en cuenta que al configurar esta directiva podría aumentar el tiempo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="46e76-171">Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e76-172">Lista de dominios de confianza</span><span class="sxs-lookup"><span data-stu-id="46e76-172">Trusted Domain List</span></span><br />
<span data-ttu-id="46e76-173">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="46e76-173">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="46e76-174">Enumera los dominios de confianza que no coinciden con el prefijo del dominio SIP del cliente.</span><span class="sxs-lookup"><span data-stu-id="46e76-174">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46e76-p113">Las directivas configuradas en el servidor tienen prioridad frente a la configuración de las directivas de grupo y las opciones de cliente que configure el usuario. En la tabla siguiente se indica el orden de prioridad de la configuración cuando se produce un conflicto.</span><span class="sxs-lookup"><span data-stu-id="46e76-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="46e76-177">Prioridad de las directivas de grupo</span><span class="sxs-lookup"><span data-stu-id="46e76-177">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46e76-178">Precedence</span><span class="sxs-lookup"><span data-stu-id="46e76-178">Precedence</span></span></th>
<th><span data-ttu-id="46e76-179">Ubicación o método de configuración</span><span class="sxs-lookup"><span data-stu-id="46e76-179">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46e76-180">1</span><span class="sxs-lookup"><span data-stu-id="46e76-180">1</span></span></p></td>
<td><p><span data-ttu-id="46e76-181">Aprovisionamiento en banda de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46e76-181">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e76-182">segundo</span><span class="sxs-lookup"><span data-stu-id="46e76-182">2</span></span></p></td>
<td><p><span data-ttu-id="46e76-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="46e76-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e76-184">3</span><span class="sxs-lookup"><span data-stu-id="46e76-184">3</span></span></p></td>
<td><p><span data-ttu-id="46e76-185">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="46e76-185">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e76-186">4 </span><span class="sxs-lookup"><span data-stu-id="46e76-186">4</span></span></p></td>
<td><p><span data-ttu-id="46e76-187">El cuadro de diálogo Lync-opciones en Lync 2013</span><span class="sxs-lookup"><span data-stu-id="46e76-187">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="46e76-188">Para definir la configuración de la Directiva de grupo con los archivos de plantilla administrativa de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="46e76-188">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="46e76-189">Cree una carpeta de nivel raíz que contenga todos los archivos ADMX independientes del idioma.</span><span class="sxs-lookup"><span data-stu-id="46e76-189">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="46e76-190">Por ejemplo, cree una carpeta de nivel raíz del almacén central en su controlador de dominio en esta ubicación:</span><span class="sxs-lookup"><span data-stu-id="46e76-190">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46e76-191">En este procedimiento se presupone que desea administrar varios equipos en su dominio.</span><span class="sxs-lookup"><span data-stu-id="46e76-191">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="46e76-192">En este caso, se almacenan las plantillas en un almacén central en la carpeta Sysvol del controlador de dominio principal.</span><span class="sxs-lookup"><span data-stu-id="46e76-192">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="46e76-193">Esto proporciona una ubicación del almacén central replicada para las plantillas administrativas del dominio.</span><span class="sxs-lookup"><span data-stu-id="46e76-193">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="46e76-194">Cree una subcarpeta para cada idioma que vaya a usar.</span><span class="sxs-lookup"><span data-stu-id="46e76-194">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="46e76-195">Estas subcarpetas contendrán los archivos de recursos ADML específicos del idioma.</span><span class="sxs-lookup"><span data-stu-id="46e76-195">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="46e76-196">Por ejemplo, cree una subcarpeta para Inglés de Estados Unidos (EN-US) en esta ubicación:</span><span class="sxs-lookup"><span data-stu-id="46e76-196">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

