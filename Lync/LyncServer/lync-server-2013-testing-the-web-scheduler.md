---
title: 'Lync Server 2013: probar el programador web'
description: 'Lync Server 2013: probar el programador web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6512bf074078005eac66d1e4f5cd3d8ba2dc4bc7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556156"
---
# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="1e1c6-103">Probar el programador web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e1c6-103">Testing the Web scheduler in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e1c6-104">_**Última modificación del tema:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="1e1c6-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e1c6-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="1e1c6-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1e1c6-106">Diario</span><span class="sxs-lookup"><span data-stu-id="1e1c6-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e1c6-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="1e1c6-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1e1c6-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e1c6-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e1c6-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="1e1c6-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1e1c6-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1e1c6-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsWebScheduler</strong> .</span><span class="sxs-lookup"><span data-stu-id="1e1c6-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="1e1c6-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1e1c6-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1e1c6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e1c6-113">Description</span></span>

<span data-ttu-id="1e1c6-114">El cmdlet **Test-CsWebScheduler** permite determinar si un usuario específico puede programar una reunión con el programador web.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-114">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="1e1c6-115">El programador web permite a los usuarios que no ejecutan Outlook programar reuniones en línea.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-115">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="1e1c6-116">Entre otras cosas, esta nueva característica (que incorpora la funcionalidad que se encuentra en la herramienta de programador web incluida en el kit de recursos de Microsoft Lync Server 2010) permite a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="1e1c6-116">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="1e1c6-117">Programar una nueva reunión en línea.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-117">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="1e1c6-118">Enumerar todas las reuniones que él o ella ha programado.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-118">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="1e1c6-119">Ver o modificar una reunión existente.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-119">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="1e1c6-120">Eliminar una reunión existente.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-120">Delete an existing meeting.</span></span>

  - <span data-ttu-id="1e1c6-121">Enviar una invitación por correo electrónico a los participantes en la reunión mediante un servidor de correo SMTP configurado previamente.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-121">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="1e1c6-122">Unirse a una llamada de conferencia existente.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-122">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1e1c6-123">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="1e1c6-123">Running the test</span></span>

<span data-ttu-id="1e1c6-124">En el siguiente ejemplo se comprueba el programador web del grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-124">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="1e1c6-125">Este comando funcionará solo si los usuarios de prueba están definidos para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-125">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="1e1c6-126">Si lo tienen, el comando determinará si el primer usuario de prueba puede programar una reunión en línea mediante el programador web.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-126">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="1e1c6-127">Si no se definen los usuarios de prueba, se producirá un error en el comando porque no sabrá en qué usuario se inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-127">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="1e1c6-128">Si no ha definido usuarios de prueba para un grupo de servidores, debe incluir el parámetro UserSipAddress y las credenciales del usuario que el comando debe usar al intentar iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-128">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="1e1c6-129">Los comandos que se muestran en el siguiente ejemplo prueban la capacidad de un usuario específico (litwareinc \\ kenmeyer) para programar una reunión en línea mediante el programador web.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-129">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="1e1c6-130">Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-130">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="1e1c6-131">(Como el nombre de inicio de sesión litwareinc \\ kenmeyer se incluye como un parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Ken Meyer). El objeto Credential resultante se almacena en una variable llamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-131">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="1e1c6-132">A continuación, el segundo comando comprueba si este usuario puede iniciar sesión en el grupo atl-cs-001.litwareinc.com y programar una reunión en línea.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-132">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="1e1c6-133">Para ejecutar esta tarea, se llama al cmdlet **Test-CsWebScheduler** , junto con tres parámetros: TargetFqdn (el FQDN del grupo de registrador); UserCredential (el objeto de Windows PowerShell que contiene las credenciales de usuario de Pilar Ackerman); y UserSipAddress (la dirección SIP que corresponde a las credenciales de usuario suministradas).</span><span class="sxs-lookup"><span data-stu-id="1e1c6-133">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1e1c6-134">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="1e1c6-134">Determining success or failure</span></span>

<span data-ttu-id="1e1c6-135">Si el programador web está configurado correctamente, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta**:</span><span class="sxs-lookup"><span data-stu-id="1e1c6-135">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="1e1c6-136">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1e1c6-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1e1c6-137">URI de destino: https://atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-137">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="1e1c6-138">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="1e1c6-138">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="1e1c6-139">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="1e1c6-139">Result : Success</span></span>

<span data-ttu-id="1e1c6-140">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="1e1c6-140">Latency : 00:00:00</span></span>

<span data-ttu-id="1e1c6-141">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="1e1c6-141">Error Message :</span></span>

<span data-ttu-id="1e1c6-142">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1e1c6-142">Diagnosis :</span></span>

<span data-ttu-id="1e1c6-143">Si el programador web no está configurado correctamente, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="1e1c6-143">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="1e1c6-144">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo</span><span class="sxs-lookup"><span data-stu-id="1e1c6-144">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="1e1c6-145">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="1e1c6-145">domain name (FQDN).</span></span> <span data-ttu-id="1e1c6-146">Se usará el número de puerto del registrador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-146">Using default Registrar port number.</span></span> <span data-ttu-id="1e1c6-147">Excepción</span><span class="sxs-lookup"><span data-stu-id="1e1c6-147">Exception:</span></span>

<span data-ttu-id="1e1c6-148">System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-148">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="1e1c6-149">Veamos</span><span class="sxs-lookup"><span data-stu-id="1e1c6-149">at</span></span>

<span data-ttu-id="1e1c6-150">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="1e1c6-150">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="1e1c6-151">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="1e1c6-151">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="1e1c6-152">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1e1c6-152">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1e1c6-153">URI de destino:</span><span class="sxs-lookup"><span data-stu-id="1e1c6-153">Target Uri :</span></span>

<span data-ttu-id="1e1c6-154">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="1e1c6-154">Result : Failure</span></span>

<span data-ttu-id="1e1c6-155">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="1e1c6-155">Latency : 00:00:00</span></span>

<span data-ttu-id="1e1c6-156">Mensaje de error: no se encontró ningún clúster que coincida en la topología.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-156">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="1e1c6-157">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1e1c6-157">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1e1c6-158">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="1e1c6-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="1e1c6-159">Estas son algunas de las razones comunes por las que **Test-CsWebScheduler** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="1e1c6-159">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="1e1c6-160">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="1e1c6-161">Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="1e1c6-162">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="1e1c6-163">Este comando producirá un error si el programador web está mal configurado o no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="1e1c6-163">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e1c6-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e1c6-164">See Also</span></span>


[<span data-ttu-id="1e1c6-165">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="1e1c6-165">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

