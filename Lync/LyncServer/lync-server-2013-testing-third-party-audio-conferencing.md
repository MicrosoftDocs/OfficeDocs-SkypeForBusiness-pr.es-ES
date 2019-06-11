---
title: 'Lync Server 2013: probar las conferencias de audio de terceros'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1c23f65015dd34f5efbaafa8472466394caa52c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="55d39-102">Prueba de conferencias de audio de terceros en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55d39-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55d39-103">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="55d39-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55d39-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="55d39-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="55d39-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="55d39-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55d39-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="55d39-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="55d39-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55d39-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55d39-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="55d39-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="55d39-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="55d39-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="55d39-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsAudioConferencingProvider.</span><span class="sxs-lookup"><span data-stu-id="55d39-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="55d39-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="55d39-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="55d39-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="55d39-112">Description</span></span>

<span data-ttu-id="55d39-113">Estos proveedores son organizaciones de terceros que suministran servicios de audioconferencia a organizaciones.</span><span class="sxs-lookup"><span data-stu-id="55d39-113">An audio conferencing provider is a third-party company that provides organizations with conferencing services.</span></span> <span data-ttu-id="55d39-114">Entre otras cosas, los proveedores de audioconferencia permiten a los usuarios que no se encuentran en la oficina, y que no están conectados a la red corporativa o Internet, participar en la parte de audio de una conferencia o una reunión.</span><span class="sxs-lookup"><span data-stu-id="55d39-114">Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting.</span></span> <span data-ttu-id="55d39-115">Los proveedores de servicios de audioconferencia suelen ofrecer servicios de alta calidad, como la traducción en vivo, la transcripción y la asistencia del operador Live por Conferencia.</span><span class="sxs-lookup"><span data-stu-id="55d39-115">Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="55d39-116">El cmdlet **Test-CsAudioConferencingProvider** se usa para comprobar que un usuario puede establecer una conexión con su proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="55d39-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="55d39-117">Tenga en cuenta que este cmdlet puede ejecutarse de una de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="55d39-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="55d39-118">Muchos administradores usarán los cmdlets de CsHealthMonitoringConfiguration para configurar los usuarios de prueba para cada uno de sus grupos de registradores.</span><span class="sxs-lookup"><span data-stu-id="55d39-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="55d39-119">Estos usuarios de prueba representan un par de cuentas de usuario preconfiguradas para su uso con transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="55d39-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="55d39-120">(Normalmente, son cuentas de prueba y no cuentas que pertenecen a usuarios reales). Si los usuarios de prueba están configurados para un grupo, los administradores pueden ejecutar el cmdlet **Test-CsAudioConferencingProvider** en ese grupo sin tener que especificar la identidad de (y proporcionar las credenciales para) la cuenta de usuario implicada en la prueba.</span><span class="sxs-lookup"><span data-stu-id="55d39-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="55d39-121">Como alternativa, los administradores pueden ejecutar el cmdlet **Test-CsAudioConferencingProvider** con una cuenta de usuario real.</span><span class="sxs-lookup"><span data-stu-id="55d39-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="55d39-122">Si decide realizar la prueba usando una cuenta de usuario real, tendrá que proporcionar el nombre de inicio de sesión y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="55d39-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="55d39-123">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="55d39-123">Running the test</span></span>

<span data-ttu-id="55d39-124">El ejemplo 1 comprueba si un usuario de prueba definido para el grupo atl-cs-001.litwareinc.com puede conectarse a su proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="55d39-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="55d39-125">Este comando requiere que se defina al menos un usuario de prueba para el grupo.</span><span class="sxs-lookup"><span data-stu-id="55d39-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="55d39-126">Si no se han definido usuarios de prueba para atl-cs-001.litwareinc.com, el comando fallará; Esto se debe a que el cmdlet **Test-CsAudioConferencingProvider** no sabrá qué usuario debe emplear en la prueba.</span><span class="sxs-lookup"><span data-stu-id="55d39-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="55d39-127">Si no ha definido usuarios de prueba para un grupo, debe incluir el parámetro UserSipAddress y las credenciales de la cuenta de usuario que debe usar el comando al comprobar la conexión con un proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="55d39-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="55d39-128">Los comandos que se muestran en el ejemplo 2 prueban la capacidad de un\\usuario específico (litwareinc kenmyer) para conectarse a su proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="55d39-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="55d39-129">Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credenciales de la interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="55d39-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="55d39-130">(Dado que el nombre de\\inicio de sesión litwareinc kenmyer se ha incluido como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta de Ken Myer). El objeto de credenciales resultante se almacena en una variable denominada $credential.</span><span class="sxs-lookup"><span data-stu-id="55d39-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="55d39-131">El segundo comando comprueba entonces si este usuario puede conectarse a su proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="55d39-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="55d39-132">Para llevar a cabo esta tarea, se llama al cmdlet test-CsAudioConferencingProvider, junto con tres parámetros: TargetFqdn (el FQDN del grupo de servidores de registrar); UserCredential (el objeto de Windows PowerShell que contiene las credenciales de usuario de Ken Myer); y UserSipAddress (la dirección SIP correspondiente a las credenciales de usuario suministradas).</span><span class="sxs-lookup"><span data-stu-id="55d39-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="55d39-133">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="55d39-133">Determining success or failure</span></span>

<span data-ttu-id="55d39-134">Si el proveedor de servicios de audioconferencia está configurado correctamente, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="55d39-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="55d39-135">FQDN de destino: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="55d39-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="55d39-136">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="55d39-136">Result : Success</span></span>

<span data-ttu-id="55d39-137">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="55d39-137">Latency : 00:00:00</span></span>

<span data-ttu-id="55d39-138">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="55d39-138">Error Message :</span></span>

<span data-ttu-id="55d39-139">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="55d39-139">Diagnosis :</span></span>

<span data-ttu-id="55d39-140">Si el usuario especificado no puede iniciar sesión o cerrar sesión, el resultado se mostrará como un **error**y se registrará información adicional en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="55d39-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="55d39-141">FQDN de destino: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="55d39-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="55d39-142">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="55d39-142">Result : Failure</span></span>

<span data-ttu-id="55d39-143">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="55d39-143">Latency : 00:00:00</span></span>

<span data-ttu-id="55d39-144">Mensaje de error: 10060, error al intentar la conexión porque la persona conectada</span><span class="sxs-lookup"><span data-stu-id="55d39-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="55d39-145">no respondió correctamente después de un período de tiempo, o</span><span class="sxs-lookup"><span data-stu-id="55d39-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="55d39-146">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="55d39-146">established connection failed because connected host has</span></span>

<span data-ttu-id="55d39-147">Error al responder \[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="55d39-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="55d39-148">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="55d39-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="55d39-149">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="55d39-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="55d39-150">hora o error de conexión establecida porque el host conectado</span><span class="sxs-lookup"><span data-stu-id="55d39-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="55d39-151">Error al responder</span><span class="sxs-lookup"><span data-stu-id="55d39-151">has failed to respond</span></span>

<span data-ttu-id="55d39-152">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="55d39-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="55d39-153">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="55d39-153">Diagnosis :</span></span>

<span data-ttu-id="55d39-154">Por ejemplo, la salida anterior incluye la nota "la persona conectada no respondió correctamente" que normalmente indica que hay un problema con el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="55d39-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="55d39-155">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="55d39-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="55d39-156">Estas son algunas de las razones comunes por las que **Test-CsAudioConferencingProvider** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="55d39-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="55d39-157">Se proporcionó un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="55d39-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="55d39-158">Tal y como se muestra en el ejemplo anterior, los parámetros opcionales deben estar configurados correctamente o no se puede realizar la prueba.</span><span class="sxs-lookup"><span data-stu-id="55d39-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="55d39-159">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="55d39-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="55d39-160">Observe que la prueba se producirá un error si el usuario empleado por el cmdlet **Test-CsAudioConferencingProvider** no ha sido asignado a un proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="55d39-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="55d39-161">Este comando fallará si el servidor perimetral está mal configurado o aún no se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="55d39-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

