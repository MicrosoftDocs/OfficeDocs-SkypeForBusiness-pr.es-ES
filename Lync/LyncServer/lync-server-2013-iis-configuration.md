---
title: 'Lync Server 2013: configuración de IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc8895a144b4911560af8fd6a2f12d576f3ec14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528157"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="e5713-102">Configuración de IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5713-102">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5713-103">_**Última modificación del tema:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="e5713-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="e5713-104">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="e5713-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="e5713-105">Antes de configurar e instalar el servidor front-end para Lync Server 2013, Standard Edition o el primer servidor front-end en un grupo de servidores, instale y configure el rol de servidor y los servicios web para Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="e5713-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="e5713-106">Si su organización requiere que localice IIS y todos los servicios web en una unidad que no sea la unidad del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server 2013 en el cuadro de diálogo de configuración cuando instale inicialmente las herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5713-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="e5713-107">Las herramientas administrativas se deben instalar antes que IIS.</span><span class="sxs-lookup"><span data-stu-id="e5713-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="e5713-108">Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, también se implementará el resto de los archivos de Lync Server 2013 en esta unidad.</span><span class="sxs-lookup"><span data-stu-id="e5713-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="e5713-109">Para Dtails, consulte <A href="lync-server-2013-install-lync-server-administrative-tools.md">install Lync Server 2013 Administrative Tools</A>.</span><span class="sxs-lookup"><span data-stu-id="e5713-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="e5713-110">Para obtener información sobre cómo reubicar la INETPUB implementada por el administrador de servidores de Windows al instalar IIS, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="e5713-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="e5713-111">En la tabla siguiente se indican los servicios de rol IIS 7,5 necesarios.</span><span class="sxs-lookup"><span data-stu-id="e5713-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="e5713-112">Servicios de rol de IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="e5713-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5713-113">Encabezado de rol</span><span class="sxs-lookup"><span data-stu-id="e5713-113">Role Heading</span></span></th>
<th><span data-ttu-id="e5713-114">Servicio de rol</span><span class="sxs-lookup"><span data-stu-id="e5713-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5713-115">Características HTTP comunas instaladas</span><span class="sxs-lookup"><span data-stu-id="e5713-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="e5713-116">Contenido estático</span><span class="sxs-lookup"><span data-stu-id="e5713-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-117">Características HTTP comunas instaladas</span><span class="sxs-lookup"><span data-stu-id="e5713-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="e5713-118">Documento predeterminado</span><span class="sxs-lookup"><span data-stu-id="e5713-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-119">Características HTTP comunas instaladas</span><span class="sxs-lookup"><span data-stu-id="e5713-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="e5713-120">Errores HTTP</span><span class="sxs-lookup"><span data-stu-id="e5713-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-121">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5713-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="e5713-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e5713-122">ASP.NET</span></span></p>
<p><span data-ttu-id="e5713-123">Windows Server 2012 también necesita ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="e5713-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-124">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5713-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="e5713-125">Extensibilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="e5713-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-126">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5713-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="e5713-127">Extensiones de Internet Server API (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="e5713-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-128">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5713-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="e5713-129">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="e5713-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-130">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e5713-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="e5713-131">Registro HTTP</span><span class="sxs-lookup"><span data-stu-id="e5713-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-132">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e5713-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="e5713-133">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="e5713-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-134">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e5713-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="e5713-135">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="e5713-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-136">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e5713-136">Security</span></span></p></td>
<td><p><span data-ttu-id="e5713-137">Autenticación anónima (instalada y habilitada de forma predeterminada)</span><span class="sxs-lookup"><span data-stu-id="e5713-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-138">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e5713-138">Security</span></span></p></td>
<td><p><span data-ttu-id="e5713-139">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="e5713-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-140">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e5713-140">Security</span></span></p></td>
<td><p><span data-ttu-id="e5713-141">Autenticación por asignación de certificados de clientes</span><span class="sxs-lookup"><span data-stu-id="e5713-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-142">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e5713-142">Security</span></span></p></td>
<td><p><span data-ttu-id="e5713-143">Filtrado de solicitudes</span><span class="sxs-lookup"><span data-stu-id="e5713-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-144">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="e5713-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="e5713-145">Compresión de contenido estático</span><span class="sxs-lookup"><span data-stu-id="e5713-145">Static content compression</span></span></p>
<p><span data-ttu-id="e5713-146">Compresión de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="e5713-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-147">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="e5713-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="e5713-148">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="e5713-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-149">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="e5713-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="e5713-150">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="e5713-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e5713-151">En el sistema operativo Windows Server 2008 R2 SP1 x64, puede usar Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="e5713-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="e5713-152">Primero debe importar el módulo ServerManager y, a continuación, instalar el rol y los servicios de rol de IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="e5713-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="e5713-153">La autenticación anónima está instalada de forma predeterminada con el rol del servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="e5713-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="e5713-154">Puede administrar la autenticación anónima después de instalar el IIS.</span><span class="sxs-lookup"><span data-stu-id="e5713-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="e5713-155">Para obtener más información, consulte "habilitar la autenticación anónima (IIS 7)" en <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .</span><span class="sxs-lookup"><span data-stu-id="e5713-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="e5713-156">En la tabla siguiente se indican los servicios de rol IIS 8,0 e IIS 8,5 necesarios para Windows Server 2012 y Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="e5713-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="e5713-157">Para Windows Server 2012 y Windows Server 2012 R2, el cmdlet Add-WindowsFeature se ha reemplazado por el cmdlet Install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="e5713-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="e5713-158">Para obtener más información, vea <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="e5713-158">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="e5713-159">Servicios de rol IIS 8,0 e IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="e5713-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5713-160">Encabezado de rol</span><span class="sxs-lookup"><span data-stu-id="e5713-160">Role Heading</span></span></th>
<th><span data-ttu-id="e5713-161">Servicio de rol</span><span class="sxs-lookup"><span data-stu-id="e5713-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5713-162">Servidor web (IIS)</span><span class="sxs-lookup"><span data-stu-id="e5713-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="e5713-163">Servidor web</span><span class="sxs-lookup"><span data-stu-id="e5713-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-164">Características comunes de HTTP</span><span class="sxs-lookup"><span data-stu-id="e5713-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="e5713-165">Documento predeterminado</span><span class="sxs-lookup"><span data-stu-id="e5713-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-166">Características comunes de HTTP</span><span class="sxs-lookup"><span data-stu-id="e5713-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="e5713-167">Examen de directorios</span><span class="sxs-lookup"><span data-stu-id="e5713-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-168">Características comunes de HTTP</span><span class="sxs-lookup"><span data-stu-id="e5713-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="e5713-169">Errores HTTP</span><span class="sxs-lookup"><span data-stu-id="e5713-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-170">Características comunes de HTTP</span><span class="sxs-lookup"><span data-stu-id="e5713-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="e5713-171">Contenido estático</span><span class="sxs-lookup"><span data-stu-id="e5713-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-172">Características HTTP comunes</span><span class="sxs-lookup"><span data-stu-id="e5713-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="e5713-173">Redirección HTTP</span><span class="sxs-lookup"><span data-stu-id="e5713-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-174">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e5713-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="e5713-175">Registro HTTP</span><span class="sxs-lookup"><span data-stu-id="e5713-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-176">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e5713-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="e5713-177">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="e5713-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-178">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e5713-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="e5713-179">Supervisor de solicitud</span><span class="sxs-lookup"><span data-stu-id="e5713-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-180">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e5713-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="e5713-181">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="e5713-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-182">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e5713-182">Security</span></span></p></td>
<td><p><span data-ttu-id="e5713-183">Filtrado de solicitudes</span><span class="sxs-lookup"><span data-stu-id="e5713-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-184">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e5713-184">Security</span></span></p></td>
<td><p><span data-ttu-id="e5713-185">Autenticación básica</span><span class="sxs-lookup"><span data-stu-id="e5713-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-186">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e5713-186">Security</span></span></p></td>
<td><p><span data-ttu-id="e5713-187">Autenticación por asignación de certificados de clientes</span><span class="sxs-lookup"><span data-stu-id="e5713-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-188">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e5713-188">Security</span></span></p></td>
<td><p><span data-ttu-id="e5713-189">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="e5713-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-190">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5713-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="e5713-191">Extensibilidad de .net 3,5</span><span class="sxs-lookup"><span data-stu-id="e5713-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-192">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5713-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="e5713-193">Extensibilidad de .net 4,5</span><span class="sxs-lookup"><span data-stu-id="e5713-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-194">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5713-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="e5713-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="e5713-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-196">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5713-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="e5713-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="e5713-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-198">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5713-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="e5713-199">Extensiones ISAPI</span><span class="sxs-lookup"><span data-stu-id="e5713-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-200">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5713-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="e5713-201">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="e5713-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-202">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5713-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="e5713-203">Inclusiones del servidor</span><span class="sxs-lookup"><span data-stu-id="e5713-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-204">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="e5713-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="e5713-205">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="e5713-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-206">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="e5713-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="e5713-207">Compatibilidad con la metabase de IIS 6</span><span class="sxs-lookup"><span data-stu-id="e5713-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-208">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="e5713-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="e5713-209">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="e5713-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-210">Características de .net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="e5713-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="e5713-211">.Net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="e5713-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-212">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="e5713-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="e5713-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="e5713-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-214">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="e5713-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="e5713-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="e5713-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-216">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="e5713-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="e5713-217">Activación HTTP</span><span class="sxs-lookup"><span data-stu-id="e5713-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-218">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="e5713-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="e5713-219">Uso compartido de puertos TCP</span><span class="sxs-lookup"><span data-stu-id="e5713-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-220">Servicio de transferencia inteligente en segundo plano</span><span class="sxs-lookup"><span data-stu-id="e5713-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="e5713-221">Extensiones de servidor IIS</span><span class="sxs-lookup"><span data-stu-id="e5713-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-222">Servicios de Escritura con lápiz y Escritura a mano</span><span class="sxs-lookup"><span data-stu-id="e5713-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="e5713-223">Servicios de Escritura con lápiz y Escritura a mano</span><span class="sxs-lookup"><span data-stu-id="e5713-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="e5713-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="e5713-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="e5713-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-226">Infraestructura e interfaces de usuario</span><span class="sxs-lookup"><span data-stu-id="e5713-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="e5713-227">Infraestructura y herramientas de administración gráficas</span><span class="sxs-lookup"><span data-stu-id="e5713-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-228">Infraestructura e interfaces de usuario</span><span class="sxs-lookup"><span data-stu-id="e5713-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="e5713-229">Experiencia de escritorio</span><span class="sxs-lookup"><span data-stu-id="e5713-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-230">Infraestructura e interfaces de usuario</span><span class="sxs-lookup"><span data-stu-id="e5713-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="e5713-231">Shell gráfico del servidor</span><span class="sxs-lookup"><span data-stu-id="e5713-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-232">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="e5713-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="e5713-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="e5713-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5713-234">Servicio de activación de procesos de Windows</span><span class="sxs-lookup"><span data-stu-id="e5713-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="e5713-235">Modelo de proceso</span><span class="sxs-lookup"><span data-stu-id="e5713-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5713-236">Servicio de activación de procesos de Windows</span><span class="sxs-lookup"><span data-stu-id="e5713-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="e5713-237">API de configuración</span><span class="sxs-lookup"><span data-stu-id="e5713-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e5713-238">En Windows Server 2012 y Windows Server 2012 R2, puede usar Windows PowerShell 3,0 para instalar los requisitos de IIS.</span><span class="sxs-lookup"><span data-stu-id="e5713-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="e5713-239">Usar el módulo ServerManager en Windows PowerShell 3,0, escriba:</span><span class="sxs-lookup"><span data-stu-id="e5713-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="e5713-240">New with Windows Server 2012 es el parámetro – Source que define dónde se puede encontrar el medio de origen de Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="e5713-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="e5713-241">El medio puede definirse como una unidad de DVD (por ejemplo, D:\Sources\Sxs) o en un recurso compartido de red en el que se han copiado los archivos multimedia (por ejemplo, \\ fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="e5713-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5713-242">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5713-242">See Also</span></span>


[<span data-ttu-id="e5713-243">Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5713-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

