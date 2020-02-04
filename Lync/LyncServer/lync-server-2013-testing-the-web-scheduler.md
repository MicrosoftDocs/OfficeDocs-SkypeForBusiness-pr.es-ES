---
title: 'Lync Server 2013: probar el programador web'
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
ms.openlocfilehash: 65d7dc70bad90dc4e4c94e2db273f44ed20c50ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="ea84b-102">Probar el programador web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea84b-102">Testing the Web scheduler in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea84b-103">_**Última modificación del tema:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="ea84b-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea84b-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="ea84b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ea84b-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="ea84b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea84b-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="ea84b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ea84b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea84b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea84b-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="ea84b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ea84b-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ea84b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ea84b-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsWebScheduler</strong> .</span><span class="sxs-lookup"><span data-stu-id="ea84b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="ea84b-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ea84b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ea84b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea84b-112">Description</span></span>

<span data-ttu-id="ea84b-113">El cmdlet **Test-CsWebScheduler** le permite determinar si un usuario específico puede programar una reunión con el programador web.</span><span class="sxs-lookup"><span data-stu-id="ea84b-113">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="ea84b-114">El programador web permite a los usuarios que no ejecutan Outlook programar reuniones en línea.</span><span class="sxs-lookup"><span data-stu-id="ea84b-114">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="ea84b-115">Entre otras cosas, esta nueva característica (que incorpora la funcionalidad que se encuentra en la herramienta de programador web que se incluía con el kit de recursos de Microsoft Lync Server 2010) permite a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="ea84b-115">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="ea84b-116">Programe una nueva reunión en línea.</span><span class="sxs-lookup"><span data-stu-id="ea84b-116">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="ea84b-117">Enumere todas las reuniones que ha programado.</span><span class="sxs-lookup"><span data-stu-id="ea84b-117">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="ea84b-118">Ver o modificar una reunión existente.</span><span class="sxs-lookup"><span data-stu-id="ea84b-118">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="ea84b-119">Eliminar una reunión existente.</span><span class="sxs-lookup"><span data-stu-id="ea84b-119">Delete an existing meeting.</span></span>

  - <span data-ttu-id="ea84b-120">Enviar una invitación por correo electrónico a los participantes de la reunión mediante un servidor de correo SMTP preconfigurado.</span><span class="sxs-lookup"><span data-stu-id="ea84b-120">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="ea84b-121">Unirse a una conferencia existente.</span><span class="sxs-lookup"><span data-stu-id="ea84b-121">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ea84b-122">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="ea84b-122">Running the test</span></span>

<span data-ttu-id="ea84b-123">En el siguiente ejemplo se comprueba el programador web para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ea84b-123">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="ea84b-124">Este comando solo funciona si se han definido usuarios de prueba para el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ea84b-124">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="ea84b-125">En ese caso, el comando determinará si el primer usuario de prueba puede programar una reunión en línea mediante el programador web.</span><span class="sxs-lookup"><span data-stu-id="ea84b-125">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="ea84b-126">Si no se definen los usuarios de prueba, el comando fallará porque no sabrá en qué usuario iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="ea84b-126">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="ea84b-127">Si no ha definido usuarios de prueba para un grupo, debe incluir el parámetro UserSipAddress y las credenciales del usuario que el comando debe usar al intentar iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="ea84b-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="ea84b-128">Los comandos que se muestran en el siguiente ejemplo prueban la capacidad de un usuario\\específico (litwareinc kenmeyer) para programar una reunión en línea mediante el programador web.</span><span class="sxs-lookup"><span data-stu-id="ea84b-128">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="ea84b-129">Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="ea84b-129">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="ea84b-130">(Dado que el nombre de\\inicio de sesión litwareinc kenmeyer se incluye como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Ken Meyer). El objeto de credencial resultante se almacena en una variable llamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="ea84b-130">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="ea84b-131">El segundo comando comprueba si este usuario puede iniciar sesión en el grupo de atl-cs-001.litwareinc.com y programar una reunión en línea.</span><span class="sxs-lookup"><span data-stu-id="ea84b-131">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="ea84b-132">Para ejecutar esta tarea, se llama al cmdlet **Test-CsWebScheduler** , junto con tres parámetros: TargetFqdn (el FQDN del grupo de servidores de registrar); UserCredential (el objeto de Windows PowerShell que contiene las credenciales de usuario de Pilar Ackerman); y UserSipAddress (la dirección SIP que corresponde a las credenciales de usuario suministradas).</span><span class="sxs-lookup"><span data-stu-id="ea84b-132">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ea84b-133">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="ea84b-133">Determining success or failure</span></span>

<span data-ttu-id="ea84b-134">Si el programador web está configurado correctamente, recibirá un resultado similar a este, con la propiedad result marcada como **correcta**:</span><span class="sxs-lookup"><span data-stu-id="ea84b-134">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="ea84b-135">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ea84b-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ea84b-136">URI de destino: https://atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ea84b-136">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="ea84b-137">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="ea84b-137">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="ea84b-138">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="ea84b-138">Result : Success</span></span>

<span data-ttu-id="ea84b-139">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ea84b-139">Latency : 00:00:00</span></span>

<span data-ttu-id="ea84b-140">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="ea84b-140">Error Message :</span></span>

<span data-ttu-id="ea84b-141">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ea84b-141">Diagnosis :</span></span>

<span data-ttu-id="ea84b-142">Si el programador web no está configurado correctamente, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="ea84b-142">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ea84b-143">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el nombre completo</span><span class="sxs-lookup"><span data-stu-id="ea84b-143">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="ea84b-144">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="ea84b-144">domain name (FQDN).</span></span> <span data-ttu-id="ea84b-145">Usando el número de puerto predeterminado del registrador.</span><span class="sxs-lookup"><span data-stu-id="ea84b-145">Using default Registrar port number.</span></span> <span data-ttu-id="ea84b-146">Excepción</span><span class="sxs-lookup"><span data-stu-id="ea84b-146">Exception:</span></span>

<span data-ttu-id="ea84b-147">System. InvalidOperationException: no se encontró ningún clúster coincidente en la topología.</span><span class="sxs-lookup"><span data-stu-id="ea84b-147">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="ea84b-148">en</span><span class="sxs-lookup"><span data-stu-id="ea84b-148">at</span></span>

<span data-ttu-id="ea84b-149">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="ea84b-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="ea84b-150">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="ea84b-150">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="ea84b-151">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ea84b-151">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ea84b-152">URI de destino:</span><span class="sxs-lookup"><span data-stu-id="ea84b-152">Target Uri :</span></span>

<span data-ttu-id="ea84b-153">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="ea84b-153">Result : Failure</span></span>

<span data-ttu-id="ea84b-154">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ea84b-154">Latency : 00:00:00</span></span>

<span data-ttu-id="ea84b-155">Mensaje de error: no se encontró ningún clúster coincidente en la topología.</span><span class="sxs-lookup"><span data-stu-id="ea84b-155">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="ea84b-156">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ea84b-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ea84b-157">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="ea84b-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="ea84b-158">Estas son algunas de las razones comunes por las que **Test-CsWebScheduler** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="ea84b-158">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="ea84b-159">Se proporcionó un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="ea84b-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ea84b-160">Si se usa, los parámetros opcionales deben estar configurados correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="ea84b-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ea84b-161">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="ea84b-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ea84b-162">Este comando producirá un error si el programador web está mal configurado o aún no se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="ea84b-162">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea84b-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea84b-163">See Also</span></span>


[<span data-ttu-id="ea84b-164">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="ea84b-164">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

