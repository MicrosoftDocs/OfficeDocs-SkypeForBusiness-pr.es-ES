---
title: 'Lync Server 2013: la herencia de permisos está deshabilitada en los contenedores Computer, users o InetOrgPerson'
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
ms.openlocfilehash: 1340c76209667d705908f5012a8182eaf1c7c4cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="7c23f-102">La herencia de permisos está deshabilitada en los contenedores Computers, users o InetOrgPerson en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c23f-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c23f-103">_**Última modificación del tema:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="7c23f-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="7c23f-104">En los servicios de dominio de Active Directory bloqueados, los objetos de usuarios y equipos a menudo se colocan en unidades organizativas específicas con la herencia de permisos deshabilitada para ayudar a proteger la delegación administrativa y habilitar el uso de objetos de directiva de grupo (GPO). para aplicar directivas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7c23f-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="7c23f-105">La preparación del dominio y la activación del servidor establecen las entradas de control de acceso (ACE) que necesita Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c23f-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="7c23f-106">Cuando la herencia de permisos está deshabilitada, los grupos de seguridad de Lync Server no pueden heredar estas ACE.</span><span class="sxs-lookup"><span data-stu-id="7c23f-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="7c23f-107">Cuando estos permisos no se heredan, los grupos de seguridad de Lync Server no pueden obtener acceso a la configuración y se producen los dos problemas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7c23f-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="7c23f-108">Para administrar usuarios, InetOrgPersons y contactos, y para operar los servidores, los grupos de seguridad de Lync Server requieren ACE establecidos por el procedimiento de preparación del dominio en cada conjunto de propiedades de usuario, comunicaciones en tiempo real (RTC), búsqueda de usuarios RTC e información pública .</span><span class="sxs-lookup"><span data-stu-id="7c23f-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="7c23f-109">Cuando la herencia de permisos está deshabilitada, los grupos de seguridad no heredan estas entradas ACE y no pueden administrar los servidores o usuarios.</span><span class="sxs-lookup"><span data-stu-id="7c23f-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="7c23f-110">Para detectar servidores y grupos de servidores, los servidores que ejecutan Lync Server se basan en ACE que se establecen mediante la activación en objetos relacionados con el equipo, incluido el objeto de servidor y el contenedor de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7c23f-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="7c23f-111">Cuando la herencia de permisos está deshabilitada, los grupos de seguridad, servidores y grupos de servidores no heredan estas entradas ACE y no pueden aprovecharlas.</span><span class="sxs-lookup"><span data-stu-id="7c23f-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="7c23f-112">Para solucionar estos problemas, Lync Server proporciona el cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="7c23f-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="7c23f-113">Este cmdlet establece las entradas ACE de Lync Server necesarias directamente en un contenedor y unidades organizativas especificadas y en los objetos del contenedor o la unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="7c23f-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="7c23f-114">Definir permisos para los objetos User, InetOrgPerson y Contact después de ejecutar la preparación del dominio</span><span class="sxs-lookup"><span data-stu-id="7c23f-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="7c23f-115">En un entorno con Active Directory bloqueado donde la herencia de permisos está deshabilitada, la preparación del dominio no establece las entradas ACE necesarias en los contenedores o las unidades organizativas que incluyen los objetos User o InetOrgPerson del dominio.</span><span class="sxs-lookup"><span data-stu-id="7c23f-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="7c23f-116">En esta situación, debe ejecutar el cmdlet **Grant-CsOuPermission** en cada contenedor o unidad organizativa que tenga objetos User o InetOrgPerson para los que la herencia de permisos esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="7c23f-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="7c23f-117">Si tiene una topología de bosque central, debe realizar también este procedimiento en los contenedores o unidades organizativas que contengan objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="7c23f-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="7c23f-118">Para obtener más información sobre las topologías de bosques centrales, consulte [topologías admitidas de Active Directory en Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="7c23f-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="7c23f-119">El parámetro ObjectType especifica el tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="7c23f-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="7c23f-120">El parámetro OU especifica la unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="7c23f-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="7c23f-121">Este cmdlet agrega las entradas ACE necesarias directamente en los contenedores o unidades organizativas especificados y los objetos User o InetOrgPerson del contenedor.</span><span class="sxs-lookup"><span data-stu-id="7c23f-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="7c23f-122">Si la unidad organizativa en la que se ejecuta este comando tiene unidades organizativas secundarias con objetos user o InetOrgPerson, los permisos no se aplicarán a dichos permisos.</span><span class="sxs-lookup"><span data-stu-id="7c23f-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="7c23f-123">Tendrá que ejecutar el comando individualmente en cada unidad organizativa secundaria.</span><span class="sxs-lookup"><span data-stu-id="7c23f-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="7c23f-124">Este es un escenario común con las implementaciones de hospedaje de Lync, por ejemplo, OU primaria = inquilinos de OCS, DC = CONTOSO, DC = LOCAL y secundaria OU = Tenant1, OU = inquilinos de OCS, DC = CONTOSO, DC = LOCAL.</span><span class="sxs-lookup"><span data-stu-id="7c23f-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="7c23f-125">Necesita tener los derechos de usuario equivalentes a la pertenencia al grupo administradores de dominio para ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7c23f-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="7c23f-126">Si las ACE de los usuarios autenticados también se han quitado en el entorno bloqueado, debe conceder a esta cuenta las entradas ACE de acceso de lectura en los contenedores relevantes o en las unidades organizativas del dominio raíz del bosque, tal y como se describe en los [permisos de usuario autenticados, se quitan en Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o use una cuenta que sea miembro del grupo administradores de empresa</span><span class="sxs-lookup"><span data-stu-id="7c23f-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="7c23f-127">**Para establecer las entradas ACE necesarias para los objetos User, InetOrgPerson y Contact**</span><span class="sxs-lookup"><span data-stu-id="7c23f-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="7c23f-128">Inicie sesión en un equipo unido al dominio con una cuenta que sea miembro del grupo Admins. del dominio o que tenga derechos de usuario equivalentes.</span><span class="sxs-lookup"><span data-stu-id="7c23f-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="7c23f-129">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7c23f-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7c23f-130">Realizar</span><span class="sxs-lookup"><span data-stu-id="7c23f-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="7c23f-131">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="7c23f-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="7c23f-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7c23f-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="7c23f-133">En el archivo de registro, busque resultado de ejecución \*\* \<correcta\> \*\* al final de cada tarea para comprobar que se establecieron los permisos y, a continuación, cierre la ventana de registro.</span><span class="sxs-lookup"><span data-stu-id="7c23f-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="7c23f-134">También puede ejecutar el comando siguiente para determinar si se establecieron los permisos:</span><span class="sxs-lookup"><span data-stu-id="7c23f-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="7c23f-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7c23f-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="7c23f-136">Establecer permisos para objetos de equipo después de ejecutar la preparación del dominio</span><span class="sxs-lookup"><span data-stu-id="7c23f-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="7c23f-137">En un entorno con Active Directory bloqueado donde la herencia de permisos está deshabilitada, la preparación del dominio no establece las entradas ACE necesarias en los contenedores o unidades organizativas que incluyen los objetos de equipo dentro del dominio.</span><span class="sxs-lookup"><span data-stu-id="7c23f-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="7c23f-138">En esta situación, debe ejecutar el cmdlet **Grant-CsOuPermission** en cada uno de los contenedores o unidades organizativas que tienen equipos que ejecutan Lync Server y la herencia de permisos está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="7c23f-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="7c23f-139">El parámetro ObjectType especifica el tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="7c23f-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="7c23f-140">Este procedimiento agrega las entradas ACE necesarias directamente en los contenedores especificados.</span><span class="sxs-lookup"><span data-stu-id="7c23f-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="7c23f-141">Necesita tener los derechos de usuario equivalentes a la pertenencia al grupo administradores de dominio para ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7c23f-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="7c23f-142">Si también se han quitado las ACE de usuario autenticado, debe conceder a esta cuenta las entradas ACE de acceso de lectura en los contenedores relevantes del dominio raíz del bosque, tal y como se describe en [permisos de usuario autenticados, se quitan en Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o use una cuenta que sea miembro del grupo administradores de la empresa.</span><span class="sxs-lookup"><span data-stu-id="7c23f-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="7c23f-143">**Para establecer las entradas ACE necesarias para los objetos de equipo**</span><span class="sxs-lookup"><span data-stu-id="7c23f-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="7c23f-144">Inicie sesión en un equipo del dominio con una cuenta que sea miembro del grupo Admins. del dominio o que tenga derechos de usuario equivalentes.</span><span class="sxs-lookup"><span data-stu-id="7c23f-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="7c23f-145">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7c23f-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7c23f-146">Realizar</span><span class="sxs-lookup"><span data-stu-id="7c23f-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="7c23f-147">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="7c23f-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="7c23f-148">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7c23f-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="7c23f-149">En el archivo de registro de ejemplo\\C\\: registra OUPermissions. XML, busque el resultado de la ejecución \*\* \<correcta\> \*\* al final de cada tarea y compruebe que no haya errores y, a continuación, cierre el registro.</span><span class="sxs-lookup"><span data-stu-id="7c23f-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="7c23f-150">Para probar los permisos, puede ejecutar el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7c23f-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="7c23f-151">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7c23f-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7c23f-152">Si ejecuta la preparación del dominio en el dominio raíz del bosque en un entorno de Active Directory bloqueado, tenga en cuenta que Lync Server requiere acceso al esquema de Active Directory y a los contenedores de configuración.</span><span class="sxs-lookup"><span data-stu-id="7c23f-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="7c23f-153">Si se quita el permiso de usuario autenticado predeterminado del esquema o los contenedores de configuración en&nbsp;AD DS, solo se permite que los miembros del grupo de administradores de esquema (para el contenedor de esquemas) o del grupo de administradores de la empresa (para el contenedor de configuración) tengan acceso al contenedor especificado.</span><span class="sxs-lookup"><span data-stu-id="7c23f-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="7c23f-154">Debido a que Setup. exe, los cmdlets del shell de administración de Lync Server y el panel de control de Lync Server necesitan acceso a estos contenedores, se producirá un error en la instalación e instalación de las herramientas administrativas, a menos que el usuario que ejecuta la instalación tenga derechos de usuario equivalentes al esquema Administradores y pertenencia al grupo administradores de empresa.</span><span class="sxs-lookup"><span data-stu-id="7c23f-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="7c23f-155">Para solucionar esta situación, deberá conceder al grupo RTCUniversalGlobalWriteGroup acceso de lectura y escritura a los contenedores de esquema y de configuración.</span><span class="sxs-lookup"><span data-stu-id="7c23f-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

