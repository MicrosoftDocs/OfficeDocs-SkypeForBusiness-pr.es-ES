---
title: 'Lync Server 2013: validación de la consulta Web de la libreta de direcciones'
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
ms.openlocfilehash: 2db1e1e0a94a73c520a3beb0ea1375688b106cfc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="e6f6b-102">Validación de la consulta Web de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f6b-102">Validating address book web query in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6f6b-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e6f6b-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6f6b-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="e6f6b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e6f6b-105">Diario</span><span class="sxs-lookup"><span data-stu-id="e6f6b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6f6b-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="e6f6b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e6f6b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6f6b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6f6b-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="e6f6b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e6f6b-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e6f6b-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsAddressBookWebQuery.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="e6f6b-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e6f6b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6f6b-112">Description</span></span>

<span data-ttu-id="e6f6b-113">El cmdlet test-CsAddressBookWebQuery permite a los administradores comprobar que los usuarios pueden usar el servicio de consulta Web de libreta de direcciones para buscar un contacto específico.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="e6f6b-114">Al ejecutar el cmdlet, test-CsAddressBookWebQuery se conectará primero al servicio de vale web para autenticarse.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="e6f6b-115">Si la autenticación se realiza correctamente, el cmdlet se conectará al servicio de consulta Web de la libreta de direcciones y buscará el contacto especificado.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="e6f6b-116">Si se encuentra ese contacto, el cmdlet intentará devolver esa información al equipo local.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="e6f6b-117">La prueba se marcará como correcta solo si se pueden completar todos los pasos.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="e6f6b-118">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="e6f6b-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e6f6b-119">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="e6f6b-119">Running the test</span></span>

<span data-ttu-id="e6f6b-120">El cmdlet test-CsAddressBookWebQuery se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="e6f6b-121">Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server y la dirección SIP del usuario que actúa como destino de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="e6f6b-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="e6f6b-123">Para ejecutar esta comprobación con una cuenta de usuario real, debe crear un objeto de credenciales de Windows PowerShell que contenga un nombre de usuario y una contraseña válidos.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="e6f6b-124">A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta cuando el código llame a test-CsAddressBookWebQuery:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="e6f6b-125">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="e6f6b-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e6f6b-126">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="e6f6b-126">Determining success or failure</span></span>

<span data-ttu-id="e6f6b-127">Si el usuario especificado puede conectarse al servicio de libreta de direcciones y recuperar la dirección del usuario de destino, se devuelve un resultado similar al siguiente con la propiedad result marcada como correcta:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="e6f6b-128">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="e6f6b-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="e6f6b-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e6f6b-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e6f6b-130">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="e6f6b-130">Result : Success</span></span>

<span data-ttu-id="e6f6b-131">Latencia: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="e6f6b-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="e6f6b-132">Error</span><span class="sxs-lookup"><span data-stu-id="e6f6b-132">Error :</span></span>

<span data-ttu-id="e6f6b-133">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e6f6b-133">Diagnosis :</span></span>

<span data-ttu-id="e6f6b-134">Si el usuario especificado no se puede conectar o si no se puede recuperar la dirección de usuario de destino, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e6f6b-135">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="e6f6b-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="e6f6b-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e6f6b-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e6f6b-137">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="e6f6b-137">Result : Failure</span></span>

<span data-ttu-id="e6f6b-138">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e6f6b-138">Latency : 00:00:00</span></span>

<span data-ttu-id="e6f6b-139">Error: error en la solicitud del servicio Web de libreta de direcciones con código de respuesta</span><span class="sxs-lookup"><span data-stu-id="e6f6b-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="e6f6b-140">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-140">NoEntryFound.</span></span>

<span data-ttu-id="e6f6b-141">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e6f6b-141">Diagnosis :</span></span>

<span data-ttu-id="e6f6b-142">La salida anterior indica que se produjo un error en la prueba porque no se encontró el usuario de destino.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="e6f6b-143">Puede determinar si se ha pasado una dirección SIP válida a test-CsAddressBookWebQuery mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="e6f6b-144">Si test-CsAddressBookWebQuery produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="e6f6b-145">Cuando se incluye el parámetro verbose, test-CsAddressBookWebQuery devolverá una cuenta paso a paso de cada acción que ha probado mientras se comprueba la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="e6f6b-146">Por ejemplo, este resultado indica que test-CsAddressBookWebQuery se pudo conectar al servicio de libreta de direcciones, pero no pudo encontrar la dirección SIP de destino:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="e6f6b-147">Se inició la actividad ' QueryAddressBookWebService '.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="e6f6b-148">Llamar al servicio de consulta Web de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="e6f6b-149">DIRECCIÓN URL DE ABWS =</span><span class="sxs-lookup"><span data-stu-id="e6f6b-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="e6f6b-150">Excepción de consulta de la libreta de direcciones: error en la solicitud de servicio Web de libreta de direcciones con código de respuesta NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e6f6b-151">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="e6f6b-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="e6f6b-152">Estas son algunas de las razones comunes por las que test-CsAddressBookWebQuery podría fallar:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="e6f6b-153">Ha especificado una cuenta de usuario no válida.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-153">You specified an invalid user account.</span></span> <span data-ttu-id="e6f6b-154">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e6f6b-155">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="e6f6b-156">Para comprobar que una cuenta de usuario se ha habilitado para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="e6f6b-157">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="e6f6b-158">Es posible que el usuario de destino no esté en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="e6f6b-159">Es posible que la libreta de direcciones no se haya actualizado completamente y replicado.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="e6f6b-160">Para forzar una actualización de todos los servidores de la libreta de direcciones de la organización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e6f6b-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

