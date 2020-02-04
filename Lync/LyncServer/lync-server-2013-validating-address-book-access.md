---
title: 'Lync Server 2013: validación del acceso a la libreta de direcciones'
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
ms.openlocfilehash: 96fe45f1491ca518a6985b0c15f8bcc229bd7f8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="05b65-102">Validar el acceso a la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05b65-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05b65-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="05b65-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05b65-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="05b65-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="05b65-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="05b65-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05b65-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="05b65-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="05b65-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05b65-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05b65-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="05b65-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="05b65-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="05b65-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="05b65-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsAddressBookService.</span><span class="sxs-lookup"><span data-stu-id="05b65-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="05b65-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="05b65-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="05b65-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="05b65-112">Description</span></span>

<span data-ttu-id="05b65-113">El cmdlet test-CsAddressBookService le permite comprobar que un usuario puede conectarse al servicio Web de descarga de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="05b65-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="05b65-114">Al ejecutar el cmdlet, test-CsAddressBookService se conecta al servicio Web de descarga de la libreta de direcciones en el grupo de servidores especificado y solicita la ubicación de los archivos de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="05b65-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="05b65-115">Si el servicio Web de descarga de la libreta de direcciones proporciona esa ubicación, la prueba se considerará satisfactoria.</span><span class="sxs-lookup"><span data-stu-id="05b65-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="05b65-116">Si la solicitud es denegada, la prueba se considerará un error.</span><span class="sxs-lookup"><span data-stu-id="05b65-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="05b65-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="05b65-117">Running the test</span></span>

<span data-ttu-id="05b65-118">El cmdlet test-CsAddressBookService se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que se haya habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05b65-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="05b65-119">Para ejecutar esta comprobación mediante una cuenta de prueba, todo lo que tiene que hacer es especificar el nombre de dominio completo (FQDN) del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="05b65-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="05b65-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="05b65-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="05b65-121">Para ejecutar esta comprobación mediante una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre de la cuenta y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="05b65-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="05b65-122">Después, debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta al llamar a test-CsAddressBookService:</span><span class="sxs-lookup"><span data-stu-id="05b65-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="05b65-123">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .</span><span class="sxs-lookup"><span data-stu-id="05b65-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="05b65-124">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="05b65-124">Determining success or failure</span></span>

<span data-ttu-id="05b65-125">Si el usuario especificado puede conectarse al servicio de libreta de direcciones, obtendrá un resultado similar a este, con la propiedad result marcada como **correcta**:</span><span class="sxs-lookup"><span data-stu-id="05b65-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="05b65-126">TargetUrihttps://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="05b65-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="05b65-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="05b65-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="05b65-128">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="05b65-128">Result : Success</span></span>

<span data-ttu-id="05b65-129">Latencia: 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="05b65-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="05b65-130">:</span><span class="sxs-lookup"><span data-stu-id="05b65-130">Error :</span></span>

<span data-ttu-id="05b65-131">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="05b65-131">Diagnosis :</span></span>

<span data-ttu-id="05b65-132">Si el usuario especificado no puede establecer esta conexión, el resultado se mostrará como error y la información adicional se registrará en las propiedades de error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="05b65-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="05b65-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="05b65-133">TargetUri :</span></span>

<span data-ttu-id="05b65-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="05b65-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="05b65-135">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="05b65-135">Result : Failure</span></span>

<span data-ttu-id="05b65-136">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="05b65-136">Latency : 00:00:00</span></span>

<span data-ttu-id="05b65-137">Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="05b65-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="05b65-138">Motivo = URI de destino no habilitado para SIP o no</span><span class="sxs-lookup"><span data-stu-id="05b65-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="05b65-139">condiciones.</span><span class="sxs-lookup"><span data-stu-id="05b65-139">exist.</span></span>

<span data-ttu-id="05b65-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="05b65-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="05b65-141">Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque el usuario especificado (es decir, el "URI de destino") no existe o no se ha habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05b65-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="05b65-142">Puede comprobar si una cuenta de usuario es válida, y comprobar si ha suministrado la dirección SIP correcta ejecutando un comando como este:</span><span class="sxs-lookup"><span data-stu-id="05b65-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="05b65-143">Get-CsUser-Identity "sip:kenmyer@litwareinc.com" | SipAddress seleccionar-objeto, habilitado</span><span class="sxs-lookup"><span data-stu-id="05b65-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="05b65-144">Si prueba-CsAddressBookService da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:</span><span class="sxs-lookup"><span data-stu-id="05b65-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="05b65-145">Prueba-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com": detallado</span><span class="sxs-lookup"><span data-stu-id="05b65-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="05b65-146">Cuando se incluye el parámetro detallado, test-CsAddressBookService devolverá una cuenta paso a paso de cada acción que se intentó realizar al comprobar la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05b65-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="05b65-147">Por ejemplo, este resultado de ejemplo muestra que test-CsAddressBookService, al menos en este ejemplo, pudo descargar el archivo de la libreta de direcciones:</span><span class="sxs-lookup"><span data-stu-id="05b65-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="05b65-148">Envío de solicitud HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="05b65-148">Sending Http GET Request.</span></span>

<span data-ttu-id="05b65-149">Ruta de archivo =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="05b65-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="05b65-150">Número de intento = 1</span><span class="sxs-lookup"><span data-stu-id="05b65-150">Attempt Number = 1</span></span>

<span data-ttu-id="05b65-151">Tiempo de espera (MS) = 60000</span><span class="sxs-lookup"><span data-stu-id="05b65-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="05b65-152">El archivo ABS se ha descargado correctamentehttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="05b65-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="05b65-153">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="05b65-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="05b65-154">Estas son algunas de las razones comunes por las que test-CsAddressBookService podría fallar:</span><span class="sxs-lookup"><span data-stu-id="05b65-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="05b65-155">Ha especificado una cuenta de usuario no válida.</span><span class="sxs-lookup"><span data-stu-id="05b65-155">You specified an invalid user account.</span></span> <span data-ttu-id="05b65-156">Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="05b65-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="05b65-157">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05b65-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="05b65-158">Para comprobar que se ha habilitado una cuenta de usuario para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="05b65-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="05b65-159">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05b65-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="05b65-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="05b65-160">See Also</span></span>


[<span data-ttu-id="05b65-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="05b65-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

