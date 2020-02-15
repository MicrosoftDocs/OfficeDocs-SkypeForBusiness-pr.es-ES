---
title: Probar los permisos de administrador en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cómo probar los permisos de administrador en Skype empresarial Server
ms.openlocfilehash: 1e06c87dcf0e436d72c510a2bc8d9f2aa2051620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030163"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="12d23-103">Probar los permisos de administrador en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="12d23-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="12d23-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="12d23-104">Verification schedule</span></span>|<span data-ttu-id="12d23-105">Después de la implementación inicial de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="12d23-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="12d23-106">Si es necesario, si surgen problemas relacionados con los permisos.</span><span class="sxs-lookup"><span data-stu-id="12d23-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="12d23-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="12d23-107">Testing tool</span></span>|<span data-ttu-id="12d23-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12d23-108">Windows PowerShell</span></span>|
|<span data-ttu-id="12d23-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="12d23-109">Permissions required</span></span>|<span data-ttu-id="12d23-110">Cuando se ejecuta de forma local mediante el shell de administración de Skype empresarial Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="12d23-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="12d23-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="12d23-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="12d23-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="12d23-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="12d23-113">Get-CsAdminRole \| Where-Object {$ _. Cmdlets-Match "test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="12d23-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="12d23-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="12d23-114">Description</span></span>

<span data-ttu-id="12d23-115">Al instalar Skype empresarial Server, una de las tareas realizadas por el programa de instalación proporciona al grupo RTCUniversalUserAdmins los permisos de Active Directory que se necesitan para administrar usuarios, equipos, contactos, contactos de aplicaciones y InetOrg ajena.</span><span class="sxs-lookup"><span data-stu-id="12d23-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="12d23-116">Si ha deshabilitado la herencia de permisos en Active Directory, el programa de instalación no podrá asignar esos permisos.</span><span class="sxs-lookup"><span data-stu-id="12d23-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="12d23-117">Como resultado, los miembros del grupo RTCUniversalUserAdmins no podrán administrar las entidades de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="12d23-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="12d23-118">Estos privilegios de administración solo estarán disponibles para los administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="12d23-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="12d23-119">El cmdlet test-CsOUPermission comprueba que los permisos necesarios para administrar usuarios, equipos y otros objetos se establecen en un contenedor de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="12d23-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="12d23-120">Si estos permisos no están establecidos, puede resolver este problema mediante la ejecución del [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission).</span><span class="sxs-lookup"><span data-stu-id="12d23-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="12d23-121">Tenga en cuenta que Grant-CsOUPermission solo puede asignar permisos a miembros del grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="12d23-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="12d23-122">No puede usar este cmdlet para conceder permisos a un usuario o grupo arbitrario.</span><span class="sxs-lookup"><span data-stu-id="12d23-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="12d23-123">Si desea que un usuario o grupo diferente tenga permisos de administración de usuarios, debe agregar el usuario (o grupo) al grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="12d23-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="12d23-124">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="12d23-124">Running the test</span></span>

<span data-ttu-id="12d23-125">Para comprobar que los permisos de administración están establecidos en un contenedor, ejecute el cmdlet test-CsOUPermission seguido por el nombre distintivo del contenedor y por el tipo de permisos que está comprobando.</span><span class="sxs-lookup"><span data-stu-id="12d23-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="12d23-126">Por ejemplo, este comando comprueba si los permisos de usuario están establecidos en ou ou = Redmond, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="12d23-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="12d23-127">Para comprobar varios permisos mediante un solo comando, encierre cada tipo de permiso entre comillas y, a continuación, separe los tipos con comas.</span><span class="sxs-lookup"><span data-stu-id="12d23-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="12d23-128">Por ejemplo, este único comando comprueba los permisos de usuario, equipo y contacto:</span><span class="sxs-lookup"><span data-stu-id="12d23-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="12d23-129">Para obtener más información, consulte el [tema de ayuda del cmdlet test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="12d23-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="12d23-130">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="12d23-130">Determining success or failure</span></span>

<span data-ttu-id="12d23-131">Si ya se han establecido los permisos necesarios, test-CsOUPermission devolverá una respuesta de una palabra:</span><span class="sxs-lookup"><span data-stu-id="12d23-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="12d23-132">True</span><span class="sxs-lookup"><span data-stu-id="12d23-132">True</span></span>

<span data-ttu-id="12d23-133">Si no se establecen los permisos necesarios, test-CsOUPermission devolverá el valor false.</span><span class="sxs-lookup"><span data-stu-id="12d23-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="12d23-134">Es posible que deba buscar un momento para encontrar este valor.</span><span class="sxs-lookup"><span data-stu-id="12d23-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="12d23-135">Por lo general, se incrustará en varias advertencias que lo acompañan.</span><span class="sxs-lookup"><span data-stu-id="12d23-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="12d23-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="12d23-136">For example:</span></span>

<span data-ttu-id="12d23-137">ADVERTENCIA: entrada de control de acceso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; permita ReadProperty ContainerInherit; Descendientes bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="12d23-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="12d23-138">ADVERTENCIA: las entradas de control de acceso (ACE) del objeto "OU = Norteamérica, DC = atl-cs-001\DC = litwareinc, DC = com" no están preparadas.</span><span class="sxs-lookup"><span data-stu-id="12d23-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="12d23-139">False</span><span class="sxs-lookup"><span data-stu-id="12d23-139">False</span></span> 

<span data-ttu-id="12d23-140">ADVERTENCIA: el procesamiento de "test-CsOUPermission" se completó con advertencias.</span><span class="sxs-lookup"><span data-stu-id="12d23-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="12d23-141">se han registrado advertencias de "2" durante esta ejecución.</span><span class="sxs-lookup"><span data-stu-id="12d23-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="12d23-142">ADVERTENCIA: los resultados detallados se pueden encontrar en "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="12d23-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="12d23-143">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="12d23-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="12d23-144">Si test-CsOUPermission produce un error, suele significar que no se ha asignado el permiso especificado al grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="12d23-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="12d23-145">Puede resolver este problema y asignar los permisos necesarios mediante el cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="12d23-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="12d23-146">Por ejemplo, este comando proporciona permisos de unidad organizativa para usuarios, contactos y inetOrgPersons al grupo RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="12d23-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="12d23-147">Para obtener más información, consulte el [tema de ayuda del cmdlet test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="12d23-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>
