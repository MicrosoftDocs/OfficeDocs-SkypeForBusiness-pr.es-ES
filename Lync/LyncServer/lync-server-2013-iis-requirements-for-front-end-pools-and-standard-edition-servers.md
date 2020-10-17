---
title: Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33c3db01f772f43ea8507cee5c309b6705c8a69d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528147"
---
# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="3e9ee-102">Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e9ee-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e9ee-103">_**Última modificación del tema:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="3e9ee-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="3e9ee-104">Para los servidores Standard Edition y los servidores front-end, y los directores, el instalador de Lync Server 2013 crea directorios virtuales en Internet Information Services (IIS) con los fines siguientes:</span><span class="sxs-lookup"><span data-stu-id="3e9ee-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="3e9ee-105">Habilitar a los usuarios para descargar archivos desde el Servicio de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="3e9ee-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="3e9ee-106">Para permitir que los clientes obtengan actualizaciones</span><span class="sxs-lookup"><span data-stu-id="3e9ee-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="3e9ee-107">Habilitar las conferencias</span><span class="sxs-lookup"><span data-stu-id="3e9ee-107">To enable conferencing</span></span>

  - <span data-ttu-id="3e9ee-108">Permitir que los usuarios descarguen el contenido de las reuniones</span><span class="sxs-lookup"><span data-stu-id="3e9ee-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="3e9ee-109">Habilitar a los usuarios para expandir grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="3e9ee-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="3e9ee-110">Habilitar las conferencias telefónicas</span><span class="sxs-lookup"><span data-stu-id="3e9ee-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="3e9ee-111">Habilitar las características de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="3e9ee-111">To enable response group features</span></span>

<span data-ttu-id="3e9ee-112">Además, la actualización acumulativa de Lync Server 2010: el instalador de noviembre de 2011 crea directorios virtuales en IIS con los siguientes fines:</span><span class="sxs-lookup"><span data-stu-id="3e9ee-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="3e9ee-113">En los servidores front-end o servidores Standard Edition para admitir la funcionalidad de movilidad, como la mensajería instantánea (mi) y la presencia, en dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="3e9ee-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="3e9ee-114">En servidores front-end o servidores Standard Edition y en directores para permitir que los dispositivos móviles detecten automáticamente recursos de movilidad</span><span class="sxs-lookup"><span data-stu-id="3e9ee-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="3e9ee-115">Si va a implementar la movilidad, se recomienda usar IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="3e9ee-116">El instalador del servicio de movilidad de Lync Server establece algunas marcas de ASP.NET para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="3e9ee-117">IIS 7.5 se instala de manera predeterminada en Windows Server 2008 R2, y el instalador del servicio de movilidad cambia automáticamente la configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="3e9ee-118">Si usa IIS 7.0 en Windows Server 2008, debe cambiar manualmente estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="3e9ee-119">Lync Server requiere que se instalen los siguientes módulos de IIS:</span><span class="sxs-lookup"><span data-stu-id="3e9ee-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="3e9ee-120">Si su organización requiere que ubique IIS y todos los servicios web en una unidad distinta de la unidad del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server en el cuadro de diálogo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="3e9ee-121">Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, el resto de los archivos de Lync Server también se implementarán en esta unidad.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="3e9ee-122">Para obtener información sobre cómo reubicar la INETPUB implementada por el administrador de servidores de Windows al instalar IIS, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="3e9ee-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="3e9ee-123">Contenido estático</span><span class="sxs-lookup"><span data-stu-id="3e9ee-123">Static Content</span></span>

  - <span data-ttu-id="3e9ee-124">Documento predeterminado</span><span class="sxs-lookup"><span data-stu-id="3e9ee-124">Default Document</span></span>

  - <span data-ttu-id="3e9ee-125">Errores HTTP</span><span class="sxs-lookup"><span data-stu-id="3e9ee-125">HTTP Errors</span></span>

  - <span data-ttu-id="3e9ee-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3e9ee-126">ASP.NET</span></span>

  - <span data-ttu-id="3e9ee-127">Extensibilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="3e9ee-127">.NET Extensibility</span></span>

  - <span data-ttu-id="3e9ee-128">Extensiones de Internet Server API (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="3e9ee-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="3e9ee-129">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="3e9ee-129">ISAPI Filters</span></span>

  - <span data-ttu-id="3e9ee-130">Registro HTTP</span><span class="sxs-lookup"><span data-stu-id="3e9ee-130">HTTP Logging</span></span>

  - <span data-ttu-id="3e9ee-131">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="3e9ee-131">Logging Tools</span></span>

  - <span data-ttu-id="3e9ee-132">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="3e9ee-132">Tracing</span></span>

  - <span data-ttu-id="3e9ee-133">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="3e9ee-133">Windows Authentication</span></span>

  - <span data-ttu-id="3e9ee-134">Filtro de solicitudes</span><span class="sxs-lookup"><span data-stu-id="3e9ee-134">Request Filtering</span></span>

  - <span data-ttu-id="3e9ee-135">Compresión de contenido estático</span><span class="sxs-lookup"><span data-stu-id="3e9ee-135">Static Content Compression</span></span>

  - <span data-ttu-id="3e9ee-136">Compresión de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="3e9ee-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="3e9ee-137">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="3e9ee-137">IIS Management Console</span></span>

  - <span data-ttu-id="3e9ee-138">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="3e9ee-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="3e9ee-139">Autenticación anónima (se instala de forma predeterminada al instalar IIS)</span><span class="sxs-lookup"><span data-stu-id="3e9ee-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="3e9ee-140">Autenticación por asignación de certificados de clientes</span><span class="sxs-lookup"><span data-stu-id="3e9ee-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="3e9ee-141">En la siguiente tabla se recogen los identificadores URI de los directorios virtuales para el acceso interno y los recursos del sistema de archivos a los que hacen referencia.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="3e9ee-142">Directorios virtuales para el acceso interno</span><span class="sxs-lookup"><span data-stu-id="3e9ee-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e9ee-143">Característica</span><span class="sxs-lookup"><span data-stu-id="3e9ee-143">Feature</span></span></th>
<th><span data-ttu-id="3e9ee-144">URI de directorio virtual</span><span class="sxs-lookup"><span data-stu-id="3e9ee-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="3e9ee-145">Hace referencia a</span><span class="sxs-lookup"><span data-stu-id="3e9ee-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e9ee-146">Servidor de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="3e9ee-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-147">https:// &lt; FQDN interno &gt; /ABS/int/handler</span><span class="sxs-lookup"><span data-stu-id="3e9ee-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-148">Ubicación de los archivos de descarga del servidor de libreta de direcciones para los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9ee-149">Servicio Detección automática</span><span class="sxs-lookup"><span data-stu-id="3e9ee-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-150">https:// &lt; FQDN interno &gt; /Autodiscover</span><span class="sxs-lookup"><span data-stu-id="3e9ee-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-151">Ubicación del servicio Detección automática de Lync Server que localiza recursos de movilidad para usuarios de dispositivos móviles internos.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9ee-152">Actualizaciones del cliente</span><span class="sxs-lookup"><span data-stu-id="3e9ee-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-153">http:// &lt; FQDN interno &gt; /AutoUpdate/int</span><span class="sxs-lookup"><span data-stu-id="3e9ee-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-154">Ubicación de los archivos de actualización para los clientes basados en equipo internos.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9ee-155">Multipunto</span><span class="sxs-lookup"><span data-stu-id="3e9ee-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-156">http:// &lt; FQDN interno &gt; /conf/int</span><span class="sxs-lookup"><span data-stu-id="3e9ee-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-157">Ubicación de los recursos de conferencia para los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9ee-158">Actualizaciones de dispositivos</span><span class="sxs-lookup"><span data-stu-id="3e9ee-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-159">&lt;FQDN &gt; /DeviceUpdateFiles_Int http://interno</span><span class="sxs-lookup"><span data-stu-id="3e9ee-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-160">Ubicación de los archivos de actualización de dispositivos de comunicaciones unificadas (UC) para los dispositivos UC internos.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9ee-161">Misma</span><span class="sxs-lookup"><span data-stu-id="3e9ee-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-162">http:// &lt; FQDN interno &gt; /etc/Place/null</span><span class="sxs-lookup"><span data-stu-id="3e9ee-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-163">Ubicación del contenido de las reuniones de los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9ee-164">Servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="3e9ee-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-165">https:// &lt; FQDN interno &gt; /MCX</span><span class="sxs-lookup"><span data-stu-id="3e9ee-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-166">Ubicación de los recursos del servicio de movilidad para usuarios de dispositivos móviles internos.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9ee-167">Servicio de consulta web de libreta de direcciones y expansión de grupos</span><span class="sxs-lookup"><span data-stu-id="3e9ee-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-168">http:// &lt; FQDN interno &gt; /GroupExpansion/int/Service.asmx</span><span class="sxs-lookup"><span data-stu-id="3e9ee-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-169">Ubicación del servicio web que habilita la expansión de grupos para los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="3e9ee-170">Además, la ubicación del servicio de consulta Web de la libreta de direcciones que proporciona información de la lista global de direcciones a clientes móviles internos de Lync Mobile Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9ee-171">Conferencias telefónicas</span><span class="sxs-lookup"><span data-stu-id="3e9ee-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-172">http:// &lt; FQDN interno &gt; /PhoneConferencing/int</span><span class="sxs-lookup"><span data-stu-id="3e9ee-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-173">Ubicación de los datos de conferencia telefónica para los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9ee-174">Actualizaciones de dispositivos</span><span class="sxs-lookup"><span data-stu-id="3e9ee-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-175">http:// &lt; FQDN interno &gt; /RequestHandler</span><span class="sxs-lookup"><span data-stu-id="3e9ee-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-176">Ubicación del controlador de solicitudes del Servicio web de actualización de dispositivos que habilita los dispositivos UC internos para cargar los registros y comprobar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9ee-177">Aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="3e9ee-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-178">http:// &lt; FQDN interno &gt; /RgsConfig</span><span class="sxs-lookup"><span data-stu-id="3e9ee-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="3e9ee-179">http:// &lt; FQDN interno &gt; /RgsClients</span><span class="sxs-lookup"><span data-stu-id="3e9ee-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="3e9ee-180">Ubicación de la herramienta de configuración de grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="3e9ee-181">Para los grupos de servidores front-end en una configuración consolidada, debe implementar IIS para poder agregar servidores al grupo.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" /><span data-ttu-id="3e9ee-183">Nota de seguridad:</span><span class="sxs-lookup"><span data-stu-id="3e9ee-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3e9ee-184">Se debe usar el complemento administrativo de IIS para asignar el certificado usado por el servidor de componentes web de IIS.</span><span class="sxs-lookup"><span data-stu-id="3e9ee-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

