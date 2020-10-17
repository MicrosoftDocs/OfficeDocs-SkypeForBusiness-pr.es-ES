---
title: 'Lync Server 2013: pruebas de uso compartido en conferencias'
description: 'Lync Server 2013: pruebas de uso compartido en conferencias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e569a97d102664b64c201af9b60061813df69ef5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556246"
---
# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="7dec7-103">Probar el uso compartido en conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dec7-103">Testing sharing in conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dec7-104">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="7dec7-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7dec7-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="7dec7-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7dec7-106">Diario</span><span class="sxs-lookup"><span data-stu-id="7dec7-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dec7-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="7dec7-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7dec7-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7dec7-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dec7-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="7dec7-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7dec7-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7dec7-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7dec7-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsDataConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="7dec7-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="7dec7-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7dec7-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7dec7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7dec7-113">Description</span></span>

<span data-ttu-id="7dec7-114">En Lync Server 2013, una conferencia de datos es cualquier conferencia en la que se usan actividades de colaboración, como la pizarra o las anotaciones.</span><span class="sxs-lookup"><span data-stu-id="7dec7-114">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="7dec7-115">El cmdlet **Test-CsDataConference** le permite comprobar que un par de usuarios pueden participar en una conferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="7dec7-115">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7dec7-116">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="7dec7-116">Running the test</span></span>

<span data-ttu-id="7dec7-p103">El comando que se muestra en el ejemplo 1 comprueba que se puede llevar a cabo una conferencia de datos en el grupo atl-cs-001.litwareinc.com. Este comando asume que ha configurado un par de usuarios de prueba para el grupo especificado. Si los usuarios de prueba no existen, se producirá un error en el comando.</span><span class="sxs-lookup"><span data-stu-id="7dec7-p103">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="7dec7-120">Los comandos que se muestran en el ejemplo 2 prueban la capacidad de un par de usuarios (litwareinc \\ Pilar y litwareinc \\ kenmyer) para iniciar sesión en Lync Server 2013 y, a continuación, realizar una conferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="7dec7-120">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="7dec7-121">Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="7dec7-121">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="7dec7-122">(Como el nombre de inicio de sesión, litwareinc \\ pilar, se ha incluido como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Pilar Ackerman). El objeto Credential resultante se almacena en una variable llamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="7dec7-122">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="7dec7-123">El segundo comando realiza la misma acción pero, esta vez, devuelve un objeto de credenciales de la cuenta de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="7dec7-123">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="7dec7-124">Con los objetos de credenciales a mano, el tercer comando determina si estos dos usuarios pueden iniciar sesión en Lync Server 2013 y realizar una conferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="7dec7-124">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="7dec7-125">Para llevar a cabo esta tarea, se llama al cmdlet **Test-CsDataConference** , junto con los siguientes parámetros: TargetFqdn (el FQDN del grupo de registrador); SenderSipAddress (la dirección SIP del primer usuario de prueba); SenderCredential (el objeto de Windows PowerShell que contiene las credenciales para este mismo usuario); ReceiverSipAddress (la dirección SIP del otro usuario de prueba); y ReceiverCredential (el objeto de Windows PowerShell que contiene las credenciales del otro usuario de prueba).</span><span class="sxs-lookup"><span data-stu-id="7dec7-125">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7dec7-126">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="7dec7-126">Determining success or failure</span></span>

<span data-ttu-id="7dec7-127">Si la Conferencia de datos está correctamente configurada, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="7dec7-127">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="7dec7-128">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7dec7-128">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7dec7-129">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="7dec7-129">Result : Success</span></span>

<span data-ttu-id="7dec7-130">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7dec7-130">Latency : 00:00:00</span></span>

<span data-ttu-id="7dec7-131">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="7dec7-131">Error Message :</span></span>

<span data-ttu-id="7dec7-132">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7dec7-132">Diagnosis :</span></span>

<span data-ttu-id="7dec7-133">Si los usuarios especificados no pueden usar el uso compartido de datos, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="7dec7-133">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="7dec7-134">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7dec7-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7dec7-135">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="7dec7-135">Result : Failure</span></span>

<span data-ttu-id="7dec7-136">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7dec7-136">Latency : 00:00:00</span></span>

<span data-ttu-id="7dec7-137">Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada</span><span class="sxs-lookup"><span data-stu-id="7dec7-137">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="7dec7-138">no respondió correctamente después de un período de tiempo o</span><span class="sxs-lookup"><span data-stu-id="7dec7-138">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="7dec7-139">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="7dec7-139">established connection failed because connected host has</span></span>

<span data-ttu-id="7dec7-140">no se pudo responder \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="7dec7-140">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="7dec7-141">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="7dec7-141">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="7dec7-142">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="7dec7-142">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="7dec7-143">tiempo o error de conexión establecida debido a que el host conectado</span><span class="sxs-lookup"><span data-stu-id="7dec7-143">time, or established connection failed because connected host</span></span>

<span data-ttu-id="7dec7-144">no respondió</span><span class="sxs-lookup"><span data-stu-id="7dec7-144">has failed to respond</span></span>

<span data-ttu-id="7dec7-145">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="7dec7-145">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="7dec7-146">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7dec7-146">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7dec7-147">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="7dec7-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="7dec7-148">Estas son algunas de las razones comunes por las que **Test-CsDataConference** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="7dec7-148">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="7dec7-149">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="7dec7-149">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="7dec7-150">Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="7dec7-150">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="7dec7-151">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="7dec7-151">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="7dec7-152">La capacidad de llevar a cabo una conferencia de datos depende de la Directiva de conferencia asignada al usuario que organizó la Conferencia (en el caso del cmdlet **Test-CsDataConference** , que es el "remitente").</span><span class="sxs-lookup"><span data-stu-id="7dec7-152">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="7dec7-153">Si el organizador no puede incluir actividades colaborativas en su reunión (por ejemplo, si su Directiva de conferencia tiene la propiedad EnableDataCollaboration establecida en false), se producirá un error en el cmdlet **Test-CsDataConference** .</span><span class="sxs-lookup"><span data-stu-id="7dec7-153">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="7dec7-154">Este comando producirá un error si el servidor perimetral está mal configurado o no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="7dec7-154">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

