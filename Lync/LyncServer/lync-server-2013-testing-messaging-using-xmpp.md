---
title: 'Lync Server 2013: probar la mensajería mediante XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acd03cdf2a5215c980b788dbaffafc5936fe5b5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="b4b92-102">Probar la mensajería con XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4b92-102">Testing messaging using XMPP in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4b92-103">_**Última modificación del tema:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="b4b92-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4b92-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="b4b92-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b4b92-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="b4b92-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b92-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="b4b92-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b4b92-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4b92-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b92-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="b4b92-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b4b92-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b4b92-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b4b92-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsXmppIM</strong> .</span><span class="sxs-lookup"><span data-stu-id="b4b92-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="b4b92-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4b92-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b4b92-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4b92-112">Description</span></span>

<span data-ttu-id="b4b92-113">El protocolo de presencia y mensajería extensible (XMPP) es un protocolo de comunicaciones estándar (basado en XML) que se usa para enviar mensajes a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="b4b92-113">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="b4b92-114">XMPP se llamaba originalmente Jabber y es compatible con varias aplicaciones de mensajería y comunicaciones de Internet, como Google Talk y la conversación de Facebook.</span><span class="sxs-lookup"><span data-stu-id="b4b92-114">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="b4b92-115">El cmdlet **Test-CsXmppIM** verifica que un usuario puede intercambiar mensajes instantáneos con un usuario en una red XMPP.</span><span class="sxs-lookup"><span data-stu-id="b4b92-115">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="b4b92-116">Tenga en cuenta que, para que esta prueba se realice correctamente, debe tener una dirección SIP válida para el usuario de XMPP, y esa dirección SIP debe estar en una red que se haya configurado como socio XMPP autorizado.</span><span class="sxs-lookup"><span data-stu-id="b4b92-116">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b4b92-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="b4b92-117">Running the test</span></span>

<span data-ttu-id="b4b92-118">En el ejemplo siguiente se comprueban las capacidades de mensajería instantánea de XMPP para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b4b92-118">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b4b92-119">Este comando solo funciona si se han definido usuarios de prueba para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b4b92-119">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b4b92-120">De ser así, el comando determinará si el primer usuario de prueba puede enviar un mensaje instantáneo XMPP a un usuario que tenga la dirección SIP adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b4b92-120">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="b4b92-121">Si no se definen los usuarios de prueba, el comando fallará porque no sabrá en qué usuario iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="b4b92-121">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="b4b92-122">Si no ha definido usuarios de prueba para un grupo, debe incluir el parámetro UserSipAddress y las credenciales del usuario que debe usar el comando al intentar iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="b4b92-122">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="b4b92-123">Los comandos que se muestran en el siguiente ejemplo prueban la capacidad de un usuario\\específico (litwareinc Pilar) para iniciar sesión y enviar un mensaje instantáneo XMPP a la adelaney@contoso.com de usuario.</span><span class="sxs-lookup"><span data-stu-id="b4b92-123">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="b4b92-124">Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="b4b92-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="b4b92-125">(Como el nombre de inicio\\de sesión litwareinc Pilar se incluyó como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta de Pilar Ackerman). El objeto de credencial resultante se almacena en una variable llamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="b4b92-125">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="b4b92-126">El segundo comando comprueba si este usuario puede iniciar sesión en el grupo atl-cs-001.litwareinc.com y enviar el mensaje instantáneo XMPP.</span><span class="sxs-lookup"><span data-stu-id="b4b92-126">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="b4b92-127">Para ejecutar esta tarea, se llama al cmdlet **Test-CsXmppIm** , junto con cuatro parámetros: TargetFqdn (el FQDN del grupo de servidores de registrar); Receptor (la dirección SIP del usuario al que se dirige el mensaje); UserCredential (el objeto de Windows PowerShell que contiene las credenciales de usuario de Pilar Ackerman); y UserSipAddress (la dirección SIP que corresponde a las credenciales de usuario suministradas).</span><span class="sxs-lookup"><span data-stu-id="b4b92-127">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b4b92-128">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="b4b92-128">Determining success or failure</span></span>

<span data-ttu-id="b4b92-129">Si la mensajería instantánea XMPP está configurada correctamente, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="b4b92-129">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b4b92-130">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b4b92-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b4b92-131">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="b4b92-131">Result : Success</span></span>

<span data-ttu-id="b4b92-132">Latencia: 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="b4b92-132">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="b4b92-133">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="b4b92-133">Error Message :</span></span>

<span data-ttu-id="b4b92-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b4b92-134">Diagnosis :</span></span>

<span data-ttu-id="b4b92-135">Si los usuarios especificados no pueden usar la mensajería instantánea de XMPP, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="b4b92-135">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b4b92-136">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el nombre completo</span><span class="sxs-lookup"><span data-stu-id="b4b92-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="b4b92-137">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="b4b92-137">domain name (FQDN).</span></span> <span data-ttu-id="b4b92-138">Usando el número de puerto predeterminado del registrador.</span><span class="sxs-lookup"><span data-stu-id="b4b92-138">Using default Registrar port number.</span></span> <span data-ttu-id="b4b92-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="b4b92-139">Exception:</span></span>

<span data-ttu-id="b4b92-140">System. InvalidOperationException: no se encontró ningún clúster coincidente en la topología.</span><span class="sxs-lookup"><span data-stu-id="b4b92-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="b4b92-141">en</span><span class="sxs-lookup"><span data-stu-id="b4b92-141">at</span></span>

<span data-ttu-id="b4b92-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="b4b92-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="b4b92-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="b4b92-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="b4b92-144">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b4b92-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b4b92-145">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="b4b92-145">Result : Failure</span></span>

<span data-ttu-id="b4b92-146">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b4b92-146">Latency : 00:00:00</span></span>

<span data-ttu-id="b4b92-147">Mensaje de error: 10060, error al intentar la conexión porque la persona conectada</span><span class="sxs-lookup"><span data-stu-id="b4b92-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="b4b92-148">no respondió correctamente después de un período de tiempo, o</span><span class="sxs-lookup"><span data-stu-id="b4b92-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="b4b92-149">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="b4b92-149">established connection failed because connected host has</span></span>

<span data-ttu-id="b4b92-150">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b4b92-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b4b92-151">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="b4b92-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="b4b92-152">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="b4b92-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="b4b92-153">hora o error de conexión establecida porque el host conectado</span><span class="sxs-lookup"><span data-stu-id="b4b92-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="b4b92-154">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b4b92-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b4b92-155">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b4b92-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b4b92-156">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="b4b92-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="b4b92-157">Estas son algunas de las razones comunes por las que **Test-CsXmppIM** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="b4b92-157">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="b4b92-158">Se proporcionó un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="b4b92-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b4b92-159">Si se usa, los parámetros opcionales deben estar configurados correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="b4b92-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b4b92-160">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4b92-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="b4b92-161">Este comando fallará si la configuración de la puerta de enlace XMPP no se ha configurado correctamente o si aún no se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="b4b92-161">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4b92-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4b92-162">See Also</span></span>


[<span data-ttu-id="b4b92-163">Set-CsXmppGatewayConfiguration</span><span class="sxs-lookup"><span data-stu-id="b4b92-163">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

