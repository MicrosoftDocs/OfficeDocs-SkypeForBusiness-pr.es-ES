---
title: 'Lync Server 2013: probar el acceso de usuarios móviles'
description: 'Lync Server 2013: probar el acceso de usuarios móviles.'
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
ms.openlocfilehash: e99a05e6ef9fe925126026452823e5edcc100ede
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541876"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="c6212-103">Probar el acceso de usuarios móviles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6212-103">Test mobile user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6212-104">_**Última modificación del tema:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="c6212-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6212-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="c6212-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c6212-106">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="c6212-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6212-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="c6212-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c6212-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6212-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6212-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="c6212-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c6212-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c6212-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c6212-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsMcxConference.</span><span class="sxs-lookup"><span data-stu-id="c6212-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="c6212-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c6212-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c6212-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6212-113">Description</span></span>

<span data-ttu-id="c6212-114">El servicio de movilidad permite a los usuarios de dispositivos móviles realizar tareas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6212-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="c6212-115">Intercambiar mensajes instantáneos e información de presencia.</span><span class="sxs-lookup"><span data-stu-id="c6212-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="c6212-116">Almacene y recupere el correo de voz internamente en lugar de con su proveedor de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="c6212-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="c6212-117">Aproveche las ventajas de las capacidades de Lync Server, como las llamadas a través del trabajo y las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c6212-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="c6212-118">El cmdlet Test-CsMcxConference proporciona una forma rápida y sencilla de comprobar que los usuarios pueden unirse a conferencias de Lync Server y participar en ellas mediante un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="c6212-118">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c6212-119">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="c6212-119">Running the test</span></span>

<span data-ttu-id="c6212-120">Para ejecutar esta comprobación, debe crear tres objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="c6212-120">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="c6212-121">A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a Test-CsMcxConference como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6212-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="c6212-122">Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .</span><span class="sxs-lookup"><span data-stu-id="c6212-122">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c6212-123">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="c6212-123">Determining success or failure</span></span>

<span data-ttu-id="c6212-124">Si la comprobación se realiza correctamente, Test-CsMcxConference notificará un resultado de prueba correcto:</span><span class="sxs-lookup"><span data-stu-id="c6212-124">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="c6212-125">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c6212-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c6212-126">URI de destino: http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="c6212-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="c6212-127">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="c6212-127">Result : Success</span></span>

<span data-ttu-id="c6212-128">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c6212-128">Latency : 00:00:00</span></span>

<span data-ttu-id="c6212-129">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="c6212-129">Error Message :</span></span>

<span data-ttu-id="c6212-130">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c6212-130">Diagnosis :</span></span>

<span data-ttu-id="c6212-131">Si la comprobación no se realiza correctamente, Test-CsMcxConference notificará un resultado de prueba de error.</span><span class="sxs-lookup"><span data-stu-id="c6212-131">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="c6212-132">Por lo general, este resultado de la prueba irá acompañado de un mensaje de error detallado y diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c6212-132">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="c6212-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c6212-133">For example:</span></span>

<span data-ttu-id="c6212-134">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c6212-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c6212-135">URI de destino: https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="c6212-135">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="c6212-136">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="c6212-136">Result : Failure</span></span>

<span data-ttu-id="c6212-137">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c6212-137">Latency : 00:00:00</span></span>

<span data-ttu-id="c6212-138">Mensaje de error: no se recibió ninguna respuesta para el servicio de Web-Ticket.</span><span class="sxs-lookup"><span data-stu-id="c6212-138">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="c6212-139">Excepción interna: la solicitud HHTP no está autorizada con el cliente</span><span class="sxs-lookup"><span data-stu-id="c6212-139">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="c6212-140">esquema de negociación ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="c6212-140">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="c6212-141">El encabezado de autenticación recibido</span><span class="sxs-lookup"><span data-stu-id="c6212-141">The authentication header received</span></span>

<span data-ttu-id="c6212-142">del servidor fue "Negotiate".</span><span class="sxs-lookup"><span data-stu-id="c6212-142">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="c6212-143">Excepción interna: el servidor remoto devolvió un error: (401)</span><span class="sxs-lookup"><span data-stu-id="c6212-143">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="c6212-144">No autorizado.</span><span class="sxs-lookup"><span data-stu-id="c6212-144">Unauthorized.</span></span>

<span data-ttu-id="c6212-145">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c6212-145">Diagnosis :</span></span>

<span data-ttu-id="c6212-146">Diagnóstico interno: X-MS-Server-Fqdb: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c6212-146">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c6212-147">Cache-Control: privado</span><span class="sxs-lookup"><span data-stu-id="c6212-147">Cache-Control : private</span></span>

<span data-ttu-id="c6212-148">Content-Type: text/html; charset = utf-8.</span><span class="sxs-lookup"><span data-stu-id="c6212-148">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="c6212-149">Servidor: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="c6212-149">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="c6212-150">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="c6212-150">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="c6212-151">Alimentado por X: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c6212-151">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="c6212-152">Opciones de tipo de contenido X: nosniffing</span><span class="sxs-lookup"><span data-stu-id="c6212-152">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="c6212-153">Fecha: miércoles, 28 de mayo de 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="c6212-153">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="c6212-154">Longitud del contenido: 6305</span><span class="sxs-lookup"><span data-stu-id="c6212-154">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c6212-155">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="c6212-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="c6212-156">Si Test-CsMcxConference no se produce ningún error, debe comprobar que el servicio de movilidad se está ejecutando y que se puede tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="c6212-156">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="c6212-157">Esto se puede hacer con un explorador Web para comprobar que se puede tener acceso a la dirección URL del servicio de movilidad de su grupo de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6212-157">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="c6212-158">Por ejemplo, este comando comprueba la dirección URL del grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="c6212-158">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="c6212-159">Si se puede tener acceso al servicio de movilidad, debe comprobar que los usuarios de prueba tengan cuentas de Lync Server válidas.</span><span class="sxs-lookup"><span data-stu-id="c6212-159">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="c6212-160">Puede recuperar la información de la cuenta con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6212-160">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="c6212-161">Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta de Lync Server válida. También debe comprobar que cada cuenta de usuario esté habilitada para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="c6212-161">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="c6212-162">Para ello, en primer lugar, determine la Directiva de movilidad que se asigna a la cuenta:</span><span class="sxs-lookup"><span data-stu-id="c6212-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="c6212-163">Una vez que se conoce el nombre de la Directiva, use el cmdlet Get-CsMobilityPolicy para comprobar que la Directiva en cuestión (por ejemplo, RedmondMobilityPolicy) tiene la propiedad Enablemobility configurada establecida en true:</span><span class="sxs-lookup"><span data-stu-id="c6212-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="c6212-164">Si recibe un mensaje de error de "encabezado de autenticación" cuando ejecuta Test-CsMcxConference que a menudo significa que no ha especificado una cuenta de usuario válida, compruebe el nombre de usuario y la contraseña y, a continuación, vuelva a intentar la prueba.</span><span class="sxs-lookup"><span data-stu-id="c6212-164">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="c6212-165">Si está convencido de que la cuenta de usuario es válida, use el cmdlet Get-CsWebServiceConfiguration y compruebe el valor de la propiedad UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="c6212-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="c6212-166">Esto le dirá qué métodos de autenticación están habilitados en la organización.</span><span class="sxs-lookup"><span data-stu-id="c6212-166">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="c6212-167">Para obtener más información sobre cómo solucionar problemas del servicio de movilidad, vea el blog de [Troubleshooting external Lync Mobility Connectivity issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="c6212-167">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

