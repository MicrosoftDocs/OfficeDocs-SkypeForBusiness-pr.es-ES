---
title: 'Lync Server 2013: cuentas de usuario habilitadas para Lync Server'
description: 'Lync Server 2013: cuentas de usuario habilitadas para Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf87177c378ffe61715d5332d2fd23b1d8e6fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569876"
---
# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="6be94-103">Cuentas de usuario habilitadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6be94-103">User accounts enabled for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6be94-104">_**Última modificación del tema:** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="6be94-104">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="6be94-105">Los temas de esta sección proporcionan procedimientos paso a paso para configurar las opciones de usuario que puede realizar mediante el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6be94-105">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6be94-106">No puede usar el panel de control de Lync Server para administrar los usuarios que son miembros del grupo administradores de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6be94-106">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="6be94-107">Para los usuarios de administradores de dominio, puede usar el panel de control de Lync Server solo para realizar operaciones de búsqueda de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="6be94-107">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="6be94-108">Para realizar operaciones de escritura en los usuarios de administradores de dominio (por ejemplo, habilitar o deshabilitar para el panel de control de Lync Server, cambiar el grupo o las asignaciones de directivas, la configuración de telefonía, la dirección SIP), debe usar los cmdlets de Windows PowerShell al iniciar sesión como un usuario de administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="6be94-108">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="6be94-109">Para obtener información detallada sobre cómo usar los cmdlets de Windows PowerShell para administrar usuarios, consulte <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span><span class="sxs-lookup"><span data-stu-id="6be94-109">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="6be94-110">Cuando se realiza cualquier tarea administrativa de Lync Server 2013 que implique buscar un usuario o filtrar los resultados de la búsqueda de usuarios, hay algunas propiedades de usuario que existen como atributos en los servicios de dominio de Active Directory, pero no se replican en el catálogo global hasta que se implementa Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="6be94-110">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="6be94-111">Microsoft Exchange, no Lync Server, marca los siguientes atributos para la replicación en el catálogo global cuando se instala:</span><span class="sxs-lookup"><span data-stu-id="6be94-111">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6be94-112">Información del usuario</span><span class="sxs-lookup"><span data-stu-id="6be94-112">User Information</span></span></th>
<th><span data-ttu-id="6be94-113">Dirección y teléfono</span><span class="sxs-lookup"><span data-stu-id="6be94-113">Address and Phone</span></span></th>
<th><span data-ttu-id="6be94-114">Organización</span><span class="sxs-lookup"><span data-stu-id="6be94-114">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6be94-115">Initials</span><span class="sxs-lookup"><span data-stu-id="6be94-115">Initials</span></span></p></td>
<td><p><span data-ttu-id="6be94-116">Dirección</span><span class="sxs-lookup"><span data-stu-id="6be94-116">Street address</span></span></p>
<p><span data-ttu-id="6be94-117">País o región</span><span class="sxs-lookup"><span data-stu-id="6be94-117">Country/region</span></span></p>
<p><span data-ttu-id="6be94-118">Pager</span><span class="sxs-lookup"><span data-stu-id="6be94-118">Pager</span></span></p>
<p><span data-ttu-id="6be94-119">Fax</span><span class="sxs-lookup"><span data-stu-id="6be94-119">Fax</span></span></p>
<p><span data-ttu-id="6be94-120">Móvil</span><span class="sxs-lookup"><span data-stu-id="6be94-120">Mobile</span></span></p></td>
<td><p><span data-ttu-id="6be94-121">El título</span><span class="sxs-lookup"><span data-stu-id="6be94-121">Title</span></span></p>
<p><span data-ttu-id="6be94-122">Company</span><span class="sxs-lookup"><span data-stu-id="6be94-122">Company</span></span></p>
<p><span data-ttu-id="6be94-123">Departamento</span><span class="sxs-lookup"><span data-stu-id="6be94-123">Department</span></span></p>
<p><span data-ttu-id="6be94-124">Oficina</span><span class="sxs-lookup"><span data-stu-id="6be94-124">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="6be94-125">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6be94-125">In This Section</span></span>

  - [<span data-ttu-id="6be94-126">Visualización de la información sobre las cuentas de usuario habilitadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6be94-126">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="6be94-127">Habilitación y deshabilitación de usuarios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6be94-127">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="6be94-128">Administración de la telefonía IP empresarial para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6be94-128">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="6be94-129">Modificación de las propiedades de la cuenta de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6be94-129">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="6be94-130">Administrar la Directiva de acceso externo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6be94-130">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="6be94-131">Asignación de directivas por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6be94-131">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6be94-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6be94-132">See Also</span></span>


[<span data-ttu-id="6be94-133">Cmdlets de administración de usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6be94-133">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="6be94-134">Administración de usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6be94-134">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

