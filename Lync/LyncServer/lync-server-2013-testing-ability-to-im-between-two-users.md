---
title: 'Lync Server 2013: posibilidad de probar la mensajería instantánea entre dos usuarios'
description: 'Lync Server 2013: posibilidad de probar la mensajería instantánea entre dos usuarios.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1409cfb58ed435a66dcf61db56660ca760e16422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560806"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="f0c15-103">Probar la capacidad de mensajería instantánea entre dos usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c15-103">Testing ability to IM between two users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0c15-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f0c15-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0c15-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="f0c15-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f0c15-106">Diario</span><span class="sxs-lookup"><span data-stu-id="f0c15-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c15-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="f0c15-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f0c15-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0c15-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c15-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="f0c15-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f0c15-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f0c15-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f0c15-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsIM.</span><span class="sxs-lookup"><span data-stu-id="f0c15-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="f0c15-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0c15-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f0c15-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0c15-113">Description</span></span>

<span data-ttu-id="f0c15-114">El cmdlet Test-CsIM comprueba que un par de usuarios de prueba puedan intercambiar mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="f0c15-114">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="f0c15-115">Cuando se llama, el cmdlet de Test-CsIM se inicia intentando iniciar sesión en un par de usuarios de prueba en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0c15-115">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="f0c15-116">Si los dos inicios de sesión son correctos, el cmdlet inicia una sesión de mi entre los dos usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="f0c15-116">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="f0c15-117">(El usuario 1 invita al usuario 2 a una sesión de mi y el usuario 2 acepta la invitación). Después de comprobar que se pueden intercambiar mensajes entre los dos usuarios, Test-CsIM finaliza la sesión de mensajería instantánea y registra a ambos usuarios fuera del sistema.</span><span class="sxs-lookup"><span data-stu-id="f0c15-117">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="f0c15-118">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="f0c15-118">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f0c15-119">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="f0c15-119">Running the Test</span></span>

<span data-ttu-id="f0c15-120">El cmdlet Test-CsIM puede ejecutarse con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0c15-120">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="f0c15-121">Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="f0c15-121">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="f0c15-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f0c15-122">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f0c15-123">Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="f0c15-123">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="f0c15-124">A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="f0c15-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="f0c15-125">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="f0c15-125">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f0c15-126">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="f0c15-126">Determining Success or Failure</span></span>

<span data-ttu-id="f0c15-127">Si los dos usuarios pueden completar una sesión de mensajería instantánea, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="f0c15-127">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f0c15-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f0c15-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f0c15-129">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="f0c15-129">Result : Success</span></span>

<span data-ttu-id="f0c15-130">Latencia: 00:00:06.6630911</span><span class="sxs-lookup"><span data-stu-id="f0c15-130">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="f0c15-131">Error</span><span class="sxs-lookup"><span data-stu-id="f0c15-131">Error :</span></span>

<span data-ttu-id="f0c15-132">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f0c15-132">Diagnosis :</span></span>

<span data-ttu-id="f0c15-133">Si los usuarios de prueba no pueden completar la sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="f0c15-133">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f0c15-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f0c15-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f0c15-135">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="f0c15-135">Result : Failure</span></span>

<span data-ttu-id="f0c15-136">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f0c15-136">Latency : 00:00:00</span></span>

<span data-ttu-id="f0c15-137">Error: 504, tiempo de espera del servidor</span><span class="sxs-lookup"><span data-stu-id="f0c15-137">Error : 504, Server time-out</span></span>

<span data-ttu-id="f0c15-138">Diagnosis: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, Reason = vea</span><span class="sxs-lookup"><span data-stu-id="f0c15-138">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="f0c15-139">código de respuesta y frase de motivo.</span><span class="sxs-lookup"><span data-stu-id="f0c15-139">response code and reason phrase.</span></span>

<span data-ttu-id="f0c15-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="f0c15-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="f0c15-141">Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se encontró el usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="f0c15-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="f0c15-142">Puede determinar si una dirección SIP es válida (y si el usuario asignado a esa dirección SIP está habilitado para Lync Server) ejecutando este comando:</span><span class="sxs-lookup"><span data-stu-id="f0c15-142">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="f0c15-143">Si Test-CsIM da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="f0c15-143">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="f0c15-144">Cuando se incluye el parámetro verbose, Test-CsIM devolverá una cuenta paso a paso por cada acción que se intentó realizar cuando se comprobó la capacidad de los dos usuarios de prueba para participar en una sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="f0c15-144">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="f0c15-145">Por ejemplo, aquí se muestran los resultados de ejemplo que se producen cuando se proporciona un conjunto incorrecto de credenciales de usuario (en este caso, una contraseña incorrecta) para test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="f0c15-145">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="f0c15-146">Enviando solicitud de registro:</span><span class="sxs-lookup"><span data-stu-id="f0c15-146">Sending Registration request :</span></span>

<span data-ttu-id="f0c15-147">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f0c15-147">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="f0c15-148">Dirección SIP del usuario = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f0c15-148">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="f0c15-149">Puerto del registrador = 5061</span><span class="sxs-lookup"><span data-stu-id="f0c15-149">Registrar Port = 5061</span></span>

<span data-ttu-id="f0c15-150">El tipo de autenticación "IWA" está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f0c15-150">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="f0c15-151">Aciertos de registro en SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="f0c15-151">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f0c15-152">La actividad "Register" se completó en "0,0601795" segundos.</span><span class="sxs-lookup"><span data-stu-id="f0c15-152">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="f0c15-153">Excepción: "se denegó el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="f0c15-153">An exception 'The log on was denied.</span></span> <span data-ttu-id="f0c15-154">Compruebe que se usan las credenciales correctas y que la cuenta está activa.</span><span class="sxs-lookup"><span data-stu-id="f0c15-154">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="f0c15-155">se produjo durante el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f0c15-155">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f0c15-156">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="f0c15-156">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="f0c15-157">Estas son algunas de las razones comunes por las que Test-CsIM podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="f0c15-157">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="f0c15-158">Ha especificado una cuenta de usuario que no es válida.</span><span class="sxs-lookup"><span data-stu-id="f0c15-158">You specified a user account that is not valid.</span></span> <span data-ttu-id="f0c15-159">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0c15-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="f0c15-160">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0c15-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f0c15-161">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0c15-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f0c15-162">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0c15-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="f0c15-163">Es posible que el servicio de mensajería instantánea no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="f0c15-163">The instant messaging service might not be available.</span></span> <span data-ttu-id="f0c15-164">Con Lync Server, puede configurar el sistema para que mi no esté disponible si no se puede tener acceso a la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="f0c15-164">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="f0c15-165">Puede comprobar si ejecuta un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0c15-165">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="f0c15-166">Si BlockOnArchiveFailure se establece en true, debe determinar si la base de datos de archivado está disponible o no.</span><span class="sxs-lookup"><span data-stu-id="f0c15-166">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="f0c15-167">Puede devolver las ubicaciones de las bases de datos de archivado con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f0c15-167">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="f0c15-168">Es posible que el servidor de archivado no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="f0c15-168">The Archiving server might not be available.</span></span> <span data-ttu-id="f0c15-169">Puede recuperar el FQDN de los servidores de archivado con este comando:</span><span class="sxs-lookup"><span data-stu-id="f0c15-169">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="f0c15-170">A continuación, puede hacer ping en el servidor adecuado para comprobar que está disponible.</span><span class="sxs-lookup"><span data-stu-id="f0c15-170">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="f0c15-171">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f0c15-171">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

