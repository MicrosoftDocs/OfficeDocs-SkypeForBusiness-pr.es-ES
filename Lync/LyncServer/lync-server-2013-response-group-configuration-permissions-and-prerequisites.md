---
title: 'Lync Server 2013: permisos y requisitos previos de configuración del grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8e27d3495ce2152dee67a5f176c4a0d9f7e7f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="64adb-102">Permisos y requisitos previos de configuración de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64adb-102">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64adb-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="64adb-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="64adb-p101">El grupo de respuesta es una característica de administración de llamadas de Enterprise Voice. Este tema describe lo que necesita preparar antes de poder configurar el grupo de respuesta, y los permisos y las credenciales administrativas que necesita para realizar tareas de configuración.</span><span class="sxs-lookup"><span data-stu-id="64adb-p101">Response Group is an Enterprise Voice call management feature. This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="64adb-106">En esta sección, se da por supuesto que ha leído la documentación de planeación relacionada con el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="64adb-106">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="64adb-107">Para obtener más información, consulte [planeación de las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="64adb-107">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="64adb-108">Herramientas de configuración y roles administrativos</span><span class="sxs-lookup"><span data-stu-id="64adb-108">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="64adb-109">Puede usar las siguientes herramientas administrativas para configurar el grupo de respuesta:</span><span class="sxs-lookup"><span data-stu-id="64adb-109">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="64adb-110">Panel de Control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="64adb-110">Lync Server Control Panel</span></span>

  - <span data-ttu-id="64adb-111">Herramienta de configuración de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="64adb-111">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="64adb-112">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="64adb-112">Lync Server Management Shell</span></span>

<span data-ttu-id="64adb-113">Para configurar el grupo de respuesta, debe ser un miembro de al menos uno de los siguientes roles administrativos:</span><span class="sxs-lookup"><span data-stu-id="64adb-113">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64adb-114"><strong>Grupo de seguridad de Active Directory (1)</strong></span><span class="sxs-lookup"><span data-stu-id="64adb-114"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="64adb-115">Crear flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="64adb-115">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="64adb-116">Asignar administrador</span><span class="sxs-lookup"><span data-stu-id="64adb-116">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="64adb-117">Crear/asignar agentes, colas</span><span class="sxs-lookup"><span data-stu-id="64adb-117">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="64adb-118">Crear/administrar vacaciones y horas laborales</span><span class="sxs-lookup"><span data-stu-id="64adb-118">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="64adb-119">Activar/desactivar flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="64adb-119">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="64adb-120">Configurar flujo de trabajo (IVR o grupo de extensiones)</span><span class="sxs-lookup"><span data-stu-id="64adb-120">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64adb-121"><strong>CsResponseGroupAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="64adb-121"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="64adb-122">√</span><span class="sxs-lookup"><span data-stu-id="64adb-122">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-123">√</span><span class="sxs-lookup"><span data-stu-id="64adb-123">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-124">√</span><span class="sxs-lookup"><span data-stu-id="64adb-124">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-125">√</span><span class="sxs-lookup"><span data-stu-id="64adb-125">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-126">√</span><span class="sxs-lookup"><span data-stu-id="64adb-126">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-127">√</span><span class="sxs-lookup"><span data-stu-id="64adb-127">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64adb-128"><strong>CsResponseGroupManager</strong></span><span class="sxs-lookup"><span data-stu-id="64adb-128"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="64adb-129">√ (2)</span><span class="sxs-lookup"><span data-stu-id="64adb-129">√(2)</span></span></p></td>
<td><p><span data-ttu-id="64adb-130">√ (3)</span><span class="sxs-lookup"><span data-stu-id="64adb-130">√(3)</span></span></p></td>
<td><p><span data-ttu-id="64adb-131">√ (3)</span><span class="sxs-lookup"><span data-stu-id="64adb-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="64adb-132">√ (3)</span><span class="sxs-lookup"><span data-stu-id="64adb-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="64adb-133">√ (3)</span><span class="sxs-lookup"><span data-stu-id="64adb-133">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64adb-134"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="64adb-134"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="64adb-135">√</span><span class="sxs-lookup"><span data-stu-id="64adb-135">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-136">√</span><span class="sxs-lookup"><span data-stu-id="64adb-136">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-137">√</span><span class="sxs-lookup"><span data-stu-id="64adb-137">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-138">√</span><span class="sxs-lookup"><span data-stu-id="64adb-138">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-139">√</span><span class="sxs-lookup"><span data-stu-id="64adb-139">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-140">√</span><span class="sxs-lookup"><span data-stu-id="64adb-140">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64adb-141"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="64adb-141"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="64adb-142">√</span><span class="sxs-lookup"><span data-stu-id="64adb-142">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-143">√</span><span class="sxs-lookup"><span data-stu-id="64adb-143">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-144">√</span><span class="sxs-lookup"><span data-stu-id="64adb-144">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-145">√</span><span class="sxs-lookup"><span data-stu-id="64adb-145">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-146">√</span><span class="sxs-lookup"><span data-stu-id="64adb-146">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-147">√</span><span class="sxs-lookup"><span data-stu-id="64adb-147">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64adb-148"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="64adb-148"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="64adb-149">√</span><span class="sxs-lookup"><span data-stu-id="64adb-149">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-150">√</span><span class="sxs-lookup"><span data-stu-id="64adb-150">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-151">√</span><span class="sxs-lookup"><span data-stu-id="64adb-151">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-152">√</span><span class="sxs-lookup"><span data-stu-id="64adb-152">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-153">√</span><span class="sxs-lookup"><span data-stu-id="64adb-153">√</span></span></p></td>
<td><p><span data-ttu-id="64adb-154">√</span><span class="sxs-lookup"><span data-stu-id="64adb-154">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64adb-155"><strong>CsViewOnlyAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="64adb-155"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="64adb-156">√ (4)</span><span class="sxs-lookup"><span data-stu-id="64adb-156">√(4)</span></span></p></td>
<td><p><span data-ttu-id="64adb-157">√ (4)</span><span class="sxs-lookup"><span data-stu-id="64adb-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="64adb-158">√ (4)</span><span class="sxs-lookup"><span data-stu-id="64adb-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="64adb-159">√ (4)</span><span class="sxs-lookup"><span data-stu-id="64adb-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="64adb-160">√ (4)</span><span class="sxs-lookup"><span data-stu-id="64adb-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="64adb-161">√ (4)</span><span class="sxs-lookup"><span data-stu-id="64adb-161">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="64adb-162"><STRONG>(1)</STRONG> un objeto de usuario de servicios de dominio de Active Directory debe ser miembro del grupo de seguridad de Active Directory especificado que aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="64adb-162"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="64adb-163">Un administrador u otro miembro delegado de grupo de Active Directory con los permisos apropiados para agregar usuarios a un grupo de seguridad (por ejemplo, administrador, operadores de cuenta) deben agregar un objeto de usuario al grupo o grupo de seguridad de la lista para que el usuario pueda Realice las funciones enumeradas.</span><span class="sxs-lookup"><span data-stu-id="64adb-163">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="64adb-164"><STRONG>(2)</STRONG> solo para flujos de trabajo que CsResponseGroupAdministrator ha asignado a la CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="64adb-164"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="64adb-165"><STRONG>(3)</STRONG> un administrador de grupo de respuesta puede asignar otro miembro de CsResponseGroupManager a un flujo de trabajo que el administrador actual ya administra.</span><span class="sxs-lookup"><span data-stu-id="64adb-165"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="64adb-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator solo puede ejecutar los cmdlets "Get" del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64adb-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="64adb-167">Requisitos previos de configuración de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="64adb-167">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="64adb-168">El grupo de respuesta requiere los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="64adb-168">Response Group requires the following components:</span></span>

  - <span data-ttu-id="64adb-169">Servicio de aplicación</span><span class="sxs-lookup"><span data-stu-id="64adb-169">Application service</span></span>

  - <span data-ttu-id="64adb-170">Aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="64adb-170">Response Group application</span></span>

  - <span data-ttu-id="64adb-171">Paquetes de idioma</span><span class="sxs-lookup"><span data-stu-id="64adb-171">Language packs</span></span>

  - <span data-ttu-id="64adb-172">Almacenamiento de archivos (para los archivos de audio)</span><span class="sxs-lookup"><span data-stu-id="64adb-172">File store (to hold audio files)</span></span>

  - <span data-ttu-id="64adb-173">Servicios web (incluye la herramienta de configuración de grupos de respuesta y la consola de inicio y cierre de sesión de los agentes)</span><span class="sxs-lookup"><span data-stu-id="64adb-173">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="64adb-174">Todos estos componentes se instalan de forma predeterminada al implementar Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="64adb-174">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="64adb-175">Es posible que deba realizar las siguientes tareas antes de configurar el grupo de respuesta:</span><span class="sxs-lookup"><span data-stu-id="64adb-175">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="64adb-176">Habilitar usuarios para Lync Server 2013 y Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="64adb-176">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="64adb-177">Modificar un archivo de configuración para que cumpla los Estándares federales de procesamiento de información (FIPS).</span><span class="sxs-lookup"><span data-stu-id="64adb-177">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="64adb-178">Modificar la intercalación de bases de datos para admitir caracteres Yi, Meng y Zang en los nombres de colas y los nombres de grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="64adb-178">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="64adb-179">Habilitar usuarios</span><span class="sxs-lookup"><span data-stu-id="64adb-179">Enabling Users</span></span>

<span data-ttu-id="64adb-180">El primer paso para configurar el grupo de respuesta es crear grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="64adb-180">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="64adb-181">Antes de poder crear un grupo de agentes, debe habilitar los usuarios que van a ser agentes para el grupo de respuesta para Lync Server 2013 y Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="64adb-181">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="64adb-182">La habilitación de usuarios para Lync Server 2013 suele ser un paso en la implementación del servidor Enterprise Edition o del servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="64adb-182">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="64adb-183">Para obtener más información sobre cómo habilitar usuarios para Lync Server 2013, vea [deshabilitar o volver a habilitar la cuenta de usuario para Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="64adb-183">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="64adb-184">Habilitar usuarios en Enterprise Voice suele ser un paso de la implementación de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="64adb-184">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="64adb-185">Para obtener más información, consulte [enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="64adb-185">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="64adb-186">Cumplimiento de los requisitos de FIPS</span><span class="sxs-lookup"><span data-stu-id="64adb-186">Complying with FIPS requirements</span></span>

<span data-ttu-id="64adb-187">Solo debe tener en cuenta esta sección si su organización necesita cumplir los Estándares federales de procesamiento de información (FIPS).</span><span class="sxs-lookup"><span data-stu-id="64adb-187">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="64adb-188">Para cumplir los FIPS, modifique el archivo Web.config del nivel de aplicación para usar otro algoritmo de criptografía diferente después de instalar los servicios web.</span><span class="sxs-lookup"><span data-stu-id="64adb-188">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="64adb-189">Especifique que ASP.NET usa el algoritmo Triple Data Encryption Standard (3DES) para procesar los datos de ver estado.</span><span class="sxs-lookup"><span data-stu-id="64adb-189">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="64adb-190">Para la aplicación de grupo de respuesta, este requisito se aplica a la herramienta de configuración del grupo de respuesta y a la consola de inicio y cierre de sesión del agente.</span><span class="sxs-lookup"><span data-stu-id="64adb-190">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="64adb-191">Para obtener más información acerca de este requisito, consulte el artículo 911722 de Microsoft Knowledge base, "puede recibir un mensaje de error cuando obtiene acceso a páginas web de ASP.NET que tienen habilitado ViewState después de la actualización de [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183)ASP.net 1,1 a ASP.net 2,0" en.</span><span class="sxs-lookup"><span data-stu-id="64adb-191">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="64adb-192">Para modificar el archivo Web.config:</span><span class="sxs-lookup"><span data-stu-id="64adb-192">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="64adb-193">En un editor de texto, como el Bloc de notas, abra el archivo Web.config del nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="64adb-193">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="64adb-194">En el archivo Web. config, busque la `<system.web>` sección.</span><span class="sxs-lookup"><span data-stu-id="64adb-194">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="64adb-195">Agregue la sección `<machineKey>` siguiente a en la `<system.web>` sección:</span><span class="sxs-lookup"><span data-stu-id="64adb-195">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="64adb-196">Guarde el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="64adb-196">Save the Web.config file.</span></span>

5.  <span data-ttu-id="64adb-197">Reinicie el servicio de Internet Information Services (IIS) ejecutando el siguiente comando en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="64adb-197">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="64adb-198">Compatibilidad con caracteres Yi, Meng y Zang</span><span class="sxs-lookup"><span data-stu-id="64adb-198">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="64adb-199">Solo debe tener en cuenta esta sección si su organización necesita admitir caracteres Yi, Meng o Zang.</span><span class="sxs-lookup"><span data-stu-id="64adb-199">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64adb-200">Para obtener información sobre los caracteres Yi, Meng y Zang y por qué son importantes para la implementación, consulte la información de los juegos <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>de caracteres GB18030.</span><span class="sxs-lookup"><span data-stu-id="64adb-200">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="64adb-p106">Para permitir la compatibilidad con caracteres Yi, Meng o Zang, debe modificar la intercalación de la base de datos de Rgsconfig. Cambie la intercalación de la columna **Nombre** en las siguientes tablas de cada base de datos de Rgsconfig:</span><span class="sxs-lookup"><span data-stu-id="64adb-p106">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database. Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="64adb-203">DBO. AgentGroups</span><span class="sxs-lookup"><span data-stu-id="64adb-203">dbo.AgentGroups</span></span>

  - <span data-ttu-id="64adb-204">DBO. BusinessHours</span><span class="sxs-lookup"><span data-stu-id="64adb-204">dbo.BusinessHours</span></span>

  - <span data-ttu-id="64adb-205">DBO. HolidaySets</span><span class="sxs-lookup"><span data-stu-id="64adb-205">dbo.HolidaySets</span></span>

  - <span data-ttu-id="64adb-206">DBO. Colas</span><span class="sxs-lookup"><span data-stu-id="64adb-206">dbo.Queues</span></span>

  - <span data-ttu-id="64adb-207">DBO. Flujos</span><span class="sxs-lookup"><span data-stu-id="64adb-207">dbo.Workflows</span></span>

<span data-ttu-id="64adb-208">Para SQL Server 2008 R2 y SQL Server 2012, use la intercalación de Latin\_general\_100 (sensible a la marca de acento).</span><span class="sxs-lookup"><span data-stu-id="64adb-208">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="64adb-209">Si usa esta intercalación, los nombres de objetos no distinguirán entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="64adb-209">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="64adb-210">Puede cambiar la intercalación usando Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="64adb-210">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="64adb-211">Para obtener más información acerca del uso de esta herramienta, consulte "uso de SQL [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184)Server Management Studio" en.</span><span class="sxs-lookup"><span data-stu-id="64adb-211">For details about using this tool, see "Using SQL Server Management Studio" at [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="64adb-212">Siga estos pasos para cambiar la intercalación:</span><span class="sxs-lookup"><span data-stu-id="64adb-212">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="64adb-213">Asegúrese de que SQL Server Management Studio está configurado para permitir los cambios que requieren que las tablas se vuelvan a crear.</span><span class="sxs-lookup"><span data-stu-id="64adb-213">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="64adb-214">Para obtener más información, vea "cuadro de diálogo Guardar (no permitido [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186))" en.</span><span class="sxs-lookup"><span data-stu-id="64adb-214">For details, see "Save (Not Permitted) Dialog Box" at [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="64adb-215">Para obtener información detallada sobre cómo establecer una intercalación de columna, vea "Cómo: establecer la intercalación de columnas [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185)(Visual Database Tools)" en.</span><span class="sxs-lookup"><span data-stu-id="64adb-215">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="64adb-216">Usando Microsoft SQL Server Management Studio, conéctese a la base de datos de Rgsconfig.</span><span class="sxs-lookup"><span data-stu-id="64adb-216">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="64adb-217">Busque la tabla que desee cambiar en la base de datos de Rgsconfig, haga clic con el botón secundario en la tabla y, a continuación, haga clic en **Diseñar**.</span><span class="sxs-lookup"><span data-stu-id="64adb-217">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="64adb-218">Cambie la intercalación de la columna **Nombre** y guarde la tabla.</span><span class="sxs-lookup"><span data-stu-id="64adb-218">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

