---
title: 'Lync Server 2013: pruebas de chat persistente'
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
ms.openlocfilehash: 2177e4fce4d32bb2dc6c82e1f3fecae367eb2543
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="734a8-102">Prueba de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="734a8-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="734a8-103">_**Última modificación del tema:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="734a8-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="734a8-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="734a8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="734a8-105">Diario</span><span class="sxs-lookup"><span data-stu-id="734a8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="734a8-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="734a8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="734a8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="734a8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="734a8-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="734a8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="734a8-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="734a8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="734a8-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsPersistentChatMessage</strong> .</span><span class="sxs-lookup"><span data-stu-id="734a8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="734a8-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="734a8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="734a8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="734a8-112">Description</span></span>

<span data-ttu-id="734a8-113">El cmdlet **Test-CsPersistentChatMessage** comprueba que un par de usuarios de prueba puedan intercambiar mensajes mediante el servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="734a8-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="734a8-114">Para ello, el cmdlet registra los dos usuarios en Lync Server 2013, conecta los usuarios a un salón de chat persistente, intercambia un par de mensajes y, a continuación, sale del salón de chat y cierra sesión en los dos usuarios.</span><span class="sxs-lookup"><span data-stu-id="734a8-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="734a8-115">Tenga en cuenta que se producirá un error en las llamadas a este cmdlet si no ha creado ningún salón de chat o si las dos cuentas de usuario de prueba no tienen asignada una directiva de chat persistente que les dé acceso al servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="734a8-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="734a8-116">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="734a8-116">Running the test</span></span>

<span data-ttu-id="734a8-117">Los comandos que se muestran en el siguiente ejemplo prueban la capacidad de un par de\\usuarios (litwareinc\\Pilar y litwareinc kenmyer) para iniciar sesión en Lync Server 2013 y, a continuación, intercambiar mensajes con el servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="734a8-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="734a8-118">Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="734a8-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="734a8-119">(Como el nombre de inicio de\\sesión, litwareinc pilar, se incluyó como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Pilar Ackerman). A continuación, el objeto de credenciales resultante se almacena en una variable llamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="734a8-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="734a8-120">El segundo comando realiza la misma acción pero, esta vez, devuelve un objeto de credenciales de la cuenta de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="734a8-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="734a8-121">Con los objetos de credenciales a mano, el tercer comando determina si estos dos usuarios pueden iniciar sesión en Lync Server 2013 y intercambiar mensajes con el chat persistente.</span><span class="sxs-lookup"><span data-stu-id="734a8-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="734a8-122">Para realizar esta tarea, se llama al cmdlet **Test-CsPersistentChatMessage** con los parámetros siguientes: TargetFqdn (el FQDN del grupo de registrador); SenderSipAddress (la dirección SIP del primer usuario de prueba); SenderCredential (el objeto de Windows PowerShell que contiene las credenciales para este mismo usuario); ReceiverSipAddress (la dirección SIP del otro usuario de prueba); y ReceiverCredential (el objeto de Windows PowerShell que contiene las credenciales del otro usuario de prueba).</span><span class="sxs-lookup"><span data-stu-id="734a8-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="734a8-123">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="734a8-123">Determining success or failure</span></span>

<span data-ttu-id="734a8-124">Si el usuario especificado tiene una directiva de ubicación válida, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta**:</span><span class="sxs-lookup"><span data-stu-id="734a8-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="734a8-125">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="734a8-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="734a8-126">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="734a8-126">Result : Success</span></span>

<span data-ttu-id="734a8-127">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="734a8-127">Latency : 00:00:00</span></span>

<span data-ttu-id="734a8-128">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="734a8-128">Error Message :</span></span>

<span data-ttu-id="734a8-129">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="734a8-129">Diagnosis :</span></span>

<span data-ttu-id="734a8-130">Si los usuarios especificados no pueden intercambiar mensajes mediante el servicio de chat persistente, el resultado se mostrará como **error**y se registrará información adicional en las propiedades error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="734a8-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="734a8-131">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo</span><span class="sxs-lookup"><span data-stu-id="734a8-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="734a8-132">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="734a8-132">domain name (FQDN).</span></span> <span data-ttu-id="734a8-133">Se usará el número de puerto del registrador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="734a8-133">Using default Registrar port number.</span></span> <span data-ttu-id="734a8-134">Excepción</span><span class="sxs-lookup"><span data-stu-id="734a8-134">Exception:</span></span>

<span data-ttu-id="734a8-135">System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.</span><span class="sxs-lookup"><span data-stu-id="734a8-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="734a8-136">Veamos</span><span class="sxs-lookup"><span data-stu-id="734a8-136">at</span></span>

<span data-ttu-id="734a8-137">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="734a8-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="734a8-138">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="734a8-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="734a8-139">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="734a8-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="734a8-140">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="734a8-140">Result : Failure</span></span>

<span data-ttu-id="734a8-141">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="734a8-141">Latency : 00:00:00</span></span>

<span data-ttu-id="734a8-142">Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada</span><span class="sxs-lookup"><span data-stu-id="734a8-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="734a8-143">no respondió correctamente después de un período de tiempo o</span><span class="sxs-lookup"><span data-stu-id="734a8-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="734a8-144">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="734a8-144">established connection failed because connected host has</span></span>

<span data-ttu-id="734a8-145">no se pudo \[responder 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061</span><span class="sxs-lookup"><span data-stu-id="734a8-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="734a8-146">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="734a8-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="734a8-147">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="734a8-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="734a8-148">tiempo o error de conexión establecida debido a que el host conectado</span><span class="sxs-lookup"><span data-stu-id="734a8-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="734a8-149">no respondió</span><span class="sxs-lookup"><span data-stu-id="734a8-149">has failed to respond</span></span>

<span data-ttu-id="734a8-150">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="734a8-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="734a8-151">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="734a8-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="734a8-152">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="734a8-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="734a8-153">Estas son algunas de las razones comunes por las que **Test-CsPersistentChatMessage** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="734a8-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="734a8-154">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="734a8-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="734a8-155">Es posible que las cuentas de prueba necesarias no existan o se hayan creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="734a8-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="734a8-156">Es posible que haya un problema de red que ocasionó un retraso inesperado que agotó el tiempo de espera de la prueba.</span><span class="sxs-lookup"><span data-stu-id="734a8-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="734a8-157">Consulta también</span><span class="sxs-lookup"><span data-stu-id="734a8-157">See Also</span></span>


[<span data-ttu-id="734a8-158">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="734a8-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="734a8-159">New-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="734a8-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="734a8-160">Set-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="734a8-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

