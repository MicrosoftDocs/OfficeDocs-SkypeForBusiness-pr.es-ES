---
title: 'Lync Server 2013: configuración de IIS'
description: 'Lync Server 2013: configuración de IIS.'
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
ms.openlocfilehash: 901aca7bf5ff8824b54e93754569a6ef5defc10e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554876"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="5ea39-103">Configuración de IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea39-103">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ea39-104">_**Última modificación del tema:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="5ea39-104">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="5ea39-105">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="5ea39-105">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="5ea39-106">Antes de configurar e instalar el servidor front-end para Lync Server 2013, Standard Edition o el primer servidor front-end en un grupo de servidores, instale y configure el rol de servidor y los servicios web para Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="5ea39-106">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="5ea39-107">Si su organización requiere que localice IIS y todos los servicios web en una unidad que no sea la unidad del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server 2013 en el cuadro de diálogo de configuración cuando instale inicialmente las herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ea39-107">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="5ea39-108">Las herramientas administrativas se deben instalar antes que IIS.</span><span class="sxs-lookup"><span data-stu-id="5ea39-108">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="5ea39-109">Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, también se implementará el resto de los archivos de Lync Server 2013 en esta unidad.</span><span class="sxs-lookup"><span data-stu-id="5ea39-109">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="5ea39-110">Para Dtails, consulte <A href="lync-server-2013-install-lync-server-administrative-tools.md">install Lync Server 2013 Administrative Tools</A>.</span><span class="sxs-lookup"><span data-stu-id="5ea39-110">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="5ea39-111">Para obtener información sobre cómo reubicar la INETPUB implementada por el administrador de servidores de Windows al instalar IIS, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="5ea39-111">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="5ea39-112">En la tabla siguiente se indican los servicios de rol IIS 7,5 necesarios.</span><span class="sxs-lookup"><span data-stu-id="5ea39-112">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="5ea39-113">Servicios de rol de IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="5ea39-113">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ea39-114">Encabezado de rol</span><span class="sxs-lookup"><span data-stu-id="5ea39-114">Role Heading</span></span></th>
<th><span data-ttu-id="5ea39-115">Servicio de rol</span><span class="sxs-lookup"><span data-stu-id="5ea39-115">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-116">Características HTTP comunas instaladas</span><span class="sxs-lookup"><span data-stu-id="5ea39-116">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="5ea39-117">Contenido estático</span><span class="sxs-lookup"><span data-stu-id="5ea39-117">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-118">Características HTTP comunas instaladas</span><span class="sxs-lookup"><span data-stu-id="5ea39-118">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="5ea39-119">Documento predeterminado</span><span class="sxs-lookup"><span data-stu-id="5ea39-119">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-120">Características HTTP comunas instaladas</span><span class="sxs-lookup"><span data-stu-id="5ea39-120">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="5ea39-121">Errores HTTP</span><span class="sxs-lookup"><span data-stu-id="5ea39-121">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-122">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5ea39-122">Application development</span></span></p></td>
<td><p><span data-ttu-id="5ea39-123">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5ea39-123">ASP.NET</span></span></p>
<p><span data-ttu-id="5ea39-124">Windows Server 2012 también necesita ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="5ea39-124">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-125">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5ea39-125">Application development</span></span></p></td>
<td><p><span data-ttu-id="5ea39-126">Extensibilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="5ea39-126">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-127">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5ea39-127">Application development</span></span></p></td>
<td><p><span data-ttu-id="5ea39-128">Extensiones de Internet Server API (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="5ea39-128">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-129">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5ea39-129">Application development</span></span></p></td>
<td><p><span data-ttu-id="5ea39-130">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="5ea39-130">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-131">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5ea39-131">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="5ea39-132">Registro HTTP</span><span class="sxs-lookup"><span data-stu-id="5ea39-132">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-133">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5ea39-133">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="5ea39-134">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="5ea39-134">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-135">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5ea39-135">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="5ea39-136">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="5ea39-136">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-137">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5ea39-137">Security</span></span></p></td>
<td><p><span data-ttu-id="5ea39-138">Autenticación anónima (instalada y habilitada de forma predeterminada)</span><span class="sxs-lookup"><span data-stu-id="5ea39-138">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-139">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5ea39-139">Security</span></span></p></td>
<td><p><span data-ttu-id="5ea39-140">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="5ea39-140">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-141">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5ea39-141">Security</span></span></p></td>
<td><p><span data-ttu-id="5ea39-142">Autenticación por asignación de certificados de clientes</span><span class="sxs-lookup"><span data-stu-id="5ea39-142">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-143">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5ea39-143">Security</span></span></p></td>
<td><p><span data-ttu-id="5ea39-144">Filtrado de solicitudes</span><span class="sxs-lookup"><span data-stu-id="5ea39-144">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-145">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="5ea39-145">Performance</span></span></p></td>
<td><p><span data-ttu-id="5ea39-146">Compresión de contenido estático</span><span class="sxs-lookup"><span data-stu-id="5ea39-146">Static content compression</span></span></p>
<p><span data-ttu-id="5ea39-147">Compresión de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="5ea39-147">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-148">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="5ea39-148">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="5ea39-149">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="5ea39-149">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-150">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="5ea39-150">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="5ea39-151">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="5ea39-151">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5ea39-152">En el sistema operativo Windows Server 2008 R2 SP1 x64, puede usar Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="5ea39-152">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="5ea39-153">Primero debe importar el módulo ServerManager y, a continuación, instalar el rol y los servicios de rol de IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="5ea39-153">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="5ea39-154">La autenticación anónima está instalada de forma predeterminada con el rol del servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="5ea39-154">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="5ea39-155">Puede administrar la autenticación anónima después de instalar el IIS.</span><span class="sxs-lookup"><span data-stu-id="5ea39-155">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="5ea39-156">Para obtener más información, consulte "habilitar la autenticación anónima (IIS 7)" en <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .</span><span class="sxs-lookup"><span data-stu-id="5ea39-156">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="5ea39-157">En la tabla siguiente se indican los servicios de rol IIS 8,0 e IIS 8,5 necesarios para Windows Server 2012 y Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="5ea39-157">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="5ea39-158">Para Windows Server 2012 y Windows Server 2012 R2, el cmdlet Add-WindowsFeature se ha reemplazado por el cmdlet Install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="5ea39-158">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="5ea39-159">Para obtener más información, vea <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="5ea39-159">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="5ea39-160">Servicios de rol IIS 8,0 e IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="5ea39-160">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ea39-161">Encabezado de rol</span><span class="sxs-lookup"><span data-stu-id="5ea39-161">Role Heading</span></span></th>
<th><span data-ttu-id="5ea39-162">Servicio de rol</span><span class="sxs-lookup"><span data-stu-id="5ea39-162">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-163">Servidor web (IIS)</span><span class="sxs-lookup"><span data-stu-id="5ea39-163">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="5ea39-164">Servidor web</span><span class="sxs-lookup"><span data-stu-id="5ea39-164">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-165">Características comunes de HTTP</span><span class="sxs-lookup"><span data-stu-id="5ea39-165">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="5ea39-166">Documento predeterminado</span><span class="sxs-lookup"><span data-stu-id="5ea39-166">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-167">Características comunes de HTTP</span><span class="sxs-lookup"><span data-stu-id="5ea39-167">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="5ea39-168">Examen de directorios</span><span class="sxs-lookup"><span data-stu-id="5ea39-168">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-169">Características comunes de HTTP</span><span class="sxs-lookup"><span data-stu-id="5ea39-169">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="5ea39-170">Errores HTTP</span><span class="sxs-lookup"><span data-stu-id="5ea39-170">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-171">Características comunes de HTTP</span><span class="sxs-lookup"><span data-stu-id="5ea39-171">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="5ea39-172">Contenido estático</span><span class="sxs-lookup"><span data-stu-id="5ea39-172">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-173">Características HTTP comunes</span><span class="sxs-lookup"><span data-stu-id="5ea39-173">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="5ea39-174">Redirección HTTP</span><span class="sxs-lookup"><span data-stu-id="5ea39-174">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-175">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5ea39-175">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="5ea39-176">Registro HTTP</span><span class="sxs-lookup"><span data-stu-id="5ea39-176">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-177">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5ea39-177">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="5ea39-178">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="5ea39-178">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-179">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5ea39-179">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="5ea39-180">Supervisor de solicitud</span><span class="sxs-lookup"><span data-stu-id="5ea39-180">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-181">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5ea39-181">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="5ea39-182">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="5ea39-182">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-183">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5ea39-183">Security</span></span></p></td>
<td><p><span data-ttu-id="5ea39-184">Filtrado de solicitudes</span><span class="sxs-lookup"><span data-stu-id="5ea39-184">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-185">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5ea39-185">Security</span></span></p></td>
<td><p><span data-ttu-id="5ea39-186">Autenticación básica</span><span class="sxs-lookup"><span data-stu-id="5ea39-186">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-187">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5ea39-187">Security</span></span></p></td>
<td><p><span data-ttu-id="5ea39-188">Autenticación por asignación de certificados de clientes</span><span class="sxs-lookup"><span data-stu-id="5ea39-188">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-189">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5ea39-189">Security</span></span></p></td>
<td><p><span data-ttu-id="5ea39-190">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="5ea39-190">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-191">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5ea39-191">Application Development</span></span></p></td>
<td><p><span data-ttu-id="5ea39-192">Extensibilidad de .net 3,5</span><span class="sxs-lookup"><span data-stu-id="5ea39-192">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-193">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5ea39-193">Application Development</span></span></p></td>
<td><p><span data-ttu-id="5ea39-194">Extensibilidad de .net 4,5</span><span class="sxs-lookup"><span data-stu-id="5ea39-194">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-195">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5ea39-195">Application Development</span></span></p></td>
<td><p><span data-ttu-id="5ea39-196">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="5ea39-196">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-197">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5ea39-197">Application Development</span></span></p></td>
<td><p><span data-ttu-id="5ea39-198">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="5ea39-198">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-199">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5ea39-199">Application Development</span></span></p></td>
<td><p><span data-ttu-id="5ea39-200">Extensiones ISAPI</span><span class="sxs-lookup"><span data-stu-id="5ea39-200">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-201">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5ea39-201">Application Development</span></span></p></td>
<td><p><span data-ttu-id="5ea39-202">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="5ea39-202">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-203">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5ea39-203">Application Development</span></span></p></td>
<td><p><span data-ttu-id="5ea39-204">Inclusiones del servidor</span><span class="sxs-lookup"><span data-stu-id="5ea39-204">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-205">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="5ea39-205">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="5ea39-206">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="5ea39-206">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-207">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="5ea39-207">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="5ea39-208">Compatibilidad con la metabase de IIS 6</span><span class="sxs-lookup"><span data-stu-id="5ea39-208">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-209">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="5ea39-209">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="5ea39-210">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="5ea39-210">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-211">Características de .net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="5ea39-211">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="5ea39-212">.Net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="5ea39-212">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-213">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="5ea39-213">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="5ea39-214">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="5ea39-214">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-215">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="5ea39-215">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="5ea39-216">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="5ea39-216">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-217">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="5ea39-217">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="5ea39-218">Activación HTTP</span><span class="sxs-lookup"><span data-stu-id="5ea39-218">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-219">Características de .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="5ea39-219">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="5ea39-220">Uso compartido de puertos TCP</span><span class="sxs-lookup"><span data-stu-id="5ea39-220">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-221">Servicio de transferencia inteligente en segundo plano</span><span class="sxs-lookup"><span data-stu-id="5ea39-221">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="5ea39-222">Extensiones de servidor IIS</span><span class="sxs-lookup"><span data-stu-id="5ea39-222">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-223">Servicios de Escritura con lápiz y Escritura a mano</span><span class="sxs-lookup"><span data-stu-id="5ea39-223">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="5ea39-224">Servicios de Escritura con lápiz y Escritura a mano</span><span class="sxs-lookup"><span data-stu-id="5ea39-224">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="5ea39-225">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="5ea39-226">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="5ea39-226">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-227">Infraestructura e interfaces de usuario</span><span class="sxs-lookup"><span data-stu-id="5ea39-227">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="5ea39-228">Infraestructura y herramientas de administración gráficas</span><span class="sxs-lookup"><span data-stu-id="5ea39-228">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-229">Infraestructura e interfaces de usuario</span><span class="sxs-lookup"><span data-stu-id="5ea39-229">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="5ea39-230">Experiencia de escritorio</span><span class="sxs-lookup"><span data-stu-id="5ea39-230">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-231">Infraestructura e interfaces de usuario</span><span class="sxs-lookup"><span data-stu-id="5ea39-231">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="5ea39-232">Shell gráfico del servidor</span><span class="sxs-lookup"><span data-stu-id="5ea39-232">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="5ea39-233">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="5ea39-234">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="5ea39-234">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea39-235">Servicio de activación de procesos de Windows</span><span class="sxs-lookup"><span data-stu-id="5ea39-235">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="5ea39-236">Modelo de proceso</span><span class="sxs-lookup"><span data-stu-id="5ea39-236">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea39-237">Servicio de activación de procesos de Windows</span><span class="sxs-lookup"><span data-stu-id="5ea39-237">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="5ea39-238">API de configuración</span><span class="sxs-lookup"><span data-stu-id="5ea39-238">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5ea39-239">En Windows Server 2012 y Windows Server 2012 R2, puede usar Windows PowerShell 3,0 para instalar los requisitos de IIS.</span><span class="sxs-lookup"><span data-stu-id="5ea39-239">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="5ea39-240">Usar el módulo ServerManager en Windows PowerShell 3,0, escriba:</span><span class="sxs-lookup"><span data-stu-id="5ea39-240">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="5ea39-241">New with Windows Server 2012 es el parámetro – Source que define dónde se puede encontrar el medio de origen de Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="5ea39-241">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="5ea39-242">El medio puede definirse como una unidad de DVD (por ejemplo, D:\Sources\Sxs) o en un recurso compartido de red en el que se han copiado los archivos multimedia (por ejemplo, \\ fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="5ea39-242">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ea39-243">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ea39-243">See Also</span></span>


[<span data-ttu-id="5ea39-244">Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea39-244">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

