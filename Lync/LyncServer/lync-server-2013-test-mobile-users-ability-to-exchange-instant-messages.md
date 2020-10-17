---
title: 'Lync Server 2013: posibilidad de probar la capacidad de los usuarios móviles para intercambiar mensajes instantáneos'
description: 'Lync Server 2013: posibilidad de probar la capacidad de los usuarios móviles para intercambiar mensajes instantáneos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675bbeff93fed374d950b2efbdf15b4ea246f861
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558296"
---
# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="e5a2a-103">Probar la capacidad de los usuarios móviles para intercambiar mensajes instantáneos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5a2a-103">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5a2a-104">_**Última modificación del tema:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="e5a2a-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5a2a-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="e5a2a-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e5a2a-106">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="e5a2a-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5a2a-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="e5a2a-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e5a2a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5a2a-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5a2a-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="e5a2a-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e5a2a-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e5a2a-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="e5a2a-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e5a2a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e5a2a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5a2a-113">Description</span></span>

<span data-ttu-id="e5a2a-114">El servicio de movilidad permite a los usuarios de dispositivos móviles realizar tareas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="e5a2a-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="e5a2a-115">Intercambiar mensajes instantáneos e información de presencia.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="e5a2a-116">Almacene y recupere el correo de voz internamente en lugar de con su proveedor de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="e5a2a-117">Aproveche las ventajas de las capacidades de Lync Server, como las llamadas a través del trabajo y las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="e5a2a-118">El cmdlet Test-CsMxcP2PIM proporciona una forma rápida y sencilla de comprobar que los usuarios pueden usar el servicio de movilidad para intercambiar mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-118">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e5a2a-119">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="e5a2a-119">Running the test</span></span>

<span data-ttu-id="e5a2a-120">Para ejecutar esta prueba, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-120">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="e5a2a-121">A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsMcxP2PIM:</span><span class="sxs-lookup"><span data-stu-id="e5a2a-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="e5a2a-122">Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="e5a2a-122">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e5a2a-123">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="e5a2a-123">Determining success or failure</span></span>

<span data-ttu-id="e5a2a-124">Si los dos usuarios de prueba pueden intercambiar mensajes instantáneos mediante el servicio de movilidad, Test-CsMcxP2PIM devolverá el resultado de la prueba correcta:</span><span class="sxs-lookup"><span data-stu-id="e5a2a-124">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="e5a2a-125">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e5a2a-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e5a2a-126">URI de destino: http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="e5a2a-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="e5a2a-127">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="e5a2a-127">Result : Success</span></span>

<span data-ttu-id="e5a2a-128">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e5a2a-128">Latency : 00:00:00</span></span>

<span data-ttu-id="e5a2a-129">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="e5a2a-129">Error Message :</span></span>

<span data-ttu-id="e5a2a-130">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e5a2a-130">Diagnosis :</span></span>

<span data-ttu-id="e5a2a-131">Si se produce un error en la prueba, el resultado se establecerá en error y se mostrará un mensaje de error detallado y un diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="e5a2a-131">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="e5a2a-132">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e5a2a-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e5a2a-133">URI de destino: https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="e5a2a-133">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="e5a2a-134">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="e5a2a-134">Result : Failure</span></span>

<span data-ttu-id="e5a2a-135">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e5a2a-135">Latency : 00:00:00</span></span>

<span data-ttu-id="e5a2a-136">Mensaje de error: no se recibió ninguna respuesta para el servicio de Web-Ticket.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-136">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="e5a2a-137">Excepción interna: la solicitud HHTP no está autorizada con</span><span class="sxs-lookup"><span data-stu-id="e5a2a-137">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="e5a2a-138">esquema de negociación del cliente ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-138">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="e5a2a-139">La autenticación</span><span class="sxs-lookup"><span data-stu-id="e5a2a-139">The authentication</span></span>

<span data-ttu-id="e5a2a-140">el encabezado recibido del servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-140">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="e5a2a-141">Excepción interna: el servidor remoto devolvió un error:</span><span class="sxs-lookup"><span data-stu-id="e5a2a-141">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="e5a2a-142">(401) no autorizado.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-142">(401) Unauthorized.</span></span>

<span data-ttu-id="e5a2a-143">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e5a2a-143">Diagnosis :</span></span>

<span data-ttu-id="e5a2a-144">Diagnóstico interno: X-MS-Server-Fqdb: ATL-CS-</span><span class="sxs-lookup"><span data-stu-id="e5a2a-144">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="e5a2a-145">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e5a2a-145">001.litwareinc.com</span></span>

<span data-ttu-id="e5a2a-146">Cache-Control: privado</span><span class="sxs-lookup"><span data-stu-id="e5a2a-146">Cache-Control : private</span></span>

<span data-ttu-id="e5a2a-147">Content-Type: text/html; charset = utf-8.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="e5a2a-148">Servidor: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="e5a2a-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="e5a2a-149">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="e5a2a-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="e5a2a-150">Alimentado por X: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e5a2a-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="e5a2a-151">Opciones de tipo de contenido X: nosniffing</span><span class="sxs-lookup"><span data-stu-id="e5a2a-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="e5a2a-152">Fecha: miércoles, 28 de mayo de 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="e5a2a-152">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="e5a2a-153">Longitud del contenido: 6305</span><span class="sxs-lookup"><span data-stu-id="e5a2a-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e5a2a-154">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="e5a2a-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="e5a2a-155">Si Test-CsMcxP2PIM no supera el primer paso debe ser comprobar que el servicio de movilidad está en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-155">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="e5a2a-156">Esto se puede hacer con un explorador Web para comprobar que se puede tener acceso a la dirección URL del servicio de movilidad de su grupo de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="e5a2a-157">Por ejemplo, este comando comprueba la dirección URL del grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="e5a2a-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="e5a2a-158">Si el servicio de movilidad parece estar en ejecución, compruebe que los dos usuarios de prueba tengan cuentas de Lync Server válidas.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-158">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="e5a2a-159">Puede recuperar la información de la cuenta con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5a2a-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="e5a2a-160">Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta de Lync Server válida.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="e5a2a-161">También debe comprobar que el usuario está habilitado para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-161">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="e5a2a-162">Para ello, en primer lugar, determine la Directiva de movilidad que se asigna a la cuenta:</span><span class="sxs-lookup"><span data-stu-id="e5a2a-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="e5a2a-163">Una vez que se conoce el nombre de la Directiva, use el cmdlet Get-CsMobilityPolicy para comprobar que la Directiva en cuestión (por ejemplo, RedmondMobilityPolicy) tiene la propiedad Enablemobility configurada establecida en true:</span><span class="sxs-lookup"><span data-stu-id="e5a2a-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="e5a2a-164">Si recibe un mensaje de error con encabezados de autenticación, a menudo significa que no ha especificado una cuenta de usuario válida.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-164">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="e5a2a-165">Compruebe el nombre de usuario y la contraseña y, a continuación, vuelva a intentar la prueba.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-165">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="e5a2a-166">Si está convencido de que la cuenta de usuario es válida, use el cmdlet Get-CsWebServiceConfiguration y compruebe el valor de la propiedad UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="e5a2a-166">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="e5a2a-167">Esto le dirá qué métodos de autenticación están habilitados en la organización. Para obtener más información sobre cómo solucionar problemas del servicio de movilidad, vea el blog de [Troubleshooting external Lync Mobility Connectivity issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="e5a2a-167">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

