---
title: 'Lync Server 2013: probar la mensajería mediante XMPP'
description: 'Lync Server 2013: probar la mensajería con XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06faeae0a6104351f9102de31c76b2424a140deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556306"
---
# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="f5be4-103">Probar la mensajería con XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5be4-103">Testing messaging using XMPP in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5be4-104">_**Última modificación del tema:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="f5be4-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5be4-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5be4-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f5be4-106">Diario</span><span class="sxs-lookup"><span data-stu-id="f5be4-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5be4-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="f5be4-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f5be4-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5be4-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5be4-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="f5be4-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f5be4-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f5be4-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f5be4-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsXmppIM</strong> .</span><span class="sxs-lookup"><span data-stu-id="f5be4-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="f5be4-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f5be4-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f5be4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5be4-113">Description</span></span>

<span data-ttu-id="f5be4-114">El protocolo de presencia y mensajería extensible (XMPP) es un protocolo de comunicaciones estándar (basado en XML) que se usa para enviar mensajes a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="f5be4-114">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="f5be4-115">XMPP se llamaba originalmente Jabber y es compatible con varias aplicaciones de mensajería y comunicaciones de Internet, como Google Talk y Facebook Chat.</span><span class="sxs-lookup"><span data-stu-id="f5be4-115">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="f5be4-116">El cmdlet **Test-CsXmppIM** comprueba que un usuario puede intercambiar mensajes instantáneos con un usuario en una red XMPP.</span><span class="sxs-lookup"><span data-stu-id="f5be4-116">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="f5be4-117">Tenga en cuenta que, para que esta prueba se realice correctamente, debe tener una dirección SIP válida para el usuario XMPP y que la dirección SIP deba estar en una red configurada como asociado de XMPP permitido.</span><span class="sxs-lookup"><span data-stu-id="f5be4-117">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f5be4-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="f5be4-118">Running the test</span></span>

<span data-ttu-id="f5be4-119">En el siguiente ejemplo se comprueba la funcionalidad de mensajería instantánea XMPP para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f5be4-119">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f5be4-120">Este comando funcionará solo si los usuarios de prueba están definidos para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f5be4-120">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f5be4-121">Si lo tienen, el comando determinará si el primer usuario de prueba puede enviar un mensaje instantáneo XMPP a un usuario que tiene la dirección SIP adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f5be4-121">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="f5be4-122">Si no se definen los usuarios de prueba, se producirá un error en el comando porque no sabrá en qué usuario se inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="f5be4-122">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="f5be4-123">Si no ha definido usuarios de prueba para un grupo de servidores, debe incluir el parámetro UserSipAddress y las credenciales del usuario que el comando debe usar al intentar iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="f5be4-123">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="f5be4-124">Los comandos que se muestran en el siguiente ejemplo prueban la capacidad de un usuario específico (litwareinc \\ Pilar) para iniciar sesión para enviar un mensaje instantáneo XMPP al usuario adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f5be4-124">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="f5be4-125">Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="f5be4-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="f5be4-126">(Como el nombre de inicio de sesión litwareinc \\ Pilar se incluyó como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Pilar Ackerman). El objeto Credential resultante se almacena en una variable llamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="f5be4-126">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="f5be4-127">A continuación, el segundo comando comprueba si el usuario puede iniciar sesión en el grupo atl-cs-001.litwareinc.com y enviar el mensaje instantáneo XMPP.</span><span class="sxs-lookup"><span data-stu-id="f5be4-127">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="f5be4-128">Para ejecutar esta tarea, se llama al cmdlet **Test-CsXmppIm** , junto con cuatro parámetros: TargetFqdn (el FQDN del grupo de registrador); Receiver (la dirección SIP del usuario al que se dirige el mensaje); UserCredential (el objeto de Windows PowerShell que contiene las credenciales de usuario de Pilar Ackerman); y UserSipAddress (la dirección SIP que corresponde a las credenciales de usuario suministradas).</span><span class="sxs-lookup"><span data-stu-id="f5be4-128">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f5be4-129">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="f5be4-129">Determining success or failure</span></span>

<span data-ttu-id="f5be4-130">Si la mensajería instantánea XMPP está configurada correctamente, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="f5be4-130">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f5be4-131">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f5be4-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f5be4-132">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="f5be4-132">Result : Success</span></span>

<span data-ttu-id="f5be4-133">Latencia: 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="f5be4-133">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="f5be4-134">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="f5be4-134">Error Message :</span></span>

<span data-ttu-id="f5be4-135">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f5be4-135">Diagnosis :</span></span>

<span data-ttu-id="f5be4-136">Si los usuarios especificados no pueden usar la mensajería instantánea XMPP, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="f5be4-136">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f5be4-137">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo</span><span class="sxs-lookup"><span data-stu-id="f5be4-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="f5be4-138">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="f5be4-138">domain name (FQDN).</span></span> <span data-ttu-id="f5be4-139">Se usará el número de puerto del registrador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f5be4-139">Using default Registrar port number.</span></span> <span data-ttu-id="f5be4-140">Excepción</span><span class="sxs-lookup"><span data-stu-id="f5be4-140">Exception:</span></span>

<span data-ttu-id="f5be4-141">System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.</span><span class="sxs-lookup"><span data-stu-id="f5be4-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="f5be4-142">Veamos</span><span class="sxs-lookup"><span data-stu-id="f5be4-142">at</span></span>

<span data-ttu-id="f5be4-143">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="f5be4-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="f5be4-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="f5be4-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="f5be4-145">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f5be4-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f5be4-146">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="f5be4-146">Result : Failure</span></span>

<span data-ttu-id="f5be4-147">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f5be4-147">Latency : 00:00:00</span></span>

<span data-ttu-id="f5be4-148">Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada</span><span class="sxs-lookup"><span data-stu-id="f5be4-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="f5be4-149">no respondió correctamente después de un período de tiempo o</span><span class="sxs-lookup"><span data-stu-id="f5be4-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="f5be4-150">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="f5be4-150">established connection failed because connected host has</span></span>

<span data-ttu-id="f5be4-151">no se pudo responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="f5be4-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="f5be4-152">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="f5be4-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="f5be4-153">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="f5be4-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="f5be4-154">tiempo o error de conexión establecida debido a que el host conectado</span><span class="sxs-lookup"><span data-stu-id="f5be4-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="f5be4-155">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="f5be4-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="f5be4-156">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f5be4-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f5be4-157">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="f5be4-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="f5be4-158">Estas son algunas de las razones comunes por las que **Test-CsXmppIM** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="f5be4-158">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="f5be4-159">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="f5be4-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="f5be4-160">Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="f5be4-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="f5be4-161">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5be4-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="f5be4-162">Este comando producirá un error si la configuración de la puerta de enlace XMPP no se ha configurado correctamente o no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="f5be4-162">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5be4-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5be4-163">See Also</span></span>


[<span data-ttu-id="f5be4-164">Set-CsXmppGatewayConfiguration</span><span class="sxs-lookup"><span data-stu-id="f5be4-164">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

