---
title: 'Lync Server 2013: prueba de la conexión del usuario a la mensajería unificada de Exchange'
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
ms.openlocfilehash: 9cf7189df06549a3008fd86b9395617c6aea3e98
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="6b5f4-102">Prueba de la conexión del usuario a la mensajería unificada de Exchange en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b5f4-102">Testing user connection to Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b5f4-103">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="6b5f4-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b5f4-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="6b5f4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6b5f4-105">Diario</span><span class="sxs-lookup"><span data-stu-id="6b5f4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b5f4-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="6b5f4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6b5f4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b5f4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b5f4-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="6b5f4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6b5f4-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6b5f4-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsExUMConnectivity</strong> .</span><span class="sxs-lookup"><span data-stu-id="6b5f4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="6b5f4-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6b5f4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6b5f4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b5f4-112">Description</span></span>

<span data-ttu-id="6b5f4-113">El cmdlet **Test-CsExUMConnectivity** comprueba que el usuario especificado puede conectarse al servicio de mensajería unificada 2013 de Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-113">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="6b5f4-114">Tenga en cuenta que este cmdlet solo comprueba que se puede establecer una conexión con el servicio.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-114">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="6b5f4-115">No prueba el servicio en sí.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-115">It does not test the service itself.</span></span> <span data-ttu-id="6b5f4-116">Para probar el servicio de mensajes unificados (al ejecutar un cmdlet de transacción sintética que realmente deje un mensaje de voz en el buzón de un usuario) utilice el cmdlet Test-CsExUMVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-116">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6b5f4-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="6b5f4-117">Running the test</span></span>

<span data-ttu-id="6b5f4-118">En el siguiente ejemplo se comprueba la conectividad de mensajería unificada de Exchange para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-118">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="6b5f4-119">Este comando solo funcionará si se definieron usuarios de prueba para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="6b5f4-120">Si lo tienen, el comando determinará si el primer usuario de prueba se puede conectar a la mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-120">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="6b5f4-121">Si no se han configurado los usuarios de prueba para el grupo, se producirá un error en el comando.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="6b5f4-122">Los comandos que se muestran en el siguiente ejemplo prueban la conectividad de la mensajería\\unificada de Exchange para el usuario litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-122">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="6b5f4-123">Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credenciales de interfaz de línea de comandos de Windows PowerShell para\\el usuario litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="6b5f4-124">Tenga en cuenta que debe proporcionar la contraseña de esta cuenta para crear un objeto de credenciales válido y para asegurarse de que el cmdlet **Test-CsExUMConnectivity** puede ejecutar su comprobación.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="6b5f4-125">El segundo comando del ejemplo usa el objeto de credenciales proporcionado ($x) y la dirección SIP del usuario litwareinc\\kenmyer para determinar si o este usuario puede conectarse a la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="6b5f4-126">El comando que se muestra en el siguiente ejemplo es una variación del comando que se acaba de mostrar.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-126">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="6b5f4-127">En este caso, el parámetro OutLoggerVariable se incluye para generar un registro detallado de cada paso realizado por la **prueba-CsExUMConnectivity** cmdletand el éxito o error de cada uno de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-127">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="6b5f4-128">Para ello, se agrega el parámetro OutLoggerVariable junto con el valor de parámetro ExumText; Esto provoca que la información de registro detallada se almacene en una variable llamada $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-128">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="6b5f4-129">En el comando final del ejemplo, el método ToXML() se utiliza para convertir la información de registro en formato XML.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-129">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="6b5f4-130">A continuación, los datos XML se escriben en un archivo denominado C\\:\\registra ExumTest. XML mediante el cmdlet out-File.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-130">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6b5f4-131">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="6b5f4-131">Determining success or failure</span></span>

<span data-ttu-id="6b5f4-132">Si la integración de Exchange está correctamente configurada, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta**:</span><span class="sxs-lookup"><span data-stu-id="6b5f4-132">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="6b5f4-133">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6b5f4-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6b5f4-134">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="6b5f4-134">Result : Success</span></span>

<span data-ttu-id="6b5f4-135">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6b5f4-135">Latency : 00:00:00</span></span>

<span data-ttu-id="6b5f4-136">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="6b5f4-136">Error Message :</span></span>

<span data-ttu-id="6b5f4-137">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="6b5f4-137">Diagnosis :</span></span>

<span data-ttu-id="6b5f4-138">Si el usuario especificado no puede recibir notificaciones, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="6b5f4-138">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6b5f4-139">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6b5f4-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6b5f4-140">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="6b5f4-140">Result : Failure</span></span>

<span data-ttu-id="6b5f4-141">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6b5f4-141">Latency : 00:00:00</span></span>

<span data-ttu-id="6b5f4-142">Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada</span><span class="sxs-lookup"><span data-stu-id="6b5f4-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="6b5f4-143">no respondió correctamente después de un período de tiempo o</span><span class="sxs-lookup"><span data-stu-id="6b5f4-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="6b5f4-144">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="6b5f4-144">established connection failed because connected host has</span></span>

<span data-ttu-id="6b5f4-145">no se pudo responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="6b5f4-145">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="6b5f4-146">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="6b5f4-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="6b5f4-147">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="6b5f4-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="6b5f4-148">tiempo o error de conexión establecida debido a que el host conectado</span><span class="sxs-lookup"><span data-stu-id="6b5f4-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="6b5f4-149">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="6b5f4-149">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="6b5f4-150">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="6b5f4-150">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6b5f4-151">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="6b5f4-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="6b5f4-152">Estas son algunas de las razones comunes por las que **Test-CsExUMConnectivity** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="6b5f4-152">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="6b5f4-153">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-153">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="6b5f4-154">Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-154">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="6b5f4-155">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-155">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="6b5f4-156">Este comando producirá un error si el servidor de Exchange está mal configurado o no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-156">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="6b5f4-157">Este comando producirá un error si el servidor de Exchange no es accesible a través de la red.</span><span class="sxs-lookup"><span data-stu-id="6b5f4-157">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6b5f4-158">Consulta también</span><span class="sxs-lookup"><span data-stu-id="6b5f4-158">See Also</span></span>


[<span data-ttu-id="6b5f4-159">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="6b5f4-159">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

