---
title: 'Lync Server 2013: posibilidad de probar los mensajes instantáneos de los usuarios móviles'
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
ms.openlocfilehash: db5af113c6ea87a700ca824bcef09b525338f4e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="e030b-102">Probar la capacidad de los usuarios móviles para intercambiar mensajes instantáneos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e030b-102">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e030b-103">_**Última modificación del tema:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="e030b-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e030b-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="e030b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e030b-105">Cada mes</span><span class="sxs-lookup"><span data-stu-id="e030b-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e030b-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="e030b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e030b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e030b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e030b-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="e030b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e030b-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e030b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e030b-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="e030b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="e030b-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e030b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e030b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e030b-112">Description</span></span>

<span data-ttu-id="e030b-113">El servicio de movilidad permite que los usuarios de dispositivos móviles realicen estas acciones como:</span><span class="sxs-lookup"><span data-stu-id="e030b-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="e030b-114">Intercambia mensajes instantáneos e información de presencia.</span><span class="sxs-lookup"><span data-stu-id="e030b-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="e030b-115">Almacene y recupere el correo de voz internamente en lugar de con su proveedor de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="e030b-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="e030b-116">Aproveche las capacidades de Lync Server, como las llamadas a través del trabajo y las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="e030b-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="e030b-117">El cmdlet test-CsMxcP2PIM ofrece una manera rápida y fácil de comprobar que los usuarios pueden usar el servicio de movilidad para intercambiar mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="e030b-117">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e030b-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="e030b-118">Running the test</span></span>

<span data-ttu-id="e030b-119">Para ejecutar esta prueba, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contengan el nombre y la contraseña de la cuenta) de cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="e030b-119">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="e030b-120">Después, debe incluir esos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsMcxP2PIM:</span><span class="sxs-lookup"><span data-stu-id="e030b-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="e030b-121">Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="e030b-121">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e030b-122">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="e030b-122">Determining success or failure</span></span>

<span data-ttu-id="e030b-123">Si los dos usuarios de prueba pueden intercambiar mensajes instantáneos con el servicio de movilidad, test-CsMcxP2PIM devolverá el resultado de la prueba:</span><span class="sxs-lookup"><span data-stu-id="e030b-123">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="e030b-124">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e030b-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e030b-125">URI de destino:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="e030b-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="e030b-126">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="e030b-126">Result : Success</span></span>

<span data-ttu-id="e030b-127">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e030b-127">Latency : 00:00:00</span></span>

<span data-ttu-id="e030b-128">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="e030b-128">Error Message :</span></span>

<span data-ttu-id="e030b-129">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e030b-129">Diagnosis :</span></span>

<span data-ttu-id="e030b-130">Si se produce un error en la prueba, el resultado se establecerá en error y aparecerá un mensaje de error detallado y un diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="e030b-130">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="e030b-131">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e030b-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e030b-132">URI de destino:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="e030b-132">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="e030b-133">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="e030b-133">Result : Failure</span></span>

<span data-ttu-id="e030b-134">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e030b-134">Latency : 00:00:00</span></span>

<span data-ttu-id="e030b-135">Mensaje de error: no se recibió respuesta para el servicio de vales Web.</span><span class="sxs-lookup"><span data-stu-id="e030b-135">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="e030b-136">Excepción interna: la solicitud HHTP no está autorizada con</span><span class="sxs-lookup"><span data-stu-id="e030b-136">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="e030b-137">esquema de negociación de cliente ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="e030b-137">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="e030b-138">La autenticación</span><span class="sxs-lookup"><span data-stu-id="e030b-138">The authentication</span></span>

<span data-ttu-id="e030b-139">el encabezado recibido del servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="e030b-139">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="e030b-140">Excepción interna: el servidor remoto devolvió un error:</span><span class="sxs-lookup"><span data-stu-id="e030b-140">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="e030b-141">(401) no autorizado.</span><span class="sxs-lookup"><span data-stu-id="e030b-141">(401) Unauthorized.</span></span>

<span data-ttu-id="e030b-142">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e030b-142">Diagnosis :</span></span>

<span data-ttu-id="e030b-143">Diagnosis interior: X-MS-Server-Fqdb: ATL-CS-</span><span class="sxs-lookup"><span data-stu-id="e030b-143">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="e030b-144">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e030b-144">001.litwareinc.com</span></span>

<span data-ttu-id="e030b-145">Cache-control: Private</span><span class="sxs-lookup"><span data-stu-id="e030b-145">Cache-Control : private</span></span>

<span data-ttu-id="e030b-146">Tipo de contenido: text/html; charset = utf-8.</span><span class="sxs-lookup"><span data-stu-id="e030b-146">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="e030b-147">Servidor: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="e030b-147">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="e030b-148">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="e030b-148">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="e030b-149">Alimentado por X: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e030b-149">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="e030b-150">Opciones de tipo de contenido X: nosniffing</span><span class="sxs-lookup"><span data-stu-id="e030b-150">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="e030b-151">Fecha: miércoles, 28 de mayo de 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="e030b-151">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="e030b-152">Longitud del contenido: 6305</span><span class="sxs-lookup"><span data-stu-id="e030b-152">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e030b-153">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="e030b-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="e030b-154">Si prueba-CsMcxP2PIM da error, el primer paso debe ser comprobar que el servicio de movilidad está funcionando.</span><span class="sxs-lookup"><span data-stu-id="e030b-154">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="e030b-155">Esto se puede realizar con un explorador Web para comprobar que se puede acceder a la dirección URL del servicio de movilidad de su grupo de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e030b-155">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="e030b-156">Por ejemplo, este comando comprueba la dirección URL del grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="e030b-156">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="e030b-157">Si el servicio de movilidad parece estar ejecutándose, compruebe que los dos usuarios de prueba tengan cuentas válidas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e030b-157">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="e030b-158">Puede recuperar información de la cuenta mediante un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="e030b-158">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="e030b-159">Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta válida de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e030b-159">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="e030b-160">También debe comprobar que el usuario está habilitado para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="e030b-160">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="e030b-161">Para ello, primero determine la Directiva de movilidad que está asignada a la cuenta:</span><span class="sxs-lookup"><span data-stu-id="e030b-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="e030b-162">Una vez que conozca el nombre de la Directiva, use el cmdlet Get-CsMobilityPolicy para comprobar que la Directiva en cuestión (por ejemplo, RedmondMobilityPolicy) tiene la propiedad EnableMobility establecida en true:</span><span class="sxs-lookup"><span data-stu-id="e030b-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="e030b-163">Si recibe un mensaje de error con encabezados de autenticación, eso a menudo significa que no ha especificado una cuenta de usuario válida.</span><span class="sxs-lookup"><span data-stu-id="e030b-163">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="e030b-164">Compruebe el nombre de usuario y la contraseña y, a continuación, vuelva a intentar la prueba.</span><span class="sxs-lookup"><span data-stu-id="e030b-164">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="e030b-165">Si está convencido de que la cuenta de usuario es válida, use el cmdlet Get-CsWebServiceConfiguration y compruebe el valor de la propiedad UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="e030b-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="e030b-166">Que le indicará qué métodos de autenticación están habilitados en su organización. Para obtener más información sobre cómo solucionar problemas del servicio de movilidad, vea la [solución de problemas de la conectividad de movilidad de Lync externa](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="e030b-166">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

