---
title: Probar los permisos de administrador en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cómo probar los permisos de administrador en Skype Empresarial Server
ms.openlocfilehash: 27ae50cca0018985ad59dbc4487dd3630cb5cf87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800100"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="549b1-103">Probar los permisos de administrador en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="549b1-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="549b1-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="549b1-104">Verification schedule</span></span>|<span data-ttu-id="549b1-105">Después de la implementación inicial de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="549b1-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="549b1-106">Según sea necesario si surgen problemas relacionados con permisos.</span><span class="sxs-lookup"><span data-stu-id="549b1-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="549b1-107">Herramienta de pruebas</span><span class="sxs-lookup"><span data-stu-id="549b1-107">Testing tool</span></span>|<span data-ttu-id="549b1-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="549b1-108">Windows PowerShell</span></span>|
|<span data-ttu-id="549b1-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="549b1-109">Permissions required</span></span>|<span data-ttu-id="549b1-110">Cuando se ejecuta localmente con el Shell de administración de Skype Empresarial Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="549b1-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="549b1-111">Cuando se ejecuta mediante una instancia remota de Windows PowerShell, se debe asignar a los usuarios un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsOUPermission remoto.</span><span class="sxs-lookup"><span data-stu-id="549b1-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="549b1-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el Windows PowerShell siguiente:</span><span class="sxs-lookup"><span data-stu-id="549b1-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="549b1-113">Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="549b1-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="549b1-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="549b1-114">Description</span></span>

<span data-ttu-id="549b1-115">Al instalar Skype Empresarial Server, una de las tareas realizadas por el programa de instalación concede al grupo RTCUniversalUserAdmins los permisos de Active Directory necesarios para administrar usuarios, equipos, contactos, contactos de aplicaciones e personas inetOrg.</span><span class="sxs-lookup"><span data-stu-id="549b1-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="549b1-116">Si ha deshabilitado la herencia de permisos en Active Directory, el programa de instalación no podrá asignar esos permisos.</span><span class="sxs-lookup"><span data-stu-id="549b1-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="549b1-117">Como resultado, los miembros del grupo RTCUniversalUserAdmins no podrán administrar entidades de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="549b1-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="549b1-118">Estos privilegios de administración solo estarán disponibles para los administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="549b1-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="549b1-119">El Test-CsOUPermission cmdlet comprueba que los permisos necesarios para administrar usuarios, equipos y otros objetos están establecidos en un contenedor de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="549b1-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="549b1-120">Si no se establecen estos permisos, puede resolver este problema ejecutando el [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission).</span><span class="sxs-lookup"><span data-stu-id="549b1-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="549b1-121">Tenga en Grant-CsOUPermission solo puede asignar permisos a los miembros del grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="549b1-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="549b1-122">No puede usar este cmdlet para conceder permisos a un usuario o grupo arbitrario.</span><span class="sxs-lookup"><span data-stu-id="549b1-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="549b1-123">Si desea que otro usuario o grupo tenga permisos de administración de usuarios, debe agregar ese usuario (o grupo) al grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="549b1-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="549b1-124">Ejecución de la prueba</span><span class="sxs-lookup"><span data-stu-id="549b1-124">Running the test</span></span>

<span data-ttu-id="549b1-125">Para comprobar que los permisos de administración están establecidos en un contenedor, ejecute el cmdlet Test-CsOUPermission seguido del nombre distintivo del contenedor y del tipo de permisos que está comprobando.</span><span class="sxs-lookup"><span data-stu-id="549b1-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="549b1-126">Por ejemplo, este comando comprueba si los permisos de usuario están establecidos en la ou=Redmond,dc=litwareinc,dc=com:</span><span class="sxs-lookup"><span data-stu-id="549b1-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="549b1-127">Para comprobar varios permisos mediante un solo comando, escriba cada tipo de permiso entre comillas y, a continuación, separe esos tipos con comas.</span><span class="sxs-lookup"><span data-stu-id="549b1-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="549b1-128">Por ejemplo, este comando comprueba los permisos de usuario, equipo y contacto:</span><span class="sxs-lookup"><span data-stu-id="549b1-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="549b1-129">Para obtener más información, consulte el [tema de ayuda del cmdlet Test-CsOUPermission.](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)</span><span class="sxs-lookup"><span data-stu-id="549b1-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="549b1-130">Determinar el éxito o el error</span><span class="sxs-lookup"><span data-stu-id="549b1-130">Determining success or failure</span></span>

<span data-ttu-id="549b1-131">Si ya se han establecido los permisos necesarios, Test-CsOUPermission devolverá una respuesta de una palabra:</span><span class="sxs-lookup"><span data-stu-id="549b1-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="549b1-132">Verdadero</span><span class="sxs-lookup"><span data-stu-id="549b1-132">True</span></span>

<span data-ttu-id="549b1-133">Si no se establecen los permisos necesarios, Test-CsOUPermission devolverá el valor False.</span><span class="sxs-lookup"><span data-stu-id="549b1-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="549b1-134">Es posible que deba buscar un momento para encontrar este valor.</span><span class="sxs-lookup"><span data-stu-id="549b1-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="549b1-135">Normalmente se incrustará dentro de varias advertencias que lo acompañan.</span><span class="sxs-lookup"><span data-stu-id="549b1-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="549b1-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="549b1-136">For example:</span></span>

<span data-ttu-id="549b1-137">ADVERTENCIA: entrada de control de acceso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; permitir; ReadProperty; ContainerInherit; Descendientes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="549b1-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="549b1-138">ADVERTENCIA: Las entradas de control de acceso (ACE) en el objeto "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" no están listas.</span><span class="sxs-lookup"><span data-stu-id="549b1-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="549b1-139">False</span><span class="sxs-lookup"><span data-stu-id="549b1-139">False</span></span> 

<span data-ttu-id="549b1-140">ADVERTENCIA: el procesamiento de "Test-CsOUPermission" se ha completado con advertencias.</span><span class="sxs-lookup"><span data-stu-id="549b1-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="549b1-141">Durante esta ejecución se registraron advertencias de "2".</span><span class="sxs-lookup"><span data-stu-id="549b1-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="549b1-142">ADVERTENCIA: Encontrará resultados detallados en "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="549b1-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="549b1-143">Motivos por los que se pudo haber fallado la prueba</span><span class="sxs-lookup"><span data-stu-id="549b1-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="549b1-144">Si Test-CsOUPermission error, normalmente significa que no se ha asignado el permiso especificado al grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="549b1-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="549b1-145">Puede resolver este problema y asignar los permisos necesarios con el cmdlet Grant-CsOUPermission usuario.</span><span class="sxs-lookup"><span data-stu-id="549b1-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="549b1-146">Por ejemplo, este comando concede permisos de unidad organizativa para usuarios, contactos e inetOrgPersons al grupo RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="549b1-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="549b1-147">Para obtener más información, consulte el [tema de ayuda del cmdlet Test-CsOUPermission.](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)</span><span class="sxs-lookup"><span data-stu-id="549b1-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>
