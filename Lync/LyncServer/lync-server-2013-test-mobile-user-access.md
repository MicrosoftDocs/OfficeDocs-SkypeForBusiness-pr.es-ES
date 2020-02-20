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
ms.openlocfilehash: 8afea8450df1533928a0407fb81866351705186e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="91084-102">Probar el acceso de usuarios móviles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91084-102">Test mobile user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91084-103">_**Última modificación del tema:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="91084-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91084-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="91084-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="91084-105">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="91084-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91084-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="91084-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="91084-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91084-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91084-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="91084-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="91084-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="91084-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="91084-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsMcxConference.</span><span class="sxs-lookup"><span data-stu-id="91084-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="91084-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="91084-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="91084-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="91084-112">Description</span></span>

<span data-ttu-id="91084-113">El servicio de movilidad permite a los usuarios de dispositivos móviles realizar tareas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="91084-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="91084-114">Intercambiar mensajes instantáneos e información de presencia.</span><span class="sxs-lookup"><span data-stu-id="91084-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="91084-115">Almacene y recupere el correo de voz internamente en lugar de con su proveedor de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="91084-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="91084-116">Aproveche las ventajas de las capacidades de Lync Server, como las llamadas a través del trabajo y las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="91084-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="91084-117">El cmdlet test-CsMcxConference proporciona una forma rápida y sencilla de comprobar que los usuarios pueden unirse a conferencias de Lync Server y participar en ellas mediante un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="91084-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="91084-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="91084-118">Running the test</span></span>

<span data-ttu-id="91084-119">Para ejecutar esta comprobación, debe crear tres objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="91084-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="91084-120">A continuación, debe incluir los objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsMcxConference como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="91084-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="91084-121">Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .</span><span class="sxs-lookup"><span data-stu-id="91084-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="91084-122">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="91084-122">Determining success or failure</span></span>

<span data-ttu-id="91084-123">Si la comprobación se realiza correctamente, test-CsMcxConference informará de que se ha realizado correctamente un resultado de prueba:</span><span class="sxs-lookup"><span data-stu-id="91084-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="91084-124">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="91084-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="91084-125">URI de destino:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="91084-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="91084-126">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="91084-126">Result : Success</span></span>

<span data-ttu-id="91084-127">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="91084-127">Latency : 00:00:00</span></span>

<span data-ttu-id="91084-128">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="91084-128">Error Message :</span></span>

<span data-ttu-id="91084-129">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="91084-129">Diagnosis :</span></span>

<span data-ttu-id="91084-130">Si la comprobación es incorrecta test-CsMcxConference notificará un resultado de prueba de error.</span><span class="sxs-lookup"><span data-stu-id="91084-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="91084-131">Por lo general, este resultado de la prueba irá acompañado de un mensaje de error detallado y diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="91084-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="91084-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="91084-132">For example:</span></span>

<span data-ttu-id="91084-133">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="91084-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="91084-134">URI de destino:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="91084-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="91084-135">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="91084-135">Result : Failure</span></span>

<span data-ttu-id="91084-136">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="91084-136">Latency : 00:00:00</span></span>

<span data-ttu-id="91084-137">Mensaje de error: no se recibió ninguna respuesta para el servicio de vales Web.</span><span class="sxs-lookup"><span data-stu-id="91084-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="91084-138">Excepción interna: la solicitud HHTP no está autorizada con el cliente</span><span class="sxs-lookup"><span data-stu-id="91084-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="91084-139">esquema de negociación ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="91084-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="91084-140">El encabezado de autenticación recibido</span><span class="sxs-lookup"><span data-stu-id="91084-140">The authentication header received</span></span>

<span data-ttu-id="91084-141">del servidor fue "Negotiate".</span><span class="sxs-lookup"><span data-stu-id="91084-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="91084-142">Excepción interna: el servidor remoto devolvió un error: (401)</span><span class="sxs-lookup"><span data-stu-id="91084-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="91084-143">No autorizado.</span><span class="sxs-lookup"><span data-stu-id="91084-143">Unauthorized.</span></span>

<span data-ttu-id="91084-144">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="91084-144">Diagnosis :</span></span>

<span data-ttu-id="91084-145">Diagnóstico interno: X-MS-Server-Fqdb: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="91084-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="91084-146">Cache-control: privado</span><span class="sxs-lookup"><span data-stu-id="91084-146">Cache-Control : private</span></span>

<span data-ttu-id="91084-147">Content-Type: text/html; charset = utf-8.</span><span class="sxs-lookup"><span data-stu-id="91084-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="91084-148">Servidor: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="91084-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="91084-149">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="91084-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="91084-150">Alimentado por X: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="91084-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="91084-151">Opciones de tipo de contenido X: nosniffing</span><span class="sxs-lookup"><span data-stu-id="91084-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="91084-152">Fecha: miércoles, 28 de mayo de 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="91084-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="91084-153">Longitud del contenido: 6305</span><span class="sxs-lookup"><span data-stu-id="91084-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="91084-154">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="91084-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="91084-155">Si test-CsMcxConference produce un error, debe comprobar que el servicio de movilidad se está ejecutando y que se puede tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="91084-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="91084-156">Esto se puede hacer con un explorador Web para comprobar que se puede tener acceso a la dirección URL del servicio de movilidad de su grupo de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91084-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="91084-157">Por ejemplo, este comando comprueba la dirección URL del grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="91084-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="91084-158">Si se puede tener acceso al servicio de movilidad, debe comprobar que los usuarios de prueba tengan cuentas de Lync Server válidas.</span><span class="sxs-lookup"><span data-stu-id="91084-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="91084-159">Puede recuperar la información de la cuenta con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="91084-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="91084-160">Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta de Lync Server válida. También debe comprobar que cada cuenta de usuario esté habilitada para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="91084-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="91084-161">Para ello, en primer lugar, determine la Directiva de movilidad que se asigna a la cuenta:</span><span class="sxs-lookup"><span data-stu-id="91084-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="91084-162">Una vez que conoce el nombre de la Directiva, use el cmdlet Get-CsMobilityPolicy para comprobar que la Directiva en cuestión (por ejemplo, RedmondMobilityPolicy) tiene la propiedad Enablemobility configurada establecida en true:</span><span class="sxs-lookup"><span data-stu-id="91084-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="91084-163">Si recibe un mensaje de error de "encabezado de autenticación" cuando ejecuta test-CsMcxConference que a menudo significa que no ha especificado una cuenta de usuario válida, compruebe el nombre de usuario y la contraseña y, a continuación, vuelva a intentar la prueba.</span><span class="sxs-lookup"><span data-stu-id="91084-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="91084-164">Si está convencido de que la cuenta de usuario es válida, use el cmdlet Get-CsWebServiceConfiguration y compruebe el valor de la propiedad UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="91084-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="91084-165">Esto le dirá qué métodos de autenticación están habilitados en la organización.</span><span class="sxs-lookup"><span data-stu-id="91084-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="91084-166">Para obtener más información sobre cómo solucionar problemas del servicio de movilidad, vea el blog de [Troubleshooting external Lync Mobility Connectivity issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="91084-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

