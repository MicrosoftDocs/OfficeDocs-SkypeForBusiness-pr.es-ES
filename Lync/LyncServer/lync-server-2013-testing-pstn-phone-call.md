---
title: 'Lync Server 2013: prueba de llamadas de teléfono RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4092f728cc691ab73432d7ca853f6441728b5713
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="929b9-102">Prueba de llamadas de teléfono RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="929b9-102">Testing PSTN phone call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="929b9-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="929b9-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="929b9-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="929b9-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="929b9-105">Diario</span><span class="sxs-lookup"><span data-stu-id="929b9-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="929b9-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="929b9-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="929b9-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="929b9-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="929b9-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="929b9-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="929b9-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="929b9-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="929b9-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="929b9-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="929b9-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="929b9-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="929b9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="929b9-112">Description</span></span>

<span data-ttu-id="929b9-113">El cmdlet test-CsPstnOutboundCall comprueba la capacidad de un usuario de realizar una llamada a un número de teléfono ubicado en la RTC.</span><span class="sxs-lookup"><span data-stu-id="929b9-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="929b9-114">Al ejecutar test-CsPstnOutboundCall, el cmdlet intenta iniciar sesión en Lync Server en el primer lugar del usuario.</span><span class="sxs-lookup"><span data-stu-id="929b9-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="929b9-115">Si el inicio de sesión se realiza correctamente, el cmdlet intentará realizar una llamada telefónica en la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="929b9-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="929b9-116">Esta llamada telefónica se realizará mediante el plan de marcado, la Directiva de voz y otras directivas y configuraciones asignadas a la cuenta de prueba.</span><span class="sxs-lookup"><span data-stu-id="929b9-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="929b9-117">Cuando se responde a la llamada, el cmdlet envía códigos de tono de marcado de frecuencia múltiple (DTMF) a través de la red para comprobar la conectividad de los medios.</span><span class="sxs-lookup"><span data-stu-id="929b9-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="929b9-118">Al realizar su prueba, test-CsPstnOutboundCall realizará una llamada de teléfono real: el teléfono de destino sonará y debe responderse para que la prueba se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="929b9-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="929b9-119">El administrador también debe finalizar manualmente esta llamada.</span><span class="sxs-lookup"><span data-stu-id="929b9-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="929b9-120">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="929b9-120">Running the test</span></span>

<span data-ttu-id="929b9-121">El cmdlet test-CsPstnOutboundCall se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="929b9-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="929b9-122">Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando y el número de teléfono RTC al que se llama.</span><span class="sxs-lookup"><span data-stu-id="929b9-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="929b9-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="929b9-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="929b9-124">Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="929b9-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="929b9-125">A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta al llamar a test-CsPstnOutboundCall:</span><span class="sxs-lookup"><span data-stu-id="929b9-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="929b9-126">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .</span><span class="sxs-lookup"><span data-stu-id="929b9-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="929b9-127">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="929b9-127">Determining success or failure</span></span>

<span data-ttu-id="929b9-128">Si el usuario especificado puede realizar la llamada y si se responde a la llamada, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="929b9-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="929b9-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="929b9-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="929b9-130">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="929b9-130">Result : Success</span></span>

<span data-ttu-id="929b9-131">Latencia: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="929b9-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="929b9-132">Error</span><span class="sxs-lookup"><span data-stu-id="929b9-132">Error :</span></span>

<span data-ttu-id="929b9-133">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="929b9-133">Diagnosis :</span></span>

<span data-ttu-id="929b9-134">Si el usuario especificado no puede realizar la llamada o si no se responde a la llamada, el resultado se mostrará como error y se registrará información adicional en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="929b9-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="929b9-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="929b9-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="929b9-136">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="929b9-136">Result : Failure</span></span>

<span data-ttu-id="929b9-137">Latencia: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="929b9-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="929b9-138">Error: 403, prohibido</span><span class="sxs-lookup"><span data-stu-id="929b9-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="929b9-139">Diagnosis: ErrorCode = 12001, Source = ATL-CS-001. litwareinc. com, Reason = User</span><span class="sxs-lookup"><span data-stu-id="929b9-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="929b9-140">La Directiva no contiene uso de ruta telefónica</span><span class="sxs-lookup"><span data-stu-id="929b9-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="929b9-141">La salida anterior indica que la prueba produjo un error porque la Directiva de voz asignada al usuario especificado no incluye un uso de teléfono.</span><span class="sxs-lookup"><span data-stu-id="929b9-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="929b9-142">(Los usos de teléfono unen las directivas de voz a las rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="929b9-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="929b9-143">Sin una directiva de voz y una ruta de voz correspondiente, no se pueden realizar llamadas a través de la RTC.</span><span class="sxs-lookup"><span data-stu-id="929b9-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="929b9-144">Si test-CsPstnOutboundCall produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="929b9-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="929b9-145">Cuando se incluye el parámetro verbose, test-CsPstnOutboundCall devolverá una cuenta paso a paso de cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="929b9-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="929b9-146">Por ejemplo, este resultado indica que hay problemas de red que impiden la conexión con la RTC:</span><span class="sxs-lookup"><span data-stu-id="929b9-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="929b9-147">Establecimiento de una llamada de audio en vídeo a ' SIP: + 12065551219@litwareinc. com; User = Phone '.</span><span class="sxs-lookup"><span data-stu-id="929b9-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="929b9-148">Se ha recibido una respuesta de excepción de 404 (no se encontró) desde la red y se ha producido un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="929b9-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="929b9-149">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="929b9-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="929b9-150">Estas son algunas de las razones comunes por las que test-CsPstnOutboundCall podría fallar:</span><span class="sxs-lookup"><span data-stu-id="929b9-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="929b9-151">Ha especificado una cuenta de usuario no válida.</span><span class="sxs-lookup"><span data-stu-id="929b9-151">You specified an invalid user account.</span></span> <span data-ttu-id="929b9-152">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="929b9-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="929b9-153">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="929b9-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="929b9-154">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="929b9-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="929b9-155">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="929b9-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="929b9-156">La Directiva de voz asignada al usuario especificado no tiene un uso de RTC válido.</span><span class="sxs-lookup"><span data-stu-id="929b9-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="929b9-157">Puede determinar la Directiva de voz que se asigna a un usuario mediante un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="929b9-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="929b9-158">A continuación, puede determinar los usos de RTC (si los hay) asignados a esa Directiva mediante un comando similar al siguiente, que recupera información sobre la Directiva de voz por usuario RedmondVoicePolicy:</span><span class="sxs-lookup"><span data-stu-id="929b9-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

