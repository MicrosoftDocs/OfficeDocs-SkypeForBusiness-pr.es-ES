---
title: 'Lync Server 2013: posibilidad de probar la capacidad de los usuarios móviles para intercambiar mensajes instantáneos'
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
ms.openlocfilehash: 84e4a79f511247b3c335872b7a1ec31fb9f2201e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="7c5e1-102">Probar la capacidad de los usuarios móviles para intercambiar mensajes instantáneos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c5e1-102">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c5e1-103">_**Última modificación del tema:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="7c5e1-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c5e1-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="7c5e1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7c5e1-105">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="7c5e1-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c5e1-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="7c5e1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7c5e1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c5e1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c5e1-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="7c5e1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7c5e1-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7c5e1-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="7c5e1-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7c5e1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7c5e1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c5e1-112">Description</span></span>

<span data-ttu-id="7c5e1-113">El servicio de movilidad permite a los usuarios de dispositivos móviles realizar tareas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="7c5e1-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="7c5e1-114">Intercambiar mensajes instantáneos e información de presencia.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="7c5e1-115">Almacene y recupere el correo de voz internamente en lugar de con su proveedor de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="7c5e1-116">Aproveche las ventajas de las capacidades de Lync Server, como las llamadas a través del trabajo y las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="7c5e1-117">El cmdlet test-CsMxcP2PIM proporciona una forma rápida y sencilla de comprobar que los usuarios pueden usar el servicio de movilidad para intercambiar mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-117">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7c5e1-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="7c5e1-118">Running the test</span></span>

<span data-ttu-id="7c5e1-119">Para ejecutar esta prueba, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-119">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="7c5e1-120">A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsMcxP2PIM:</span><span class="sxs-lookup"><span data-stu-id="7c5e1-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="7c5e1-121">Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="7c5e1-121">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7c5e1-122">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="7c5e1-122">Determining success or failure</span></span>

<span data-ttu-id="7c5e1-123">Si los dos usuarios de prueba pueden intercambiar mensajes instantáneos mediante el servicio de movilidad, test-CsMcxP2PIM devolverá el resultado de la prueba correcta:</span><span class="sxs-lookup"><span data-stu-id="7c5e1-123">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="7c5e1-124">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7c5e1-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7c5e1-125">URI de destino:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="7c5e1-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="7c5e1-126">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="7c5e1-126">Result : Success</span></span>

<span data-ttu-id="7c5e1-127">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7c5e1-127">Latency : 00:00:00</span></span>

<span data-ttu-id="7c5e1-128">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="7c5e1-128">Error Message :</span></span>

<span data-ttu-id="7c5e1-129">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7c5e1-129">Diagnosis :</span></span>

<span data-ttu-id="7c5e1-130">Si se produce un error en la prueba, el resultado se establecerá en error y se mostrará un mensaje de error detallado y un diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="7c5e1-130">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="7c5e1-131">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7c5e1-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7c5e1-132">URI de destino:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="7c5e1-132">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="7c5e1-133">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="7c5e1-133">Result : Failure</span></span>

<span data-ttu-id="7c5e1-134">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7c5e1-134">Latency : 00:00:00</span></span>

<span data-ttu-id="7c5e1-135">Mensaje de error: no se recibió ninguna respuesta para el servicio de vales Web.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-135">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="7c5e1-136">Excepción interna: la solicitud HHTP no está autorizada con</span><span class="sxs-lookup"><span data-stu-id="7c5e1-136">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="7c5e1-137">esquema de negociación del cliente ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-137">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="7c5e1-138">La autenticación</span><span class="sxs-lookup"><span data-stu-id="7c5e1-138">The authentication</span></span>

<span data-ttu-id="7c5e1-139">el encabezado recibido del servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-139">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="7c5e1-140">Excepción interna: el servidor remoto devolvió un error:</span><span class="sxs-lookup"><span data-stu-id="7c5e1-140">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="7c5e1-141">(401) no autorizado.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-141">(401) Unauthorized.</span></span>

<span data-ttu-id="7c5e1-142">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7c5e1-142">Diagnosis :</span></span>

<span data-ttu-id="7c5e1-143">Diagnóstico interno: X-MS-Server-Fqdb: ATL-CS-</span><span class="sxs-lookup"><span data-stu-id="7c5e1-143">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="7c5e1-144">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7c5e1-144">001.litwareinc.com</span></span>

<span data-ttu-id="7c5e1-145">Cache-control: privado</span><span class="sxs-lookup"><span data-stu-id="7c5e1-145">Cache-Control : private</span></span>

<span data-ttu-id="7c5e1-146">Content-Type: text/html; charset = utf-8.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-146">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="7c5e1-147">Servidor: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="7c5e1-147">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="7c5e1-148">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="7c5e1-148">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="7c5e1-149">Alimentado por X: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7c5e1-149">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="7c5e1-150">Opciones de tipo de contenido X: nosniffing</span><span class="sxs-lookup"><span data-stu-id="7c5e1-150">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="7c5e1-151">Fecha: miércoles, 28 de mayo de 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="7c5e1-151">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="7c5e1-152">Longitud del contenido: 6305</span><span class="sxs-lookup"><span data-stu-id="7c5e1-152">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7c5e1-153">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="7c5e1-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="7c5e1-154">Si test-CsMcxP2PIM produce un error, el primer paso debe ser comprobar que el servicio de movilidad está en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-154">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="7c5e1-155">Esto se puede hacer con un explorador Web para comprobar que se puede tener acceso a la dirección URL del servicio de movilidad de su grupo de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-155">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="7c5e1-156">Por ejemplo, este comando comprueba la dirección URL del grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="7c5e1-156">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="7c5e1-157">Si el servicio de movilidad parece estar en ejecución, compruebe que los dos usuarios de prueba tengan cuentas de Lync Server válidas.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-157">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="7c5e1-158">Puede recuperar la información de la cuenta con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="7c5e1-158">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="7c5e1-159">Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta de Lync Server válida.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-159">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="7c5e1-160">También debe comprobar que el usuario está habilitado para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-160">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="7c5e1-161">Para ello, en primer lugar, determine la Directiva de movilidad que se asigna a la cuenta:</span><span class="sxs-lookup"><span data-stu-id="7c5e1-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="7c5e1-162">Una vez que conoce el nombre de la Directiva, use el cmdlet Get-CsMobilityPolicy para comprobar que la Directiva en cuestión (por ejemplo, RedmondMobilityPolicy) tiene la propiedad Enablemobility configurada establecida en true:</span><span class="sxs-lookup"><span data-stu-id="7c5e1-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="7c5e1-163">Si recibe un mensaje de error con encabezados de autenticación, a menudo significa que no ha especificado una cuenta de usuario válida.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-163">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="7c5e1-164">Compruebe el nombre de usuario y la contraseña y, a continuación, vuelva a intentar la prueba.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-164">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="7c5e1-165">Si está convencido de que la cuenta de usuario es válida, use el cmdlet Get-CsWebServiceConfiguration y compruebe el valor de la propiedad UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="7c5e1-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="7c5e1-166">Esto le dirá qué métodos de autenticación están habilitados en la organización. Para obtener más información sobre cómo solucionar problemas del servicio de movilidad, vea el blog de [Troubleshooting external Lync Mobility Connectivity issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="7c5e1-166">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

