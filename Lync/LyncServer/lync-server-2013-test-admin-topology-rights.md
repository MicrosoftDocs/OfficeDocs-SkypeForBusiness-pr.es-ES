---
title: 'Lync Server 2013: derechos de topología de administración de prueba'
description: 'Lync Server 2013: derechos de topología de administración de prueba.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d713297d0e944c7acbc5efcb11b21ea1b26639
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568566"
---
# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="19003-103">Probar los derechos de topología de administración en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19003-103">Test admin topology rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19003-104">_**Última modificación del tema:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="19003-104">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19003-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="19003-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="19003-106">Después de la implementación inicial de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19003-106">After initial Lync Server deployment.</span></span> <span data-ttu-id="19003-107">Si es necesario, si surgen problemas relacionados con los permisos.</span><span class="sxs-lookup"><span data-stu-id="19003-107">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19003-108">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="19003-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="19003-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="19003-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19003-110">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="19003-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="19003-111">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="19003-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="19003-112">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="19003-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="19003-113">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="19003-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="19003-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="19003-114">Description</span></span>

<span data-ttu-id="19003-115">De forma predeterminada, solo los administradores de dominio pueden habilitar una topología de Lync Server y realizar cambios importantes en la infraestructura de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19003-115">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="19003-116">Esto no será un problema siempre que los administradores de dominio y los administradores de Lync Server sean uno y el mismo. En muchas organizaciones, los administradores de Lync Server no mantienen derechos administrativos en todo el dominio.</span><span class="sxs-lookup"><span data-stu-id="19003-116">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="19003-117">De forma predeterminada, esto significa que estos administradores (definidos como miembros del grupo RTCUniversalServerAdmins) no pueden hacer cambios en la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19003-117">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="19003-118">Para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de realizar cambios en la topología, debe asignar los permisos necesarios de Active Directory mediante el cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="19003-118">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="19003-119">El cmdlet Test-CsSetupPermission comprueba que los permisos necesarios para instalar Lync Server o uno de sus componentes estén configurados en el contenedor de Active Directory especificado.</span><span class="sxs-lookup"><span data-stu-id="19003-119">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="19003-120">Si no se asignan los permisos, puede ejecutar el cmdlet Grant-CsSetupPermission para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de instalar y habilitar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19003-120">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19003-121">Para obtener una lista detallada de los permisos asignados por Grant-CsSetupPermission, consulte la entrada de blog <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission y Grant-CsOUPermission</A>.</span><span class="sxs-lookup"><span data-stu-id="19003-121">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="19003-122">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="19003-122">Running the test</span></span>

<span data-ttu-id="19003-123">Para determinar si se asignan permisos de configuración para un contenedor de Active Directory, llame al cmdlet Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="19003-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="19003-124">Especifique el nombre distintivo del contenedor que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="19003-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="19003-125">Por ejemplo, este comando comprueba los permisos de configuración en el contenedor ou = CsServers, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="19003-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="19003-126">Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="19003-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="19003-127">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="19003-127">Determining success or failure</span></span>

<span data-ttu-id="19003-128">Si Test-CsSetupPermission determina que ya se han establecido los permisos necesarios en un contenedor de Active Directory, el cmdlet devolverá el valor true:</span><span class="sxs-lookup"><span data-stu-id="19003-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="19003-129">Verdadero</span><span class="sxs-lookup"><span data-stu-id="19003-129">True</span></span>

<span data-ttu-id="19003-130">Si no se establecen los permisos, Test-CsSetupPermission devolverá el valor false.</span><span class="sxs-lookup"><span data-stu-id="19003-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="19003-131">Tenga en cuenta que este valor normalmente se incluirá en muchos mensajes de advertencia.</span><span class="sxs-lookup"><span data-stu-id="19003-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="19003-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="19003-132">For example:</span></span>

<span data-ttu-id="19003-133">ADVERTENCIA: entrada de control de acceso (ACE) ATL-CS-001 \\ RTCUniversalServerAdmins; Permita ExtendedRight; None None 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="19003-133">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="19003-134">ADVERTENCIA: las entradas de control de acceso (ACE) del objeto "CN = Computers, DC = litwareinc, DC = com" no están preparadas.</span><span class="sxs-lookup"><span data-stu-id="19003-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="19003-135">False</span><span class="sxs-lookup"><span data-stu-id="19003-135">False</span></span>

<span data-ttu-id="19003-136">ADVERTENCIA: el procesamiento de "test-CsSetupPermission" se completó con advertencias.</span><span class="sxs-lookup"><span data-stu-id="19003-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="19003-137">se han registrado advertencias de "2" durante esta ejecución.</span><span class="sxs-lookup"><span data-stu-id="19003-137">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="19003-138">ADVERTENCIA: los resultados detallados se pueden encontrar en "C: \\ users \\ admin \\ AppData \\ local \\ temp \\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span><span class="sxs-lookup"><span data-stu-id="19003-138">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="19003-139">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="19003-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="19003-140">Aunque existen raras excepciones, si se produce un error en Test-CsSetupPermission que normalmente significa que no se asignan permisos de configuración para el contenedor de Active Directory especificado.</span><span class="sxs-lookup"><span data-stu-id="19003-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="19003-141">Estos permisos se pueden asignar mediante el cmdlet Grant-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="19003-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="19003-142">Por ejemplo, este comando concede permisos de configuración al contenedor Computers del dominio litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="19003-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="19003-143">Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="19003-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

