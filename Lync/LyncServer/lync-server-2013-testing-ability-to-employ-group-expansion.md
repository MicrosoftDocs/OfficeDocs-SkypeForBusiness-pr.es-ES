---
title: 'Lync Server 2013: probar la capacidad de usar la expansión de grupos'
description: 'Lync Server 2013: probar la capacidad de usar la expansión de grupos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6267bc2099fc420c5c57e1ef80f4bf4491334938
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560796"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="83eb1-103">Probar la capacidad de usar la expansión de grupos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83eb1-103">Testing ability to employ group expansion in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83eb1-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="83eb1-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83eb1-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="83eb1-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="83eb1-106">Diario</span><span class="sxs-lookup"><span data-stu-id="83eb1-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83eb1-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="83eb1-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="83eb1-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="83eb1-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83eb1-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="83eb1-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="83eb1-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="83eb1-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="83eb1-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsGroupExpansion.</span><span class="sxs-lookup"><span data-stu-id="83eb1-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="83eb1-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="83eb1-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="83eb1-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="83eb1-113">Description</span></span>

<span data-ttu-id="83eb1-114">El cmdlet Test-CsGroupExpansion le permite determinar si la expansión de grupos funciona en su organización.</span><span class="sxs-lookup"><span data-stu-id="83eb1-114">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="83eb1-115">Cuando la expansión de grupos está habilitada, los usuarios configuran los grupos de distribución como un contacto.</span><span class="sxs-lookup"><span data-stu-id="83eb1-115">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="83eb1-116">Esto significa que los usuarios pueden enviar el mismo mensaje instantáneo a todos los miembros del grupo al dirigir el mensaje al grupo en lugar de a los miembros individuales de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="83eb1-116">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="83eb1-117">La expansión de grupos permite ver, rápida y fácilmente, todos los miembros del grupo y su estado actual.</span><span class="sxs-lookup"><span data-stu-id="83eb1-117">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="83eb1-118">Con el cmdlet Test-CsGroupExpansion, debe especificar un grupo de distribución de Active Directory mediante la dirección de correo electrónico del grupo.</span><span class="sxs-lookup"><span data-stu-id="83eb1-118">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="83eb1-119">A continuación, Test-CsGroupExpansion usa la expansión de grupos para recuperar la pertenencia a grupos y compara la lista recuperada con la pertenencia de la dirección de correo electrónico del grupo que ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="83eb1-119">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="83eb1-120">Si las dos listas coinciden, la expansión de grupos funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="83eb1-120">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="83eb1-121">Tenga en cuenta que puede probar la expansión de grupos de dos maneras: probando el servicio mismo o probando el servicio web asociado.</span><span class="sxs-lookup"><span data-stu-id="83eb1-121">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="83eb1-122">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="83eb1-122">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="83eb1-123">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="83eb1-123">Running the test</span></span>

<span data-ttu-id="83eb1-124">El cmdlet Test-CsGroupExpansion se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que se haya habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83eb1-124">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="83eb1-125">Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando y la dirección de correo electrónico de un grupo de distribución válido.</span><span class="sxs-lookup"><span data-stu-id="83eb1-125">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="83eb1-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="83eb1-126">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="83eb1-127">Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Lync Server que contenga el nombre y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="83eb1-127">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="83eb1-128">A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta cuando el sistema llame a test-CsGroupExpansion:</span><span class="sxs-lookup"><span data-stu-id="83eb1-128">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="83eb1-129">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="83eb1-129">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="83eb1-130">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="83eb1-130">Determining success or failure</span></span>

<span data-ttu-id="83eb1-131">Si el usuario especificado puede usar la expansión de grupo, recibirá un resultado similar al siguiente con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="83eb1-131">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="83eb1-132">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="83eb1-132">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="83eb1-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="83eb1-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="83eb1-134">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="83eb1-134">Result : Success</span></span>

<span data-ttu-id="83eb1-135">Latencia: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="83eb1-135">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="83eb1-136">Error</span><span class="sxs-lookup"><span data-stu-id="83eb1-136">Error :</span></span>

<span data-ttu-id="83eb1-137">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="83eb1-137">Diagnosis :</span></span>

<span data-ttu-id="83eb1-138">Si el usuario especificado no puede usar la expansión de grupo, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="83eb1-138">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="83eb1-139">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="83eb1-139">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="83eb1-140">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="83eb1-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="83eb1-141">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="83eb1-141">Result : Failure</span></span>

<span data-ttu-id="83eb1-142">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="83eb1-142">Latency : 00:00:00</span></span>

<span data-ttu-id="83eb1-143">Error</span><span class="sxs-lookup"><span data-stu-id="83eb1-143">Error :</span></span>

<span data-ttu-id="83eb1-144">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="83eb1-144">Diagnosis :</span></span>

<span data-ttu-id="83eb1-145">Test-CsGroupExpansion: no se pudo registrar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="83eb1-145">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="83eb1-146">Consulte ErrorCode por motivos específicos.</span><span class="sxs-lookup"><span data-stu-id="83eb1-146">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="83eb1-147">La salida anterior indica que se produjo un error en la prueba porque el usuario especificado no se pudo registrar con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83eb1-147">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="83eb1-148">Normalmente, esto ocurrirá si la cuenta de prueba no existe o no se ha habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83eb1-148">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="83eb1-149">Puede comprobar que la cuenta existe y determinar si la cuenta se ha habilitado para nm-OCS-14-3rd ejecutando un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="83eb1-149">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="83eb1-150">Si Test-CsGroupExpansion da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="83eb1-150">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="83eb1-151">Cuando se incluye el parámetro verbose, Test-CsGroupExpansion devolverá una cuenta paso a paso de cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83eb1-151">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="83eb1-152">Por ejemplo, este resultado indica que no se encontró el grupo de distribución especificado:</span><span class="sxs-lookup"><span data-stu-id="83eb1-152">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="83eb1-153">Intentando obtener el vale Web.</span><span class="sxs-lookup"><span data-stu-id="83eb1-153">Trying to get web ticket.</span></span>

<span data-ttu-id="83eb1-154">Dirección URL del servicio Web: https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="83eb1-154">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="83eb1-155">Uso de la autenticación NTLM/Kerbtray</span><span class="sxs-lookup"><span data-stu-id="83eb1-155">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="83eb1-156">GetWebTicketActivity completado.</span><span class="sxs-lookup"><span data-stu-id="83eb1-156">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="83eb1-157">Se inició la actividad ' VerifyDistributionList '.</span><span class="sxs-lookup"><span data-stu-id="83eb1-157">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="83eb1-158">El estado de respuesta del servicio Web de DLX es: NotFound.</span><span class="sxs-lookup"><span data-stu-id="83eb1-158">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="83eb1-159">Actividad ' VerifyDistributionList ' completada en ' 0,2597923 ' en segundos.</span><span class="sxs-lookup"><span data-stu-id="83eb1-159">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="83eb1-160">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="83eb1-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="83eb1-161">Estas son algunas de las razones comunes por las que Test-CsGroupExpansion podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="83eb1-161">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="83eb1-162">Ha especificado una cuenta de usuario no válida.</span><span class="sxs-lookup"><span data-stu-id="83eb1-162">You specified an invalid user account.</span></span> <span data-ttu-id="83eb1-163">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="83eb1-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="83eb1-164">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83eb1-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="83eb1-165">Para comprobar que una cuenta de usuario se habilitó para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="83eb1-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="83eb1-166">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83eb1-166">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="83eb1-167">La expansión del grupo puede estar deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="83eb1-167">Group expansion might be disabled.</span></span> <span data-ttu-id="83eb1-168">Es posible desactivar la expansión de grupos.</span><span class="sxs-lookup"><span data-stu-id="83eb1-168">It is possible to turn off group expansion.</span></span> <span data-ttu-id="83eb1-169">Si se deshabilitó la expansión de grupos, se producirá un error en el cmdlet Test-CsGroupExpansion.</span><span class="sxs-lookup"><span data-stu-id="83eb1-169">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="83eb1-170">Para determinar si la expansión de grupos está habilitada, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="83eb1-170">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

