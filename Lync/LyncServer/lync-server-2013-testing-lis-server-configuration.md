---
title: 'Lync Server 2013: prueba de la configuración del servidor LIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e5baed37e4c72da8b8348dab9702b5d22fbbc5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="9da51-102">Probar la configuración del servidor LIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9da51-102">Testing LIS server configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9da51-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9da51-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9da51-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="9da51-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9da51-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="9da51-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da51-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="9da51-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9da51-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9da51-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da51-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="9da51-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9da51-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9da51-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9da51-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsLisConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9da51-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="9da51-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9da51-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9da51-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9da51-112">Description</span></span>

<span data-ttu-id="9da51-113">El cmdlet test-CsLisConfiguration verifica su capacidad para ponerse en contacto con el servicio Web de LIS.</span><span class="sxs-lookup"><span data-stu-id="9da51-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="9da51-114">Si se puede contactar con el servicio Web, la prueba se considerará satisfactoria, independientemente de si se puede encontrar algún lugar específico.</span><span class="sxs-lookup"><span data-stu-id="9da51-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9da51-115">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="9da51-115">Running the test</span></span>

<span data-ttu-id="9da51-116">El cmdlet test-CsLisConfguration se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9da51-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="9da51-117">Para ejecutar esta comprobación mediante una cuenta de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando.</span><span class="sxs-lookup"><span data-stu-id="9da51-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="9da51-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9da51-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="9da51-119">Para ejecutar esta comprobación mediante una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre de la cuenta y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="9da51-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="9da51-120">Después debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta al llamar a test-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="9da51-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="9da51-121">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="9da51-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9da51-122">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="9da51-122">Determining success or failure</span></span>

<span data-ttu-id="9da51-123">Si el LIS está configurado correctamente, recibirá un resultado similar a este, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="9da51-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9da51-124">TargetUrihttps://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="9da51-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="9da51-125">liservice. SVC</span><span class="sxs-lookup"><span data-stu-id="9da51-125">liservice.svc</span></span>

<span data-ttu-id="9da51-126">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9da51-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9da51-127">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="9da51-127">Result : Success</span></span>

<span data-ttu-id="9da51-128">Latencia: 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="9da51-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="9da51-129">:</span><span class="sxs-lookup"><span data-stu-id="9da51-129">Error :</span></span>

<span data-ttu-id="9da51-130">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="9da51-130">Diagnosis :</span></span>

<span data-ttu-id="9da51-131">Si el usuario especificado no puede iniciar sesión o cerrar sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="9da51-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9da51-132">TargetUri</span><span class="sxs-lookup"><span data-stu-id="9da51-132">TargetUri :</span></span>

<span data-ttu-id="9da51-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9da51-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9da51-134">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="9da51-134">Result : Failure</span></span>

<span data-ttu-id="9da51-135">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9da51-135">Latency : 00:00:00</span></span>

<span data-ttu-id="9da51-136">Error: 11004, el nombre solicitado es válido pero no se han especificado datos del</span><span class="sxs-lookup"><span data-stu-id="9da51-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="9da51-137">se encontró el tipo</span><span class="sxs-lookup"><span data-stu-id="9da51-137">type was found</span></span>

<span data-ttu-id="9da51-138">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="9da51-138">Diagnosis :</span></span>

<span data-ttu-id="9da51-139">Prueba-CsLisConfiguration: no se encontró ningún clúster coincidente en la topología.</span><span class="sxs-lookup"><span data-stu-id="9da51-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="9da51-140">Por ejemplo, la salida anterior incluye la nota "no se encontró ningún clúster coincidente en la topología".</span><span class="sxs-lookup"><span data-stu-id="9da51-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="9da51-141">Esto suele indicar un problema con el servidor perimetral: LIS con el servidor perimetral para conectarse al proveedor de servicios y validar las direcciones.</span><span class="sxs-lookup"><span data-stu-id="9da51-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="9da51-142">Si prueba-CsLisConfiguration da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:</span><span class="sxs-lookup"><span data-stu-id="9da51-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="9da51-143">Cuando se incluye el parámetro detallado, test-CsLisConfiguration devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9da51-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="9da51-144">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9da51-144">For example:</span></span>

<span data-ttu-id="9da51-145">Servicio de información de ubicación de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9da51-145">Calling Location Information Service.</span></span>

<span data-ttu-id="9da51-146">Ruta de servicio =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="9da51-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="9da51-147">Subnet =</span><span class="sxs-lookup"><span data-stu-id="9da51-147">Subnet =</span></span>

<span data-ttu-id="9da51-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="9da51-148">BssId = 5</span></span>

<span data-ttu-id="9da51-149">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="9da51-149">ChassisId =</span></span>

<span data-ttu-id="9da51-150">PortId =</span><span class="sxs-lookup"><span data-stu-id="9da51-150">PortId =</span></span>

<span data-ttu-id="9da51-151">PortIdSubType = tipo no definido</span><span class="sxs-lookup"><span data-stu-id="9da51-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="9da51-152">Mac</span><span class="sxs-lookup"><span data-stu-id="9da51-152">Mac</span></span>

<span data-ttu-id="9da51-153">Error en la solicitud de servicio Web de información de ubicación de excepción con un código de respuesta de Item400 '.</span><span class="sxs-lookup"><span data-stu-id="9da51-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="9da51-154">durante el flujo de trabajo, Microsoft. RTC. SyntheticTrsnactions. workflows. STLisConfigurationWorkflow Execution.</span><span class="sxs-lookup"><span data-stu-id="9da51-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="9da51-155">Si examina atentamente la salida anterior, verá que el cmdlet falló después de intentar llamar al servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="9da51-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="9da51-156">Uno de los parámetros que se usó en la llamada fue este:</span><span class="sxs-lookup"><span data-stu-id="9da51-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="9da51-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="9da51-157">BssId = 5</span></span>

<span data-ttu-id="9da51-158">Ese no es un valor válido para el identificador de conjunto de servicios (BssID) básico.</span><span class="sxs-lookup"><span data-stu-id="9da51-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="9da51-159">En su lugar, un BssID debe tener un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="9da51-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="9da51-160">12-34-56-78-90-AB</span><span class="sxs-lookup"><span data-stu-id="9da51-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9da51-161">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="9da51-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="9da51-162">Estas son algunas de las razones comunes por las que test-CsLisConfiguration podría fallar:</span><span class="sxs-lookup"><span data-stu-id="9da51-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="9da51-163">Se proporcionó un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="9da51-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="9da51-164">Tal y como se muestra en el ejemplo anterior, los parámetros opcionales deben estar configurados correctamente o no se puede realizar la prueba.</span><span class="sxs-lookup"><span data-stu-id="9da51-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="9da51-165">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="9da51-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

