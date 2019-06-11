---
title: 'Lync Server 2013: validación de la consulta Web de la libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44c43b4332be67bb164f21a2bb07459d61b23e85
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="02c56-102">Validación de la consulta Web de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02c56-102">Validating address book web query in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02c56-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="02c56-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02c56-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="02c56-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="02c56-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="02c56-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02c56-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="02c56-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="02c56-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02c56-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02c56-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="02c56-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="02c56-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="02c56-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="02c56-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsAddressBookWebQuery.</span><span class="sxs-lookup"><span data-stu-id="02c56-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="02c56-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="02c56-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="02c56-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="02c56-112">Description</span></span>

<span data-ttu-id="02c56-113">El cmdlet test-CsAddressBookWebQuery permite a los administradores comprobar que los usuarios pueden usar el servicio de consultas Web de la libreta de direcciones para buscar un contacto específico.</span><span class="sxs-lookup"><span data-stu-id="02c56-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="02c56-114">Al ejecutar el cmdlet, test-CsAddressBookWebQuery se conectará en primer lugar con el servicio de vales web para que se autentique.</span><span class="sxs-lookup"><span data-stu-id="02c56-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="02c56-115">Si la autenticación se realiza correctamente, el cmdlet se conectará al servicio de consulta Web de la libreta de direcciones y buscará el contacto especificado.</span><span class="sxs-lookup"><span data-stu-id="02c56-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="02c56-116">Si se encuentra ese contacto, el cmdlet intentará devolver esa información al equipo local.</span><span class="sxs-lookup"><span data-stu-id="02c56-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="02c56-117">La prueba se marcará como correcta solo si se pueden completar todos los pasos.</span><span class="sxs-lookup"><span data-stu-id="02c56-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="02c56-118">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="02c56-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="02c56-119">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="02c56-119">Running the test</span></span>

<span data-ttu-id="02c56-120">El cmdlet test-CsAddressBookWebQuery se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02c56-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="02c56-121">Para ejecutar esta comprobación mediante una cuenta de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync y la dirección SIP del usuario que actúa como destino de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="02c56-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="02c56-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02c56-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="02c56-123">Para ejecutar esta comprobación mediante una cuenta de usuario real, debe crear un objeto de credenciales de Windows PowerShell que contenga un nombre de usuario y una contraseña válidos.</span><span class="sxs-lookup"><span data-stu-id="02c56-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="02c56-124">Después debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta cuando el código llama a test-CsAddressBookWebQuery:</span><span class="sxs-lookup"><span data-stu-id="02c56-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="02c56-125">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="02c56-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="02c56-126">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="02c56-126">Determining success or failure</span></span>

<span data-ttu-id="02c56-127">Si el usuario especificado puede conectarse al servicio de libreta de direcciones y recuperar la dirección de usuario de destino, devolverá un resultado similar a este, con la propiedad result marcada como correcta:</span><span class="sxs-lookup"><span data-stu-id="02c56-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="02c56-128">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="02c56-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="02c56-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="02c56-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="02c56-130">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="02c56-130">Result : Success</span></span>

<span data-ttu-id="02c56-131">Latencia: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="02c56-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="02c56-132">:</span><span class="sxs-lookup"><span data-stu-id="02c56-132">Error :</span></span>

<span data-ttu-id="02c56-133">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="02c56-133">Diagnosis :</span></span>

<span data-ttu-id="02c56-134">Si el usuario especificado no se puede conectar o si la dirección de usuario de destino no se puede recuperar, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="02c56-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="02c56-135">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="02c56-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="02c56-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="02c56-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="02c56-137">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="02c56-137">Result : Failure</span></span>

<span data-ttu-id="02c56-138">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="02c56-138">Latency : 00:00:00</span></span>

<span data-ttu-id="02c56-139">Error: error en la solicitud de servicio Web de libreta de direcciones con código de respuesta</span><span class="sxs-lookup"><span data-stu-id="02c56-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="02c56-140">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="02c56-140">NoEntryFound.</span></span>

<span data-ttu-id="02c56-141">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="02c56-141">Diagnosis :</span></span>

<span data-ttu-id="02c56-142">La salida anterior indica que no se pudo realizar la prueba porque no se pudo encontrar el usuario de destino.</span><span class="sxs-lookup"><span data-stu-id="02c56-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="02c56-143">Puede determinar si se ha pasado o no una dirección SIP válida a test-CsAddressBookWebQuery ejecutando un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="02c56-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="02c56-144">Si prueba-CsAddressBookWebQuery da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:</span><span class="sxs-lookup"><span data-stu-id="02c56-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="02c56-145">Cuando se incluye el parámetro detallado, test-CsAddressBookWebQuery devolverá una cuenta paso a paso de cada acción que intentó realizar comprobando la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02c56-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="02c56-146">Por ejemplo, esta salida indica que test-CsAddressBookWebQuery pudo conectarse al servicio de libreta de direcciones, pero no pudo encontrar la dirección SIP de destino:</span><span class="sxs-lookup"><span data-stu-id="02c56-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="02c56-147">Actividad ' QueryAddressBookWebService ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="02c56-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="02c56-148">Llamar al servicio de consultas Web de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="02c56-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="02c56-149">DIRECCIÓN URL DE ABWS =</span><span class="sxs-lookup"><span data-stu-id="02c56-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="02c56-150">Excepción de consulta de la libreta de direcciones: error en la solicitud de servicio Web de libreta de direcciones con código de respuesta NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="02c56-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="02c56-151">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="02c56-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="02c56-152">Estas son algunas de las razones comunes por las que test-CsAddressBookWebQuery podría fallar:</span><span class="sxs-lookup"><span data-stu-id="02c56-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="02c56-153">Ha especificado una cuenta de usuario no válida.</span><span class="sxs-lookup"><span data-stu-id="02c56-153">You specified an invalid user account.</span></span> <span data-ttu-id="02c56-154">Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="02c56-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="02c56-155">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02c56-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="02c56-156">Para comprobar que se ha habilitado una cuenta de usuario para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="02c56-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="02c56-157">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02c56-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="02c56-158">Es posible que el usuario de destino no esté en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="02c56-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="02c56-159">Es posible que la libreta de direcciones no se haya actualizado completamente y se haya replicado.</span><span class="sxs-lookup"><span data-stu-id="02c56-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="02c56-160">Puede forzar una actualización de todos los servidores de la libreta de direcciones de su organización ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="02c56-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

