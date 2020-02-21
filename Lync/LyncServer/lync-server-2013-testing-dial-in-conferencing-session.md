---
title: 'Lync Server 2013: prueba de la sesión de conferencia de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94999d2f3ce69308e38da1b261a4b0d96a2ef5cd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="85b70-102">Prueba de la sesión de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85b70-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85b70-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="85b70-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85b70-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="85b70-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="85b70-105">Diario</span><span class="sxs-lookup"><span data-stu-id="85b70-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85b70-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="85b70-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="85b70-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="85b70-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85b70-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="85b70-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="85b70-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="85b70-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="85b70-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsDialInConferencing.</span><span class="sxs-lookup"><span data-stu-id="85b70-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="85b70-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="85b70-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="85b70-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="85b70-112">Description</span></span>

<span data-ttu-id="85b70-113">El cmdlet test-CsDialInConferencing comprueba si un usuario puede participar en una conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="85b70-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="85b70-114">Test-CsDialInConferencing funciona intentando registrar un usuario de prueba en el sistema.</span><span class="sxs-lookup"><span data-stu-id="85b70-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="85b70-115">Si el inicio de sesión se realiza correctamente, el cmdlet usará las credenciales y permisos del usuario para probar todos los números de acceso de conferencia de acceso telefónico disponibles.</span><span class="sxs-lookup"><span data-stu-id="85b70-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="85b70-116">Se indicará el éxito o el error de cada intento de acceso telefónico y, a continuación, el usuario de prueba se cerrará en Lync Server. test-CsDialInConferencing solo comprueba que se puedan realizar las conexiones adecuadas.</span><span class="sxs-lookup"><span data-stu-id="85b70-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="85b70-117">El cmdlet no realiza ninguna llamada telefónica real ni crea ninguna conferencia de acceso telefónico a la que puedan unirse otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="85b70-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="85b70-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="85b70-118">Running the test</span></span>

<span data-ttu-id="85b70-119">El cmdlet test-CsDialInConferencing se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85b70-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="85b70-120">Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="85b70-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="85b70-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="85b70-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="85b70-122">Para ejecutar esta comprobación con una cuenta de usuario real, debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="85b70-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="85b70-123">A continuación, debe incluir ese objeto de credenciales y la dirección SIP de la cuenta que llama a test-CsDialInConferencing:</span><span class="sxs-lookup"><span data-stu-id="85b70-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="85b70-124">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="85b70-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="85b70-125">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="85b70-125">Determining success or failure</span></span>

<span data-ttu-id="85b70-126">Si el usuario especificado puede iniciar sesión en Lync Server y, a continuación, realizar una conexión con uno de los números de acceso de conferencia de acceso telefónico disponible, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="85b70-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="85b70-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="85b70-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="85b70-128">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="85b70-128">Result : Success</span></span>

<span data-ttu-id="85b70-129">Latencia: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="85b70-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="85b70-130">Error</span><span class="sxs-lookup"><span data-stu-id="85b70-130">Error :</span></span>

<span data-ttu-id="85b70-131">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="85b70-131">Diagnosis :</span></span>

<span data-ttu-id="85b70-132">Si el usuario especificado no puede realizar esta conexión, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="85b70-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="85b70-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="85b70-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="85b70-134">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="85b70-134">Result : Failure</span></span>

<span data-ttu-id="85b70-135">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="85b70-135">Latency : 00:00:00</span></span>

<span data-ttu-id="85b70-136">Error: se denegó el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="85b70-136">Error : The log on was denied.</span></span> <span data-ttu-id="85b70-137">Compruebe que las credenciales correctas están</span><span class="sxs-lookup"><span data-stu-id="85b70-137">Check that the proper credentials are</span></span>

<span data-ttu-id="85b70-138">en uso y la cuenta está activa.</span><span class="sxs-lookup"><span data-stu-id="85b70-138">being used and the account is active.</span></span>

<span data-ttu-id="85b70-139">Excepción interna: error de NegotiateSecurityAssociation, error:-</span><span class="sxs-lookup"><span data-stu-id="85b70-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="85b70-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="85b70-140">2146893044</span></span>

<span data-ttu-id="85b70-141">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="85b70-141">Diagnosis :</span></span>

<span data-ttu-id="85b70-142">El resultado anterior indica que se ha denegado el acceso del usuario de prueba a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85b70-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="85b70-143">Normalmente, esto significa que las credenciales de usuario pasadas a test-CsDialInConferencing no eran válidas.</span><span class="sxs-lookup"><span data-stu-id="85b70-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="85b70-144">A su vez, debe volver a crear el objeto de credenciales de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85b70-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="85b70-145">Aunque puede recuperar la contraseña de la cuenta de usuario, puede comprobar la dirección SIP con un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="85b70-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="85b70-146">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="85b70-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="85b70-147">Estas son algunas de las razones comunes por las que test-CsDialInConferencing podría fallar:</span><span class="sxs-lookup"><span data-stu-id="85b70-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="85b70-148">Ha especificado una cuenta de usuario que no es válida.</span><span class="sxs-lookup"><span data-stu-id="85b70-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="85b70-149">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="85b70-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="85b70-150">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85b70-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="85b70-151">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="85b70-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="85b70-152">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85b70-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="85b70-153">Es posible que tenga un número de acceso de conferencia de acceso telefónico incorrecta.</span><span class="sxs-lookup"><span data-stu-id="85b70-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="85b70-154">Puede devolver la lista configurada actualmente de números de acceso a conferencias de acceso telefónico local con este comando:</span><span class="sxs-lookup"><span data-stu-id="85b70-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

