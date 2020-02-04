---
title: 'Lync Server 2013: probar el acceso de usuarios móviles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 628fd3aae4f66316627176c3af025eb63202bafb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="ec4cc-102">Probar el acceso de usuarios móviles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec4cc-102">Test mobile user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec4cc-103">_**Última modificación del tema:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="ec4cc-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec4cc-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="ec4cc-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ec4cc-105">Cada mes</span><span class="sxs-lookup"><span data-stu-id="ec4cc-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec4cc-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="ec4cc-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ec4cc-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec4cc-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec4cc-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="ec4cc-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ec4cc-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ec4cc-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsMcxConference.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="ec4cc-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec4cc-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ec4cc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec4cc-112">Description</span></span>

<span data-ttu-id="ec4cc-113">El servicio de movilidad permite que los usuarios de dispositivos móviles realicen estas acciones como:</span><span class="sxs-lookup"><span data-stu-id="ec4cc-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="ec4cc-114">Intercambia mensajes instantáneos e información de presencia.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="ec4cc-115">Almacene y recupere el correo de voz internamente en lugar de con su proveedor de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="ec4cc-116">Aproveche las capacidades de Lync Server, como las llamadas a través del trabajo y las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="ec4cc-117">El cmdlet test-CsMcxConference ofrece una manera rápida y sencilla de comprobar que los usuarios pueden unirse a conferencias de Lync Server y participar en ellas con un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ec4cc-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="ec4cc-118">Running the test</span></span>

<span data-ttu-id="ec4cc-119">Para ejecutar esta comprobación, debe crear tres objetos de credenciales de Windows PowerShell (objetos que contengan el nombre y la contraseña de la cuenta) de cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="ec4cc-120">Después, debe incluir esos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsMcxConference como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ec4cc-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="ec4cc-121">Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .</span><span class="sxs-lookup"><span data-stu-id="ec4cc-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ec4cc-122">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="ec4cc-122">Determining success or failure</span></span>

<span data-ttu-id="ec4cc-123">Si la comprobación se realiza correctamente, test-CsMcxConference notificará un resultado de prueba de éxito:</span><span class="sxs-lookup"><span data-stu-id="ec4cc-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="ec4cc-124">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec4cc-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ec4cc-125">URI de destino:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="ec4cc-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="ec4cc-126">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="ec4cc-126">Result : Success</span></span>

<span data-ttu-id="ec4cc-127">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ec4cc-127">Latency : 00:00:00</span></span>

<span data-ttu-id="ec4cc-128">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="ec4cc-128">Error Message :</span></span>

<span data-ttu-id="ec4cc-129">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ec4cc-129">Diagnosis :</span></span>

<span data-ttu-id="ec4cc-130">Si la comprobación es incorrecta: CsMcxConference informará de un resultado de prueba de error.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="ec4cc-131">Por lo general, este resultado de la prueba va acompañado de un mensaje de error y diagnóstico detallado.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="ec4cc-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ec4cc-132">For example:</span></span>

<span data-ttu-id="ec4cc-133">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec4cc-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ec4cc-134">URI de destino:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="ec4cc-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="ec4cc-135">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="ec4cc-135">Result : Failure</span></span>

<span data-ttu-id="ec4cc-136">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ec4cc-136">Latency : 00:00:00</span></span>

<span data-ttu-id="ec4cc-137">Mensaje de error: no se recibió respuesta para el servicio de vales Web.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="ec4cc-138">Excepción interna: la solicitud HHTP está desautorizada con el cliente</span><span class="sxs-lookup"><span data-stu-id="ec4cc-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="ec4cc-139">esquema de negociación ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="ec4cc-140">El encabezado de autenticación recibido</span><span class="sxs-lookup"><span data-stu-id="ec4cc-140">The authentication header received</span></span>

<span data-ttu-id="ec4cc-141">desde el servidor fue ' Negotiate '.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="ec4cc-142">Excepción interna: el servidor remoto devolvió un error: (401)</span><span class="sxs-lookup"><span data-stu-id="ec4cc-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="ec4cc-143">No autorizado.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-143">Unauthorized.</span></span>

<span data-ttu-id="ec4cc-144">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ec4cc-144">Diagnosis :</span></span>

<span data-ttu-id="ec4cc-145">Diagnosis interior: X-MS-Server-Fqdb: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec4cc-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ec4cc-146">Cache-control: Private</span><span class="sxs-lookup"><span data-stu-id="ec4cc-146">Cache-Control : private</span></span>

<span data-ttu-id="ec4cc-147">Tipo de contenido: text/html; charset = utf-8.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="ec4cc-148">Servidor: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="ec4cc-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="ec4cc-149">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="ec4cc-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="ec4cc-150">Alimentado por X: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ec4cc-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="ec4cc-151">Opciones de tipo de contenido X: nosniffing</span><span class="sxs-lookup"><span data-stu-id="ec4cc-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="ec4cc-152">Fecha: miércoles, 28 de mayo de 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="ec4cc-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="ec4cc-153">Longitud del contenido: 6305</span><span class="sxs-lookup"><span data-stu-id="ec4cc-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ec4cc-154">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="ec4cc-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="ec4cc-155">Si prueba-CsMcxConference no se ejecuta correctamente, verifique que el servicio de movilidad se esté ejecutando y que se pueda obtener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="ec4cc-156">Esto se puede realizar con un explorador Web para comprobar que se puede acceder a la dirección URL del servicio de movilidad de su grupo de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="ec4cc-157">Por ejemplo, este comando comprueba la dirección URL del grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="ec4cc-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="ec4cc-158">Si se puede acceder al servicio de movilidad, debe comprobar que los usuarios de prueba tengan cuentas válidas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="ec4cc-159">Puede recuperar información de la cuenta mediante un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="ec4cc-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="ec4cc-160">Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta válida de Lync Server. También debe comprobar que cada cuenta de usuario está habilitada para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="ec4cc-161">Para ello, primero determine la Directiva de movilidad que está asignada a la cuenta:</span><span class="sxs-lookup"><span data-stu-id="ec4cc-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="ec4cc-162">Una vez que conozca el nombre de la Directiva, use el cmdlet Get-CsMobilityPolicy para comprobar que la Directiva en cuestión (por ejemplo, RedmondMobilityPolicy) tiene la propiedad EnableMobility establecida en true:</span><span class="sxs-lookup"><span data-stu-id="ec4cc-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="ec4cc-163">Si recibe un mensaje de error "encabezado de autenticación" cuando ejecuta test-CsMcxConference que a menudo significa que no ha especificado una cuenta de usuario válida, compruebe el nombre de usuario y la contraseña y, a continuación, vuelva a intentar la prueba.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="ec4cc-164">Si está convencido de que la cuenta de usuario es válida, use el cmdlet Get-CsWebServiceConfiguration y compruebe el valor de la propiedad UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="ec4cc-165">Que le indicará qué métodos de autenticación están habilitados en su organización.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="ec4cc-166">Para obtener más información sobre cómo solucionar problemas del servicio de movilidad, vea la [solución de problemas de la conectividad de movilidad de Lync externa](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="ec4cc-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

