---
title: 'Lync Server 2013: probar las notificaciones de inserción en teléfonos inteligentes'
description: 'Lync Server 2013: probar las notificaciones de inserción en los teléfonos inteligentes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b92ef444a5331c9a673fd2db506631554e96eea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550846"
---
# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="c7328-103">Probar las notificaciones de inserción con teléfonos inteligentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7328-103">Test push notifications to smart phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7328-104">_**Última modificación del tema:** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="c7328-104">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7328-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="c7328-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c7328-106">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="c7328-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7328-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="c7328-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c7328-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7328-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7328-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="c7328-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c7328-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c7328-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c7328-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="c7328-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="c7328-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c7328-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c7328-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7328-113">Description</span></span>

<span data-ttu-id="c7328-114">El servicio de notificaciones de inserción (servicio de notificaciones de inserción de Apple y servicio de notificaciones de inserción de Microsoft) puede enviar notificaciones sobre eventos como nuevos mensajes instantáneos o correo de voz nuevo a dispositivos móviles, como iPhone y Windows Phone, incluso si el cliente de Lync en estos dispositivos está actualmente suspendido o en ejecución en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c7328-114">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="c7328-115">El servicio de notificaciones de inserción es un servicio basado en la nube que se ejecuta en servidores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7328-115">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="c7328-116">Para aprovechar las notificaciones de inserción, debe ser capaz de conectarse y autenticarse con el centro de notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="c7328-116">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="c7328-117">El cmdlet Test-CsMcxPushNotification permite a los administradores comprobar que las solicitudes de notificación de inserción se pueden enrutar a través del servidor perimetral hacia el centro de notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="c7328-117">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c7328-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="c7328-118">Running the test</span></span>

<span data-ttu-id="c7328-119">Para probar el servicio de notificaciones de inserción, llame al cmdlet Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="c7328-119">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="c7328-120">Asegúrese de especificar el nombre de dominio completo del servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="c7328-120">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="c7328-121">Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .</span><span class="sxs-lookup"><span data-stu-id="c7328-121">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c7328-122">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="c7328-122">Determining success or failure</span></span>

<span data-ttu-id="c7328-123">Si Test-CsMcxPushNotification tiene éxito, el cmdlet devolverá el resultado de la prueba:</span><span class="sxs-lookup"><span data-stu-id="c7328-123">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="c7328-124">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c7328-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c7328-125">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="c7328-125">Result : Success</span></span>

<span data-ttu-id="c7328-126">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c7328-126">Latency : 00:00:00</span></span>

<span data-ttu-id="c7328-127">Error</span><span class="sxs-lookup"><span data-stu-id="c7328-127">Error :</span></span>

<span data-ttu-id="c7328-128">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c7328-128">Diagnosis :</span></span>

<span data-ttu-id="c7328-129">Si Test-CsMcxPushNotification no puede conectarse al centro de notificaciones de inserción, el cmdlet no devolverá normalmente un resultado de prueba de error.</span><span class="sxs-lookup"><span data-stu-id="c7328-129">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="c7328-130">En su lugar, el comando producirá un error por completo.</span><span class="sxs-lookup"><span data-stu-id="c7328-130">Instead the command will usually fail completely.</span></span> <span data-ttu-id="c7328-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c7328-131">For example:</span></span>

<span data-ttu-id="c7328-132">Test-CsMcxPushNotification: se recibió una respuesta 504 (tiempo de espera del servidor) desde la red y se produjo un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="c7328-132">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="c7328-133">Vea los detalles de la excepción para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c7328-133">See the exception details for more information.</span></span>

<span data-ttu-id="c7328-134">En la línea: 1 carácter: 27</span><span class="sxs-lookup"><span data-stu-id="c7328-134">At line:1 char:27</span></span>

<span data-ttu-id="c7328-135">\+Test-CsMcxPushNotification \< \< \< \< AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="c7328-135">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="c7328-136">\+ CategoryInfo: OperationStopped: (:) \[ Test-CsMcxPushNotification \] , FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="c7328-136">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="c7328-137">\+ FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="c7328-137">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c7328-138">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="c7328-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="c7328-139">Si se produce un error en el servicio de notificaciones de inserción que normalmente indica problemas de comunicación con el servidor perimetral o problemas de comunicación con el centro de enrutamiento de notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="c7328-139">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="c7328-140">Si surgen problemas al ejecutar test-CsMcxPushNotification, lo primero que debe hacer es comprobar que el servidor perimetral funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="c7328-140">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="c7328-141">Una forma de hacerlo es usar el cmdlet Test-CsAVEdgeConnectivity:</span><span class="sxs-lookup"><span data-stu-id="c7328-141">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="c7328-142">Esta comprobación comprueba que un usuario especificado puede conectarse al servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c7328-142">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="c7328-143">Si el servidor perimetral parece funcionar correctamente, esto suele significar que no puede conectarse al centro de notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="c7328-143">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="c7328-144">A su vez, eso suele significar que no ha configurado correctamente el URI del centro de activación o que no tiene un registro SRV de DNS que señale a esta dirección URL.</span><span class="sxs-lookup"><span data-stu-id="c7328-144">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="c7328-145">Puede comprobar que el URI está establecido en el valor correcto (sip:push@push.lync.com) ejecutando este comando:</span><span class="sxs-lookup"><span data-stu-id="c7328-145">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="c7328-146">Si la propiedad PushNotificationProxyUri se establece en un valor distinto de sip:push@push.lync.com, puede corregir el problema mediante el cmdlet Set-McxConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c7328-146">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="c7328-147">Por ejemplo, este comando establece correctamente el URI en toda la organización:</span><span class="sxs-lookup"><span data-stu-id="c7328-147">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="c7328-148">Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="c7328-148">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="c7328-149">Si el URI está configurado correctamente, el siguiente paso debe ser comprobar que tiene un registro SRV de DNS que se resuelve en el dominio SIP y el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="c7328-149">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="c7328-150">Para obtener más información acerca de cómo configurar estos registros, consulte el tema de ayuda sobre los requisitos de DNS para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="c7328-150">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="c7328-151">Tenga en cuenta que el siguiente mensaje de error suele indicar un problema con los registros DNS:</span><span class="sxs-lookup"><span data-stu-id="c7328-151">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="c7328-152">Se ha recibido una respuesta 504 (tiempo de espera del servidor) de la red y se ha producido un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="c7328-152">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="c7328-153">Vea los detalles de la excepción para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c7328-153">See the exception details for more information.</span></span>

<span data-ttu-id="c7328-154">También es posible que se produzca un error en Test-CsMcxConfiguration con este mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="c7328-154">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="c7328-155">Test-CsMcxPushNotification: se rechazó la solicitud de notificación de inserción.</span><span class="sxs-lookup"><span data-stu-id="c7328-155">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="c7328-156">En la línea: 1 carácter: 27</span><span class="sxs-lookup"><span data-stu-id="c7328-156">At line:1 char:27</span></span>

<span data-ttu-id="c7328-157">\+ Test-CsMcxPushNotification \<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="c7328-157">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="c7328-158">\+ CategoryInfo: OperationStopped: (:) \[ Test-CsMcxPushNotification \] , SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="c7328-158">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="c7328-159">\+ FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="c7328-159">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="c7328-160">El mensaje "se rechazó la solicitud de notificación de inserción" suele producirse si ha habilitado el filtrado de URL y está bloqueando los prefijos http: y https:.</span><span class="sxs-lookup"><span data-stu-id="c7328-160">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="c7328-161">Puede determinar qué prefijos se están bloqueando mediante un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7328-161">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="c7328-162">Si http: o https: aparecen en los resultados, debe quitarlos de la lista de prefijos bloqueados para que funcionen las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="c7328-162">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="c7328-163">Esto se puede hacer con comandos similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7328-163">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="c7328-164">Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).</span><span class="sxs-lookup"><span data-stu-id="c7328-164">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

