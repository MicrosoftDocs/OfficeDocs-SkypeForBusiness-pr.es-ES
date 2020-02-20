---
title: 'Lync Server 2013: probar el acceso anónimo a la aplicación Web'
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
ms.openlocfilehash: 9df6a040e71b0dfe82a52cf519357d058b78a1d7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="5d7f0-102">Probar el acceso anónimo a una aplicación web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d7f0-102">Test anonymous Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d7f0-103">_**Última modificación del tema:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="5d7f0-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d7f0-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d7f0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5d7f0-105">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="5d7f0-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d7f0-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="5d7f0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5d7f0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d7f0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d7f0-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="5d7f0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5d7f0-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5d7f0-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="5d7f0-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5d7f0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5d7f0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d7f0-112">Description</span></span>

<span data-ttu-id="5d7f0-113">El cmdlet test-CsWebAppAnonymous comprueba que un usuario anónimo puede unirse a conferencias de Lync Server mediante Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-113">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="5d7f0-114">Cuando se ejecuta el cmdlet, test-CsWebAppAnonymous se pone en contacto con el servicio de vales web para obtener un vale web para el usuario anónimo.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-114">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="5d7f0-115">Si el cmdlet consigue obtener este vale, test-CsWebAppAnonymous se pondrá en contacto con Lync Server e intentará establecer conferencias independientes para la mensajería instantánea, el uso compartido de aplicaciones y la colaboración de datos.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-115">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="5d7f0-116">Tenga en cuenta que test-CsWebAppAnonymous solo comprueba las API y las conexiones usadas para crear estas conferencias.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-116">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="5d7f0-117">En realidad, el cmdlet no crea y realiza ninguna Conferencia.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-117">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5d7f0-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="5d7f0-118">Running the test</span></span>

<span data-ttu-id="5d7f0-119">El cmdlet test-CsWebAppAnonymous se puede ejecutar usando tanto un par de cuentas de prueba preconfiguradas como las cuentas de dos usuarios que están habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-119">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="5d7f0-120">Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el nombre de dominio completo del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-120">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="5d7f0-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5d7f0-121">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="5d7f0-122">Para ejecutar esta comprobación mediante cuentas de usuario reales, debe crear dos objetos de credenciales del shell de administración de Lync Server (objetos que contengan el nombre y la contraseña de la cuenta) para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-122">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="5d7f0-123">A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsWebAppAnonymous:</span><span class="sxs-lookup"><span data-stu-id="5d7f0-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="5d7f0-124">Para obtener más información, consulte el tema de ayuda del cmdlet test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-124">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="5d7f0-125">Tenga en cuenta que test-CsWebAppAnonymous está en desuso para su uso en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-125">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5d7f0-126">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="5d7f0-126">Determining success or failure</span></span>

<span data-ttu-id="5d7f0-127">Si test-CsWebAppAnonymous se puede unir al usuario anónimo a sus conferencias, el cmdlet devolverá el resultado de la prueba correcto:</span><span class="sxs-lookup"><span data-stu-id="5d7f0-127">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="5d7f0-128">FQDN de destino:</span><span class="sxs-lookup"><span data-stu-id="5d7f0-128">Target Fqdn :</span></span>

<span data-ttu-id="5d7f0-129">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="5d7f0-129">Result : Success</span></span>

<span data-ttu-id="5d7f0-130">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5d7f0-130">Latency : 00:00:00</span></span>

<span data-ttu-id="5d7f0-131">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="5d7f0-131">Error Message :</span></span>

<span data-ttu-id="5d7f0-132">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5d7f0-132">Diagnosis :</span></span>

<span data-ttu-id="5d7f0-133">Si el usuario anónimo no puede unirse a las conferencias necesarias, el resultado de la prueba se marcará como error.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-133">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="5d7f0-134">Por lo general, test-CsWebAppAnonymous también devolverá un mensaje de error detallado y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="5d7f0-134">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="5d7f0-135">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5d7f0-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5d7f0-136">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="5d7f0-136">Result : Failure</span></span>

<span data-ttu-id="5d7f0-137">Latencia: 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="5d7f0-137">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="5d7f0-138">Mensaje de error: no se recibió ninguna respuesta para el servicio de vales Web</span><span class="sxs-lookup"><span data-stu-id="5d7f0-138">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="5d7f0-139">Diagnóstico: la solicitud HTTP no está autorizada con el cliente</span><span class="sxs-lookup"><span data-stu-id="5d7f0-139">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="5d7f0-140">esquema de autenticación ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-140">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="5d7f0-141">La autenticación</span><span class="sxs-lookup"><span data-stu-id="5d7f0-141">The authentication</span></span>

<span data-ttu-id="5d7f0-142">el encabezado recibido del servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-142">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5d7f0-143">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="5d7f0-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="5d7f0-144">Los errores de test-CsWebAppAnonymous suelen girar alrededor de los errores de autenticación de usuario: debe ejecutar la prueba con una cuenta de usuario válida aunque el cmdlet esté comprobando la capacidad de un usuario anónimo para conectarse a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-144">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="5d7f0-145">Si test-CsWebAppAnonymous produce un error, debe comprobar que el usuario especificado tiene una cuenta de usuario de Lync Server válida.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-145">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="5d7f0-146">Puede recuperar la información de la cuenta de Lync Server mediante un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d7f0-146">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="5d7f0-147">Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta de Lync Server válida.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-147">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="5d7f0-148">También debe comprobar que la contraseña que ha proporcionado al ejecutar el cmdlet es una contraseña válida.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-148">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="5d7f0-149">Los problemas de configuración de Office Web Apps Server también pueden provocar errores de test-CsWebAppAnonymous; Esto será el caso con frecuencia si recibe el siguiente diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="5d7f0-149">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="5d7f0-150">La solicitud HTTP no está autorizada con el esquema de autenticación de cliente ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-150">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="5d7f0-151">El encabezado de autenticación recibido del servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="5d7f0-151">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="5d7f0-152">Para obtener más información sobre el diagnóstico y la solución de problemas de Office Web Apps Server, vea el blog de [Office Web Apps server 2013-los equipos se notifican siempre como en mal estado](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span><span class="sxs-lookup"><span data-stu-id="5d7f0-152">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

