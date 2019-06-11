---
title: 'Lync Server 2013: cuentas de usuario habilitadas para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7a8935e83b79cfac1c4d3283fe0011a72aa3ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="15536-102">Cuentas de usuario habilitadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15536-102">User accounts enabled for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15536-103">_**Última modificación del tema:** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="15536-103">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="15536-104">Los temas de esta sección proporcionan procedimientos paso a paso para configurar las opciones de usuario que puede realizar con el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15536-104">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="15536-105">No puede usar el panel de control de Lync Server para administrar los usuarios que son miembros del grupo administradores de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="15536-105">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="15536-106">Para los usuarios de administradores de dominio, puede usar el panel de control de Lync Server solo para realizar operaciones de búsqueda de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="15536-106">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="15536-107">Para realizar operaciones de escritura en los usuarios de administradores de dominio (por ejemplo, habilitar o deshabilitar el panel de control de Lync Server, cambiar las asignaciones de directivas, la configuración de telefonía, la dirección SIP), debe usar los cmdlets de Windows PowerShell al iniciar sesión como un usuario administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="15536-107">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="15536-108">Para obtener más información sobre cómo usar los cmdlets de Windows PowerShell para administrar usuarios, consulte <A href="lync-server-2013-lync-server-management-shell.md">consola de administración de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="15536-108">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="15536-109">Al realizar cualquier tarea administrativa de Lync Server 2013 que implique buscar un usuario o filtrar los resultados de la búsqueda de usuarios, hay algunas propiedades de usuario que existen como atributos en los servicios de dominio de Active Directory, pero que no se replican en el catálogo global hasta que se implemente Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="15536-109">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="15536-110">Microsoft Exchange, no Lync Server, marca los siguientes atributos para la replicación en el catálogo global cuando está instalado:</span><span class="sxs-lookup"><span data-stu-id="15536-110">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15536-111">Información de usuario</span><span class="sxs-lookup"><span data-stu-id="15536-111">User Information</span></span></th>
<th><span data-ttu-id="15536-112">Dirección y teléfono</span><span class="sxs-lookup"><span data-stu-id="15536-112">Address and Phone</span></span></th>
<th><span data-ttu-id="15536-113">Organización</span><span class="sxs-lookup"><span data-stu-id="15536-113">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15536-114">Iniciales</span><span class="sxs-lookup"><span data-stu-id="15536-114">Initials</span></span></p></td>
<td><p><span data-ttu-id="15536-115">Dirección</span><span class="sxs-lookup"><span data-stu-id="15536-115">Street address</span></span></p>
<p><span data-ttu-id="15536-116">País o región</span><span class="sxs-lookup"><span data-stu-id="15536-116">Country/region</span></span></p>
<p><span data-ttu-id="15536-117">Localizador</span><span class="sxs-lookup"><span data-stu-id="15536-117">Pager</span></span></p>
<p><span data-ttu-id="15536-118">Fax</span><span class="sxs-lookup"><span data-stu-id="15536-118">Fax</span></span></p>
<p><span data-ttu-id="15536-119">Móvil</span><span class="sxs-lookup"><span data-stu-id="15536-119">Mobile</span></span></p></td>
<td><p><span data-ttu-id="15536-120">Título</span><span class="sxs-lookup"><span data-stu-id="15536-120">Title</span></span></p>
<p><span data-ttu-id="15536-121">Compañía</span><span class="sxs-lookup"><span data-stu-id="15536-121">Company</span></span></p>
<p><span data-ttu-id="15536-122">Grandes</span><span class="sxs-lookup"><span data-stu-id="15536-122">Department</span></span></p>
<p><span data-ttu-id="15536-123">Office</span><span class="sxs-lookup"><span data-stu-id="15536-123">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="15536-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="15536-124">In This Section</span></span>

  - [<span data-ttu-id="15536-125">Ver información sobre las cuentas de usuario habilitadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15536-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="15536-126">Habilitar y deshabilitar usuarios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15536-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="15536-127">Administración de telefonía IP empresarial para usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15536-127">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="15536-128">Modificar las propiedades de la cuenta de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15536-128">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="15536-129">Administrar la directiva de acceso de la organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15536-129">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="15536-130">Asignación de directivas por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15536-130">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15536-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="15536-131">See Also</span></span>


[<span data-ttu-id="15536-132">Cmdlets de administración de usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15536-132">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="15536-133">Administración de usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15536-133">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

