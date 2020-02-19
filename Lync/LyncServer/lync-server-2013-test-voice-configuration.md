---
title: 'Lync Server 2013: probar la configuración de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f0d5c8aef7c3cca22a41f591a208413cc453898
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="b4227-102">Probar la configuración de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4227-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4227-103">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="b4227-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4227-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="b4227-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b4227-105">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="b4227-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4227-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="b4227-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b4227-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4227-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4227-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="b4227-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b4227-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b4227-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b4227-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b4227-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="b4227-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4227-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b4227-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4227-112">Description</span></span>

<span data-ttu-id="b4227-113">Lync Server incluye varios cmdlets de Windows PowerShell (como test-CsVoiceRoute y test-CsVoicePolicy, test-CsTrunkConfiguration) que le permiten comprobar que las partes individuales de su infraestructura de telefonía IP empresarial (rutas de voz, voz) directivas, troncos SIP: funcionan según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="b4227-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="b4227-114">Aunque es importante con telefonía IP empresarial que funcionan todas las piezas individuales: es posible tener una ruta de voz válida, una directiva de voz válida y un tronco SIP válido, pero seguir haciendo que los usuarios no puedan realizar o recibir llamadas telefónicas.</span><span class="sxs-lookup"><span data-stu-id="b4227-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="b4227-115">Por eso, Lync Server también ofrece la posibilidad de crear configuraciones de prueba de voz.</span><span class="sxs-lookup"><span data-stu-id="b4227-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="b4227-116">Las configuraciones de prueba de voz representan escenarios comunes de Enterprise Voice: puede especificar aspectos como una ruta de voz, una directiva de voz y un plan de marcado y, a continuación, comprobar que esos elementos individuales funcionan conjuntamente para proporcionar el servicio telefónico.</span><span class="sxs-lookup"><span data-stu-id="b4227-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="b4227-117">Además, puede validar sus expectativas en un escenario determinado.</span><span class="sxs-lookup"><span data-stu-id="b4227-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="b4227-118">Por ejemplo, supongamos que espera que la combinación de plan de marcado A y Directiva de voz B dé como resultado que las llamadas se enruten a través de la ruta de voz C. Puede escribir la ruta de voz C como ExpectedRoute.</span><span class="sxs-lookup"><span data-stu-id="b4227-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="b4227-119">Cuando se ejecuta la prueba, si no se usa la ruta de voz C, la prueba se marcará como con error.</span><span class="sxs-lookup"><span data-stu-id="b4227-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b4227-120">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="b4227-120">Running the test</span></span>

<span data-ttu-id="b4227-121">Antes de probar las colecciones de configuración de voz con Windows PowerShell, primero debe usar el cmdlet Get-CsVoiceTestConfiguration para recuperar una instancia de estas opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="b4227-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="b4227-122">A continuación, esa instancia se debe canalizar a test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b4227-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="b4227-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b4227-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="b4227-124">Para validar todas las opciones de configuración de prueba de voz al mismo tiempo, use este comando en su lugar:</span><span class="sxs-lookup"><span data-stu-id="b4227-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="b4227-125">Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoiceTestConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b4227-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b4227-126">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="b4227-126">Determining success or failure</span></span>

<span data-ttu-id="b4227-127">El cmdlet test-CsVoiceTestConfiguration informa si una prueba ha tenido éxito o no se ha realizado correctamente y proporciona información adicional acerca de cada una de las pruebas, como la regla de conversión, la ruta de voz y el uso de RTC que se usan para completar la tarea:</span><span class="sxs-lookup"><span data-stu-id="b4227-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="b4227-128">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="b4227-128">Result:             Success</span></span>

<span data-ttu-id="b4227-129">TranslatedNumber: + 15551234</span><span class="sxs-lookup"><span data-stu-id="b4227-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="b4227-130">MatchingRule: Description =; Pattern = ^ (\\d{4}) $; Traducción = + 1\\d; Name = test; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="b4227-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="b4227-131">FirstMatchingRoute: sitio: Redmond</span><span class="sxs-lookup"><span data-stu-id="b4227-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="b4227-132">MatchingUsage: local</span><span class="sxs-lookup"><span data-stu-id="b4227-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="b4227-133">Si se produce un error en la prueba, se notifica que el resultado es incorrecto:</span><span class="sxs-lookup"><span data-stu-id="b4227-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="b4227-134">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="b4227-134">Result:             Fail</span></span>

<span data-ttu-id="b4227-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="b4227-135">TranslatedNumber:</span></span>   

<span data-ttu-id="b4227-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="b4227-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="b4227-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="b4227-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b4227-138">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="b4227-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="b4227-139">Debido a que la prueba de la configuración de prueba de voz prueba varios elementos diferentes, como directivas de voz, planes de marcado, rutas de voz, etc., hay varios factores diferentes que podrían dar como resultado una prueba con errores.</span><span class="sxs-lookup"><span data-stu-id="b4227-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="b4227-140">Si se produce un error en una prueba, el primer paso debe ser revisar las opciones de configuración mediante el cmdlet Get-CsVoiceTestConfiguration:</span><span class="sxs-lookup"><span data-stu-id="b4227-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="b4227-141">Si la configuración parece estar correctamente configurada, vuelva a ejecutar la prueba al incluir el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="b4227-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="b4227-142">El parámetro verbose proporcionará una cuenta paso a paso de cada acción que test-CsVoiceTestConfiguration toma como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b4227-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="b4227-143">VERBOse: cargando plan de marcado: "global"</span><span class="sxs-lookup"><span data-stu-id="b4227-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="b4227-144">VERBOse: cargando Directiva de voz: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="b4227-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="b4227-145">Esta cuenta paso a paso puede proporcionar una pista útil sobre dónde se produjo el error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="b4227-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="b4227-146">Si no es así, puede usar otros cmdlets de Windows PowerShell (como test-CsVoicePolicy) y empezar a comprobar los componentes individuales que se incluyen en las opciones de configuración de la prueba de voz.</span><span class="sxs-lookup"><span data-stu-id="b4227-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="b4227-147">Además, tenga en cuenta que es posible que una prueba pueda enrutar una llamada y que todavía se marque como un error; Esto puede ocurrir si escribe valores para ExpectedRoute, ExpectedTranslatedNumber y ExpectedUsage, y no se cumple alguna de estas expectativas.</span><span class="sxs-lookup"><span data-stu-id="b4227-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="b4227-148">Por ejemplo, supongamos que escribe ruta de voz C como la ruta de voz esperada, pero la prueba completa realmente la llamada usando la ruta de voz D. En ese caso, la prueba se marcará como fallida porque no se usó la ruta de voz esperada.</span><span class="sxs-lookup"><span data-stu-id="b4227-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="b4227-149">Si se produce un error en una prueba, puede quitar los valores de ExpectedRoute, ExpectedTranslatedNumber y ExpectedUsage y, a continuación, volver a ejecutar la prueba.</span><span class="sxs-lookup"><span data-stu-id="b4227-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="b4227-150">Esto le ayudará a determinar si el error se debe a que la llamada no se ha podido completar o porque se espera una cosa y se recibe realmente otra.</span><span class="sxs-lookup"><span data-stu-id="b4227-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4227-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4227-151">See Also</span></span>


[<span data-ttu-id="b4227-152">Test-CsVoiceTestConfiguration</span><span class="sxs-lookup"><span data-stu-id="b4227-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

