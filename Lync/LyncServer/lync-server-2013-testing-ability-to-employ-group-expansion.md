---
title: 'Lync Server 2013: probar la capacidad de usar la expansión de grupos'
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
ms.openlocfilehash: e8c12d687d6c23c7c7bdc2bf2d8046038154c871
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520747"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="aca8b-102">Probar la capacidad de usar la expansión de grupos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aca8b-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aca8b-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="aca8b-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aca8b-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="aca8b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="aca8b-105">Diario</span><span class="sxs-lookup"><span data-stu-id="aca8b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aca8b-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="aca8b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="aca8b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aca8b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aca8b-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="aca8b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="aca8b-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="aca8b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="aca8b-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsGroupExpansion.</span><span class="sxs-lookup"><span data-stu-id="aca8b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="aca8b-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aca8b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="aca8b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="aca8b-112">Description</span></span>

<span data-ttu-id="aca8b-113">El cmdlet Test-CsGroupExpansion le permite determinar si la expansión de grupos funciona en su organización.</span><span class="sxs-lookup"><span data-stu-id="aca8b-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="aca8b-114">Cuando la expansión de grupos está habilitada, los usuarios configuran los grupos de distribución como un contacto.</span><span class="sxs-lookup"><span data-stu-id="aca8b-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="aca8b-115">Esto significa que los usuarios pueden enviar el mismo mensaje instantáneo a todos los miembros del grupo al dirigir el mensaje al grupo en lugar de a los miembros individuales de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="aca8b-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="aca8b-116">La expansión de grupos permite ver, rápida y fácilmente, todos los miembros del grupo y su estado actual.</span><span class="sxs-lookup"><span data-stu-id="aca8b-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="aca8b-117">Con el cmdlet Test-CsGroupExpansion, debe especificar un grupo de distribución de Active Directory mediante la dirección de correo electrónico del grupo.</span><span class="sxs-lookup"><span data-stu-id="aca8b-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="aca8b-118">A continuación, Test-CsGroupExpansion usa la expansión de grupos para recuperar la pertenencia a grupos y compara la lista recuperada con la pertenencia de la dirección de correo electrónico del grupo que ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="aca8b-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="aca8b-119">Si las dos listas coinciden, la expansión de grupos funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="aca8b-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="aca8b-120">Tenga en cuenta que puede probar la expansión de grupos de dos maneras: probando el servicio mismo o probando el servicio web asociado.</span><span class="sxs-lookup"><span data-stu-id="aca8b-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="aca8b-121">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="aca8b-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="aca8b-122">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="aca8b-122">Running the test</span></span>

<span data-ttu-id="aca8b-123">El cmdlet Test-CsGroupExpansion se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que se haya habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aca8b-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="aca8b-124">Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando y la dirección de correo electrónico de un grupo de distribución válido.</span><span class="sxs-lookup"><span data-stu-id="aca8b-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="aca8b-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aca8b-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="aca8b-126">Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Lync Server que contenga el nombre y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="aca8b-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="aca8b-127">A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta cuando el sistema llame a test-CsGroupExpansion:</span><span class="sxs-lookup"><span data-stu-id="aca8b-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="aca8b-128">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="aca8b-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="aca8b-129">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="aca8b-129">Determining success or failure</span></span>

<span data-ttu-id="aca8b-130">Si el usuario especificado puede usar la expansión de grupo, recibirá un resultado similar al siguiente con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="aca8b-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="aca8b-131">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="aca8b-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="aca8b-132">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="aca8b-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="aca8b-133">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="aca8b-133">Result : Success</span></span>

<span data-ttu-id="aca8b-134">Latencia: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="aca8b-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="aca8b-135">Error</span><span class="sxs-lookup"><span data-stu-id="aca8b-135">Error :</span></span>

<span data-ttu-id="aca8b-136">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="aca8b-136">Diagnosis :</span></span>

<span data-ttu-id="aca8b-137">Si el usuario especificado no puede usar la expansión de grupo, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="aca8b-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="aca8b-138">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="aca8b-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="aca8b-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="aca8b-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="aca8b-140">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="aca8b-140">Result : Failure</span></span>

<span data-ttu-id="aca8b-141">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="aca8b-141">Latency : 00:00:00</span></span>

<span data-ttu-id="aca8b-142">Error</span><span class="sxs-lookup"><span data-stu-id="aca8b-142">Error :</span></span>

<span data-ttu-id="aca8b-143">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="aca8b-143">Diagnosis :</span></span>

<span data-ttu-id="aca8b-144">Test-CsGroupExpansion: no se pudo registrar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="aca8b-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="aca8b-145">Consulte ErrorCode por motivos específicos.</span><span class="sxs-lookup"><span data-stu-id="aca8b-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="aca8b-146">La salida anterior indica que se produjo un error en la prueba porque el usuario especificado no se pudo registrar con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aca8b-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="aca8b-147">Normalmente, esto ocurrirá si la cuenta de prueba no existe o no se ha habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aca8b-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="aca8b-148">Puede comprobar que la cuenta existe y determinar si la cuenta se ha habilitado para nm-OCS-14-3rd ejecutando un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="aca8b-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="aca8b-149">Si Test-CsGroupExpansion da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="aca8b-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="aca8b-150">Cuando se incluye el parámetro verbose, Test-CsGroupExpansion devolverá una cuenta paso a paso de cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aca8b-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="aca8b-151">Por ejemplo, este resultado indica que no se encontró el grupo de distribución especificado:</span><span class="sxs-lookup"><span data-stu-id="aca8b-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="aca8b-152">Intentando obtener el vale Web.</span><span class="sxs-lookup"><span data-stu-id="aca8b-152">Trying to get web ticket.</span></span>

<span data-ttu-id="aca8b-153">Dirección URL del servicio Web: https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="aca8b-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="aca8b-154">Uso de la autenticación NTLM/Kerbtray</span><span class="sxs-lookup"><span data-stu-id="aca8b-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="aca8b-155">GetWebTicketActivity completado.</span><span class="sxs-lookup"><span data-stu-id="aca8b-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="aca8b-156">Se inició la actividad ' VerifyDistributionList '.</span><span class="sxs-lookup"><span data-stu-id="aca8b-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="aca8b-157">El estado de respuesta del servicio Web de DLX es: NotFound.</span><span class="sxs-lookup"><span data-stu-id="aca8b-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="aca8b-158">Actividad ' VerifyDistributionList ' completada en ' 0,2597923 ' en segundos.</span><span class="sxs-lookup"><span data-stu-id="aca8b-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="aca8b-159">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="aca8b-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="aca8b-160">Estas son algunas de las razones comunes por las que Test-CsGroupExpansion podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="aca8b-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="aca8b-161">Ha especificado una cuenta de usuario no válida.</span><span class="sxs-lookup"><span data-stu-id="aca8b-161">You specified an invalid user account.</span></span> <span data-ttu-id="aca8b-162">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="aca8b-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="aca8b-163">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aca8b-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="aca8b-164">Para comprobar que una cuenta de usuario se habilitó para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="aca8b-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="aca8b-165">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aca8b-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="aca8b-166">La expansión del grupo puede estar deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="aca8b-166">Group expansion might be disabled.</span></span> <span data-ttu-id="aca8b-167">Es posible desactivar la expansión de grupos.</span><span class="sxs-lookup"><span data-stu-id="aca8b-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="aca8b-168">Si se deshabilitó la expansión de grupos, se producirá un error en el cmdlet Test-CsGroupExpansion.</span><span class="sxs-lookup"><span data-stu-id="aca8b-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="aca8b-169">Para determinar si la expansión de grupos está habilitada, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="aca8b-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

