---
title: 'Lync Server 2013: capacidad de prueba de la mensajería instantánea entre dos usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea824216c456e9f673a5383eab0b788933bf53d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="d0662-102">Posibilidad de probar la mensajería instantánea entre dos usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0662-102">Testing ability to IM between two users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0662-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d0662-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0662-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="d0662-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d0662-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="d0662-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0662-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="d0662-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d0662-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0662-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0662-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="d0662-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d0662-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d0662-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d0662-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsIM.</span><span class="sxs-lookup"><span data-stu-id="d0662-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="d0662-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d0662-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d0662-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0662-112">Description</span></span>

<span data-ttu-id="d0662-113">El cmdlet test-CsIM verifica que un par de usuarios de prueba puedan intercambiar mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="d0662-113">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="d0662-114">Cuando se llama, el cmdlet test-CsIM comienza intentando iniciar sesión en un par de usuarios de prueba en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d0662-114">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="d0662-115">Suponiendo que los dos inicios de sesión se hayan realizado correctamente, el cmdlet inicia una sesión de mensajería instantánea entre los dos usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="d0662-115">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="d0662-116">(El usuario 1 invita al usuario 2 a una sesión de mensajería instantánea y el usuario 2 la acepta). Después de comprobar que los mensajes se pueden intercambiar entre los dos usuarios, test-CsIM finaliza la sesión de mensajería instantánea y registra a ambos usuarios del sistema.</span><span class="sxs-lookup"><span data-stu-id="d0662-116">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="d0662-117">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="d0662-117">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d0662-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="d0662-118">Running the Test</span></span>

<span data-ttu-id="d0662-119">El cmdlet test-CsIM se puede ejecutar con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d0662-119">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="d0662-120">Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando.</span><span class="sxs-lookup"><span data-stu-id="d0662-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="d0662-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d0662-121">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="d0662-122">Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contengan el nombre y la contraseña de la cuenta) de cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="d0662-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="d0662-123">Después, debe incluir esos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="d0662-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="d0662-124">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="d0662-124">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d0662-125">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="d0662-125">Determining Success or Failure</span></span>

<span data-ttu-id="d0662-126">Si los dos usuarios pueden completar una sesión de mensajería instantánea, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="d0662-126">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d0662-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d0662-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d0662-128">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="d0662-128">Result : Success</span></span>

<span data-ttu-id="d0662-129">Latencia: 00:00:06.6630911</span><span class="sxs-lookup"><span data-stu-id="d0662-129">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="d0662-130">:</span><span class="sxs-lookup"><span data-stu-id="d0662-130">Error :</span></span>

<span data-ttu-id="d0662-131">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d0662-131">Diagnosis :</span></span>

<span data-ttu-id="d0662-132">Si los usuarios de prueba no pueden completar la sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades de error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="d0662-132">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d0662-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d0662-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d0662-134">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="d0662-134">Result : Failure</span></span>

<span data-ttu-id="d0662-135">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d0662-135">Latency : 00:00:00</span></span>

<span data-ttu-id="d0662-136">Error: 504, tiempo de espera del servidor</span><span class="sxs-lookup"><span data-stu-id="d0662-136">Error : 504, Server time-out</span></span>

<span data-ttu-id="d0662-137">Diagnosis: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, razón = ver</span><span class="sxs-lookup"><span data-stu-id="d0662-137">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="d0662-138">código de respuesta y frase de motivo.</span><span class="sxs-lookup"><span data-stu-id="d0662-138">response code and reason phrase.</span></span>

<span data-ttu-id="d0662-139">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="d0662-139">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="d0662-140">Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se encontró el usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="d0662-140">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="d0662-141">Puede determinar si una dirección SIP es válida (y si el usuario asignó la dirección SIP a Lync Server) ejecutando este comando:</span><span class="sxs-lookup"><span data-stu-id="d0662-141">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="d0662-142">Si prueba-CsIM da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:</span><span class="sxs-lookup"><span data-stu-id="d0662-142">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="d0662-143">Cuando se incluye el parámetro detallado, test-CsIM devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad de los dos usuarios de prueba para tomar parte en una sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="d0662-143">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="d0662-144">Por ejemplo, este es un resultado de ejemplo que se produce cuando se proporciona un conjunto incorrecto de credenciales de usuario (en este caso, una contraseña incorrecta) para probar-CsIM:</span><span class="sxs-lookup"><span data-stu-id="d0662-144">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="d0662-145">Enviando solicitud de registro:</span><span class="sxs-lookup"><span data-stu-id="d0662-145">Sending Registration request :</span></span>

<span data-ttu-id="d0662-146">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d0662-146">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="d0662-147">Dirección SIP del usuario = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d0662-147">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="d0662-148">Registrar puerto = 5061</span><span class="sxs-lookup"><span data-stu-id="d0662-148">Registrar Port = 5061</span></span>

<span data-ttu-id="d0662-149">El tipo de autenticación ' IWA ' está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d0662-149">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="d0662-150">Registro de visitas contra SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="d0662-150">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d0662-151">Actividad ' Register ' completada en ' 0,0601795 ' s.</span><span class="sxs-lookup"><span data-stu-id="d0662-151">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="d0662-152">Excepción ' se denegó el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="d0662-152">An exception 'The log on was denied.</span></span> <span data-ttu-id="d0662-153">Compruebe que se están usando las credenciales correctas y que la cuenta está activa.</span><span class="sxs-lookup"><span data-stu-id="d0662-153">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="d0662-154">durante el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d0662-154">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d0662-155">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="d0662-155">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="d0662-156">Estas son algunas de las razones comunes por las que test-CsIM podría fallar:</span><span class="sxs-lookup"><span data-stu-id="d0662-156">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="d0662-157">Ha especificado una cuenta de usuario que no es válida.</span><span class="sxs-lookup"><span data-stu-id="d0662-157">You specified a user account that is not valid.</span></span> <span data-ttu-id="d0662-158">Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="d0662-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="d0662-159">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d0662-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="d0662-160">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d0662-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="d0662-161">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d0662-161">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="d0662-162">Es posible que el servicio de mensajería instantánea no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="d0662-162">The instant messaging service might not be available.</span></span> <span data-ttu-id="d0662-163">Con Lync Server, puede configurar el sistema para que el mensaje instantáneo no esté disponible si no se puede obtener acceso a la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="d0662-163">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="d0662-164">Puede comprobar que al ejecutar un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d0662-164">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="d0662-165">Si BlockOnArchiveFailure se establece en true, debe determinar si la base de datos de archivado está disponible o no.</span><span class="sxs-lookup"><span data-stu-id="d0662-165">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="d0662-166">Puede devolver las ubicaciones de las bases de datos de archivado con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d0662-166">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="d0662-167">Es posible que el servidor de archivado no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="d0662-167">The Archiving server might not be available.</span></span> <span data-ttu-id="d0662-168">Puede recuperar el FQDN de los servidores de archivado con este comando:</span><span class="sxs-lookup"><span data-stu-id="d0662-168">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="d0662-169">Después, puede hacer ping al servidor apropiado para comprobar que está disponible.</span><span class="sxs-lookup"><span data-stu-id="d0662-169">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="d0662-170">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d0662-170">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

