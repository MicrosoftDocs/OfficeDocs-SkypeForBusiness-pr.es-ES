---
title: 'Lync Server 2013: validación de la consulta Web de la libreta de direcciones'
description: 'Lync Server 2013: validación de la consulta Web de la libreta de direcciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e73c39fc33f8d1851fc89d277333a94aaa137790
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547256"
---
# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="13a97-103">Validación de la consulta Web de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13a97-103">Validating address book web query in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13a97-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="13a97-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13a97-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="13a97-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="13a97-106">Diario</span><span class="sxs-lookup"><span data-stu-id="13a97-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13a97-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="13a97-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="13a97-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13a97-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13a97-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="13a97-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="13a97-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="13a97-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="13a97-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsAddressBookWebQuery.</span><span class="sxs-lookup"><span data-stu-id="13a97-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="13a97-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="13a97-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="13a97-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="13a97-113">Description</span></span>

<span data-ttu-id="13a97-114">El cmdlet Test-CsAddressBookWebQuery permite a los administradores comprobar que los usuarios pueden usar el servicio de consulta Web de libreta de direcciones para buscar un contacto específico.</span><span class="sxs-lookup"><span data-stu-id="13a97-114">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="13a97-115">Al ejecutar el cmdlet, Test-CsAddressBookWebQuery se conectará primero al servicio de vale web para autenticarse.</span><span class="sxs-lookup"><span data-stu-id="13a97-115">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="13a97-116">Si la autenticación se realiza correctamente, el cmdlet se conectará al servicio de consulta Web de la libreta de direcciones y buscará el contacto especificado.</span><span class="sxs-lookup"><span data-stu-id="13a97-116">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="13a97-117">Si se encuentra ese contacto, el cmdlet intentará devolver esa información al equipo local.</span><span class="sxs-lookup"><span data-stu-id="13a97-117">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="13a97-118">La prueba se marcará como correcta solo si se pueden completar todos los pasos.</span><span class="sxs-lookup"><span data-stu-id="13a97-118">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="13a97-119">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="13a97-119">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="13a97-120">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="13a97-120">Running the test</span></span>

<span data-ttu-id="13a97-121">El cmdlet Test-CsAddressBookWebQuery se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13a97-121">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="13a97-122">Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server y la dirección SIP del usuario que actúa como destino de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="13a97-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="13a97-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="13a97-123">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="13a97-124">Para ejecutar esta comprobación con una cuenta de usuario real, debe crear un objeto de credenciales de Windows PowerShell que contenga un nombre de usuario y una contraseña válidos.</span><span class="sxs-lookup"><span data-stu-id="13a97-124">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="13a97-125">A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta cuando el código llame a test-CsAddressBookWebQuery:</span><span class="sxs-lookup"><span data-stu-id="13a97-125">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="13a97-126">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="13a97-126">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="13a97-127">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="13a97-127">Determining success or failure</span></span>

<span data-ttu-id="13a97-128">Si el usuario especificado puede conectarse al servicio de libreta de direcciones y recuperar la dirección del usuario de destino, se devuelve un resultado similar al siguiente con la propiedad result marcada como correcta:</span><span class="sxs-lookup"><span data-stu-id="13a97-128">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="13a97-129">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="13a97-129">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="13a97-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="13a97-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="13a97-131">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="13a97-131">Result : Success</span></span>

<span data-ttu-id="13a97-132">Latencia: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="13a97-132">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="13a97-133">Error</span><span class="sxs-lookup"><span data-stu-id="13a97-133">Error :</span></span>

<span data-ttu-id="13a97-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="13a97-134">Diagnosis :</span></span>

<span data-ttu-id="13a97-135">Si el usuario especificado no se puede conectar o si no se puede recuperar la dirección de usuario de destino, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="13a97-135">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="13a97-136">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="13a97-136">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="13a97-137">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="13a97-137">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="13a97-138">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="13a97-138">Result : Failure</span></span>

<span data-ttu-id="13a97-139">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="13a97-139">Latency : 00:00:00</span></span>

<span data-ttu-id="13a97-140">Error: error en la solicitud del servicio Web de libreta de direcciones con código de respuesta</span><span class="sxs-lookup"><span data-stu-id="13a97-140">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="13a97-141">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="13a97-141">NoEntryFound.</span></span>

<span data-ttu-id="13a97-142">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="13a97-142">Diagnosis :</span></span>

<span data-ttu-id="13a97-143">La salida anterior indica que se produjo un error en la prueba porque no se encontró el usuario de destino.</span><span class="sxs-lookup"><span data-stu-id="13a97-143">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="13a97-144">Puede determinar si se ha pasado una dirección SIP válida a Test-CsAddressBookWebQuery mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="13a97-144">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="13a97-145">Si Test-CsAddressBookWebQuery da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="13a97-145">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="13a97-146">Cuando se incluye el parámetro verbose, Test-CsAddressBookWebQuery devolverá una cuenta paso a paso de cada acción que ha probado mientras se comprueba la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13a97-146">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="13a97-147">Por ejemplo, este resultado indica que Test-CsAddressBookWebQuery se pudo conectar al servicio de libreta de direcciones, pero no pudo encontrar la dirección SIP de destino:</span><span class="sxs-lookup"><span data-stu-id="13a97-147">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="13a97-148">Se inició la actividad ' QueryAddressBookWebService '.</span><span class="sxs-lookup"><span data-stu-id="13a97-148">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="13a97-149">Llamar al servicio de consulta Web de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="13a97-149">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="13a97-150">DIRECCIÓN URL DE ABWS =</span><span class="sxs-lookup"><span data-stu-id="13a97-150">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="13a97-151">Excepción de consulta de la libreta de direcciones: error en la solicitud de servicio Web de libreta de direcciones con código de respuesta NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="13a97-151">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="13a97-152">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="13a97-152">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="13a97-153">Estas son algunas de las razones comunes por las que Test-CsAddressBookWebQuery podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="13a97-153">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="13a97-154">Ha especificado una cuenta de usuario no válida.</span><span class="sxs-lookup"><span data-stu-id="13a97-154">You specified an invalid user account.</span></span> <span data-ttu-id="13a97-155">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="13a97-155">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="13a97-156">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13a97-156">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="13a97-157">Para comprobar que una cuenta de usuario se ha habilitado para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="13a97-157">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="13a97-158">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13a97-158">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="13a97-159">Es posible que el usuario de destino no esté en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="13a97-159">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="13a97-160">Es posible que la libreta de direcciones no se haya actualizado completamente y replicado.</span><span class="sxs-lookup"><span data-stu-id="13a97-160">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="13a97-161">Para forzar una actualización de todos los servidores de la libreta de direcciones de la organización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="13a97-161">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

