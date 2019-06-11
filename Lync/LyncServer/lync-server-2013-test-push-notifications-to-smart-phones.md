---
title: 'Lync Server 2013: probar las notificaciones de inserción en teléfonos inteligentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a0d58c79fcd66229ffda43fa60ab99cedc308ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="ac5b0-102">Probar las notificaciones Push a Smart Phone en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac5b0-102">Test push notifications to smart phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac5b0-103">_**Última modificación del tema:** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="ac5b0-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac5b0-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="ac5b0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ac5b0-105">Cada mes</span><span class="sxs-lookup"><span data-stu-id="ac5b0-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac5b0-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="ac5b0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ac5b0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac5b0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac5b0-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="ac5b0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ac5b0-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ac5b0-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="ac5b0-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ac5b0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac5b0-112">Description</span></span>

<span data-ttu-id="ac5b0-113">El servicio de notificaciones push (servicio de notificaciones push de Apple y servicio de notificaciones push de Microsoft) puede enviar notificaciones sobre eventos como nuevos mensajes instantáneos o un nuevo correo de voz a dispositivos móviles como iPhone y Windows Phone, incluso si el cliente de Lync en estos dispositivos está suspendido o se está ejecutando en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="ac5b0-114">El servicio de notificaciones push es un servicio basado en la nube que se ejecuta en servidores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="ac5b0-115">Para aprovechar las notificaciones push, debe poder conectarse a la conexión de notificaciones Push y autenticarla en él.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="ac5b0-116">El cmdlet test-CsMcxPushNotification permite a los administradores comprobar que las solicitudes de notificaciones push se pueden enrutar a través del servidor perimetral al centro de notificaciones Push.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ac5b0-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="ac5b0-117">Running the test</span></span>

<span data-ttu-id="ac5b0-118">Para probar el servicio de notificaciones push, llame al cmdlet test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="ac5b0-119">Asegúrese de especificar el nombre de dominio completo del servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="ac5b0-120">Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .</span><span class="sxs-lookup"><span data-stu-id="ac5b0-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ac5b0-121">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="ac5b0-121">Determining success or failure</span></span>

<span data-ttu-id="ac5b0-122">Si prueba-CsMcxPushNotification se ejecuta correctamente, el cmdlet devolverá el resultado de la prueba correctamente:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="ac5b0-123">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac5b0-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ac5b0-124">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="ac5b0-124">Result : Success</span></span>

<span data-ttu-id="ac5b0-125">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ac5b0-125">Latency : 00:00:00</span></span>

<span data-ttu-id="ac5b0-126">:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-126">Error :</span></span>

<span data-ttu-id="ac5b0-127">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ac5b0-127">Diagnosis :</span></span>

<span data-ttu-id="ac5b0-128">Si prueba-CsMcxPushNotification no puede conectarse al centro de notificaciones push, el cmdlet normalmente no devolverá un resultado de prueba de error.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="ac5b0-129">En su lugar, el comando fallará por completo.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="ac5b0-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-130">For example:</span></span>

<span data-ttu-id="ac5b0-131">Prueba-CsMcxPushNotification: se recibió una respuesta de 504 (tiempo de espera del servidor) desde la red y se produjo un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="ac5b0-132">Para obtener más información, consulta los detalles de la excepción.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-132">See the exception details for more information.</span></span>

<span data-ttu-id="ac5b0-133">En la línea: 1 carácter: 27</span><span class="sxs-lookup"><span data-stu-id="ac5b0-133">At line:1 char:27</span></span>

<span data-ttu-id="ac5b0-134">\+Prueba-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="ac5b0-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="ac5b0-135">\+CategoryInfo: OperationStopped: (:) \[Prueba-CsMcxPushNotification\], FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="ac5b0-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="ac5b0-136">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="ac5b0-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ac5b0-137">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="ac5b0-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="ac5b0-138">Si se produce un error en el servicio de notificaciones Push que normalmente indica problemas de comunicación con el servidor perimetral o problemas de comunicación con el centro de enrutamiento de notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="ac5b0-139">Si experimenta problemas al ejecutar test-CsMcxPushNotification, lo primero que debe hacer es comprobar que el servidor perimetral funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="ac5b0-140">Una forma de hacerlo es usar el cmdlet test-CsAVEdgeConnectivity:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="ac5b0-141">Esta comprobación comprueba que un usuario especificado puede conectarse al servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="ac5b0-142">Si el servidor perimetral parece funcionar correctamente, eso a menudo significa que no puede conectarse al centro de notificaciones Push.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="ac5b0-143">A su vez, eso significa que no ha configurado el URI de Clearinghouse correctamente o que no tiene un registro SRV de DNS que apunte a esta dirección URL.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="ac5b0-144">Puede comprobar que el URI está configurado con el valor correcto (sip:push@push.lync.com) ejecutando este comando:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="ac5b0-145">Si la propiedad PushNotificationProxyUri se establece en un valor distinto de sip:push@push.lync.com, puede corregir ese problema mediante el cmdlet Set-McxConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="ac5b0-146">Por ejemplo, este comando establece correctamente el URI en toda la organización:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="ac5b0-147">Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="ac5b0-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="ac5b0-148">Si el URI está configurado correctamente, el siguiente paso debe ser comprobar que tiene un registro SRV de DNS que se resuelve en el dominio SIP y en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="ac5b0-149">Para obtener más información sobre cómo configurar estos registros, vea el tema de ayuda sobre los requisitos de DNS para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="ac5b0-150">Tenga en cuenta que el siguiente mensaje de error suele indicar un problema con los registros DNS:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="ac5b0-151">Se ha recibido una respuesta 504 (tiempo de espera del servidor) de la red y se ha producido un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="ac5b0-152">Para obtener más información, consulta los detalles de la excepción.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-152">See the exception details for more information.</span></span>

<span data-ttu-id="ac5b0-153">También es posible que la prueba-CsMcxConfiguration falle con este mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="ac5b0-154">Prueba-CsMcxPushNotification: se rechazó la solicitud de notificaciones Push.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="ac5b0-155">En la línea: 1 carácter: 27</span><span class="sxs-lookup"><span data-stu-id="ac5b0-155">At line:1 char:27</span></span>

<span data-ttu-id="ac5b0-156">\+Prueba-CsMcxPushNotification\<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="ac5b0-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="ac5b0-157">\+CategoryInfo: OperationStopped: (:) \[Prueba-CsMcxPushNotification\], SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="ac5b0-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="ac5b0-158">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="ac5b0-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="ac5b0-159">El mensaje "se rechazó la solicitud de notificación de inserción" suele ocurrir si ha habilitado el filtrado de URL y está bloqueando los prefijos http: y https:.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="ac5b0-160">Puede determinar qué prefijos se están bloqueando mediante un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

``` 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="ac5b0-161">Si http: o https: aparecen en los resultados, debe eliminarlos de la lista de prefijos bloqueados para que las notificaciones de inserción funcionen.</span><span class="sxs-lookup"><span data-stu-id="ac5b0-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="ac5b0-162">Esto se puede hacer con comandos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="ac5b0-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="ac5b0-163">Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).</span><span class="sxs-lookup"><span data-stu-id="ac5b0-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

