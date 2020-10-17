---
title: 'Lync Server 2013: prueba de la conexión del usuario al correo de voz de mensajería unificada de Exchange'
description: 'Lync Server 2013: prueba de la conexión del usuario al correo de voz de mensajería unificada de Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b887b5b0df02a5864e0a39f2b62893d20105a86a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552616"
---
# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="3b9f0-103">Prueba de la conexión del usuario al correo de voz de mensajería unificada de Exchange en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b9f0-103">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b9f0-104">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="3b9f0-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b9f0-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="3b9f0-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3b9f0-106">Diario</span><span class="sxs-lookup"><span data-stu-id="3b9f0-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b9f0-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="3b9f0-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3b9f0-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b9f0-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b9f0-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="3b9f0-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3b9f0-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3b9f0-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsExUMVoiceMail</strong> .</span><span class="sxs-lookup"><span data-stu-id="3b9f0-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="3b9f0-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3b9f0-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3b9f0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b9f0-113">Description</span></span>

<span data-ttu-id="3b9f0-114">El cmdlet **Test-CsExUMVoiceMail** permite a los administradores comprobar que un usuario puede tener acceso y usar el servicio de mensajería unificada de Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-114">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="3b9f0-115">Para ello, el cmdlet se conecta al servicio de mensajería unificado y deja un correo de voz en el buzón especificado.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-115">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="3b9f0-116">Este puede ser un correo de voz proporcionado por el sistema o un archivo .WAV personalizado que haya grabado.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-116">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3b9f0-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="3b9f0-117">Running the test</span></span>

<span data-ttu-id="3b9f0-118">En el siguiente ejemplo se comprueba la Conectividad del correo de voz de mensajería unificada de Exchange para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-118">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="3b9f0-119">Este comando solo funcionará si se definieron usuarios de prueba para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="3b9f0-120">Si lo tienen, el comando determinará si el primer usuario de prueba puede usar el correo de voz de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-120">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="3b9f0-121">Si no se han configurado los usuarios de prueba para el grupo, se producirá un error en el comando.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="3b9f0-122">Los comandos que aparecen en el siguiente ejemplo prueban la Conectividad del correo de voz de mensajería unificada de Exchange para el usuario litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-122">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="3b9f0-123">Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credenciales de interfaz de línea de comandos de Windows PowerShell para el usuario litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="3b9f0-124">Tenga en cuenta que debe proporcionar la contraseña de esta cuenta para crear un objeto de credenciales válido y para asegurarse de que el cmdlet **Test-CsExUMVoiceMail** puede ejecutar su comprobación.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="3b9f0-125">El segundo comando del ejemplo usa el objeto de credenciales proporcionado ($x) y la dirección SIP del usuario litwareinc \\ kenmyer para determinar si o este usuario puede conectarse al correo de voz de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="3b9f0-126">El comando que se muestra en el ejemplo siguiente es una variación del comando que se muestra en el ejemplo 1; en este caso, el parámetro OutLoggerVariable se incluye para generar un registro detallado de cada paso realizado por la **prueba-CsExUMVoiceMail** cmdletand el éxito o error de cada uno de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-126">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="3b9f0-127">Para ello, se agrega el parámetro OutLoggerVariable junto con el valor del parámetro ExumText; Esto provoca que la información de registro detallada se almacene en una variable llamada $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-127">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="3b9f0-128">En el comando final del ejemplo, el método ToXML() se utiliza para convertir la información de registro en formato XML.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-128">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="3b9f0-129">A continuación, los datos XML se escriben en un archivo denominado C: \\ registros \\VoicemailTest.xml con el cmdlet Out-File.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-129">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3b9f0-130">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="3b9f0-130">Determining success or failure</span></span>

<span data-ttu-id="3b9f0-131">Si la integración de Exchange está correctamente configurada, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta**:</span><span class="sxs-lookup"><span data-stu-id="3b9f0-131">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="3b9f0-132">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3b9f0-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3b9f0-133">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="3b9f0-133">Result : Success</span></span>

<span data-ttu-id="3b9f0-134">Latencia: 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="3b9f0-134">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="3b9f0-135">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="3b9f0-135">Error Message :</span></span>

<span data-ttu-id="3b9f0-136">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3b9f0-136">Diagnosis :</span></span>

<span data-ttu-id="3b9f0-137">Si el usuario especificado no puede conectarse al correo de voz, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="3b9f0-137">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3b9f0-138">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo</span><span class="sxs-lookup"><span data-stu-id="3b9f0-138">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="3b9f0-139">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="3b9f0-139">domain name (FQDN).</span></span> <span data-ttu-id="3b9f0-140">Se usará el número de puerto del registrador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-140">Using default Registrar port number.</span></span> <span data-ttu-id="3b9f0-141">Excepción</span><span class="sxs-lookup"><span data-stu-id="3b9f0-141">Exception:</span></span>

<span data-ttu-id="3b9f0-142">System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-142">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="3b9f0-143">Veamos</span><span class="sxs-lookup"><span data-stu-id="3b9f0-143">at</span></span>

<span data-ttu-id="3b9f0-144">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="3b9f0-144">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="3b9f0-145">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="3b9f0-145">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="3b9f0-146">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3b9f0-146">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3b9f0-147">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="3b9f0-147">Result : Failure</span></span>

<span data-ttu-id="3b9f0-148">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3b9f0-148">Latency : 00:00:00</span></span>

<span data-ttu-id="3b9f0-149">Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada</span><span class="sxs-lookup"><span data-stu-id="3b9f0-149">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="3b9f0-150">no respondió correctamente después de un período de tiempo o</span><span class="sxs-lookup"><span data-stu-id="3b9f0-150">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="3b9f0-151">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="3b9f0-151">established connection failed because connected host has</span></span>

<span data-ttu-id="3b9f0-152">no se pudo responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="3b9f0-152">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="3b9f0-153">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="3b9f0-153">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="3b9f0-154">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="3b9f0-154">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="3b9f0-155">tiempo o error de conexión establecida debido a que el host conectado</span><span class="sxs-lookup"><span data-stu-id="3b9f0-155">time, or established connection failed because connected host</span></span>

<span data-ttu-id="3b9f0-156">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="3b9f0-156">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="3b9f0-157">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3b9f0-157">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3b9f0-158">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="3b9f0-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="3b9f0-159">Estas son algunas de las razones comunes por las que **Test-CsExUMVoiceMail** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="3b9f0-159">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="3b9f0-160">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="3b9f0-161">Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="3b9f0-162">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="3b9f0-163">Este comando producirá un error si el servidor de Exchange está mal configurado o no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="3b9f0-163">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b9f0-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b9f0-164">See Also</span></span>


[<span data-ttu-id="3b9f0-165">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="3b9f0-165">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

