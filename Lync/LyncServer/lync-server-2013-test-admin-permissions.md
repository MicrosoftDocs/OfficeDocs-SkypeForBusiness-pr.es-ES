---
title: 'Lync Server 2013: permisos de administrador de prueba'
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
ms.openlocfilehash: d4543501d668b61bbb90073c80c4e85373341d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="beb6e-102">Probar permisos de administrador en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="beb6e-102">Test admin permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beb6e-103">_**Última modificación del tema:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="beb6e-103">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beb6e-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="beb6e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="beb6e-105">Después de la implementación inicial de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="beb6e-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="beb6e-106">Según sea necesario, si surgen problemas relacionados con los permisos.</span><span class="sxs-lookup"><span data-stu-id="beb6e-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beb6e-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="beb6e-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="beb6e-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="beb6e-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beb6e-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="beb6e-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="beb6e-110">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="beb6e-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="beb6e-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="beb6e-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="beb6e-112">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="beb6e-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="beb6e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="beb6e-113">Description</span></span>

<span data-ttu-id="beb6e-114">Al instalar Lync Server 2013 1 de las tareas que realizó el programa de instalación, el grupo RTCUniversalUserAdmins los permisos de Active Directory que se necesitan para administrar usuarios, equipos, contactos, contactos de aplicaciones y personas de InetOrg.</span><span class="sxs-lookup"><span data-stu-id="beb6e-114">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="beb6e-115">Si ha deshabilitado la herencia de permisos en la instalación de Active Directory, no podrá asignar esos permisos.</span><span class="sxs-lookup"><span data-stu-id="beb6e-115">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="beb6e-116">Como resultado, los miembros del grupo RTCUniversalUserAdmins no podrán administrar entidades de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="beb6e-116">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="beb6e-117">Esos privilegios de administración solo estarán disponibles para los administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="beb6e-117">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="beb6e-118">El cmdlet test-CsOUPermission comprueba que los permisos necesarios para administrar usuarios, equipos y otros objetos se establecen en un contenedor de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="beb6e-118">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="beb6e-119">Si no se han establecido esos permisos, puede resolver este problema ejecutando el cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="beb6e-119">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="beb6e-120">Tenga en cuenta que Grant-CsOUPermission solo puede asignar permisos a miembros del grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="beb6e-120">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="beb6e-121">No puede usar este cmdlet para conceder permisos a un usuario o grupo arbitrario.</span><span class="sxs-lookup"><span data-stu-id="beb6e-121">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="beb6e-122">Si desea que un usuario o grupo diferente tenga permisos de administración de usuarios, debe agregar ese usuario (o grupo) al grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="beb6e-122">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="beb6e-123">Para obtener más información sobre los permisos de Uo, vea el artículo la [herencia de permisos está deshabilitada en los contenedores de equipos, usuarios o inetOrgPerson en Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span><span class="sxs-lookup"><span data-stu-id="beb6e-123">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="beb6e-124">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="beb6e-124">Running the test</span></span>

<span data-ttu-id="beb6e-125">Para comprobar que los permisos de administración se establecen en un contenedor, ejecute el cmdlet test-CsOUPermission seguido del nombre distintivo del contenedor y del tipo de permisos que está comprobando.</span><span class="sxs-lookup"><span data-stu-id="beb6e-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="beb6e-126">Por ejemplo, este comando comprueba si los permisos de usuario están establecidos en la ou ou = Redmond, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="beb6e-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="beb6e-127">Para comprobar varios permisos con un solo comando, encierra cada tipo de permiso entre comillas y luego separa esos tipos con comas.</span><span class="sxs-lookup"><span data-stu-id="beb6e-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="beb6e-128">Por ejemplo, este comando comprueba los permisos de usuario, equipo y contacto:</span><span class="sxs-lookup"><span data-stu-id="beb6e-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="beb6e-129">Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="beb6e-129">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="beb6e-130">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="beb6e-130">Determining success or failure</span></span>

<span data-ttu-id="beb6e-131">Si los permisos necesarios ya se han establecido, test-CsOUPermission devolverá una respuesta de una palabra:</span><span class="sxs-lookup"><span data-stu-id="beb6e-131">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="beb6e-132">Verdadero</span><span class="sxs-lookup"><span data-stu-id="beb6e-132">True</span></span>

<span data-ttu-id="beb6e-133">Si no se establecen los permisos necesarios, test-CsOUPermission devolverá el valor false.</span><span class="sxs-lookup"><span data-stu-id="beb6e-133">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="beb6e-134">Es posible que tenga que buscar un momento para encontrar este valor.</span><span class="sxs-lookup"><span data-stu-id="beb6e-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="beb6e-135">Normalmente, se incluirá en varias advertencias de acompañamiento.</span><span class="sxs-lookup"><span data-stu-id="beb6e-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="beb6e-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="beb6e-136">For example:</span></span>

<span data-ttu-id="beb6e-137">ADVERTENCIA: entrada de control de acceso (ACE) ATL-CS\\-001 RTCUniversalUserReadOnlyGroup; permitir ReadProperty; ContainerInherit; Descendientes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="beb6e-137">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="beb6e-138">ADVERTENCIA: las entradas de control de acceso (ACE) del objeto "OU = Norteamérica, DC = ATL-CS-\\001 DC = LITWAREINC, DC = com" no están listas.</span><span class="sxs-lookup"><span data-stu-id="beb6e-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="beb6e-139">Falso</span><span class="sxs-lookup"><span data-stu-id="beb6e-139">False</span></span>

<span data-ttu-id="beb6e-140">ADVERTENCIA: el procesamiento de "prueba-CsOUPermission" se completó con advertencias.</span><span class="sxs-lookup"><span data-stu-id="beb6e-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="beb6e-141">durante esta ejecución, se grabaron "2" advertencias.</span><span class="sxs-lookup"><span data-stu-id="beb6e-141">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="beb6e-142">ADVERTENCIA: los resultados detallados se encuentran en "\\C\\:\\users\\admin\\\\local Temp test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de. html".</span><span class="sxs-lookup"><span data-stu-id="beb6e-142">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="beb6e-143">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="beb6e-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="beb6e-144">Si prueba-CsOUPermission se produce un error que normalmente significa que el permiso especificado no se ha asignado al grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="beb6e-144">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="beb6e-145">Puede resolver este problema y asignar los permisos necesarios mediante el cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="beb6e-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="beb6e-146">Por ejemplo, este comando proporciona a los usuarios, los contactos y el inetOrgPersons permisos para el grupo RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="beb6e-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="beb6e-147">Para obtener más información, consulte el tema de ayuda para el cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="beb6e-147">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

