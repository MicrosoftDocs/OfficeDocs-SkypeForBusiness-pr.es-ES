---
title: 'Lync Server 2013: Planeación del control de acceso basado en roles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65f6411023c80a527cff31c389a8283d090dfc0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528037"
---
# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="b9c05-102">Planeación del control de acceso basado en roles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9c05-102">Planning for role-based access control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9c05-103">_**Última modificación del tema:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="b9c05-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="b9c05-104">Para permitirle delegar tareas administrativas a la vez que se mantienen los altos estándares de seguridad, Lync Server 2013 ofrece control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="b9c05-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="b9c05-105">Con el RBAC, los privilegios administrativos se conceden asignando a los usuarios roles administrativos.</span><span class="sxs-lookup"><span data-stu-id="b9c05-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="b9c05-106">Lync Server 2013 incluye un amplio conjunto de funciones administrativas integradas y también permite crear nuevos roles y especificar una lista personalizada de cmdlets para cada nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="b9c05-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="b9c05-107">También puede añadir scripts de cmdlets a las tareas permitidas tanto de los roles RBAC predefinidos como personalizados.</span><span class="sxs-lookup"><span data-stu-id="b9c05-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="b9c05-108">Mejor seguridad y centralización de los servidores</span><span class="sxs-lookup"><span data-stu-id="b9c05-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="b9c05-109">Con RBAC, el acceso y la autorización se basan con precisión en el rol de servidor Lync de un usuario.</span><span class="sxs-lookup"><span data-stu-id="b9c05-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="b9c05-110">Esto permite un mayor uso de la práctica de seguridad de "privilegios mínimos", que únicamente concede a los administradores y usuarios los derechos que son necesarios para su trabajo.</span><span class="sxs-lookup"><span data-stu-id="b9c05-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b9c05-111">Las restricciones RBAC solo funcionan en los administradores que trabajan de forma remota, mediante el panel de control de Lync Server o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9c05-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="b9c05-112">Un usuario que se encuentra sentado en un servidor que ejecuta Lync Server no está restringido por RBAC.</span><span class="sxs-lookup"><span data-stu-id="b9c05-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="b9c05-113">Por lo tanto, es importante que la seguridad física de Lync Server Conserve las restricciones RBAC.</span><span class="sxs-lookup"><span data-stu-id="b9c05-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="b9c05-114">Roles y ámbito</span><span class="sxs-lookup"><span data-stu-id="b9c05-114">Roles and Scope</span></span>

<span data-ttu-id="b9c05-p104">En el RBAC, un *rol* permite utilizar una lista de cmdlets y está diseñado para que sea de utilidad para un determinado tipo de administrador o técnico. Un *ámbito* es el conjunto de objetos en el que pueden actuar los cmdlets definidos en un rol. Los objetos a los que afecta el ámbito pueden ser cuentas de usuario (agrupadas por unidad organizativa) o servidores (agrupados por sitio).</span><span class="sxs-lookup"><span data-stu-id="b9c05-p104">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician. A *scope* is the set of objects which the cmdlets defined in a role can operate on. The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="b9c05-118">En la siguiente tabla se enumeran los roles predefinidos en Lync Server y se proporciona una descripción general de los tipos de tareas que puede realizar cada uno.</span><span class="sxs-lookup"><span data-stu-id="b9c05-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="b9c05-119">En la cuarta columna se muestra el rol de servidor de Microsoft Exchange similar para cada rol de Lync Server, si hay alguno.</span><span class="sxs-lookup"><span data-stu-id="b9c05-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="b9c05-120">Roles administrativos predefinidos</span><span class="sxs-lookup"><span data-stu-id="b9c05-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9c05-121">Role</span><span class="sxs-lookup"><span data-stu-id="b9c05-121">Role</span></span></th>
<th><span data-ttu-id="b9c05-122">Tareas permitidas</span><span class="sxs-lookup"><span data-stu-id="b9c05-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="b9c05-123">Grupo subyacente de Active Directory</span><span class="sxs-lookup"><span data-stu-id="b9c05-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="b9c05-124">Equivalente en Exchange</span><span class="sxs-lookup"><span data-stu-id="b9c05-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9c05-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-p106">Puede realizar todas las tareas administrativas y modificar todas las configuraciones, como crear roles y asignar usuarios a roles. Puede ampliar una implementación agregando nuevos sitios, grupos de servidores y servicios.</span><span class="sxs-lookup"><span data-stu-id="b9c05-p106">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles. Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="b9c05-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-129">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="b9c05-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9c05-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-131">Puede habilitar y deshabilitar usuarios para Lync Server, mover usuarios y asignar directivas existentes a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b9c05-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="b9c05-132">No puede modificar directivas.</span><span class="sxs-lookup"><span data-stu-id="b9c05-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="b9c05-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-134">Destinatarios de correo</span><span class="sxs-lookup"><span data-stu-id="b9c05-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9c05-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-136">Puede crear, definir y administrar las configuraciones y las directivas relacionadas con la voz.</span><span class="sxs-lookup"><span data-stu-id="b9c05-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="b9c05-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-138">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="b9c05-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9c05-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-p108">Puede administrar, supervisar y solucionar problemas de servidores y servicios. Puede impedir nuevas conexiones con servidores, detener e iniciar servicios y aplicar actualizaciones de software. No puede efectuar cambios que afecten a la configuración global.</span><span class="sxs-lookup"><span data-stu-id="b9c05-p108">Can manage, monitor, and troubleshoot servers and services. Can prevent new connections to servers, stop and start services, and apply software updates. Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="b9c05-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-144">Administración de servidores</span><span class="sxs-lookup"><span data-stu-id="b9c05-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9c05-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-146">Puede ver la implementación, incluida la información de usuarios y servidores, para supervisar el estado de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b9c05-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="b9c05-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-148">Administración de la organización con derecho a solo ver</span><span class="sxs-lookup"><span data-stu-id="b9c05-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9c05-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="b9c05-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="b9c05-p109">Puede ver la implementación, incluidas las propiedades y directivas de usuario. Puede ejecutar determinadas tareas de solución de problemas. No puede cambiar propiedades ni directivas de usuario, configuración de servidores ni servicios.</span><span class="sxs-lookup"><span data-stu-id="b9c05-p109">Can view the deployment, including user's properties and policies. Can run specific troubleshooting tasks. Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="b9c05-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="b9c05-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="b9c05-154">Escritorio</span><span class="sxs-lookup"><span data-stu-id="b9c05-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9c05-155">Rol csarchivingadministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-156">Puede modificar la configuración y las directivas de archivado.</span><span class="sxs-lookup"><span data-stu-id="b9c05-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="b9c05-157">Rol csarchivingadministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-158">Administración de retención, Retención legal</span><span class="sxs-lookup"><span data-stu-id="b9c05-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9c05-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-160">Puede administrar la configuración de la aplicación Grupo de respuesta en un sitio.</span><span class="sxs-lookup"><span data-stu-id="b9c05-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="b9c05-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-162">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b9c05-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9c05-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-p110">Nivel mínimo de derechos para administración de 9-1-1 mejorado (E9-1-1), que incluye crear ubicaciones e identificadores de red de E9-1-1 y asociarlos entre sí. Este rol se asigna siempre con un ámbito global.</span><span class="sxs-lookup"><span data-stu-id="b9c05-p110">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other. This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="b9c05-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-167">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b9c05-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9c05-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="b9c05-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="b9c05-169">Puede administrar las grupos de respuesta específicos.</span><span class="sxs-lookup"><span data-stu-id="b9c05-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="b9c05-170">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="b9c05-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="b9c05-171">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b9c05-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9c05-172">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-173">Puede administrar la característica de chat persistente y las salas de chat persistente específicas.</span><span class="sxs-lookup"><span data-stu-id="b9c05-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="b9c05-174">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="b9c05-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b9c05-175">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b9c05-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b9c05-176">Todos los roles predefinidos que se incluyen en Lync Server tienen un ámbito global.</span><span class="sxs-lookup"><span data-stu-id="b9c05-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="b9c05-177">Para seguir las prácticas de privilegios mínimos, no se deben asignar usuarios a roles de ámbito global si solo van a administrar un conjunto limitado de servidores o usuarios.</span><span class="sxs-lookup"><span data-stu-id="b9c05-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="b9c05-178">Para ello, puede crear roles basados en un rol existente pero con un ámbito más limitado.</span><span class="sxs-lookup"><span data-stu-id="b9c05-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="b9c05-179">Creación de un rol con un ámbito</span><span class="sxs-lookup"><span data-stu-id="b9c05-179">Creating a Scoped Role</span></span>

<span data-ttu-id="b9c05-180">Cuando crea un rol con un ámbito limitado (un rol con ámbito), puede especificar el ámbito junto con el rol existente con el que se basa y el grupo de Active Directory al que se le asignará el rol.</span><span class="sxs-lookup"><span data-stu-id="b9c05-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="b9c05-181">El grupo de Active Directory que se especifique debe haberse creado ya.</span><span class="sxs-lookup"><span data-stu-id="b9c05-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="b9c05-182">El siguiente cmdlet es un ejemplo de una creación de un rol que tiene los privilegios de uno de los roles administrativos predefinidos, pero con un ámbito limitado.</span><span class="sxs-lookup"><span data-stu-id="b9c05-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="b9c05-183">Crea un nuevo rol denominado `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="b9c05-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="b9c05-184">El rol tiene la capacidad de un rol CsServerAdministrator predefinido, pero solo para los servidores ubicados en el sitio Site01.</span><span class="sxs-lookup"><span data-stu-id="b9c05-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="b9c05-185">Para que este cmdlet funcione, el sitio de Site01 debe estar ya definido y el grupo de seguridad universal `Site01 Server Administrators` debe existir previamente.</span><span class="sxs-lookup"><span data-stu-id="b9c05-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="b9c05-186">Después de ejecutar este cmdlet, todos los usuarios que sean miembros del `Site01 Server Administrators` grupo tendrán privilegios de administrador de servidor para los servidores de Site01.</span><span class="sxs-lookup"><span data-stu-id="b9c05-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="b9c05-187">Además, los usuarios que se agreguen posteriormente a este grupo de seguridad universal también obtendrán los privilegios de esta función.</span><span class="sxs-lookup"><span data-stu-id="b9c05-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="b9c05-188">Tenga en cuenta que se llama al propio rol y al grupo de seguridad universal al que está asignado `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="b9c05-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="b9c05-189">En el siguiente ejemplo se limita el ámbito de usuario en lugar del ámbito de servidor.</span><span class="sxs-lookup"><span data-stu-id="b9c05-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="b9c05-190">Crea una `Sales Users Administrator` función para administrar las cuentas de usuario en la unidad organizativa ventas.</span><span class="sxs-lookup"><span data-stu-id="b9c05-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="b9c05-191">El grupo de seguridad universal de SalesUsersAdministrator ya debe estar creado para que funcione este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b9c05-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="b9c05-192">Creación de un nuevo rol</span><span class="sxs-lookup"><span data-stu-id="b9c05-192">Creating a New Role</span></span>

<span data-ttu-id="b9c05-p115">Para crear un rol que tenga acceso a un conjunto de cmdlets no incluido en uno de los roles predefinidos, o a un conjunto de scripts o módulos, debe empezar de nuevo utilizando uno de los roles predefinidos como plantilla. Tenga en cuenta que los scripts y los módulos que pueden ejecutar estos roles se deben almacenar en las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b9c05-p115">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template. Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="b9c05-195">La ruta del módulo de Lync, que de forma predeterminada es C: \\ archivos de programa archivos \\ comunes \\ Microsoft Lync Server 2013 \\ módulos \\ Lync</span><span class="sxs-lookup"><span data-stu-id="b9c05-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="b9c05-196">La ruta de acceso del script de usuario, que es de forma predeterminada C: \\ archivos de programa archivos \\ comunes \\ Microsoft Lync Server 2013 \\ AdminScripts</span><span class="sxs-lookup"><span data-stu-id="b9c05-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="b9c05-197">Para crear un nuevo rol, debe utilizar el cmdlet **New-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="b9c05-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="b9c05-198">Antes **de ejecutar New-CsAdminRole**, debe crear primero el grupo de seguridad universal subyacente que se asociará a este rol.</span><span class="sxs-lookup"><span data-stu-id="b9c05-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="b9c05-199">Los siguientes cmdlets constituyen un ejemplo de la creación de un nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="b9c05-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="b9c05-200">Crean un nuevo tipo de rol denominado `MyHelpDeskScriptRole` .</span><span class="sxs-lookup"><span data-stu-id="b9c05-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="b9c05-201">El nuevo rol tiene la capacidad del rol CsHelpDesk predefinido, y se puede ejecutar adicionalmente las funciones en un script denominado “testscript”.</span><span class="sxs-lookup"><span data-stu-id="b9c05-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="b9c05-202">Para que este cmdlet funcione, primero debe haber creado el grupo de seguridad universal MyHelpDeskScriptRole.</span><span class="sxs-lookup"><span data-stu-id="b9c05-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="b9c05-203">Después de ejecutar este cmdlet, puede asignar usuarios directamente a este rol (en ese caso tendrán un ámbito global), o crear un rol con ámbito basado en este rol, tal como se explica en el apartado Creación de un rol con ámbito, anteriormente en este documento.</span><span class="sxs-lookup"><span data-stu-id="b9c05-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="b9c05-204">Asignar roles a usuarios</span><span class="sxs-lookup"><span data-stu-id="b9c05-204">Assigning Roles to Users</span></span>

<span data-ttu-id="b9c05-205">Cada rol de Lync Server está asociado a un grupo de seguridad universal de Active Directory subyacente.</span><span class="sxs-lookup"><span data-stu-id="b9c05-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="b9c05-206">Los usuarios que se agreguen al grupo subyacente obtendrán las capacidades del rol.</span><span class="sxs-lookup"><span data-stu-id="b9c05-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="b9c05-207">En los ejemplos de las secciones anteriores se creó un nuevo rol y se asignó un grupo de seguridad universal existente a la nueva función.</span><span class="sxs-lookup"><span data-stu-id="b9c05-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="b9c05-208">Para asignar un rol existente a uno o más usuarios, agregue los usuarios al grupo asociado al rol.</span><span class="sxs-lookup"><span data-stu-id="b9c05-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="b9c05-209">Puede Agregar usuarios individuales y grupos de seguridad universal a estos grupos.</span><span class="sxs-lookup"><span data-stu-id="b9c05-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="b9c05-210">Por ejemplo, el rol **CsAdministrator** se concede automáticamente al grupo de seguridad universal **administradores de CS** en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9c05-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="b9c05-211">Este grupo de seguridad universal se crea en Active Directory al implementar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9c05-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="b9c05-212">Para conceder este privilegio a un usuario o grupo, basta con agregarlos al grupo **Administradores CS**.</span><span class="sxs-lookup"><span data-stu-id="b9c05-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="b9c05-213">A un usuario se le pueden asignar varios roles RBAC siempre que se agregue a los grupos subyacentes de Active Directory correspondientes a cada rol.</span><span class="sxs-lookup"><span data-stu-id="b9c05-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="b9c05-214">Tenga en cuenta que cuando se crea un rol, los usuarios que se agreguen más adelante al grupo subyacente de Active Directory obtendrán las capacidades de dicho rol.</span><span class="sxs-lookup"><span data-stu-id="b9c05-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="b9c05-215">Modificación de las capacidades de un rol</span><span class="sxs-lookup"><span data-stu-id="b9c05-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="b9c05-p121">Puede modificar la lista de cmdlets y scripts que un rol puede ejecutar. Puede modificar tanto los cmdlets como los scripts que pueden ejecutar los roles personalizados, pero solo puede modificar los scripts de roles predefinidos. En cada cmdlet que escriba, puede agregar, quitar o cambiar cmdlets o scripts.</span><span class="sxs-lookup"><span data-stu-id="b9c05-p121">You can modify the list of cmdlets and scripts that a role can run. You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles. Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="b9c05-219">Para modificar un rol, utilice el cmdlet **Set-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="b9c05-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="b9c05-220">El siguiente cmdlet quita un script del rol.</span><span class="sxs-lookup"><span data-stu-id="b9c05-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="b9c05-221">Planeación del RBAC</span><span class="sxs-lookup"><span data-stu-id="b9c05-221">Planning for RBAC</span></span>

<span data-ttu-id="b9c05-222">Para cada persona a la que se va a conceder cualquier tipo de derechos administrativos para la implementación de Lync Server, tenga en cuenta exactamente qué tareas deben realizar y, a continuación, asígnelas a funciones con el menor privilegio y el ámbito necesario para su trabajo.</span><span class="sxs-lookup"><span data-stu-id="b9c05-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="b9c05-223">Si es necesario, puede utilizar el cmdlet **Set-CsAdminRole** para crear un nuevo rol con solo los cmdlets necesarios para las tareas de esa persona.</span><span class="sxs-lookup"><span data-stu-id="b9c05-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="b9c05-p124">Los usuarios que dispongan del rol CsAdministrator pueden crear todo tipo de roles, incluidos los roles que se basan en CsAdministrator, y asignarles usuarios. Se recomienda asignar el rol CsAdministrator a un conjunto muy pequeño de usuarios de confianza.</span><span class="sxs-lookup"><span data-stu-id="b9c05-p124">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them. The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

