---
title: 'Lync Server 2013: la herencia de permisos está deshabilitada en los contenedores Computer, users o InetOrgPerson'
description: 'Lync Server 2013: la herencia de permisos está deshabilitada en los contenedores Computer, users o InetOrgPerson.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a619ccd00e328ccef2e3b9eef4d64b190bdbdfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545166"
---
# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="791db-103">La herencia de permisos está deshabilitada en los contenedores Computers, users o InetOrgPerson en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="791db-103">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="791db-104">_**Última modificación del tema:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="791db-104">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="791db-105">En los servicios de dominio de Active Directory bloqueados, los objetos de usuarios y equipos a menudo se colocan en unidades organizativas específicas con la herencia de permisos deshabilitada para ayudar a proteger la delegación administrativa y habilitar el uso de objetos de directiva de grupo (GPO) para aplicar directivas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="791db-105">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="791db-106">La preparación del dominio y la activación del servidor establecen las entradas de control de acceso (ACE) que necesita Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="791db-106">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="791db-107">Cuando la herencia de permisos está deshabilitada, los grupos de seguridad de Lync Server no pueden heredar estas ACE.</span><span class="sxs-lookup"><span data-stu-id="791db-107">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="791db-108">Cuando estos permisos no se heredan, los grupos de seguridad de Lync Server no pueden obtener acceso a la configuración y se producen los dos problemas siguientes:</span><span class="sxs-lookup"><span data-stu-id="791db-108">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="791db-109">Para administrar usuarios, InetOrgPersons y contactos, y para operar los servidores, los grupos de seguridad de Lync Server requieren ACE establecidos por el procedimiento de preparación del dominio en cada conjunto de propiedades de usuario, comunicaciones en tiempo real (RTC), búsqueda de usuarios RTC e información pública.</span><span class="sxs-lookup"><span data-stu-id="791db-109">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="791db-110">Cuando la herencia de permisos está deshabilitada, los grupos de seguridad no heredan estas entradas ACE y no pueden administrar los servidores o usuarios.</span><span class="sxs-lookup"><span data-stu-id="791db-110">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="791db-111">Para detectar servidores y grupos de servidores, los servidores que ejecutan Lync Server se basan en ACE que se establecen mediante la activación en objetos relacionados con el equipo, incluido el objeto de servidor y el contenedor de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="791db-111">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="791db-112">Cuando la herencia de permisos está deshabilitada, los grupos de seguridad, servidores y grupos de servidores no heredan estas entradas ACE y no pueden aprovecharlas.</span><span class="sxs-lookup"><span data-stu-id="791db-112">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="791db-113">Para solucionar estos problemas, Lync Server proporciona el cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="791db-113">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="791db-114">Este cmdlet establece las entradas ACE de Lync Server necesarias directamente en un contenedor y unidades organizativas especificadas y en los objetos del contenedor o la unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="791db-114">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="791db-115">Definir permisos para los objetos User, InetOrgPerson y Contact después de ejecutar la preparación del dominio</span><span class="sxs-lookup"><span data-stu-id="791db-115">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="791db-116">En un entorno con Active Directory bloqueado donde la herencia de permisos está deshabilitada, la preparación del dominio no establece las entradas ACE necesarias en los contenedores o las unidades organizativas que incluyen los objetos User o InetOrgPerson del dominio.</span><span class="sxs-lookup"><span data-stu-id="791db-116">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="791db-117">En esta situación, debe ejecutar el cmdlet **Grant-CsOuPermission** en cada contenedor o unidad organizativa que tenga objetos User o InetOrgPerson para los que la herencia de permisos esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="791db-117">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="791db-118">Si tiene una topología de bosque central, debe realizar también este procedimiento en los contenedores o unidades organizativas que contengan objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="791db-118">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="791db-119">Para obtener más información sobre las topologías de bosques centrales, consulte [topologías admitidas de Active Directory en Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="791db-119">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="791db-120">El parámetro ObjectType especifica el tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="791db-120">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="791db-121">El parámetro OU especifica la unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="791db-121">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="791db-122">Este cmdlet agrega las entradas ACE necesarias directamente en los contenedores o unidades organizativas especificados y los objetos User o InetOrgPerson del contenedor.</span><span class="sxs-lookup"><span data-stu-id="791db-122">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="791db-123">Si la unidad organizativa en la que se ejecuta este comando tiene unidades organizativas secundarias con objetos user o InetOrgPerson, los permisos no se aplicarán a dichos permisos.</span><span class="sxs-lookup"><span data-stu-id="791db-123">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="791db-124">Tendrá que ejecutar el comando individualmente en cada unidad organizativa secundaria.</span><span class="sxs-lookup"><span data-stu-id="791db-124">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="791db-125">Este es un escenario común con las implementaciones de hospedaje de Lync, por ejemplo, OU primaria = inquilinos de OCS, DC = CONTOSO, DC = LOCAL y secundaria OU = Tenant1, OU = inquilinos de OCS, DC = CONTOSO, DC = LOCAL.</span><span class="sxs-lookup"><span data-stu-id="791db-125">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="791db-126">Necesita tener los derechos de usuario equivalentes a la pertenencia al grupo administradores de dominio para ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="791db-126">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="791db-127">Si las ACE de los usuarios autenticados también se han quitado en el entorno bloqueado, debe conceder a esta cuenta las entradas ACE de acceso de lectura en los contenedores relevantes o en las unidades organizativas del dominio raíz del bosque, tal y como se describe en los [permisos de usuario autenticados, se quitan en Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o use una cuenta que sea miembro del grupo administradores de empresa</span><span class="sxs-lookup"><span data-stu-id="791db-127">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="791db-128">**Para establecer las entradas ACE necesarias para los objetos User, InetOrgPerson y Contact**</span><span class="sxs-lookup"><span data-stu-id="791db-128">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="791db-129">Inicie sesión en un equipo unido al dominio con una cuenta que sea miembro del grupo Admins. del dominio o que tenga derechos de usuario equivalentes.</span><span class="sxs-lookup"><span data-stu-id="791db-129">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="791db-130">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="791db-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="791db-131">Realizar</span><span class="sxs-lookup"><span data-stu-id="791db-131">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="791db-132">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="791db-132">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="791db-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="791db-133">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="791db-134">En el archivo de registro, busque **\<Success\>** resultado de ejecución al final de cada tarea para comprobar que se establecieron los permisos y, a continuación, cierre la ventana de registro.</span><span class="sxs-lookup"><span data-stu-id="791db-134">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="791db-135">También puede ejecutar el comando siguiente para determinar si se establecieron los permisos:</span><span class="sxs-lookup"><span data-stu-id="791db-135">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="791db-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="791db-136">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="791db-137">Establecer permisos para objetos de equipo después de ejecutar la preparación del dominio</span><span class="sxs-lookup"><span data-stu-id="791db-137">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="791db-138">En un entorno con Active Directory bloqueado donde la herencia de permisos está deshabilitada, la preparación del dominio no establece las entradas ACE necesarias en los contenedores o unidades organizativas que incluyen los objetos de equipo dentro del dominio.</span><span class="sxs-lookup"><span data-stu-id="791db-138">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="791db-139">En esta situación, debe ejecutar el cmdlet **Grant-CsOuPermission** en cada uno de los contenedores o unidades organizativas que tienen equipos que ejecutan Lync Server y la herencia de permisos está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="791db-139">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="791db-140">El parámetro ObjectType especifica el tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="791db-140">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="791db-141">Este procedimiento agrega las entradas ACE necesarias directamente en los contenedores especificados.</span><span class="sxs-lookup"><span data-stu-id="791db-141">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="791db-142">Necesita tener los derechos de usuario equivalentes a la pertenencia al grupo administradores de dominio para ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="791db-142">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="791db-143">Si también se han quitado las ACE de usuario autenticado, debe conceder a esta cuenta las entradas ACE de acceso de lectura en los contenedores relevantes del dominio raíz del bosque, tal y como se describe en [permisos de usuario autenticados, se quitan en Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o use una cuenta que sea miembro del grupo administradores de la empresa.</span><span class="sxs-lookup"><span data-stu-id="791db-143">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="791db-144">**Para establecer las entradas ACE necesarias para los objetos de equipo**</span><span class="sxs-lookup"><span data-stu-id="791db-144">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="791db-145">Inicie sesión en un equipo del dominio con una cuenta que sea miembro del grupo Admins. del dominio o que tenga derechos de usuario equivalentes.</span><span class="sxs-lookup"><span data-stu-id="791db-145">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="791db-146">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="791db-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="791db-147">Realizar</span><span class="sxs-lookup"><span data-stu-id="791db-147">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="791db-148">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="791db-148">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="791db-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="791db-149">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="791db-150">En el archivo de registro de ejemplo C: \\ registra \\OUPermissions.xml, debería buscar **\<Success\>** el resultado de la ejecución al final de cada tarea y comprobar que no hay errores y, a continuación, cierra el registro.</span><span class="sxs-lookup"><span data-stu-id="791db-150">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="791db-151">Para probar los permisos, puede ejecutar el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="791db-151">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="791db-152">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="791db-152">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="791db-153">Si ejecuta la preparación del dominio en el dominio raíz del bosque en un entorno de Active Directory bloqueado, tenga en cuenta que Lync Server requiere acceso al esquema de Active Directory y a los contenedores de configuración.</span><span class="sxs-lookup"><span data-stu-id="791db-153">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="791db-154">Si se quita el permiso de usuario autenticado predeterminado del esquema o los contenedores de configuración en AD &nbsp; DS, solo se permite que los miembros del grupo de administradores de esquema (para el contenedor de esquemas) o del grupo de administradores de la empresa (para el contenedor de configuración) tengan acceso al contenedor especificado.</span><span class="sxs-lookup"><span data-stu-id="791db-154">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="791db-155">Debido a que Setup.exe, los cmdlets del shell de administración de Lync Server y el panel de control de Lync Server necesitan acceso a estos contenedores, se producirá un error en la instalación y la instalación de las herramientas administrativas, a menos que el usuario que ejecuta la instalación tenga los mismos derechos que los administradores de esquema y la pertenencia al grupo de administradores de empresa.</span><span class="sxs-lookup"><span data-stu-id="791db-155">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="791db-156">Para solucionar esta situación, deberá conceder al grupo RTCUniversalGlobalWriteGroup acceso de lectura y escritura a los contenedores de esquema y de configuración.</span><span class="sxs-lookup"><span data-stu-id="791db-156">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

