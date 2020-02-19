---
title: 'Lync Server 2013: prueba de la configuración del servidor LIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ca367d288b219f3873f511173626500d5d43aa3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="f2e8f-102">Prueba de la configuración del servidor LIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2e8f-102">Testing LIS server configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2e8f-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f2e8f-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2e8f-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="f2e8f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f2e8f-105">Diario</span><span class="sxs-lookup"><span data-stu-id="f2e8f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2e8f-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="f2e8f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f2e8f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2e8f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2e8f-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="f2e8f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f2e8f-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f2e8f-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsLisConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="f2e8f-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f2e8f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f2e8f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2e8f-112">Description</span></span>

<span data-ttu-id="f2e8f-113">El cmdlet test-CsLisConfiguration comprueba su capacidad para ponerse en contacto con el servicio Web de LIS.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="f2e8f-114">Si se puede contactar con el servicio Web, la prueba se considerará un éxito, independientemente de si se encuentra alguna ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f2e8f-115">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="f2e8f-115">Running the test</span></span>

<span data-ttu-id="f2e8f-116">El cmdlet test-CsLisConfguration se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="f2e8f-117">Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="f2e8f-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f2e8f-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f2e8f-119">Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="f2e8f-120">A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta al llamar a test-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="f2e8f-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="f2e8f-121">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="f2e8f-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f2e8f-122">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="f2e8f-122">Determining success or failure</span></span>

<span data-ttu-id="f2e8f-123">Si el LIS está configurado correctamente, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="f2e8f-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f2e8f-124">TargetUrihttps://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="f2e8f-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="f2e8f-125">liservice. SVC</span><span class="sxs-lookup"><span data-stu-id="f2e8f-125">liservice.svc</span></span>

<span data-ttu-id="f2e8f-126">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2e8f-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f2e8f-127">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="f2e8f-127">Result : Success</span></span>

<span data-ttu-id="f2e8f-128">Latencia: 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="f2e8f-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="f2e8f-129">Error</span><span class="sxs-lookup"><span data-stu-id="f2e8f-129">Error :</span></span>

<span data-ttu-id="f2e8f-130">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f2e8f-130">Diagnosis :</span></span>

<span data-ttu-id="f2e8f-131">Si el usuario especificado no puede iniciar o cerrar sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="f2e8f-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f2e8f-132">TargetUri</span><span class="sxs-lookup"><span data-stu-id="f2e8f-132">TargetUri :</span></span>

<span data-ttu-id="f2e8f-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2e8f-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f2e8f-134">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="f2e8f-134">Result : Failure</span></span>

<span data-ttu-id="f2e8f-135">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f2e8f-135">Latency : 00:00:00</span></span>

<span data-ttu-id="f2e8f-136">Error: 11004, el nombre solicitado es válido pero no hay datos de la solicitud</span><span class="sxs-lookup"><span data-stu-id="f2e8f-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="f2e8f-137">se encontró el tipo</span><span class="sxs-lookup"><span data-stu-id="f2e8f-137">type was found</span></span>

<span data-ttu-id="f2e8f-138">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f2e8f-138">Diagnosis :</span></span>

<span data-ttu-id="f2e8f-139">Test-CsLisConfiguration: no se encontró ningún clúster que coincida en la topología.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="f2e8f-140">Por ejemplo, la salida anterior incluye la nota "no se encontró ningún clúster que coincida en la topología".</span><span class="sxs-lookup"><span data-stu-id="f2e8f-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="f2e8f-141">Esto suele indicar un problema con el servidor perimetral: el LIS que usa el servidor perimetral para conectarse al proveedor de servicios y validar las direcciones.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="f2e8f-142">Si test-CsLisConfiguration produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="f2e8f-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="f2e8f-143">Cuando se incluye el parámetro verbose, test-CsLisConfiguration devolverá una cuenta paso a paso de cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="f2e8f-144">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f2e8f-144">For example:</span></span>

<span data-ttu-id="f2e8f-145">Servicio de información de ubicación de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-145">Calling Location Information Service.</span></span>

<span data-ttu-id="f2e8f-146">Ruta de acceso al servicio =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="f2e8f-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="f2e8f-147">Subnet =</span><span class="sxs-lookup"><span data-stu-id="f2e8f-147">Subnet =</span></span>

<span data-ttu-id="f2e8f-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="f2e8f-148">BssId = 5</span></span>

<span data-ttu-id="f2e8f-149">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="f2e8f-149">ChassisId =</span></span>

<span data-ttu-id="f2e8f-150">PortId =</span><span class="sxs-lookup"><span data-stu-id="f2e8f-150">PortId =</span></span>

<span data-ttu-id="f2e8f-151">PortIdSubType = tipo no definido</span><span class="sxs-lookup"><span data-stu-id="f2e8f-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="f2e8f-152">Mac</span><span class="sxs-lookup"><span data-stu-id="f2e8f-152">Mac</span></span>

<span data-ttu-id="f2e8f-153">Error en la solicitud de servicio Web de información de ubicación de la excepción con un código de respuesta Item400.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="f2e8f-154">se produjeron durante la ejecución del flujo de trabajo Microsoft. RTC. SyntheticTrsnactions. workflows. STLisConfigurationWorkflow.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="f2e8f-155">Si examina atentamente la salida anterior, verá que el cmdlet produjo un error después de intentar llamar al servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="f2e8f-156">Uno de los parámetros usados en la llamada fue el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2e8f-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="f2e8f-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="f2e8f-157">BssId = 5</span></span>

<span data-ttu-id="f2e8f-158">No es un valor válido para el identificador de conjunto de servicios (BssID) básico.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="f2e8f-159">En su lugar, un BssID debe tener un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="f2e8f-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="f2e8f-160">12-34-56-78-90-AB</span><span class="sxs-lookup"><span data-stu-id="f2e8f-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f2e8f-161">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="f2e8f-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="f2e8f-162">Estas son algunas de las razones comunes por las que test-CsLisConfiguration podría fallar:</span><span class="sxs-lookup"><span data-stu-id="f2e8f-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="f2e8f-163">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="f2e8f-164">Como se muestra en el ejemplo anterior, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="f2e8f-165">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="f2e8f-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

