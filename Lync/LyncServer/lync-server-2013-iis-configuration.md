---
title: 'Lync Server 2013: Configuración de IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de2205ad049beb05f30dd58795257b62eca68d46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="3188a-102">Configuración de IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3188a-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3188a-103">_**Última modificación del tema:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="3188a-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="3188a-104">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor como mínimo como administrador local y como usuario del dominio.</span><span class="sxs-lookup"><span data-stu-id="3188a-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="3188a-105">Antes de configurar e instalar el servidor front-end para Lync Server 2013, Standard Edition o el primer servidor front-end de un grupo, instale y configure el rol de servidor y los servicios web para servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="3188a-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="3188a-106">Si su organización requiere que encuentre IIS y todos los servicios web en una unidad distinta de la del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server 2013 en el cuadro de diálogo de configuración cuando instale inicialmente Lync Server 2013 Herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="3188a-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="3188a-107">Instale las herramientas administrativas antes de instalar IIS.</span><span class="sxs-lookup"><span data-stu-id="3188a-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="3188a-108">Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server 2013 se implementarán también en esta unidad.</span><span class="sxs-lookup"><span data-stu-id="3188a-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="3188a-109">Para Dtails, consulte <A href="lync-server-2013-install-lync-server-administrative-tools.md">instalar las herramientas administrativas 2013 de Lync Server</A>.</span><span class="sxs-lookup"><span data-stu-id="3188a-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="3188a-110">Para más información sobre cómo cambiar la ubicación de INETPUB implementada por el administrador de Windows Server al <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>instalar IIS, consulte.</span><span class="sxs-lookup"><span data-stu-id="3188a-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="3188a-111">En la tabla siguiente se indican los servicios de rol IIS 7,5 requeridos.</span><span class="sxs-lookup"><span data-stu-id="3188a-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="3188a-112">Servicios de rol IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="3188a-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3188a-113">Encabezado de rol</span><span class="sxs-lookup"><span data-stu-id="3188a-113">Role Heading</span></span></th>
<th><span data-ttu-id="3188a-114">Servicio de rol</span><span class="sxs-lookup"><span data-stu-id="3188a-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3188a-115">Características HTTP comunes instaladas</span><span class="sxs-lookup"><span data-stu-id="3188a-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="3188a-116">Contenido estático</span><span class="sxs-lookup"><span data-stu-id="3188a-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-117">Características HTTP comunes instaladas</span><span class="sxs-lookup"><span data-stu-id="3188a-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="3188a-118">Documento predeterminado</span><span class="sxs-lookup"><span data-stu-id="3188a-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-119">Características HTTP comunes instaladas</span><span class="sxs-lookup"><span data-stu-id="3188a-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="3188a-120">Errores HTTP</span><span class="sxs-lookup"><span data-stu-id="3188a-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-121">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3188a-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="3188a-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3188a-122">ASP.NET</span></span></p>
<p><span data-ttu-id="3188a-123">Windows Server 2012 también requiere ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="3188a-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-124">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3188a-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="3188a-125">Extensibilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="3188a-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-126">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3188a-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="3188a-127">Extensiones de API de servidor de Internet (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="3188a-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-128">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3188a-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="3188a-129">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="3188a-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-130">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3188a-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="3188a-131">Registro HTTP</span><span class="sxs-lookup"><span data-stu-id="3188a-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-132">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3188a-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="3188a-133">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="3188a-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-134">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3188a-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="3188a-135">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="3188a-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-136">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3188a-136">Security</span></span></p></td>
<td><p><span data-ttu-id="3188a-137">Autenticación anónima (instalado y habilitado de forma predeterminada)</span><span class="sxs-lookup"><span data-stu-id="3188a-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-138">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3188a-138">Security</span></span></p></td>
<td><p><span data-ttu-id="3188a-139">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="3188a-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-140">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3188a-140">Security</span></span></p></td>
<td><p><span data-ttu-id="3188a-141">Autenticación de asignación de certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="3188a-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-142">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3188a-142">Security</span></span></p></td>
<td><p><span data-ttu-id="3188a-143">Filtrado de solicitudes</span><span class="sxs-lookup"><span data-stu-id="3188a-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-144">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="3188a-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="3188a-145">Compresión de contenido estático</span><span class="sxs-lookup"><span data-stu-id="3188a-145">Static content compression</span></span></p>
<p><span data-ttu-id="3188a-146">Compresión de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="3188a-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-147">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="3188a-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="3188a-148">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="3188a-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-149">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="3188a-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="3188a-150">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="3188a-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3188a-151">En el sistema operativo Windows Server 2008 R2 SP1 x64, puede usar Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="3188a-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="3188a-152">Primero debe importar el módulo de ServerManager y, a continuación, instalar el rol y los servicios de rol de IIS 7,5.</span><span class="sxs-lookup"><span data-stu-id="3188a-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="3188a-153">La autenticación anónima se instala de forma predeterminada con la función de servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="3188a-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="3188a-154">Puede administrar la autenticación anónima después de la instalación de IIS.</span><span class="sxs-lookup"><span data-stu-id="3188a-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="3188a-155">Para obtener más información, vea "habilitar la autenticación anónima (IIS 7 <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>)" en.</span><span class="sxs-lookup"><span data-stu-id="3188a-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="3188a-156">La tabla siguiente indica los servicios de rol IIS 8,0 e IIS 8,5 requeridos para Windows Server 2012 y Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="3188a-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="3188a-157">Para Windows Server 2012 y Windows Server 2012 R2, el cmdlet Add-WindowsFeature ha sido reemplazado por el cmdlet install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="3188a-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="3188a-158">Para obtener información detallada, vea <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="3188a-158">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="3188a-159">Servicios de rol IIS 8,0 e IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="3188a-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3188a-160">Encabezado de rol</span><span class="sxs-lookup"><span data-stu-id="3188a-160">Role Heading</span></span></th>
<th><span data-ttu-id="3188a-161">Servicio de rol</span><span class="sxs-lookup"><span data-stu-id="3188a-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3188a-162">Servidor Web (IIS)</span><span class="sxs-lookup"><span data-stu-id="3188a-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="3188a-163">Servidor Web</span><span class="sxs-lookup"><span data-stu-id="3188a-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-164">Características HTTP comunes</span><span class="sxs-lookup"><span data-stu-id="3188a-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="3188a-165">Documento predeterminado</span><span class="sxs-lookup"><span data-stu-id="3188a-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-166">Características HTTP comunes</span><span class="sxs-lookup"><span data-stu-id="3188a-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="3188a-167">Examen de directorios</span><span class="sxs-lookup"><span data-stu-id="3188a-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-168">Características HTTP comunes</span><span class="sxs-lookup"><span data-stu-id="3188a-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="3188a-169">Errores HTTP</span><span class="sxs-lookup"><span data-stu-id="3188a-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-170">Características HTTP comunes</span><span class="sxs-lookup"><span data-stu-id="3188a-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="3188a-171">Contenido estático</span><span class="sxs-lookup"><span data-stu-id="3188a-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-172">Características HTTP comunes</span><span class="sxs-lookup"><span data-stu-id="3188a-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="3188a-173">Redireccionamiento HTTP</span><span class="sxs-lookup"><span data-stu-id="3188a-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-174">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3188a-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="3188a-175">Registro HTTP</span><span class="sxs-lookup"><span data-stu-id="3188a-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-176">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3188a-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="3188a-177">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="3188a-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-178">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3188a-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="3188a-179">Solicitar monitor</span><span class="sxs-lookup"><span data-stu-id="3188a-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-180">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3188a-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="3188a-181">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="3188a-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-182">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3188a-182">Security</span></span></p></td>
<td><p><span data-ttu-id="3188a-183">Filtro de solicitudes</span><span class="sxs-lookup"><span data-stu-id="3188a-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-184">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3188a-184">Security</span></span></p></td>
<td><p><span data-ttu-id="3188a-185">Autenticación básica</span><span class="sxs-lookup"><span data-stu-id="3188a-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-186">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3188a-186">Security</span></span></p></td>
<td><p><span data-ttu-id="3188a-187">Autenticación por asignación de certificados de clientes</span><span class="sxs-lookup"><span data-stu-id="3188a-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-188">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3188a-188">Security</span></span></p></td>
<td><p><span data-ttu-id="3188a-189">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="3188a-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-190">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3188a-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="3188a-191">Extensibilidad de .net 3,5</span><span class="sxs-lookup"><span data-stu-id="3188a-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-192">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3188a-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="3188a-193">Extensibilidad de .net 4,5</span><span class="sxs-lookup"><span data-stu-id="3188a-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-194">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3188a-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="3188a-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="3188a-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-196">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3188a-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="3188a-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="3188a-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-198">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3188a-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="3188a-199">Extensiones ISAPI</span><span class="sxs-lookup"><span data-stu-id="3188a-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-200">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3188a-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="3188a-201">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="3188a-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-202">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3188a-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="3188a-203">Inclusiones del servidor</span><span class="sxs-lookup"><span data-stu-id="3188a-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-204">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="3188a-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="3188a-205">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="3188a-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-206">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="3188a-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="3188a-207">Compatibilidad de metabase de IIS 6</span><span class="sxs-lookup"><span data-stu-id="3188a-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-208">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="3188a-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="3188a-209">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="3188a-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-210">Características de .net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="3188a-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="3188a-211">.Net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="3188a-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-212">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="3188a-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="3188a-213">4,5 de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3188a-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-214">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="3188a-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="3188a-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="3188a-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-216">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="3188a-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="3188a-217">Activación HTTP</span><span class="sxs-lookup"><span data-stu-id="3188a-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-218">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="3188a-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="3188a-219">Uso compartido de puertos TCP</span><span class="sxs-lookup"><span data-stu-id="3188a-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-220">Servicio de transferencia inteligente en segundo plano</span><span class="sxs-lookup"><span data-stu-id="3188a-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="3188a-221">Extensiones de servidor IIS</span><span class="sxs-lookup"><span data-stu-id="3188a-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-222">Servicios de tinta y escritura a mano</span><span class="sxs-lookup"><span data-stu-id="3188a-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="3188a-223">Servicios de tinta y escritura a mano</span><span class="sxs-lookup"><span data-stu-id="3188a-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="3188a-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="3188a-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="3188a-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-226">Infraestructura y interfaces de usuario</span><span class="sxs-lookup"><span data-stu-id="3188a-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="3188a-227">Herramientas de administración gráfica e infraestructura</span><span class="sxs-lookup"><span data-stu-id="3188a-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-228">Infraestructura y interfaces de usuario</span><span class="sxs-lookup"><span data-stu-id="3188a-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="3188a-229">Experiencia de escritorio</span><span class="sxs-lookup"><span data-stu-id="3188a-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-230">Infraestructura y interfaces de usuario</span><span class="sxs-lookup"><span data-stu-id="3188a-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="3188a-231">Shell gráfico de servidor</span><span class="sxs-lookup"><span data-stu-id="3188a-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-232">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="3188a-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="3188a-233">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="3188a-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3188a-234">Servicio de activación de procesos de Windows</span><span class="sxs-lookup"><span data-stu-id="3188a-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="3188a-235">Modelo de proceso</span><span class="sxs-lookup"><span data-stu-id="3188a-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3188a-236">Servicio de activación de procesos de Windows</span><span class="sxs-lookup"><span data-stu-id="3188a-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="3188a-237">API de configuración</span><span class="sxs-lookup"><span data-stu-id="3188a-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3188a-238">En Windows Server 2012 y Windows Server 2012 R2, puede usar Windows PowerShell 3,0 para instalar los requisitos de IIS.</span><span class="sxs-lookup"><span data-stu-id="3188a-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="3188a-239">Usar el módulo ServerManager en Windows PowerShell 3,0, escriba:</span><span class="sxs-lookup"><span data-stu-id="3188a-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="3188a-240">Novedades de Windows Server 2012 es el parámetro – Source que define dónde se pueden encontrar los medios de origen de Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="3188a-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="3188a-241">El medio se puede definir como una unidad de DVD (por ejemplo, D:\Sources\Sxs) o como un recurso compartido de red en el que se han copiado los archivos \\multimedia (por ejemplo, fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="3188a-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3188a-242">Vea también</span><span class="sxs-lookup"><span data-stu-id="3188a-242">See Also</span></span>


[<span data-ttu-id="3188a-243">Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3188a-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

