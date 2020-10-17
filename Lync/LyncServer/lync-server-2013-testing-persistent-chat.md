---
title: 'Lync Server 2013: pruebas de chat persistente'
description: 'Lync Server 2013: prueba de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8b1dc4eef1870f1287dacdc1852ab1e24edd169
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556286"
---
# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="98b63-103">Prueba de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98b63-103">Testing persistent chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98b63-104">_**Última modificación del tema:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="98b63-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98b63-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="98b63-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="98b63-106">Diario</span><span class="sxs-lookup"><span data-stu-id="98b63-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b63-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="98b63-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="98b63-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98b63-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b63-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="98b63-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="98b63-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="98b63-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="98b63-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsPersistentChatMessage</strong> .</span><span class="sxs-lookup"><span data-stu-id="98b63-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="98b63-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="98b63-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="98b63-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="98b63-113">Description</span></span>

<span data-ttu-id="98b63-114">El cmdlet **Test-CsPersistentChatMessage** comprueba que un par de usuarios de prueba puedan intercambiar mensajes mediante el servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="98b63-114">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="98b63-115">Para ello, el cmdlet registra los dos usuarios en Lync Server 2013, conecta los usuarios a un salón de chat persistente, intercambia un par de mensajes y, a continuación, sale del salón de chat y cierra sesión en los dos usuarios.</span><span class="sxs-lookup"><span data-stu-id="98b63-115">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="98b63-116">Tenga en cuenta que se producirá un error en las llamadas a este cmdlet si no ha creado ningún salón de chat o si las dos cuentas de usuario de prueba no tienen asignada una directiva de chat persistente que les dé acceso al servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="98b63-116">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="98b63-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="98b63-117">Running the test</span></span>

<span data-ttu-id="98b63-118">Los comandos que se muestran en el siguiente ejemplo prueban la capacidad de un par de usuarios (litwareinc \\ Pilar y litwareinc \\ kenmyer) para iniciar sesión en Lync Server 2013 y, a continuación, intercambiar mensajes con el servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="98b63-118">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="98b63-119">Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="98b63-119">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="98b63-120">(Como el nombre de inicio de sesión, litwareinc \\ pilar, se incluyó como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Pilar Ackerman). A continuación, el objeto de credenciales resultante se almacena en una variable llamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="98b63-120">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="98b63-121">El segundo comando realiza la misma acción pero, esta vez, devuelve un objeto de credenciales de la cuenta de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="98b63-121">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="98b63-122">Con los objetos de credenciales a mano, el tercer comando determina si estos dos usuarios pueden iniciar sesión en Lync Server 2013 y intercambiar mensajes con el chat persistente.</span><span class="sxs-lookup"><span data-stu-id="98b63-122">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="98b63-123">Para realizar esta tarea, se llama al cmdlet **Test-CsPersistentChatMessage** con los parámetros siguientes: TargetFqdn (el FQDN del grupo de registrador); SenderSipAddress (la dirección SIP del primer usuario de prueba); SenderCredential (el objeto de Windows PowerShell que contiene las credenciales para este mismo usuario); ReceiverSipAddress (la dirección SIP del otro usuario de prueba); y ReceiverCredential (el objeto de Windows PowerShell que contiene las credenciales del otro usuario de prueba).</span><span class="sxs-lookup"><span data-stu-id="98b63-123">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="98b63-124">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="98b63-124">Determining success or failure</span></span>

<span data-ttu-id="98b63-125">Si el usuario especificado tiene una directiva de ubicación válida, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta**:</span><span class="sxs-lookup"><span data-stu-id="98b63-125">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="98b63-126">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="98b63-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="98b63-127">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="98b63-127">Result : Success</span></span>

<span data-ttu-id="98b63-128">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="98b63-128">Latency : 00:00:00</span></span>

<span data-ttu-id="98b63-129">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="98b63-129">Error Message :</span></span>

<span data-ttu-id="98b63-130">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="98b63-130">Diagnosis :</span></span>

<span data-ttu-id="98b63-131">Si los usuarios especificados no pueden intercambiar mensajes mediante el servicio de chat persistente, el resultado se mostrará como **error**y se registrará información adicional en las propiedades error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="98b63-131">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="98b63-132">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo</span><span class="sxs-lookup"><span data-stu-id="98b63-132">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="98b63-133">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="98b63-133">domain name (FQDN).</span></span> <span data-ttu-id="98b63-134">Se usará el número de puerto del registrador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="98b63-134">Using default Registrar port number.</span></span> <span data-ttu-id="98b63-135">Excepción</span><span class="sxs-lookup"><span data-stu-id="98b63-135">Exception:</span></span>

<span data-ttu-id="98b63-136">System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.</span><span class="sxs-lookup"><span data-stu-id="98b63-136">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="98b63-137">Veamos</span><span class="sxs-lookup"><span data-stu-id="98b63-137">at</span></span>

<span data-ttu-id="98b63-138">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="98b63-138">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="98b63-139">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="98b63-139">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="98b63-140">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="98b63-140">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="98b63-141">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="98b63-141">Result : Failure</span></span>

<span data-ttu-id="98b63-142">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="98b63-142">Latency : 00:00:00</span></span>

<span data-ttu-id="98b63-143">Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada</span><span class="sxs-lookup"><span data-stu-id="98b63-143">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="98b63-144">no respondió correctamente después de un período de tiempo o</span><span class="sxs-lookup"><span data-stu-id="98b63-144">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="98b63-145">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="98b63-145">established connection failed because connected host has</span></span>

<span data-ttu-id="98b63-146">no se pudo responder \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="98b63-146">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="98b63-147">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="98b63-147">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="98b63-148">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="98b63-148">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="98b63-149">tiempo o error de conexión establecida debido a que el host conectado</span><span class="sxs-lookup"><span data-stu-id="98b63-149">time, or established connection failed because connected host</span></span>

<span data-ttu-id="98b63-150">no respondió</span><span class="sxs-lookup"><span data-stu-id="98b63-150">has failed to respond</span></span>

<span data-ttu-id="98b63-151">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="98b63-151">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="98b63-152">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="98b63-152">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="98b63-153">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="98b63-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="98b63-154">Estas son algunas de las razones comunes por las que **Test-CsPersistentChatMessage** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="98b63-154">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="98b63-155">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="98b63-155">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="98b63-156">Es posible que las cuentas de prueba necesarias no existan o se hayan creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="98b63-156">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="98b63-157">Es posible que haya un problema de red que ocasionó un retraso inesperado que agotó el tiempo de espera de la prueba.</span><span class="sxs-lookup"><span data-stu-id="98b63-157">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98b63-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98b63-158">See Also</span></span>


[<span data-ttu-id="98b63-159">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="98b63-159">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="98b63-160">New-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="98b63-160">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="98b63-161">Set-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="98b63-161">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

