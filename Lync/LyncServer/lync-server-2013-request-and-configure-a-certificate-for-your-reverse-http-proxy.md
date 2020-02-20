---
title: Solicitar y configurar un certificado para el proxy HTTP inverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c380cb67e1e156bef616f81ce0c42f699b472d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="04e7c-102">Solicitar y configurar un certificado para el proxy HTTP inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e7c-102">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04e7c-103">_**Última modificación del tema:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="04e7c-103">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="04e7c-104">Debe instalar el certificado de la entidad de certificación raíz (CA) en el servidor que ejecuta Microsoft Forefront Threat Management Gateway 2010 o IIS ARR para la infraestructura de CA que emitió los certificados de servidor a los servidores internos que ejecutan Microsoft Lync. Servidor 2013.</span><span class="sxs-lookup"><span data-stu-id="04e7c-104">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="04e7c-105">También debe instalar un certificado de servidor web público en el servidor de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="04e7c-105">You also must install a public web server certificate on your reverse proxy server.</span></span> <span data-ttu-id="04e7c-106">Los nombres alternativos del sujeto de este certificado deben contener los nombres de dominio completos (FQDN) externos publicados de cada grupo de servidores que se hospedan en los usuarios habilitados para acceso remoto, y los FQDN externos de todos los directores o grupos de directores que se usarán en esa infraestructura perimetral.</span><span class="sxs-lookup"><span data-stu-id="04e7c-106">This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure.</span></span> <span data-ttu-id="04e7c-107">El nombre de sujeto alternativo también debe contener la dirección URL simple de la reunión, la dirección URL simple de marcación y, si desea implementar aplicaciones móviles y planea usar el servicio de detección automática, la dirección URL del servicio de autodetección externo tal como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="04e7c-107">The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="04e7c-108">Valor</span><span class="sxs-lookup"><span data-stu-id="04e7c-108">Value</span></span></th>
<th><span data-ttu-id="04e7c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04e7c-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04e7c-110">Nombre de sujeto</span><span class="sxs-lookup"><span data-stu-id="04e7c-110">Subject name</span></span></p></td>
<td><p><span data-ttu-id="04e7c-111">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="04e7c-111">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="04e7c-112">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04e7c-112">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04e7c-113">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="04e7c-113">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="04e7c-114">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="04e7c-114">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="04e7c-115">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04e7c-115">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="04e7c-116">El nombre del sujeto también debe estar presente en el nombre alternativo del sujeto.</span><span class="sxs-lookup"><span data-stu-id="04e7c-116">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04e7c-117">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="04e7c-117">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="04e7c-118">Servicios Web de Director opcional (si se implementa el director)</span><span class="sxs-lookup"><span data-stu-id="04e7c-118">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="04e7c-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04e7c-119">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04e7c-120">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="04e7c-120">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="04e7c-121">URL sencilla de reunión</span><span class="sxs-lookup"><span data-stu-id="04e7c-121">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="04e7c-p102">Todas las URL sencillas de reunión deben incluirse en el nombre alternativo de sujeto. Cada dominio SIP debe tener al menos una URL sencilla de reunión activa.</span><span class="sxs-lookup"><span data-stu-id="04e7c-p102">All meeting simple URLs must be in the subject alternative name. Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="04e7c-124">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04e7c-124">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04e7c-125">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="04e7c-125">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="04e7c-126">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="04e7c-126">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="04e7c-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04e7c-127">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04e7c-128">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="04e7c-128">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="04e7c-129">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="04e7c-129">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="04e7c-130">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04e7c-130">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04e7c-131">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="04e7c-131">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="04e7c-132">URL externa del servicio Detección automática</span><span class="sxs-lookup"><span data-stu-id="04e7c-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="04e7c-133">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04e7c-133">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="04e7c-134">Si también usa Microsoft Exchange Server, también tendrá que configurar las reglas de proxy inverso para las direcciones URL de Exchange Autodiscover y servicios Web.</span><span class="sxs-lookup"><span data-stu-id="04e7c-134">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="04e7c-135">Si la implementación interna está formada por más de un servidor Standard Edition o grupo de servidores front-end, deberá configurar reglas de publicación de web para cada FQDN de la granja de servidores web externo y también necesitará un certificado y una escucha de web para cada uno o deberá obtener un certificado cuyo nombre alternativo de sujeto contenga los nombres que usan todos los grupos de servidores, asignarlo a una escucha de web y compartirlo entre las varias reglas de publicación de web.</span><span class="sxs-lookup"><span data-stu-id="04e7c-135">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="04e7c-136">Crear una solicitud de certificado</span><span class="sxs-lookup"><span data-stu-id="04e7c-136">Create a Certificate Request</span></span>

<span data-ttu-id="04e7c-137">Cree una solicitud de certificado en el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="04e7c-137">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="04e7c-138">Crea una solicitud en otro equipo, pero debe exportar el certificado firmado con la clave privada e importarlo en el proxy inverso una vez que lo haya recibido de la entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="04e7c-138">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="04e7c-139">Una solicitud de certificado o una solicitud de firma de certificado (CSR) es una solicitud a una entidad de certificación pública de confianza (CA) para validar y firmar la clave pública del equipo de solicitud.</span><span class="sxs-lookup"><span data-stu-id="04e7c-139">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="04e7c-140">Cuando se genera un certificado, se crea una clave pública y una clave privada.</span><span class="sxs-lookup"><span data-stu-id="04e7c-140">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="04e7c-141">Solo se comparte y firma la clave pública.</span><span class="sxs-lookup"><span data-stu-id="04e7c-141">Only the public key is shared and signed.</span></span> <span data-ttu-id="04e7c-142">Como su nombre implica, la clave pública se pone a disposición de cualquier solicitud pública.</span><span class="sxs-lookup"><span data-stu-id="04e7c-142">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="04e7c-143">La clave pública es para su uso por parte de clientes, servidores y otros solicitantes que necesitan intercambiar información de forma segura y validar la identidad de un equipo.</span><span class="sxs-lookup"><span data-stu-id="04e7c-143">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="04e7c-144">La clave privada se mantiene protegida y solo la usa el equipo que creó el par de claves para descifrar los mensajes cifrados con su clave pública.</span><span class="sxs-lookup"><span data-stu-id="04e7c-144">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="04e7c-145">La clave privada se puede usar para otros fines.</span><span class="sxs-lookup"><span data-stu-id="04e7c-145">The private key can be used for other purposes.</span></span> <span data-ttu-id="04e7c-146">Para fines de proxy inverso, el cifrado de datos es el uso principal.</span><span class="sxs-lookup"><span data-stu-id="04e7c-146">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="04e7c-147">Secondarily, la autenticación del certificado en el nivel de clave del certificado es otro uso y solo está limitada a la validación de que un solicitante tiene la clave pública del equipo, o que el equipo para el que tiene una clave pública es realmente el equipo que dice ser.</span><span class="sxs-lookup"><span data-stu-id="04e7c-147">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="04e7c-148">Si planea los certificados del servidor perimetral y los certificados de proxy inverso al mismo tiempo, debe tener en cuenta que hay un gran grado de similitud entre los dos requisitos de los certificados.</span><span class="sxs-lookup"><span data-stu-id="04e7c-148">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="04e7c-149">Cuando configure y solicite el certificado del servidor perimetral, combine el servidor perimetral y los nombres alternativos del sujeto del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="04e7c-149">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="04e7c-150">Puede usar el mismo certificado para el proxy inverso Si exporta el certificado y la clave privada, y copia el archivo exportado en el proxy inverso y, a continuación, importa el par de certificado/clave y lo asigna según sea necesario en los procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="04e7c-150">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="04e7c-151">Consulte los requisitos de certificado para el plan del&nbsp;servidor perimetral<A href="lync-server-2013-plan-for-edge-server-certificates.md">para los certificados del servidor perimetral en Lync Server 2013</A> y el resumen del certificado de proxy inverso <A href="lync-server-2013-certificate-summary-reverse-proxy.md">-proxy inverso en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="04e7c-151">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="04e7c-152">Asegúrese de crear el certificado con una clave privada exportable.</span><span class="sxs-lookup"><span data-stu-id="04e7c-152">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="04e7c-153">La creación del certificado y la solicitud de certificado con una clave privada exportable es necesaria para los servidores perimetrales agrupados, por lo que se trata de un procedimiento normal y el Asistente para la implementación de Lync Server para el servidor perimetral le permitirá establecer la marca de <STRONG>hacer que la clave privada sea exportable</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="04e7c-153">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="04e7c-154">Una vez que haya recibido la solicitud de certificado de la entidad de certificación pública, deberá exportar el certificado y la clave privada.</span><span class="sxs-lookup"><span data-stu-id="04e7c-154">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="04e7c-155">Consulte la sección "para exportar el certificado con la clave privada para servidores perimetrales en un grupo de servidores" en el tema set up Certificates for <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">The external Edge Interface for Lync Server 2013</A> para obtener más información sobre cómo crear y exportar el certificado con una clave privada.</span><span class="sxs-lookup"><span data-stu-id="04e7c-155">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="04e7c-156">La extensión del certificado debe ser del tipo <STRONG>. pfx</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="04e7c-156">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="04e7c-157">Para generar una solicitud de firma de certificado en el equipo donde se asignará el certificado y la clave privada, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="04e7c-157">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="04e7c-158">**Creación de una solicitud de firma de certificado**</span><span class="sxs-lookup"><span data-stu-id="04e7c-158">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="04e7c-159">Abra Microsoft Management Console (MMC), agregue el complemento certificados y seleccione **equipos**y, a continuación, expanda **personal**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-159">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="04e7c-160">Para obtener más información sobre cómo crear una consola de certificados en Microsoft Management Console (MMC), [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616)consulte.</span><span class="sxs-lookup"><span data-stu-id="04e7c-160">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="04e7c-161">Haga clic con el botón secundario en **certificados**, haga clic en **todas las tareas**y en **operaciones avanzadas**, haga clic en **crear solicitud personalizada**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-161">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="04e7c-162">En la página **inscripción de certificado** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-162">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="04e7c-163">En la página **seleccionar Directiva de inscripción de certificados** , en **solicitud personalizada**, seleccione **continuar sin directiva de inscripción**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-163">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="04e7c-164">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-164">Click **Next**.</span></span>

5.  <span data-ttu-id="04e7c-165">En la página **solicitud personalizada** , para la clave de **plantilla** **(sin plantilla) heredada**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-165">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="04e7c-166">A menos que su proveedor de certificados le indique lo contrario, deje **suprimir las extensiones predeterminadas** desactivadas y la selección de **formato de solicitud** en **PKCS \#10**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-166">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="04e7c-167">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-167">Click **Next**.</span></span>

6.  <span data-ttu-id="04e7c-168">En la página **información del certificado** , haga clic en **detalles**y, a continuación, en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-168">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="04e7c-169">En la página de **propiedades del certificado** , en la ficha **General** , en el campo **nombre descriptivo** , escriba un nombre para este certificado.</span><span class="sxs-lookup"><span data-stu-id="04e7c-169">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="04e7c-170">Si lo desea, puede escribir una descripción en el campo **Descripción** .</span><span class="sxs-lookup"><span data-stu-id="04e7c-170">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="04e7c-171">El administrador suele usar el nombre descriptivo y la descripción para identificar cuál es el propósito del certificado, como la **escucha de proxy inverso para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-171">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="04e7c-172">Seleccione la pestaña **asunto** . En **nombre de sujeto** del **tipo**, seleccione **nombre común** para el tipo de nombre de sujeto.</span><span class="sxs-lookup"><span data-stu-id="04e7c-172">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="04e7c-173">Para el **valor**, escriba el nombre de sujeto que va a usar para el proxy inverso y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-173">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="04e7c-174">En el ejemplo que se proporciona en la tabla de este tema, el nombre del sujeto es webext.contoso.com y se escribiría en el campo valor para el nombre del sujeto.</span><span class="sxs-lookup"><span data-stu-id="04e7c-174">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="04e7c-175">En la ficha **asunto** , en **nombre alternativo**, seleccione **DNS** en el menú desplegable para **tipo**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-175">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="04e7c-176">Para cada nombre alternativo de sujeto definido que necesite en el certificado, escriba el nombre de dominio completo y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-176">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="04e7c-177">Por ejemplo, en la tabla hay tres nombres alternativos de sujeto, meet.contoso.com, dialin.contoso.com y lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="04e7c-177">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="04e7c-178">En el campo **valor** , escriba meet.contoso.com y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-178">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="04e7c-179">Repita el procedimiento para cada uno de los nombres alternativos de sujeto que necesite definir.</span><span class="sxs-lookup"><span data-stu-id="04e7c-179">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="04e7c-180">En la página de **propiedades del certificado** , haga clic en la ficha **extensiones** . En esta página, se definen los objetivos de la clave de cifrado en **uso clave** y el uso de la clave extendida en el **uso mejorado de clave (directivas de aplicación)**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-180">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="04e7c-181">Haga clic en la flecha **uso de clave** para mostrar las **opciones disponibles**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-181">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="04e7c-182">En opciones disponibles, haga clic en **firma digital**y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-182">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="04e7c-183">Haga clic en **cifrado de clave**y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-183">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="04e7c-184">Si la casilla de verificación **hacer que estos usos de clave sean críticos** no está seleccionada, active la casilla.</span><span class="sxs-lookup"><span data-stu-id="04e7c-184">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="04e7c-185">Haga clic en la flecha **uso mejorado de clave (directivas de aplicación)** para mostrar las **opciones disponibles**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-185">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="04e7c-186">En opciones disponibles, haga clic en **autenticación del servidor**y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-186">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="04e7c-187">Haga clic en **autenticación de cliente**y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-187">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="04e7c-188">Si está activada la casilla de verificación **hacer que los usos de la clave extendida sean críticos** , anule la selección de la casilla.</span><span class="sxs-lookup"><span data-stu-id="04e7c-188">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="04e7c-189">Al contrario que la casilla uso de la clave (que debe comprobarse), debe asegurarse de que la casilla uso de clave extendida no está activada.</span><span class="sxs-lookup"><span data-stu-id="04e7c-189">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="04e7c-190">En la página de **propiedades del certificado** , haga clic en la ficha **clave privada** . Haga clic en la flecha **Opciones de clave** .</span><span class="sxs-lookup"><span data-stu-id="04e7c-190">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="04e7c-191">En **tamaño de clave**, seleccione **2048** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="04e7c-191">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="04e7c-192">Si va a generar este par de claves y CSR en un equipo distinto del proxy inverso para el que se ha diseñado este certificado, seleccione hacer que la **clave privada sea exportable**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-192">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" /><span data-ttu-id="04e7c-194">Nota de seguridad:</span><span class="sxs-lookup"><span data-stu-id="04e7c-194">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="04e7c-195">Por lo general, es aconsejable seleccionar <strong>hacer que una clave privada exportable</strong> cuando hay más de un proxy inverso en una granja de servidores, ya que copiará el certificado y la clave privada en cada uno de los equipos de la granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="04e7c-195">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="04e7c-196">Si permite una clave privada exportable, debe tener especial cuidado con el certificado y el equipo en el que se genera.</span><span class="sxs-lookup"><span data-stu-id="04e7c-196">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="04e7c-197">La clave privada, si se encuentra en peligro, representará el certificado inútil, así como la posibilidad de exponer el equipo o los equipos a acceso externo y otras vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04e7c-197">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="04e7c-198">En la ficha **clave privada** , haga clic en la flecha **tipo de clave** .</span><span class="sxs-lookup"><span data-stu-id="04e7c-198">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="04e7c-199">Seleccione la opción **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="04e7c-199">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="04e7c-200">Haga clic en **Aceptar** para guardar las **propiedades del certificado** que ha establecido.</span><span class="sxs-lookup"><span data-stu-id="04e7c-200">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="04e7c-201">En la página **inscripción de certificado** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-201">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="04e7c-202">En la página **¿dónde desea guardar la solicitud sin conexión?** , se le pedirá un nombre de **archivo** y un **formato de archivo** para guardar la solicitud de firma de certificado.</span><span class="sxs-lookup"><span data-stu-id="04e7c-202">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="04e7c-203">En el campo entrada de **nombre de archivo** , escriba una ruta de acceso y un nombre de archivo para la solicitud, o haga clic en **examinar** para seleccionar una ubicación para el archivo y escriba el nombre de archivo para la solicitud.</span><span class="sxs-lookup"><span data-stu-id="04e7c-203">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="04e7c-204">En **formato de archivo**, haga clic en **base 64** o **binario**.</span><span class="sxs-lookup"><span data-stu-id="04e7c-204">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="04e7c-205">Seleccione **Base 64** a menos que el proveedor le indique lo contrario para los certificados.</span><span class="sxs-lookup"><span data-stu-id="04e7c-205">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="04e7c-206">Busque el archivo de solicitud que guardó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="04e7c-206">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="04e7c-207">Envíe a su entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="04e7c-207">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="04e7c-208">Microsoft ha identificado entidades de certificación públicas que cumplen con los requisitos de las comunicaciones unificadas.</span><span class="sxs-lookup"><span data-stu-id="04e7c-208">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="04e7c-209">Se mantiene una lista en el siguiente artículo de Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="04e7c-209">A list is maintained in the following knowledge base article.</span></span> <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

