---
title: Solicitar y configurar un certificado para el proxy HTTP inverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffe1ce6a4b206b927b2fcdec4c02b905e01d5bd1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="f9175-102">Solicitar y configurar un certificado para el proxy HTTP inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9175-102">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9175-103">_**Última modificación del tema:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="f9175-103">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="f9175-104">Debe instalar el certificado de la entidad emisora de certificados raíz (CA) en el servidor que ejecuta Microsoft Forefront Threat Management Gateway 2010 o IIS ARR para la infraestructura de CA que emitió los certificados de servidor a los servidores internos que ejecutan Microsoft Lync. Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9175-104">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="f9175-105">También debe instalar un certificado de servidor web público en el servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f9175-105">You also must install a public web server certificate on your reverse proxy server.</span></span> <span data-ttu-id="f9175-106">Los nombres alternativos de los sujetos de este certificado deben contener los nombres de dominio completos (FQDN) externos de cada grupo que está en la parte principal de los usuarios habilitados para acceso remoto, y los FQDN externos de todos los directores o grupos de directores que se usarán en esa infraestructura perimetral.</span><span class="sxs-lookup"><span data-stu-id="f9175-106">This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure.</span></span> <span data-ttu-id="f9175-107">El nombre alternativo del sujeto también debe contener la dirección URL simple de la reunión, la dirección URL simple de acceso telefónico y, si está implementando aplicaciones móviles y va a usar la detección automática, la dirección URL del servicio de detección automática externa tal como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f9175-107">The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f9175-108">Valor</span><span class="sxs-lookup"><span data-stu-id="f9175-108">Value</span></span></th>
<th><span data-ttu-id="f9175-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9175-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9175-110">Nombre del asunto</span><span class="sxs-lookup"><span data-stu-id="f9175-110">Subject name</span></span></p></td>
<td><p><span data-ttu-id="f9175-111">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="f9175-111">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="f9175-112">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9175-112">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9175-113">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="f9175-113">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="f9175-114">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="f9175-114">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="f9175-115">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9175-115">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="f9175-116">El nombre del asunto también debe estar presente en el nombre alternativo del firmante.</span><span class="sxs-lookup"><span data-stu-id="f9175-116">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9175-117">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="f9175-117">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="f9175-118">Servicios Web de directores opcionales (si el director está implementado)</span><span class="sxs-lookup"><span data-stu-id="f9175-118">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="f9175-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9175-119">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9175-120">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="f9175-120">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="f9175-121">Dirección URL simple de la reunión</span><span class="sxs-lookup"><span data-stu-id="f9175-121">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="f9175-122">Todas las direcciones URL simples de la reunión deben encontrarse en el nombre alternativo del firmante.</span><span class="sxs-lookup"><span data-stu-id="f9175-122">All meeting simple URLs must be in the subject alternative name.</span></span> <span data-ttu-id="f9175-123">Cada dominio SIP debe tener al menos una dirección URL simple de la reunión activa.</span><span class="sxs-lookup"><span data-stu-id="f9175-123">Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="f9175-124">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9175-124">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9175-125">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="f9175-125">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="f9175-126">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="f9175-126">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="f9175-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9175-127">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9175-128">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="f9175-128">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="f9175-129">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="f9175-129">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="f9175-130">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9175-130">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9175-131">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="f9175-131">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="f9175-132">Dirección URL del servicio de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="f9175-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="f9175-133">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9175-133">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="f9175-134">Si también usa Microsoft Exchange Server, también tendrá que configurar las reglas de proxy inverso para las direcciones URL de Autodiscover y servicios Web de Exchange.</span><span class="sxs-lookup"><span data-stu-id="f9175-134">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="f9175-135">Si su implementación interna consta de más de un servidor Standard Edition o un grupo de servidores front-end, debe configurar reglas de publicación web para cada FQDN de granja de servidores Web externo y necesitará un certificado y una escucha de web para cada uno, o debe obtener un certificado. el nombre de sujeto alternativo contiene los nombres que se usan en todas las agrupaciones, la asigna a una escucha de web y la comparte entre varias reglas de publicación Web.</span><span class="sxs-lookup"><span data-stu-id="f9175-135">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="f9175-136">Crear una solicitud de certificado</span><span class="sxs-lookup"><span data-stu-id="f9175-136">Create a Certificate Request</span></span>

<span data-ttu-id="f9175-137">Crear una solicitud de certificado en el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f9175-137">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="f9175-138">Usted crea una solicitud en otro equipo, pero debe exportar el certificado firmado con la clave privada e importarlo en el proxy inverso una vez que lo haya recibido de la entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="f9175-138">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f9175-139">Una solicitud de certificado o una solicitud de firma de certificado (CSR) es una solicitud a una entidad de certificación (CA) pública de confianza para validar y firmar la clave pública del equipo de solicitud.</span><span class="sxs-lookup"><span data-stu-id="f9175-139">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="f9175-140">Cuando se genera un certificado, se crea una clave pública y una clave privada.</span><span class="sxs-lookup"><span data-stu-id="f9175-140">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="f9175-141">Solo la clave pública está compartida y firmada.</span><span class="sxs-lookup"><span data-stu-id="f9175-141">Only the public key is shared and signed.</span></span> <span data-ttu-id="f9175-142">Como su nombre indica, la clave pública está disponible para cualquier solicitud pública.</span><span class="sxs-lookup"><span data-stu-id="f9175-142">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="f9175-143">La clave pública es para que la usen los clientes, los servidores y otros solicitantes que necesiten intercambiar información de forma segura y validar la identidad de un equipo.</span><span class="sxs-lookup"><span data-stu-id="f9175-143">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="f9175-144">La clave privada se mantiene protegida y solo la usa el equipo que creó el par de claves para descifrar mensajes cifrados con su clave pública.</span><span class="sxs-lookup"><span data-stu-id="f9175-144">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="f9175-145">La clave privada se puede usar para otros fines.</span><span class="sxs-lookup"><span data-stu-id="f9175-145">The private key can be used for other purposes.</span></span> <span data-ttu-id="f9175-146">Para fines de proxy inverso, el cifrado de datos es el uso principal.</span><span class="sxs-lookup"><span data-stu-id="f9175-146">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="f9175-147">Secondarily, la autenticación de certificados en el nivel de clave de certificado es otro uso, y solo se limita a la validación de que un solicitante tiene la clave pública del equipo o que el equipo al que tiene una clave pública es realmente el equipo que dice ser.</span><span class="sxs-lookup"><span data-stu-id="f9175-147">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="f9175-148">Si planea los certificados de su servidor perimetral y los certificados de proxy inverso al mismo tiempo, debe tener en cuenta que hay una gran similitud entre los dos requisitos de los certificados.</span><span class="sxs-lookup"><span data-stu-id="f9175-148">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="f9175-149">Cuando configure y solicite el certificado del servidor perimetral, combine los nombres alternativos con el servidor perimetral y el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f9175-149">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="f9175-150">Puede usar el mismo certificado para el proxy inverso si exporte el certificado y la clave privada, y copie el archivo exportado en el proxy inverso y, a continuación, importe el par de certificado o clave y asígnelo según sea necesario en los procedimientos que se describen a continuación.</span><span class="sxs-lookup"><span data-stu-id="f9175-150">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="f9175-151">Consulte los requisitos de certificado para el plan de&nbsp;servidores perimetrales<A href="lync-server-2013-plan-for-edge-server-certificates.md">para los certificados de servidor perimetral en Lync Server 2013</A> y el resumen del certificado de proxy inverso <A href="lync-server-2013-certificate-summary-reverse-proxy.md">: proxy inverso en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f9175-151">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="f9175-152">Asegúrese de crear el certificado con una clave privada exportable.</span><span class="sxs-lookup"><span data-stu-id="f9175-152">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="f9175-153">La creación del certificado y de la solicitud de certificados con una clave privada exportable es necesaria para los servidores perimetrales agrupados, por lo que esto es una práctica normal, y el Asistente de certificados del asistente de implementación de Lync Server para el servidor perimetral le permitirá establecer la <STRONG>marca marca de exportación de clave privada</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f9175-153">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="f9175-154">Una vez que reciba de nuevo la solicitud de certificado de la entidad emisora de certificados pública, exportará el certificado y la clave privada.</span><span class="sxs-lookup"><span data-stu-id="f9175-154">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="f9175-155">Consulte la sección "para exportar el certificado con la clave privada para servidores perimetrales en un grupo" en el tema <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">configurar certificados para la interfaz de borde externo para Lync Server 2013</A> para obtener más información sobre cómo crear y exportar el certificado con una clave privada.</span><span class="sxs-lookup"><span data-stu-id="f9175-155">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="f9175-156">La extensión del certificado debe ser de tipo <STRONG>. pfx</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f9175-156">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="f9175-157">Para generar una solicitud de firma de certificado en el equipo en el que se asignará el certificado y la clave privada, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9175-157">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="f9175-158">**Crear una solicitud de firma de certificado**</span><span class="sxs-lookup"><span data-stu-id="f9175-158">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="f9175-159">Abra Microsoft Management Console (MMC), agregue el complemento certificados, seleccione **equipos**y, a continuación, expanda **personal**.</span><span class="sxs-lookup"><span data-stu-id="f9175-159">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="f9175-160">Para obtener más información sobre cómo crear una consola de certificados en la consola de administración de Microsoft ( [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)MMC), consulte.</span><span class="sxs-lookup"><span data-stu-id="f9175-160">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="f9175-161">Haga clic con el botón derecho en **certificados**, haga clic en **todas las tareas**, en **operaciones avanzadas**y en **crear solicitud personalizada**.</span><span class="sxs-lookup"><span data-stu-id="f9175-161">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="f9175-162">En la página **inscripción de certificados** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9175-162">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="f9175-163">En la página **seleccionar Directiva de inscripción de certificados** , en **solicitud personalizada**, seleccione **continuar sin directiva de inscripción**.</span><span class="sxs-lookup"><span data-stu-id="f9175-163">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="f9175-164">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9175-164">Click **Next**.</span></span>

5.  <span data-ttu-id="f9175-165">En la página de **solicitud personalizada** , para la clave de selección de **plantilla** **(sin plantilla) heredada**.</span><span class="sxs-lookup"><span data-stu-id="f9175-165">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="f9175-166">A menos que su proveedor de certificados le indique lo contrario, deje **suprimir las extensiones** predeterminadas desactivadas y la **solicitud de formato** seleccionado en **PKCS \#10**.</span><span class="sxs-lookup"><span data-stu-id="f9175-166">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="f9175-167">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9175-167">Click **Next**.</span></span>

6.  <span data-ttu-id="f9175-168">En la página **información del certificado** , haga clic en **detalles**y, a continuación, en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f9175-168">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="f9175-169">En la página de **propiedades del certificado** , en la pestaña **General** , en el campo **nombre descriptivo** , escriba un nombre para este certificado.</span><span class="sxs-lookup"><span data-stu-id="f9175-169">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="f9175-170">De manera opcional, escriba una descripción en el campo **Descripción** .</span><span class="sxs-lookup"><span data-stu-id="f9175-170">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="f9175-171">El administrador suele usar el nombre descriptivo y la descripción para identificar cuál es el propósito del certificado, como la **escucha de proxy invertida para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f9175-171">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="f9175-172">Seleccione la pestaña **asunto** . En **nombre del sujeto** del **tipo**, seleccione **nombre común** para el tipo de nombre de sujeto.</span><span class="sxs-lookup"><span data-stu-id="f9175-172">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="f9175-173">Para el **valor**, escriba el nombre del asunto que usará para el proxy inverso y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9175-173">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="f9175-174">En el ejemplo que se proporciona en la tabla de este tema, el nombre del asunto es webext.contoso.com y se escribiría en el campo de valor del nombre del asunto.</span><span class="sxs-lookup"><span data-stu-id="f9175-174">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="f9175-175">En la pestaña **asunto** , en **nombre alternativo**, seleccione **DNS** de la lista desplegable para **tipo**.</span><span class="sxs-lookup"><span data-stu-id="f9175-175">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="f9175-176">Para cada nombre alternativo de asunto definido que necesite en el certificado, escriba el nombre de dominio completo y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9175-176">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="f9175-177">Por ejemplo, en la tabla hay tres nombres alternativos de asunto, meet.contoso.com, dialin.contoso.com y lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f9175-177">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="f9175-178">En el campo **valor** , escriba meet.contoso.com y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9175-178">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="f9175-179">Repita el procedimiento para cada uno de los nombres alternativos de asunto que necesite definir.</span><span class="sxs-lookup"><span data-stu-id="f9175-179">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="f9175-180">En la página de **propiedades del certificado** , haga clic en la pestaña **extensiones** . En esta página, definirá los objetivos de las claves criptográficas en **uso de claves** y el uso de claves extendidas en el **uso mejorado de claves (directivas de aplicación)**.</span><span class="sxs-lookup"><span data-stu-id="f9175-180">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="f9175-181">Haga clic en la flecha **uso de clave** para mostrar las **opciones disponibles**.</span><span class="sxs-lookup"><span data-stu-id="f9175-181">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="f9175-182">En opciones disponibles, haga clic en **firma digital**y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9175-182">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="f9175-183">Haga clic en cifrado de **clave**y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9175-183">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="f9175-184">Si la casilla para **hacer que estos usos de claves sean críticas** no está marcada, active la casilla.</span><span class="sxs-lookup"><span data-stu-id="f9175-184">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="f9175-185">Haga clic en la flecha **uso de clave extendida (directivas de aplicación)** para mostrar las **opciones disponibles**.</span><span class="sxs-lookup"><span data-stu-id="f9175-185">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="f9175-186">En opciones disponibles, haga clic en **autenticación de servidor**y luego en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9175-186">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="f9175-187">Haga clic en **autenticación de cliente**y luego en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9175-187">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="f9175-188">Si la casilla para **hacer que los usos extendidos de claves** estén marcadas, anule la selección de la casilla.</span><span class="sxs-lookup"><span data-stu-id="f9175-188">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="f9175-189">Al contrario que la casilla de uso de claves (que debe estar activada), debe asegurarse de que la casilla uso de clave extendida no esté activada.</span><span class="sxs-lookup"><span data-stu-id="f9175-189">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="f9175-190">En la página de **propiedades del certificado** , haga clic en la pestaña **clave privada** . Haga clic en la flecha **Opciones de clave** .</span><span class="sxs-lookup"><span data-stu-id="f9175-190">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="f9175-191">En **tamaño de clave**, seleccione **2048** de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f9175-191">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="f9175-192">Si está generando este par de claves y CSR en un equipo distinto del proxy inverso para el que se ha diseñado este certificado, seleccione hacer que la **clave privada**sea exportable.</span><span class="sxs-lookup"><span data-stu-id="f9175-192">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" /><span data-ttu-id="f9175-194">Nota de seguridad:</span><span class="sxs-lookup"><span data-stu-id="f9175-194">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="f9175-195">La selección de <strong>hacer que una clave privada</strong> sea exportable se suele aconsejar cuando tiene más de un proxy inverso en una granja de servidores porque copiará el certificado y la clave privada en cada uno de los equipos de la granja.</span><span class="sxs-lookup"><span data-stu-id="f9175-195">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="f9175-196">Si permite una clave privada exportable, debe tener especial cuidado con el certificado y el equipo en el que está generada.</span><span class="sxs-lookup"><span data-stu-id="f9175-196">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="f9175-197">La clave privada, si se pone en peligro, representará el certificado sin utilidad, y también expondrá el equipo o equipos a acceso externo y otras vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f9175-197">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="f9175-198">En la pestaña **clave privada** , haga clic en la flecha **tipo de clave** .</span><span class="sxs-lookup"><span data-stu-id="f9175-198">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="f9175-199">Seleccione la opción **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="f9175-199">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="f9175-200">Haga clic en **Aceptar** para guardar las **propiedades del certificado** que ha establecido.</span><span class="sxs-lookup"><span data-stu-id="f9175-200">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="f9175-201">En la página **inscripción de certificados** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9175-201">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="f9175-202">En la página **¿dónde desea guardar la solicitud sin conexión?** , se le pedirá un nombre de **archivo** y un **formato de archivo** para guardar la solicitud de firma de certificado.</span><span class="sxs-lookup"><span data-stu-id="f9175-202">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="f9175-203">En el campo de entrada **nombre de archivo** , escriba una ruta y un nombre de archivo para la solicitud, o haga clic en **examinar** para seleccionar una ubicación para el archivo y escriba el nombre de archivo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f9175-203">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="f9175-204">En **formato de archivo**, haga clic en **base 64** o en **binario**.</span><span class="sxs-lookup"><span data-stu-id="f9175-204">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="f9175-205">Seleccione **64 base** a menos que el proveedor le indique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="f9175-205">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="f9175-206">Busque el archivo de solicitud que guardó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="f9175-206">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="f9175-207">Envía a tu entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="f9175-207">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="f9175-208">Microsoft ha identificado entidades emisoras públicas que cumplen con los requisitos de las comunicaciones unificadas.</span><span class="sxs-lookup"><span data-stu-id="f9175-208">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="f9175-209">Una lista se mantiene en el siguiente artículo de Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="f9175-209">A list is maintained in the following knowledge base article.</span></span> <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

