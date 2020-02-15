---
title: 'Lync Server 2013: preparar los servicios de dominio de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03436a59fa9fbab99608e4fa3b979e4802115ed1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="d4f49-102">Preparación de los servicios de dominio de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f49-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4f49-103">_**Última modificación del tema:** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="d4f49-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="d4f49-104">En Lync Server 2013, puede usar el Asistente para la implementación de Lync Server para preparar los servicios de dominio de Active Directory o puede usar los cmdlets del shell de administración de Lync Server directamente.</span><span class="sxs-lookup"><span data-stu-id="d4f49-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="d4f49-105">También puede usar la herramienta de línea de comandos ldifde.exe directamente en sus controladores de dominio, según se describe más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="d4f49-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="d4f49-106">El Asistente para la implementación de Lync Server le guía por todas las tareas de preparación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d4f49-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="d4f49-107">El Asistente para la implementación ejecuta los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4f49-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="d4f49-108">Esta herramienta es útil para los entornos con una topología de dominio único y bosque único u otra topología similar.</span><span class="sxs-lookup"><span data-stu-id="d4f49-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d4f49-109">Puede implementar Lync Server en un bosque o dominio donde los controladores de dominio ejecutan versiones de 32 bits de algunos sistemas operativos (para obtener más información, consulte <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory Infrastructure Requirements for Lync Server 2013</A>).</span><span class="sxs-lookup"><span data-stu-id="d4f49-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="d4f49-110">Sin embargo, no puede usar el Asistente para la implementación de Lync Server para ejecutar el esquema, el bosque y la preparación del dominio en estos entornos porque el Asistente para la implementación y los archivos auxiliares son solo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="d4f49-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="d4f49-111">En su lugar, puede usar ldifde.exe y los archivos .ldf asociados en un controlador de dominio de 32 bits para preparar el esquema, el bosque y el dominio.</span><span class="sxs-lookup"><span data-stu-id="d4f49-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="d4f49-112">Consulte la sección “Uso de Ldifde.exe”, más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="d4f49-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="d4f49-113">Puede usar los cmdlets del shell de administración de Lync Server para ejecutar tareas de forma remota o para entornos más complejos.</span><span class="sxs-lookup"><span data-stu-id="d4f49-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="d4f49-114">Requisitos previos de preparación de Active Directory</span><span class="sxs-lookup"><span data-stu-id="d4f49-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="d4f49-115">Debe ejecutar los pasos de preparación de Active Directory en un equipo que ejecute Windows Server 2012, Windows Server 2012 R2 o Windows Server 2008 R2 con SP1 (64 bits).</span><span class="sxs-lookup"><span data-stu-id="d4f49-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="d4f49-116">La preparación de Active Directory requiere Shell de administración de Lync Server y OCSCore.</span><span class="sxs-lookup"><span data-stu-id="d4f49-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="d4f49-117">Se necesitan los siguientes componentes para ejecutar las tareas de preparación de Active Directory:</span><span class="sxs-lookup"><span data-stu-id="d4f49-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="d4f49-118">Componentes principales de Lync Server (OCScore. msi)</span><span class="sxs-lookup"><span data-stu-id="d4f49-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4f49-119">Si tiene previsto usar el shell de administración de Lync Server para la preparación de Active Directory, primero debe ejecutar el Asistente para la implementación de Lync Server para instalar los componentes principales.</span><span class="sxs-lookup"><span data-stu-id="d4f49-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="d4f49-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d4f49-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4f49-121">Para Windows Server 2012 y Windows Server 2012 R2, debe instalar y activar .NET Framework 4,5 mediante el administrador del servidor.</span><span class="sxs-lookup"><span data-stu-id="d4f49-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="d4f49-122">Para obtener más información, consulte "Microsoft .NET Framework 4,5" en <A href="lync-server-2013-additional-software-requirements.md">requisitos de software adicionales para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d4f49-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="d4f49-123">Para Windows Server&nbsp;2008&nbsp;R2, descargue e instale <A href="http://www.microsoft.com/download/details.aspx?id=30653">.NET Framework 4,5</A> desde el sitio web de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4f49-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="http://www.microsoft.com/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="d4f49-124">Herramientas de administración remota del servidor (RSAT)</span><span class="sxs-lookup"><span data-stu-id="d4f49-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4f49-125">Se necesitan algunas herramientas RSAT para ejecutar los pasos de preparación de Active Directory en un servidor miembro en lugar de en un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="d4f49-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="d4f49-126">Instale los complementos y las herramientas de línea de comandos de AD DS y el módulo de Active Directory para Windows PowerShell desde el nodo herramientas de AD DS y AD LDS del administrador del servidor.</span><span class="sxs-lookup"><span data-stu-id="d4f49-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="d4f49-127">Paquete redistribuible de Microsoft Visual C++ 11</span><span class="sxs-lookup"><span data-stu-id="d4f49-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4f49-p107">El programa de instalación solicita la instalación de este requisito previo si aún no está instalado en el equipo. El paquete se suministra de modo que no tenga que adquirirlo por separado.</span><span class="sxs-lookup"><span data-stu-id="d4f49-p107">Setup prompts you to install this prerequisite if it is not already installed on the computer. The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="d4f49-130">Windows PowerShell 3,0 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="d4f49-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="d4f49-131">Para Windows Server 2012 y Windows Server 2012 R2, Windows PowerShell 3,0 debe incluirse con la instalación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4f49-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="d4f49-132">Para Windows Server 2008 R2, debe instalar o actualizar a Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d4f49-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="d4f49-133">Para obtener más información, consulte [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span><span class="sxs-lookup"><span data-stu-id="d4f49-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="d4f49-134">Roles y derechos administrativos</span><span class="sxs-lookup"><span data-stu-id="d4f49-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="d4f49-135">En la tabla siguiente, se muestran los roles y los derechos administrativos necesarios para cada tarea de preparación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d4f49-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="d4f49-136">Derechos de usuario necesarios para la preparación de Active Directory</span><span class="sxs-lookup"><span data-stu-id="d4f49-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4f49-137">Procedure</span><span class="sxs-lookup"><span data-stu-id="d4f49-137">Procedure</span></span></th>
<th><span data-ttu-id="d4f49-138">Derechos o roles</span><span class="sxs-lookup"><span data-stu-id="d4f49-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4f49-139">Preparación del esquema</span><span class="sxs-lookup"><span data-stu-id="d4f49-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="d4f49-140">Miembro del grupo de Administradores de esquema en el dominio de raíz del bosque y derechos de administrador en el maestro de esquema</span><span class="sxs-lookup"><span data-stu-id="d4f49-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4f49-141">Preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="d4f49-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="d4f49-142">Miembro del grupo de Administradores Enterprise en el bosque</span><span class="sxs-lookup"><span data-stu-id="d4f49-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4f49-143">Preparación del dominio</span><span class="sxs-lookup"><span data-stu-id="d4f49-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="d4f49-144">Miembro del grupo Administradores Enterprise o Administradores de dominio en el dominio especificado</span><span class="sxs-lookup"><span data-stu-id="d4f49-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="d4f49-145">Cmdlets de preparación de Active Directory</span><span class="sxs-lookup"><span data-stu-id="d4f49-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="d4f49-146">En la siguiente tabla se comparan los cmdlets del shell de administración de Lync Server que se usan para preparar AD DS para los comandos de LcsCmd que se usan para preparar AD DS en Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d4f49-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="d4f49-147">Cmdlets comparados con LcsCmd</span><span class="sxs-lookup"><span data-stu-id="d4f49-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4f49-148">Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d4f49-148">Cmdlets</span></span></th>
<th><span data-ttu-id="d4f49-149">LcsCmd</span><span class="sxs-lookup"><span data-stu-id="d4f49-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4f49-150">Install-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="d4f49-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="d4f49-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span><span class="sxs-lookup"><span data-stu-id="d4f49-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4f49-152">Get-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="d4f49-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="d4f49-153">Lcscmd /forest /action:CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="d4f49-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4f49-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="d4f49-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="d4f49-155">Lcscmd /forest /action:ForestPrep</span><span class="sxs-lookup"><span data-stu-id="d4f49-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4f49-156">Disable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="d4f49-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="d4f49-157">Lcscmd /forest /action:ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="d4f49-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4f49-158">Get-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="d4f49-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="d4f49-159">Lcscmd /forest /action:CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="d4f49-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4f49-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="d4f49-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="d4f49-161">Lcscmd /domain /action:DomainPrep</span><span class="sxs-lookup"><span data-stu-id="d4f49-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4f49-162">Disable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="d4f49-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="d4f49-163">Lcscmd /domain /action: DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="d4f49-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4f49-164">Get-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="d4f49-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="d4f49-165">Lcscmd /domain /action:CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="d4f49-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="d4f49-166">Requisitos de Active Directory bloqueado</span><span class="sxs-lookup"><span data-stu-id="d4f49-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="d4f49-167">Si la herencia de permisos está deshabilitada o si deben deshabilitarse los permisos de usuarios autenticados en su organización, debe realizar pasos adicionales durante la preparación de los dominios.</span><span class="sxs-lookup"><span data-stu-id="d4f49-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="d4f49-168">Para obtener más información, consulte [preparar los servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="d4f49-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="d4f49-169">Permisos para contenedores personalizados</span><span class="sxs-lookup"><span data-stu-id="d4f49-169">Custom Container Permissions</span></span>

<span data-ttu-id="d4f49-170">Si en su organización se usan contenedores personalizados en lugar de los tres contenedores integrados (es decir, usuarios, equipos y controladores de dominio), debe conceder acceso de lectura de los contenedores personalizados al grupo Usuarios autenticados.</span><span class="sxs-lookup"><span data-stu-id="d4f49-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="d4f49-171">El acceso de lectura de los contenedores se necesita para preparar dominios.</span><span class="sxs-lookup"><span data-stu-id="d4f49-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="d4f49-172">Para obtener más información, consulte [preparación de dominios para Lync Server 2013](lync-server-2013-preparing-domains.md).</span><span class="sxs-lookup"><span data-stu-id="d4f49-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="d4f49-173">Uso de cmdlets y Ldifde.exe</span><span class="sxs-lookup"><span data-stu-id="d4f49-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="d4f49-174">El paso **preparar el esquema** en el Asistente para la implementación de Lync Server y el cmdlet **install-CsAdServerSchema** amplían el esquema de Active Directory en controladores de dominio que ejecutan un sistema operativo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="d4f49-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="d4f49-175">Si necesita extender el esquema de Active Directory en un controlador de dominio que ejecute un sistema operativo de 32 bits, puede ejecutar el cmdlet **Install-CsAdServerSchema** de forma remota desde un servidor miembro (procedimiento recomendado).</span><span class="sxs-lookup"><span data-stu-id="d4f49-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="d4f49-176">Sin embargo, si necesita ejecutar la preparación del esquema directamente en el controlador de dominio, puede usar la herramienta Ldifde.exe para importar los archivos del esquema.</span><span class="sxs-lookup"><span data-stu-id="d4f49-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="d4f49-177">La herramienta Ldifde.exe viene incluida en la mayoría de las versiones del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="d4f49-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="d4f49-p112">Si usa Ldifde.exe para importar los archivos del esquema, debe importar los cuatro archivos, ya esté migrando desde una versión anterior o realizando una instalación limpia. Debe importarlos en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="d4f49-p112">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation. You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="d4f49-180">ExternalSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="d4f49-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="d4f49-181">ServerSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="d4f49-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="d4f49-182">BackCompatSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="d4f49-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="d4f49-183">VersionSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="d4f49-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4f49-184">Los cuatro archivos .ldf se encuentran en el directorio \Support\Schema de la descarga o el medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="d4f49-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="d4f49-185">Si desea usar Ldifde.exe para importar los cuatro archivos del esquema en un controlador de dominio que sea el maestro de esquema, use el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="d4f49-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="d4f49-186">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d4f49-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="d4f49-p113">Use el parámetro b solo si ha iniciado sesión como otro usuario. Para ver más detalles acerca de los derechos de usuario necesarios, consulte la sección "Roles y derechos administrativos", anteriormente en este mismo tema.</span><span class="sxs-lookup"><span data-stu-id="d4f49-p113">Use the b parameter only if you are logged in as a different user. For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="d4f49-189">Si desea usar Ldifde.exe para importar los cuatro archivos del esquema en un controlador de dominio que no sea el maestro de esquema, use el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="d4f49-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="d4f49-190">Para obtener más información sobre el uso de Ldifde, consulte el artículo 237677 de Microsoft Knowledge base, "Using LDIFDE to Import and Export Directory Objects to Active Directory" en [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).</span><span class="sxs-lookup"><span data-stu-id="d4f49-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d4f49-191">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d4f49-191">In This Section</span></span>

  - [<span data-ttu-id="d4f49-192">Preparar el esquema de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f49-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="d4f49-193">Preparar el bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f49-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="d4f49-194">Preparar dominios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f49-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

