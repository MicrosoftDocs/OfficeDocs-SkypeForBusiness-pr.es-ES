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
ms.openlocfilehash: 8efd91c3222e5918640c4a8b078d9fdd5ebcdaae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="6cd26-102">Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cd26-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cd26-103">_**Última modificación del tema:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="6cd26-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="6cd26-104">Para los servidores Standard Edition y los servidores front-end, y los directores, el instalador de Lync Server 2013 crea directorios virtuales en Internet Information Services (IIS) con los fines siguientes:</span><span class="sxs-lookup"><span data-stu-id="6cd26-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="6cd26-105">Habilitar a los usuarios para descargar archivos desde el Servicio de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="6cd26-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="6cd26-106">Para permitir que los clientes obtengan actualizaciones</span><span class="sxs-lookup"><span data-stu-id="6cd26-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="6cd26-107">Habilitar las conferencias</span><span class="sxs-lookup"><span data-stu-id="6cd26-107">To enable conferencing</span></span>

  - <span data-ttu-id="6cd26-108">Permitir que los usuarios descarguen el contenido de las reuniones</span><span class="sxs-lookup"><span data-stu-id="6cd26-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="6cd26-109">Habilitar a los usuarios para expandir grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="6cd26-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="6cd26-110">Habilitar las conferencias telefónicas</span><span class="sxs-lookup"><span data-stu-id="6cd26-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="6cd26-111">Habilitar las características de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6cd26-111">To enable response group features</span></span>

<span data-ttu-id="6cd26-112">Además, la actualización acumulativa de Lync Server 2010: el instalador de noviembre de 2011 crea directorios virtuales en IIS con los siguientes fines:</span><span class="sxs-lookup"><span data-stu-id="6cd26-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="6cd26-113">En los servidores front-end o servidores Standard Edition para admitir la funcionalidad de movilidad, como la mensajería instantánea (mi) y la presencia, en dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="6cd26-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="6cd26-114">En servidores front-end o servidores Standard Edition y en directores para permitir que los dispositivos móviles detecten automáticamente recursos de movilidad</span><span class="sxs-lookup"><span data-stu-id="6cd26-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="6cd26-115">Si va a implementar la movilidad, se recomienda usar IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="6cd26-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="6cd26-116">El instalador del servicio de movilidad de Lync Server establece algunas marcas de ASP.NET para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6cd26-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="6cd26-117">IIS 7.5 se instala de manera predeterminada en Windows Server 2008 R2, y el instalador del servicio de movilidad cambia automáticamente la configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6cd26-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="6cd26-118">Si usa IIS 7.0 en Windows Server 2008, debe cambiar manualmente estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="6cd26-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="6cd26-119">Lync Server requiere que se instalen los siguientes módulos de IIS:</span><span class="sxs-lookup"><span data-stu-id="6cd26-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="6cd26-120">Si su organización requiere que ubique IIS y todos los servicios web en una unidad distinta de la unidad del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server en el cuadro de diálogo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6cd26-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="6cd26-121">Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server también se implementarán en esta unidad.</span><span class="sxs-lookup"><span data-stu-id="6cd26-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="6cd26-122">Para obtener información sobre cómo reubicar la INETPUB implementada por el administrador de servidores de Windows <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>al instalar IIS, consulte.</span><span class="sxs-lookup"><span data-stu-id="6cd26-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="6cd26-123">Contenido estático</span><span class="sxs-lookup"><span data-stu-id="6cd26-123">Static Content</span></span>

  - <span data-ttu-id="6cd26-124">Documento predeterminado</span><span class="sxs-lookup"><span data-stu-id="6cd26-124">Default Document</span></span>

  - <span data-ttu-id="6cd26-125">Errores HTTP</span><span class="sxs-lookup"><span data-stu-id="6cd26-125">HTTP Errors</span></span>

  - <span data-ttu-id="6cd26-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6cd26-126">ASP.NET</span></span>

  - <span data-ttu-id="6cd26-127">Extensibilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="6cd26-127">.NET Extensibility</span></span>

  - <span data-ttu-id="6cd26-128">Extensiones de Internet Server API (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="6cd26-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="6cd26-129">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="6cd26-129">ISAPI Filters</span></span>

  - <span data-ttu-id="6cd26-130">Registro HTTP</span><span class="sxs-lookup"><span data-stu-id="6cd26-130">HTTP Logging</span></span>

  - <span data-ttu-id="6cd26-131">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="6cd26-131">Logging Tools</span></span>

  - <span data-ttu-id="6cd26-132">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="6cd26-132">Tracing</span></span>

  - <span data-ttu-id="6cd26-133">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="6cd26-133">Windows Authentication</span></span>

  - <span data-ttu-id="6cd26-134">Filtro de solicitudes</span><span class="sxs-lookup"><span data-stu-id="6cd26-134">Request Filtering</span></span>

  - <span data-ttu-id="6cd26-135">Compresión de contenido estático</span><span class="sxs-lookup"><span data-stu-id="6cd26-135">Static Content Compression</span></span>

  - <span data-ttu-id="6cd26-136">Compresión de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="6cd26-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="6cd26-137">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="6cd26-137">IIS Management Console</span></span>

  - <span data-ttu-id="6cd26-138">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="6cd26-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="6cd26-139">Autenticación anónima (se instala de forma predeterminada al instalar IIS)</span><span class="sxs-lookup"><span data-stu-id="6cd26-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="6cd26-140">Autenticación por asignación de certificados de clientes</span><span class="sxs-lookup"><span data-stu-id="6cd26-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="6cd26-141">En la siguiente tabla se recogen los identificadores URI de los directorios virtuales para el acceso interno y los recursos del sistema de archivos a los que hacen referencia.</span><span class="sxs-lookup"><span data-stu-id="6cd26-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="6cd26-142">Directorios virtuales para el acceso interno</span><span class="sxs-lookup"><span data-stu-id="6cd26-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cd26-143">Característica</span><span class="sxs-lookup"><span data-stu-id="6cd26-143">Feature</span></span></th>
<th><span data-ttu-id="6cd26-144">URI de directorio virtual</span><span class="sxs-lookup"><span data-stu-id="6cd26-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="6cd26-145">Hace referencia a</span><span class="sxs-lookup"><span data-stu-id="6cd26-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cd26-146">Servidor de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="6cd26-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="6cd26-147">https://&lt;FQDN&gt;interno/ABS/int/handler</span><span class="sxs-lookup"><span data-stu-id="6cd26-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="6cd26-148">Ubicación de los archivos de descarga del servidor de libreta de direcciones para los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="6cd26-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd26-149">Servicio Detección automática</span><span class="sxs-lookup"><span data-stu-id="6cd26-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="6cd26-150">https://&lt;FQDN&gt;interno/Autodiscover</span><span class="sxs-lookup"><span data-stu-id="6cd26-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="6cd26-151">Ubicación del servicio Detección automática de Lync Server que localiza recursos de movilidad para usuarios de dispositivos móviles internos.</span><span class="sxs-lookup"><span data-stu-id="6cd26-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd26-152">Actualizaciones del cliente</span><span class="sxs-lookup"><span data-stu-id="6cd26-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="6cd26-153">http://&lt;FQDN&gt;interno/AutoUpdate/int</span><span class="sxs-lookup"><span data-stu-id="6cd26-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="6cd26-154">Ubicación de los archivos de actualización para los clientes basados en equipo internos.</span><span class="sxs-lookup"><span data-stu-id="6cd26-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd26-155">Multipunto</span><span class="sxs-lookup"><span data-stu-id="6cd26-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="6cd26-156">http://&lt;FQDN&gt;interno/conf/int</span><span class="sxs-lookup"><span data-stu-id="6cd26-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="6cd26-157">Ubicación de los recursos de conferencia para los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="6cd26-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd26-158">Actualizaciones de dispositivos</span><span class="sxs-lookup"><span data-stu-id="6cd26-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="6cd26-159">FQDN&lt;&gt;/DeviceUpdateFiles_Int http://interno</span><span class="sxs-lookup"><span data-stu-id="6cd26-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="6cd26-160">Ubicación de los archivos de actualización de dispositivos de comunicaciones unificadas (UC) para los dispositivos UC internos.</span><span class="sxs-lookup"><span data-stu-id="6cd26-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd26-161">Misma</span><span class="sxs-lookup"><span data-stu-id="6cd26-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="6cd26-162">http://&lt;FQDN&gt;interno/etc/Place/null</span><span class="sxs-lookup"><span data-stu-id="6cd26-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="6cd26-163">Ubicación del contenido de las reuniones de los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="6cd26-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd26-164">Servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="6cd26-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="6cd26-165">https://&lt;FQDN&gt;interno/MCX</span><span class="sxs-lookup"><span data-stu-id="6cd26-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="6cd26-166">Ubicación de los recursos del servicio de movilidad para usuarios de dispositivos móviles internos.</span><span class="sxs-lookup"><span data-stu-id="6cd26-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd26-167">Servicio de consulta web de libreta de direcciones y expansión de grupos</span><span class="sxs-lookup"><span data-stu-id="6cd26-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="6cd26-168">http://&lt;FQDN&gt;interno/GroupExpansion/int/Service.asmx</span><span class="sxs-lookup"><span data-stu-id="6cd26-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="6cd26-169">Ubicación del servicio web que habilita la expansión de grupos para los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="6cd26-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="6cd26-170">Además, la ubicación del servicio de consulta Web de la libreta de direcciones que proporciona información de la lista global de direcciones a clientes móviles internos de Lync Mobile Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="6cd26-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd26-171">Conferencias telefónicas</span><span class="sxs-lookup"><span data-stu-id="6cd26-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="6cd26-172">http://&lt;FQDN&gt;interno/PhoneConferencing/int</span><span class="sxs-lookup"><span data-stu-id="6cd26-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="6cd26-173">Ubicación de los datos de conferencia telefónica para los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="6cd26-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd26-174">Actualizaciones de dispositivos</span><span class="sxs-lookup"><span data-stu-id="6cd26-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="6cd26-175">http://&lt;FQDN&gt;interno/RequestHandler</span><span class="sxs-lookup"><span data-stu-id="6cd26-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="6cd26-176">Ubicación del controlador de solicitudes del Servicio web de actualización de dispositivos que habilita los dispositivos UC internos para cargar los registros y comprobar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="6cd26-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd26-177">Aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6cd26-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="6cd26-178">http://&lt;FQDN&gt;interno/RgsConfig</span><span class="sxs-lookup"><span data-stu-id="6cd26-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="6cd26-179">http://&lt;FQDN&gt;interno/RgsClients</span><span class="sxs-lookup"><span data-stu-id="6cd26-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="6cd26-180">Ubicación de la herramienta de configuración de grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6cd26-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="6cd26-181">Para los grupos de servidores front-end en una configuración consolidada, debe implementar IIS para poder agregar servidores al grupo.</span><span class="sxs-lookup"><span data-stu-id="6cd26-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" /><span data-ttu-id="6cd26-183">Nota de seguridad:</span><span class="sxs-lookup"><span data-stu-id="6cd26-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6cd26-184">Se debe usar el complemento administrativo de IIS para asignar el certificado usado por el servidor de componentes web de IIS.</span><span class="sxs-lookup"><span data-stu-id="6cd26-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

