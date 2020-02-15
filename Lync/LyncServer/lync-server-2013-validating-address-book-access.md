---
title: 'Lync Server 2013: validar el acceso a la libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f18651cd75df62cf1d5f8c543d0e5c11361c7db
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="e8718-102">Validar el acceso a la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8718-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8718-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e8718-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8718-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="e8718-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e8718-105">Diario</span><span class="sxs-lookup"><span data-stu-id="e8718-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8718-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="e8718-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e8718-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8718-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8718-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="e8718-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e8718-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e8718-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e8718-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsAddressBookService.</span><span class="sxs-lookup"><span data-stu-id="e8718-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="e8718-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e8718-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e8718-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8718-112">Description</span></span>

<span data-ttu-id="e8718-113">El cmdlet test-CsAddressBookService proporciona una manera de comprobar que un usuario puede conectarse al servicio Web de descarga de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e8718-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="e8718-114">Cuando se ejecuta el cmdlet, test-CsAddressBookService se conecta al servicio Web de descarga de la libreta de direcciones en el grupo de servidores especificado y solicita la ubicación de los archivos de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e8718-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="e8718-115">Si el servicio Web de descarga de la libreta de direcciones proporciona esa ubicación, se considerará que la prueba se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e8718-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="e8718-116">Si se deniega la petición, el resultado de la prueba es erróneo.</span><span class="sxs-lookup"><span data-stu-id="e8718-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e8718-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="e8718-117">Running the test</span></span>

<span data-ttu-id="e8718-118">El cmdlet test-CsAddressBookService se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que se haya habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8718-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="e8718-119">Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el nombre de dominio completo (FQDN) del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="e8718-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="e8718-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e8718-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e8718-121">Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="e8718-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="e8718-122">A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta al llamar a test-CsAddressBookService:</span><span class="sxs-lookup"><span data-stu-id="e8718-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="e8718-123">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .</span><span class="sxs-lookup"><span data-stu-id="e8718-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e8718-124">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="e8718-124">Determining success or failure</span></span>

<span data-ttu-id="e8718-125">Si el usuario especificado puede conectarse al servicio de libreta de direcciones, obtendrá una salida similar a la siguiente, con la propiedad result marcada como **correcta**:</span><span class="sxs-lookup"><span data-stu-id="e8718-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="e8718-126">TargetUrihttps://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="e8718-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="e8718-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e8718-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e8718-128">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="e8718-128">Result : Success</span></span>

<span data-ttu-id="e8718-129">Latencia: 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="e8718-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="e8718-130">Error</span><span class="sxs-lookup"><span data-stu-id="e8718-130">Error :</span></span>

<span data-ttu-id="e8718-131">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e8718-131">Diagnosis :</span></span>

<span data-ttu-id="e8718-132">Si el usuario especificado no puede realizar esta conexión, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="e8718-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e8718-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="e8718-133">TargetUri :</span></span>

<span data-ttu-id="e8718-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e8718-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e8718-135">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="e8718-135">Result : Failure</span></span>

<span data-ttu-id="e8718-136">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e8718-136">Latency : 00:00:00</span></span>

<span data-ttu-id="e8718-137">Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e8718-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="e8718-138">Razón = URI de destino no habilitado para SIP o no</span><span class="sxs-lookup"><span data-stu-id="e8718-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="e8718-139">haber.</span><span class="sxs-lookup"><span data-stu-id="e8718-139">exist.</span></span>

<span data-ttu-id="e8718-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="e8718-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="e8718-141">Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque el usuario especificado (es decir, el "URI de destino") no existe o no se ha habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8718-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="e8718-142">Puede comprobar si una cuenta de usuario es válida y comprobar que ha proporcionado la dirección SIP correcta, mediante la ejecución de un comando como este:</span><span class="sxs-lookup"><span data-stu-id="e8718-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="e8718-143">Get-CsUser-Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span><span class="sxs-lookup"><span data-stu-id="e8718-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="e8718-144">Si test-CsAddressBookService produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="e8718-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="e8718-145">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-verbose</span><span class="sxs-lookup"><span data-stu-id="e8718-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="e8718-146">Cuando se incluye el parámetro verbose test-CsAddressBookService devolverá una cuenta paso a paso de cada acción que intentó realizar la comprobación de la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8718-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="e8718-147">Por ejemplo, este resultado de ejemplo muestra que test-CsAddressBookService, al menos en este ejemplo, pudo descargar el archivo de la libreta de direcciones:</span><span class="sxs-lookup"><span data-stu-id="e8718-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="e8718-148">Envío de la solicitud HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="e8718-148">Sending Http GET Request.</span></span>

<span data-ttu-id="e8718-149">Ruta de acceso de archivo =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="e8718-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="e8718-150">Número de intento = 1</span><span class="sxs-lookup"><span data-stu-id="e8718-150">Attempt Number = 1</span></span>

<span data-ttu-id="e8718-151">Tiempo de espera (MS) = 60000</span><span class="sxs-lookup"><span data-stu-id="e8718-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="e8718-152">El archivo ABS se descargó correctamentehttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="e8718-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e8718-153">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="e8718-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="e8718-154">Estas son algunas de las razones comunes por las que test-CsAddressBookService podría fallar:</span><span class="sxs-lookup"><span data-stu-id="e8718-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="e8718-155">Ha especificado una cuenta de usuario no válida.</span><span class="sxs-lookup"><span data-stu-id="e8718-155">You specified an invalid user account.</span></span> <span data-ttu-id="e8718-156">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8718-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e8718-157">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8718-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="e8718-158">Para comprobar que una cuenta de usuario se ha habilitado para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8718-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="e8718-159">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8718-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8718-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8718-160">See Also</span></span>


[<span data-ttu-id="e8718-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="e8718-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

