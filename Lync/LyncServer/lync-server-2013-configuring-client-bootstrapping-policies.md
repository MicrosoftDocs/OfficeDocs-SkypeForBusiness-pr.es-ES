---
title: 'Lync Server 2013: configuración de directivas de arranque de cliente'
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
ms.openlocfilehash: 826f732f25996a9f8fcbd708f7e76157a5753a01
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512777"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="03bdf-102">Configuración de directivas de arranque de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03bdf-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03bdf-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="03bdf-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="03bdf-104">La consola de administración de directivas de grupo (GPMC) y el editor de objetos de directiva de grupo son herramientas que se usan para administrar la Directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="03bdf-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="03bdf-105">En la plantilla administrativa de la Directiva de grupo de Office se incluyen plantillas administrativas de Lync 2013. ADMX (ADMX) y. ADML (ADML), que contienen las opciones de directiva basadas en el registro que se configuran para los objetos de directiva de grupo en el dominio.</span><span class="sxs-lookup"><span data-stu-id="03bdf-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="03bdf-106">Los archivos ADML son complementos específicos de idioma para archivos ADMX.</span><span class="sxs-lookup"><span data-stu-id="03bdf-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="03bdf-107">Cada archivo ADMX y ADML contiene la configuración de directiva para una sola aplicación de Office.</span><span class="sxs-lookup"><span data-stu-id="03bdf-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="03bdf-108">Para obtener más información, consulte "Office 2013 Administrative template files (ADMX, ADML)" en la documentación de Office 2013 en <https://go.microsoft.com/fwlink/p/?linkid=267516> .</span><span class="sxs-lookup"><span data-stu-id="03bdf-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="03bdf-109">Para Lync 2013, hay varias directivas de arranque de cliente que debe considerar configurar antes de que los usuarios inicien sesión en el servidor por primera vez.</span><span class="sxs-lookup"><span data-stu-id="03bdf-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="03bdf-110">Por ejemplo, el modo de seguridad y los servidores predeterminados que el cliente debe usar hasta que se complete el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="03bdf-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="03bdf-111">Puede usar la Directiva de grupo para establecer estas opciones en los registros del equipo de los usuarios antes de iniciar sesión y comenzar a recibir la configuración de aprovisionamiento en banda del servidor.</span><span class="sxs-lookup"><span data-stu-id="03bdf-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="03bdf-112">En la siguiente tabla se enumeran las opciones de configuración de directiva de grupo que están disponibles para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="03bdf-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="03bdf-113">Configuración de directiva de grupo para Lync 2013</span><span class="sxs-lookup"><span data-stu-id="03bdf-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03bdf-114">Configuración de directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="03bdf-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="03bdf-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="03bdf-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03bdf-116">Especificar servidor</span><span class="sxs-lookup"><span data-stu-id="03bdf-116">Specify Server</span></span><br />
<span data-ttu-id="03bdf-117">ConfigurationMode</span><span class="sxs-lookup"><span data-stu-id="03bdf-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-118">Especifica cómo Lync 2013 identifica el transporte y el servidor que se deben usar durante el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="03bdf-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="03bdf-119">En esta configuración, debe especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="03bdf-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="03bdf-120">ServerAddressExternal: especifica el nombre del servidor o la dirección IP que usan los clientes y los contactos federados cuando se conectan desde fuera del firewall externo.</span><span class="sxs-lookup"><span data-stu-id="03bdf-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="03bdf-121">ServerAddressInternal: especifica el nombre del servidor o la dirección IP que se usa cuando los clientes se conectan desde dentro del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="03bdf-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="03bdf-122">Transport: especifica el protocolo de control de transmisión (TCP) o la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="03bdf-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03bdf-123">Versiones de servidor adicionales admitidas</span><span class="sxs-lookup"><span data-stu-id="03bdf-123">Additional server versions supported</span></span><br />
<span data-ttu-id="03bdf-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="03bdf-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-125">Especifica una lista de nombres de versiones de servidor separados por punto y coma en los que Lync Server 2013 iniciará sesión, además de las versiones de servidor admitidas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="03bdf-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03bdf-126">Deshabilitar la carga automática de registros de error de inicio de sesión (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="03bdf-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-127">Carga automáticamente los registros de error de inicio de sesión en Lync Server para su análisis.</span><span class="sxs-lookup"><span data-stu-id="03bdf-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="03bdf-128">Si el inicio de sesión se realiza correctamente, no se cargará automáticamente ningún registro.</span><span class="sxs-lookup"><span data-stu-id="03bdf-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="03bdf-129">Si esta Directiva no está configurada, ocurrirá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="03bdf-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="03bdf-130">Para los usuarios de Lync Online: los registros de error de inicio de sesión se cargan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="03bdf-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="03bdf-131">Para los usuarios de Lync local: se muestra un cuadro de diálogo de confirmación al usuario antes de cargarlo.</span><span class="sxs-lookup"><span data-stu-id="03bdf-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="03bdf-132">Cuando esta configuración está deshabilitada, los registros de inicio de sesión se cargan automáticamente en el servidor Lync para los usuarios de Lync local y Lync Online.</span><span class="sxs-lookup"><span data-stu-id="03bdf-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="03bdf-133">Cuando esta configuración está habilitada, los registros de inicio de sesión nunca se cargan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="03bdf-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03bdf-134">Deshabilitar la reserva HTTP para la conexión SIP</span><span class="sxs-lookup"><span data-stu-id="03bdf-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="03bdf-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="03bdf-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-136">Impide que Lync Server intente conectarse al servidor mediante HTTP, si TLS o TCP no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="03bdf-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="03bdf-137">De forma predeterminada, Lync intenta primero conectar con el servidor mediante TLS o TCP y, si ninguno de estos métodos de transporte funciona correctamente, Lync intenta conectarse mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="03bdf-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="03bdf-138">Use esta directiva para deshabilitar el intento de conexión HTTP de reserva.</span><span class="sxs-lookup"><span data-stu-id="03bdf-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03bdf-139">Requerir credenciales de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="03bdf-139">Require logon credentials</span></span><br />
<span data-ttu-id="03bdf-140">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="03bdf-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-141">Requiere que el usuario proporcione credenciales de inicio de sesión para Lync en lugar de usar automáticamente las credenciales de Windows durante el inicio de sesión en un servidor SIP.</span><span class="sxs-lookup"><span data-stu-id="03bdf-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03bdf-142">Deshabilitar la comprobación de la versión del servidor</span><span class="sxs-lookup"><span data-stu-id="03bdf-142">Disable server version check</span></span><br />
<span data-ttu-id="03bdf-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="03bdf-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-144">Si establece esta directiva en 1, impide que Lync Compruebe el nombre del servidor y la versión antes de iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="03bdf-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="03bdf-145">De forma predeterminada, Lync realiza estas comprobaciones antes de iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="03bdf-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03bdf-146">Habilitar el uso de BITS para descargar archivos del servicio de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="03bdf-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="03bdf-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="03bdf-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-148">Permite que Lync use el servicio de transferencia inteligente en segundo plano (BITS) para descargar los archivos de los servicios de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="03bdf-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03bdf-149">Configurar el modo de seguridad SIP</span><span class="sxs-lookup"><span data-stu-id="03bdf-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="03bdf-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="03bdf-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-151">Permite a Lync enviar y recibir mensajes instantáneos de forma más segura.</span><span class="sxs-lookup"><span data-stu-id="03bdf-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="03bdf-152">Esta directiva no se aplica a los servicios de Windows .NET o Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="03bdf-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="03bdf-153">Si no establece esta configuración de Directiva, Lync puede usar cualquier transporte.</span><span class="sxs-lookup"><span data-stu-id="03bdf-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="03bdf-154">Pero si no usa TLS y el servidor autentica a los usuarios, Lync debe usar la autenticación NTLM o Kerberos.</span><span class="sxs-lookup"><span data-stu-id="03bdf-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03bdf-155">Retraso inicial de descarga de libreta de direcciones global</span><span class="sxs-lookup"><span data-stu-id="03bdf-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="03bdf-156">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="03bdf-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-157">Especifica el período de tiempo que debe transcurrir antes de que se produzca una descarga de la lista global de direcciones (GAL).</span><span class="sxs-lookup"><span data-stu-id="03bdf-157">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="03bdf-158">El valor predeterminado es de 60 minutos, lo que significa que el servidor retrasa la descarga del archivo GAL durante un período aleatorio comprendido entre 0 y 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="03bdf-158">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03bdf-159">Impedir que los usuarios ejecuten Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="03bdf-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="03bdf-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="03bdf-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-161">Impide que los usuarios ejecuten Lync.</span><span class="sxs-lookup"><span data-stu-id="03bdf-161">Prevents users from running Lync.</span></span> <span data-ttu-id="03bdf-162">Puede configurar esta opción de directiva en Configuración del equipo y Configuración de usuario, si bien la configuración de directiva establecida en Configuración del equipo tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="03bdf-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03bdf-163">Permitir el almacenamiento de contraseñas de usuario</span><span class="sxs-lookup"><span data-stu-id="03bdf-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="03bdf-164">SavePassword</span><span class="sxs-lookup"><span data-stu-id="03bdf-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-165">Permite que Lync almacene contraseñas.</span><span class="sxs-lookup"><span data-stu-id="03bdf-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03bdf-166">Configurar el modo de compresión SIP</span><span class="sxs-lookup"><span data-stu-id="03bdf-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="03bdf-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="03bdf-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-168">Especifica cuándo se debe activar la compresión SIP.</span><span class="sxs-lookup"><span data-stu-id="03bdf-168">Specifies when to turn on SIP compression.</span></span> <span data-ttu-id="03bdf-169">De forma predeterminada, la compresión SIP está habilitada en función de la velocidad del adaptador.</span><span class="sxs-lookup"><span data-stu-id="03bdf-169">By default, SIP compression is enabled based on the adapter speed.</span></span> <span data-ttu-id="03bdf-170">Tenga en cuenta que al configurar esta directiva podría aumentar el tiempo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="03bdf-170">Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03bdf-171">Lista de dominios de confianza</span><span class="sxs-lookup"><span data-stu-id="03bdf-171">Trusted Domain List</span></span><br />
<span data-ttu-id="03bdf-172">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="03bdf-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="03bdf-173">Enumera los dominios de confianza que no coinciden con el prefijo del dominio SIP del cliente.</span><span class="sxs-lookup"><span data-stu-id="03bdf-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="03bdf-p113">Las directivas configuradas en el servidor tienen prioridad frente a la configuración de las directivas de grupo y las opciones de cliente que configure el usuario. En la tabla siguiente se indica el orden de prioridad de la configuración cuando se produce un conflicto.</span><span class="sxs-lookup"><span data-stu-id="03bdf-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="03bdf-176">Prioridad de las directivas de grupo</span><span class="sxs-lookup"><span data-stu-id="03bdf-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03bdf-177">Precedence</span><span class="sxs-lookup"><span data-stu-id="03bdf-177">Precedence</span></span></th>
<th><span data-ttu-id="03bdf-178">Ubicación o método de configuración</span><span class="sxs-lookup"><span data-stu-id="03bdf-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03bdf-179">1</span><span class="sxs-lookup"><span data-stu-id="03bdf-179">1</span></span></p></td>
<td><p><span data-ttu-id="03bdf-180">Aprovisionamiento en banda de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03bdf-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03bdf-181">segundo</span><span class="sxs-lookup"><span data-stu-id="03bdf-181">2</span></span></p></td>
<td><p><span data-ttu-id="03bdf-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="03bdf-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03bdf-183">3</span><span class="sxs-lookup"><span data-stu-id="03bdf-183">3</span></span></p></td>
<td><p><span data-ttu-id="03bdf-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="03bdf-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03bdf-185">4 </span><span class="sxs-lookup"><span data-stu-id="03bdf-185">4</span></span></p></td>
<td><p><span data-ttu-id="03bdf-186">El cuadro de diálogo Lync-opciones en Lync 2013</span><span class="sxs-lookup"><span data-stu-id="03bdf-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="03bdf-187">Para definir la configuración de la Directiva de grupo con los archivos de plantilla administrativa de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="03bdf-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="03bdf-188">Cree una carpeta de nivel raíz que contenga todos los archivos ADMX independientes del idioma.</span><span class="sxs-lookup"><span data-stu-id="03bdf-188">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="03bdf-189">Por ejemplo, cree una carpeta de nivel raíz del almacén central en su controlador de dominio en esta ubicación:</span><span class="sxs-lookup"><span data-stu-id="03bdf-189">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="03bdf-190">En este procedimiento se presupone que desea administrar varios equipos en su dominio.</span><span class="sxs-lookup"><span data-stu-id="03bdf-190">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="03bdf-191">En este caso, se almacenan las plantillas en un almacén central en la carpeta Sysvol del controlador de dominio principal.</span><span class="sxs-lookup"><span data-stu-id="03bdf-191">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="03bdf-192">Esto proporciona una ubicación del almacén central replicada para las plantillas administrativas del dominio.</span><span class="sxs-lookup"><span data-stu-id="03bdf-192">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="03bdf-193">Cree una subcarpeta para cada idioma que vaya a usar.</span><span class="sxs-lookup"><span data-stu-id="03bdf-193">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="03bdf-194">Estas subcarpetas contendrán los archivos de recursos ADML específicos del idioma.</span><span class="sxs-lookup"><span data-stu-id="03bdf-194">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="03bdf-195">Por ejemplo, cree una subcarpeta para Inglés de Estados Unidos (EN-US) en esta ubicación:</span><span class="sxs-lookup"><span data-stu-id="03bdf-195">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

