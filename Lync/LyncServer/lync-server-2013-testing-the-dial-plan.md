---
title: 'Lync Server 2013: probar el plan de marcado'
description: 'Lync Server 2013: probar el plan de marcado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef2e3fce9d1fbbb0186b1b7aef608834145d3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556176"
---
# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="ca117-103">Probar el plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca117-103">Testing the dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca117-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ca117-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca117-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="ca117-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ca117-106">Diario</span><span class="sxs-lookup"><span data-stu-id="ca117-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca117-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="ca117-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ca117-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca117-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca117-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="ca117-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ca117-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ca117-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ca117-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="ca117-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="ca117-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ca117-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ca117-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca117-113">Description</span></span>

<span data-ttu-id="ca117-114">El cmdlet Test-CsDialPlan permite ver los resultados de la aplicación de un plan de marcado a un número de teléfono determinado.</span><span class="sxs-lookup"><span data-stu-id="ca117-114">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="ca117-115">Los planes de marcado proporcionan información, como la forma en que se aplican las reglas de normalización, necesarias para permitir a los usuarios de Enterprise Voice realizar llamadas telefónicas.</span><span class="sxs-lookup"><span data-stu-id="ca117-115">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="ca117-116">Después de especificar un número de marcado y un plan de marcado, el cmdlet verificará qué regla de normalización del plan de marcado se aplicará y cuál será el número traducido.</span><span class="sxs-lookup"><span data-stu-id="ca117-116">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="ca117-117">Puede usar este cmdlet para solucionar problemas con las traducciones de números o para comprobar cómo aplicar reglas a determinados números.</span><span class="sxs-lookup"><span data-stu-id="ca117-117">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ca117-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="ca117-118">Running the test</span></span>

<span data-ttu-id="ca117-119">El cmdlet Test-CsDialPlan requiere que haga dos cosas.</span><span class="sxs-lookup"><span data-stu-id="ca117-119">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="ca117-120">En primer lugar, debe obtener una instancia del plan de marcado que se está probando; Esto se puede hacer con el cmdlet Get-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="ca117-120">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="ca117-121">En segundo lugar, debe especificar el número de teléfono que se va a normalizar.</span><span class="sxs-lookup"><span data-stu-id="ca117-121">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="ca117-122">El formato que se usa para el número de teléfono debe coincidir con el número marcado o escrito por un usuario.</span><span class="sxs-lookup"><span data-stu-id="ca117-122">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="ca117-123">Por ejemplo, este comando recupera una instancia del plan de marcado, RedmondDialPlan, y comprueba si el número de teléfono 12065551219 se puede normalizar:</span><span class="sxs-lookup"><span data-stu-id="ca117-123">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="ca117-124">Si tiene una regla de normalización que agrega automáticamente el código de país (en este ejemplo, 1) y el código de área (206), es posible que desee comprobar el número de teléfono 5551219 de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ca117-124">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="ca117-125">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .</span><span class="sxs-lookup"><span data-stu-id="ca117-125">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ca117-126">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="ca117-126">Determining success or failure</span></span>

<span data-ttu-id="ca117-127">Test-CsDialPlan difieren de muchos de los cmdlets de prueba de Lync Server porque solo indica indirectamente si una prueba se ha realizado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="ca117-127">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="ca117-128">Cuando se usa Test-CsDialPlan no recibe un resultado similar al siguiente con el resultado claramente marcado:</span><span class="sxs-lookup"><span data-stu-id="ca117-128">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="ca117-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ca117-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ca117-130">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="ca117-130">Result : Success</span></span>

<span data-ttu-id="ca117-131">Latencia: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="ca117-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="ca117-132">Error</span><span class="sxs-lookup"><span data-stu-id="ca117-132">Error :</span></span>

<span data-ttu-id="ca117-133">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ca117-133">Diagnosis :</span></span>

<span data-ttu-id="ca117-134">En su lugar, si Test-CsDialPlan tiene éxito, recibirá información acerca de la regla de normalización que pudo traducir correctamente y usar el número de teléfono especificado:</span><span class="sxs-lookup"><span data-stu-id="ca117-134">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="ca117-135">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="ca117-135">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="ca117-136">MatchingRule: Description =; Pattern = ^ ( \\ d (11)) $; Traducción = + $1;</span><span class="sxs-lookup"><span data-stu-id="ca117-136">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="ca117-137">Name = prefix All; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="ca117-137">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="ca117-138">Si Test-CsDialPlan da error (es decir, si el plan de marcado no tiene una regla de normalización que pueda traducir el número de teléfono especificado), solo recibirá el resultado "vacío" de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ca117-138">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="ca117-139">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="ca117-139">TranslatedNumber :</span></span>

<span data-ttu-id="ca117-140">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="ca117-140">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ca117-141">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="ca117-141">Reasons why the test might have failed</span></span>

<span data-ttu-id="ca117-142">Estas son algunas de las razones comunes por las que Test-CsDialPlan podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="ca117-142">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="ca117-143">Es posible que haya usado un formato incorrecto al especificar el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="ca117-143">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="ca117-144">Los planes de marcado incluyen reglas de normalización que permiten que Lync Server traduzca los números de teléfono marcados o introducidos por un usuario.</span><span class="sxs-lookup"><span data-stu-id="ca117-144">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="ca117-145">Por lo tanto, el plan de marcado debe tener reglas de normalización que coinciden con los números que los usuarios pueden marcar.</span><span class="sxs-lookup"><span data-stu-id="ca117-145">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="ca117-146">Por ejemplo, si los usuarios pueden marcar el código de país, el código de área y, a continuación, el número de teléfono, significa que su plan de marcado debe tener una regla de normalización para controlar los números de teléfono como esta:</span><span class="sxs-lookup"><span data-stu-id="ca117-146">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="ca117-147">12065551219</span><span class="sxs-lookup"><span data-stu-id="ca117-147">12065551219</span></span>
    
    <span data-ttu-id="ca117-148">Sin embargo, si escribe un número de teléfono incorrecto (por ejemplo, dejando fuera del último dígito), se producirá un error en Test-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="ca117-148">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="ca117-149">No es porque el plan de marcado es defectuoso, pero ya ha escrito un número de teléfono que no se puede interpretar.</span><span class="sxs-lookup"><span data-stu-id="ca117-149">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

