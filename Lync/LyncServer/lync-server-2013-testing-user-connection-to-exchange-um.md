---
title: 'Lync Server 2013: probar la conexión de usuario para la mensajería unificada de Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d4a4c4194ad730a64b167aaaf33151c8a7684e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="4a79e-102">Probar la conexión de usuario a la mensajería unificada de Exchange en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a79e-102">Testing user connection to Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a79e-103">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="4a79e-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a79e-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="4a79e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4a79e-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="4a79e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a79e-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="4a79e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4a79e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a79e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a79e-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="4a79e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4a79e-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4a79e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4a79e-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsExUMConnectivity</strong> .</span><span class="sxs-lookup"><span data-stu-id="4a79e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="4a79e-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4a79e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4a79e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a79e-112">Description</span></span>

<span data-ttu-id="4a79e-113">El cmdlet **Test-CsExUMConnectivity** comprueba que el usuario especificado puede conectarse al servicio de mensajería unificada de Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a79e-113">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="4a79e-114">Tenga en cuenta que este cmdlet solo comprueba que se puede establecer una conexión con el servicio.</span><span class="sxs-lookup"><span data-stu-id="4a79e-114">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="4a79e-115">No prueba el servicio en sí.</span><span class="sxs-lookup"><span data-stu-id="4a79e-115">It does not test the service itself.</span></span> <span data-ttu-id="4a79e-116">Para probar el servicio de mensajería unificada (ejecutando un cmdlet de transacción sintética que realmente deja un mensaje de correo de voz en el buzón de un usuario) Use el cmdlet test-CsExUMVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="4a79e-116">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4a79e-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="4a79e-117">Running the test</span></span>

<span data-ttu-id="4a79e-118">En el siguiente ejemplo se prueba la conectividad de la mensajería unificada de Exchange para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4a79e-118">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="4a79e-119">Este comando solo funcionará si se definieron usuarios de prueba para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4a79e-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="4a79e-120">De ser así, el comando determinará si el primer usuario de prueba puede conectarse a la mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="4a79e-120">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="4a79e-121">Si no se han configurado los usuarios de prueba para el grupo, el comando fallará.</span><span class="sxs-lookup"><span data-stu-id="4a79e-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="4a79e-122">Los comandos que se muestran en el siguiente ejemplo prueban la conectividad de la mensajería\\unificada de Exchange para el usuario litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="4a79e-122">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="4a79e-123">Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credenciales de la interfaz de línea de comandos de Windows PowerShell\\para el usuario litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="4a79e-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="4a79e-124">Tenga en cuenta que debe proporcionar la contraseña de esta cuenta para crear un objeto de credenciales válido y asegurarse de que el cmdlet **Test-CsExUMConnectivity** puede ejecutar su comprobación.</span><span class="sxs-lookup"><span data-stu-id="4a79e-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="4a79e-125">El segundo comando del ejemplo usa el objeto de credenciales proporcionado ($x) y la dirección SIP del usuario litwareinc\\kenmyer para determinar si este usuario puede conectarse a la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="4a79e-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="4a79e-126">El comando que se muestra en el ejemplo siguiente es una variación del comando que se acaba de mostrar.</span><span class="sxs-lookup"><span data-stu-id="4a79e-126">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="4a79e-127">En este caso, se incluye el parámetro OutLoggerVariable para generar un registro detallado de cada paso realizado por la **CsExUMConnectivity de prueba** cmdletand el éxito o el fracaso de cada uno de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4a79e-127">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="4a79e-128">Para ello, se agrega el parámetro OutLoggerVariable junto con el valor de parámetro ExumText; Esto provoca que la información de registro detallada se almacene en una variable denominada $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="4a79e-128">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="4a79e-129">En el último comando del ejemplo, el método ToXML () se usa para convertir la información de registro a formato XML.</span><span class="sxs-lookup"><span data-stu-id="4a79e-129">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="4a79e-130">Esos datos XML se escriben en un archivo denominado C:\\registra\\ExumTest. XML mediante el cmdlet out-File.</span><span class="sxs-lookup"><span data-stu-id="4a79e-130">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4a79e-131">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="4a79e-131">Determining success or failure</span></span>

<span data-ttu-id="4a79e-132">Si la integración de Exchange se ha configurado correctamente, recibirá un resultado similar a este, con la propiedad result marcada como **correcta**:</span><span class="sxs-lookup"><span data-stu-id="4a79e-132">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="4a79e-133">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4a79e-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4a79e-134">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="4a79e-134">Result : Success</span></span>

<span data-ttu-id="4a79e-135">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="4a79e-135">Latency : 00:00:00</span></span>

<span data-ttu-id="4a79e-136">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="4a79e-136">Error Message :</span></span>

<span data-ttu-id="4a79e-137">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="4a79e-137">Diagnosis :</span></span>

<span data-ttu-id="4a79e-138">Si el usuario especificado no puede recibir notificaciones, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="4a79e-138">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="4a79e-139">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4a79e-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4a79e-140">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="4a79e-140">Result : Failure</span></span>

<span data-ttu-id="4a79e-141">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="4a79e-141">Latency : 00:00:00</span></span>

<span data-ttu-id="4a79e-142">Mensaje de error: 10060, error al intentar la conexión porque la persona conectada</span><span class="sxs-lookup"><span data-stu-id="4a79e-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="4a79e-143">no respondió correctamente después de un período de tiempo, o</span><span class="sxs-lookup"><span data-stu-id="4a79e-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="4a79e-144">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="4a79e-144">established connection failed because connected host has</span></span>

<span data-ttu-id="4a79e-145">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="4a79e-145">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="4a79e-146">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="4a79e-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="4a79e-147">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="4a79e-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="4a79e-148">hora o error de conexión establecida porque el host conectado</span><span class="sxs-lookup"><span data-stu-id="4a79e-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="4a79e-149">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="4a79e-149">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="4a79e-150">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="4a79e-150">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4a79e-151">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="4a79e-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="4a79e-152">Estas son algunas de las razones comunes por las que **Test-CsExUMConnectivity** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="4a79e-152">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="4a79e-153">Se proporcionó un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="4a79e-153">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="4a79e-154">Si se usa, los parámetros opcionales deben estar configurados correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="4a79e-154">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="4a79e-155">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="4a79e-155">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="4a79e-156">Este comando fallará si el servidor de Exchange está mal configurado o aún no se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="4a79e-156">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="4a79e-157">Este comando fallará si no se puede comunicar con el servidor de Exchange a través de la red.</span><span class="sxs-lookup"><span data-stu-id="4a79e-157">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4a79e-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a79e-158">See Also</span></span>


[<span data-ttu-id="4a79e-159">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="4a79e-159">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

