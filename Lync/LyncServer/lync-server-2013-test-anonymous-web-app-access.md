---
title: 'Lync Server 2013: probar el acceso anónimo a la aplicación Web'
description: 'Lync Server 2013: probar el acceso anónimo a la aplicación Web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c33840912fefcaeef069e14773cfefd0834a8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547476"
---
# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="5451d-103">Probar el acceso anónimo a una aplicación web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5451d-103">Test anonymous Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5451d-104">_**Última modificación del tema:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="5451d-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5451d-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="5451d-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5451d-106">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="5451d-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5451d-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="5451d-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5451d-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5451d-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5451d-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="5451d-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5451d-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5451d-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5451d-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="5451d-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="5451d-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5451d-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5451d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5451d-113">Description</span></span>

<span data-ttu-id="5451d-114">El cmdlet Test-CsWebAppAnonymous comprueba que un usuario anónimo puede unirse a conferencias de Lync Server mediante Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="5451d-114">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="5451d-115">Al ejecutar el cmdlet, Test-CsWebAppAnonymous se pone en contacto con el servicio de vales web para obtener un vale web para el usuario anónimo.</span><span class="sxs-lookup"><span data-stu-id="5451d-115">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="5451d-116">Si el cmdlet consigue obtener este vale, Test-CsWebAppAnonymous se pondrá en contacto con Lync Server e intentará establecer conferencias independientes para la mensajería instantánea, el uso compartido de aplicaciones y la colaboración de datos.</span><span class="sxs-lookup"><span data-stu-id="5451d-116">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="5451d-117">Tenga en cuenta que Test-CsWebAppAnonymous solo comprueba las API y las conexiones usadas para crear estas conferencias.</span><span class="sxs-lookup"><span data-stu-id="5451d-117">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="5451d-118">En realidad, el cmdlet no crea y realiza ninguna Conferencia.</span><span class="sxs-lookup"><span data-stu-id="5451d-118">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5451d-119">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="5451d-119">Running the test</span></span>

<span data-ttu-id="5451d-120">El cmdlet Test-CsWebAppAnonymous puede ejecutarse con un par de cuentas de prueba preconfiguradas o con las cuentas de dos usuarios que están habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5451d-120">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="5451d-121">Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el nombre de dominio completo del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="5451d-121">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="5451d-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5451d-122">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="5451d-123">Para ejecutar esta comprobación mediante cuentas de usuario reales, debe crear dos objetos de credenciales del shell de administración de Lync Server (objetos que contengan el nombre y la contraseña de la cuenta) para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="5451d-123">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="5451d-124">A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsWebAppAnonymous:</span><span class="sxs-lookup"><span data-stu-id="5451d-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="5451d-125">Para obtener más información, consulte el tema de ayuda para el cmdlet Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="5451d-125">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="5451d-126">Tenga en cuenta que Test-CsWebAppAnonymous está en desuso para su uso en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5451d-126">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5451d-127">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="5451d-127">Determining success or failure</span></span>

<span data-ttu-id="5451d-128">Si Test-CsWebAppAnonymous se puede unir al usuario anónimo a sus conferencias, el cmdlet devolverá el resultado de la prueba correcto:</span><span class="sxs-lookup"><span data-stu-id="5451d-128">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="5451d-129">FQDN de destino:</span><span class="sxs-lookup"><span data-stu-id="5451d-129">Target Fqdn :</span></span>

<span data-ttu-id="5451d-130">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="5451d-130">Result : Success</span></span>

<span data-ttu-id="5451d-131">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5451d-131">Latency : 00:00:00</span></span>

<span data-ttu-id="5451d-132">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="5451d-132">Error Message :</span></span>

<span data-ttu-id="5451d-133">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5451d-133">Diagnosis :</span></span>

<span data-ttu-id="5451d-134">Si el usuario anónimo no puede unirse a las conferencias necesarias, el resultado de la prueba se marcará como error.</span><span class="sxs-lookup"><span data-stu-id="5451d-134">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="5451d-135">Por lo general, Test-CsWebAppAnonymous también devolverá un mensaje de error detallado y un diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="5451d-135">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="5451d-136">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5451d-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5451d-137">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="5451d-137">Result : Failure</span></span>

<span data-ttu-id="5451d-138">Latencia: 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="5451d-138">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="5451d-139">Mensaje de error: no se recibió ninguna respuesta para el servicio Web-Ticket</span><span class="sxs-lookup"><span data-stu-id="5451d-139">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="5451d-140">Diagnóstico: la solicitud HTTP no está autorizada con el cliente</span><span class="sxs-lookup"><span data-stu-id="5451d-140">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="5451d-141">esquema de autenticación ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="5451d-141">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="5451d-142">La autenticación</span><span class="sxs-lookup"><span data-stu-id="5451d-142">The authentication</span></span>

<span data-ttu-id="5451d-143">el encabezado recibido del servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="5451d-143">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5451d-144">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="5451d-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="5451d-145">Los errores de Test-CsWebAppAnonymous suelen girar en torno a errores de autenticación de usuario: debe ejecutar la prueba con una cuenta de usuario válida aunque el cmdlet esté comprobando la capacidad de un usuario anónimo para conectarse a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5451d-145">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="5451d-146">Si Test-CsWebAppAnonymous da error, debe comprobar que el usuario especificado tiene una cuenta de usuario de Lync Server válida.</span><span class="sxs-lookup"><span data-stu-id="5451d-146">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="5451d-147">Puede recuperar la información de la cuenta de Lync Server mediante un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5451d-147">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="5451d-148">Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta de Lync Server válida.</span><span class="sxs-lookup"><span data-stu-id="5451d-148">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="5451d-149">También debe comprobar que la contraseña que ha proporcionado al ejecutar el cmdlet es una contraseña válida.</span><span class="sxs-lookup"><span data-stu-id="5451d-149">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="5451d-150">Los problemas de configuración de Office Web Apps Server también pueden provocar errores en Test-CsWebAppAnonymous; Esto será el caso con frecuencia si recibe el siguiente diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="5451d-150">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="5451d-151">La solicitud HTTP no está autorizada con el esquema de autenticación de cliente ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="5451d-151">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="5451d-152">El encabezado de autenticación recibido del servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="5451d-152">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="5451d-153">Para obtener más información sobre el diagnóstico y la solución de problemas de Office Web Apps Server, vea el blog de [Office Web Apps server 2013-los equipos se notifican siempre como en mal estado](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span><span class="sxs-lookup"><span data-stu-id="5451d-153">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

