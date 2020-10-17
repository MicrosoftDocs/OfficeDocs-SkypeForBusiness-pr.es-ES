---
title: 'Lync Server 2013: permisos de administrador de pruebas'
description: 'Lync Server 2013: permisos de administrador de prueba.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e15be288ed31afe9303d91ce3e623d19822428
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568526"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="b98cf-103">Probar permisos de administrador en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b98cf-103">Test admin permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b98cf-104">_**Última modificación del tema:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="b98cf-104">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b98cf-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="b98cf-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b98cf-106">Después de la implementación inicial de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b98cf-106">After initial Lync Server deployment.</span></span> <span data-ttu-id="b98cf-107">Si es necesario, si surgen problemas relacionados con los permisos.</span><span class="sxs-lookup"><span data-stu-id="b98cf-107">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b98cf-108">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="b98cf-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b98cf-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b98cf-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b98cf-110">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="b98cf-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b98cf-111">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b98cf-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b98cf-112">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="b98cf-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="b98cf-113">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b98cf-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b98cf-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b98cf-114">Description</span></span>

<span data-ttu-id="b98cf-115">Al instalar Lync Server 2013 1 de las tareas realizadas por el programa de instalación, el grupo RTCUniversalUserAdmins los permisos de Active Directory necesarios para administrar usuarios, equipos, contactos, contactos de aplicaciones y personas InetOrg.</span><span class="sxs-lookup"><span data-stu-id="b98cf-115">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="b98cf-116">Si ha deshabilitado la herencia de permisos en el programa de instalación de Active Directory, no podrá asignar esos permisos.</span><span class="sxs-lookup"><span data-stu-id="b98cf-116">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="b98cf-117">Como resultado, los miembros del grupo RTCUniversalUserAdmins no podrán administrar entidades de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b98cf-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="b98cf-118">Estos privilegios de administración solo estarán disponibles para los administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="b98cf-118">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="b98cf-119">El cmdlet Test-CsOUPermission comprueba que los permisos necesarios para administrar usuarios, equipos y otros objetos se establecen en un contenedor de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b98cf-119">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="b98cf-120">Si estos permisos no están establecidos, puede resolver este problema mediante la ejecución del cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="b98cf-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="b98cf-121">Tenga en cuenta que Grant-CsOUPermission solo se pueden asignar permisos a miembros del grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="b98cf-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="b98cf-122">No puede usar este cmdlet para conceder permisos a un usuario o grupo arbitrario.</span><span class="sxs-lookup"><span data-stu-id="b98cf-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="b98cf-123">Si desea que un usuario o grupo diferente tenga permisos de administración de usuarios, debe agregar el usuario (o grupo) al grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="b98cf-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="b98cf-124">Para obtener más información sobre los permisos de OU, vea el artículo la [herencia de permisos está deshabilitada en los contenedores Computers, users o inetOrgPerson en Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span><span class="sxs-lookup"><span data-stu-id="b98cf-124">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b98cf-125">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="b98cf-125">Running the test</span></span>

<span data-ttu-id="b98cf-126">Para comprobar que los permisos de administración están establecidos en un contenedor, ejecute el cmdlet Test-CsOUPermission seguido del nombre distintivo del contenedor y del tipo de permisos que está comprobando.</span><span class="sxs-lookup"><span data-stu-id="b98cf-126">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="b98cf-127">Por ejemplo, este comando comprueba si los permisos de usuario están establecidos en ou ou = Redmond, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="b98cf-127">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="b98cf-128">Para comprobar varios permisos mediante un solo comando, encierre cada tipo de permiso entre comillas y, a continuación, separe los tipos con comas.</span><span class="sxs-lookup"><span data-stu-id="b98cf-128">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="b98cf-129">Por ejemplo, este único comando comprueba los permisos de usuario, equipo y contacto:</span><span class="sxs-lookup"><span data-stu-id="b98cf-129">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="b98cf-130">Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="b98cf-130">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b98cf-131">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="b98cf-131">Determining success or failure</span></span>

<span data-ttu-id="b98cf-132">Si ya se han establecido los permisos necesarios, Test-CsOUPermission devolverá una respuesta de una palabra:</span><span class="sxs-lookup"><span data-stu-id="b98cf-132">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="b98cf-133">Verdadero</span><span class="sxs-lookup"><span data-stu-id="b98cf-133">True</span></span>

<span data-ttu-id="b98cf-134">Si no se establecen los permisos necesarios, Test-CsOUPermission devolverá el valor false.</span><span class="sxs-lookup"><span data-stu-id="b98cf-134">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="b98cf-135">Es posible que deba buscar un momento para encontrar este valor.</span><span class="sxs-lookup"><span data-stu-id="b98cf-135">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="b98cf-136">Por lo general, se incrustará en varias advertencias que lo acompañan.</span><span class="sxs-lookup"><span data-stu-id="b98cf-136">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="b98cf-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b98cf-137">For example:</span></span>

<span data-ttu-id="b98cf-138">ADVERTENCIA: entrada de control de acceso (ACE) ATL-CS-001 \\ RTCUniversalUserReadOnlyGroup; permitir; ReadProperty ContainerInherit; Descendientes bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="b98cf-138">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="b98cf-139">ADVERTENCIA: las entradas de control de acceso (ACE) del objeto "OU = Norteamérica, DC = ATL-CS-001 \\ DC = litwareinc, DC = com" no están preparadas.</span><span class="sxs-lookup"><span data-stu-id="b98cf-139">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="b98cf-140">False</span><span class="sxs-lookup"><span data-stu-id="b98cf-140">False</span></span>

<span data-ttu-id="b98cf-141">ADVERTENCIA: el procesamiento de "test-CsOUPermission" se completó con advertencias.</span><span class="sxs-lookup"><span data-stu-id="b98cf-141">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="b98cf-142">se han registrado advertencias de "2" durante esta ejecución.</span><span class="sxs-lookup"><span data-stu-id="b98cf-142">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="b98cf-143">ADVERTENCIA: los resultados detallados se pueden encontrar en "C: \\ users \\ admin \\ AppData \\ local \\ temp \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="b98cf-143">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b98cf-144">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="b98cf-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="b98cf-145">Si Test-CsOUPermission falla, normalmente significa que no se ha asignado el permiso especificado al grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="b98cf-145">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="b98cf-146">Puede resolver este problema y asignar los permisos necesarios mediante el cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="b98cf-146">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="b98cf-147">Por ejemplo, este comando proporciona permisos de unidad organizativa para usuarios, contactos y inetOrgPersons al grupo RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="b98cf-147">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="b98cf-148">Para obtener más información, consulte el tema de ayuda para el cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="b98cf-148">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

