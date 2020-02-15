---
title: 'Lync Server 2013: probar el plan de marcado'
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
ms.openlocfilehash: 4c35d204a8a3fa16ff38dbcce89c0c8f36da2039
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="94c78-102">Probar el plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94c78-102">Testing the dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94c78-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="94c78-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94c78-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="94c78-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="94c78-105">Diario</span><span class="sxs-lookup"><span data-stu-id="94c78-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c78-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="94c78-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="94c78-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="94c78-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c78-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="94c78-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="94c78-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="94c78-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="94c78-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="94c78-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="94c78-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="94c78-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="94c78-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="94c78-112">Description</span></span>

<span data-ttu-id="94c78-113">El cmdlet test-CsDialPlan permite ver los resultados de la aplicación de un plan de marcado a un número de teléfono determinado.</span><span class="sxs-lookup"><span data-stu-id="94c78-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="94c78-114">Los planes de marcado proporcionan información, como la forma en que se aplican las reglas de normalización, necesarias para permitir a los usuarios de Enterprise Voice realizar llamadas telefónicas.</span><span class="sxs-lookup"><span data-stu-id="94c78-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="94c78-115">Después de especificar un número de marcado y un plan de marcado, el cmdlet verificará qué regla de normalización del plan de marcado se aplicará y cuál será el número traducido.</span><span class="sxs-lookup"><span data-stu-id="94c78-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="94c78-116">Puede usar este cmdlet para solucionar problemas con las traducciones de números o para comprobar cómo aplicar reglas a determinados números.</span><span class="sxs-lookup"><span data-stu-id="94c78-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="94c78-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="94c78-117">Running the test</span></span>

<span data-ttu-id="94c78-118">El cmdlet test-CsDialPlan requiere que haga dos cosas.</span><span class="sxs-lookup"><span data-stu-id="94c78-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="94c78-119">En primer lugar, debe obtener una instancia del plan de marcado que se está probando; Esto se puede hacer con el cmdlet Get-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="94c78-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="94c78-120">En segundo lugar, debe especificar el número de teléfono que se va a normalizar.</span><span class="sxs-lookup"><span data-stu-id="94c78-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="94c78-121">El formato que se usa para el número de teléfono debe coincidir con el número marcado o escrito por un usuario.</span><span class="sxs-lookup"><span data-stu-id="94c78-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="94c78-122">Por ejemplo, este comando recupera una instancia del plan de marcado, RedmondDialPlan, y comprueba si el número de teléfono 12065551219 se puede normalizar:</span><span class="sxs-lookup"><span data-stu-id="94c78-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="94c78-123">Si tiene una regla de normalización que agrega automáticamente el código de país (en este ejemplo, 1) y el código de área (206), es posible que desee comprobar el número de teléfono 5551219 de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="94c78-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="94c78-124">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .</span><span class="sxs-lookup"><span data-stu-id="94c78-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="94c78-125">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="94c78-125">Determining success or failure</span></span>

<span data-ttu-id="94c78-126">Test-CsDialPlan se diferencia de muchos de los cmdlets de prueba de Lync Server porque solo indica indirectamente si una prueba se ha realizado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="94c78-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="94c78-127">Cuando se usa test-CsDialPlan, no se obtiene una salida similar a la siguiente con el resultado claramente marcado:</span><span class="sxs-lookup"><span data-stu-id="94c78-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="94c78-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="94c78-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="94c78-129">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="94c78-129">Result : Success</span></span>

<span data-ttu-id="94c78-130">Latencia: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="94c78-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="94c78-131">Error</span><span class="sxs-lookup"><span data-stu-id="94c78-131">Error :</span></span>

<span data-ttu-id="94c78-132">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="94c78-132">Diagnosis :</span></span>

<span data-ttu-id="94c78-133">En su lugar, si test-CsDialPlan se realiza correctamente, recibirá información acerca de la regla de normalización que pudo traducir correctamente y usar el número de teléfono especificado:</span><span class="sxs-lookup"><span data-stu-id="94c78-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="94c78-134">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="94c78-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="94c78-135">MatchingRule: Description =; Pattern = ^ (\\d (11)) $; Traducción = + $1;</span><span class="sxs-lookup"><span data-stu-id="94c78-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="94c78-136">Name = prefix All; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="94c78-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="94c78-137">Si test-CsDialPlan produce un error (es decir, si el plan de marcado no tiene una regla de normalización que pueda traducir el número de teléfono especificado), solo recibirá el resultado "vacío" de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="94c78-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="94c78-138">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="94c78-138">TranslatedNumber :</span></span>

<span data-ttu-id="94c78-139">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="94c78-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="94c78-140">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="94c78-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="94c78-141">Estas son algunas de las razones comunes por las que test-CsDialPlan podría fallar:</span><span class="sxs-lookup"><span data-stu-id="94c78-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="94c78-142">Es posible que haya usado un formato incorrecto al especificar el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="94c78-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="94c78-143">Los planes de marcado incluyen reglas de normalización que permiten que Lync Server traduzca los números de teléfono marcados o introducidos por un usuario.</span><span class="sxs-lookup"><span data-stu-id="94c78-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="94c78-144">Por lo tanto, el plan de marcado debe tener reglas de normalización que coinciden con los números que los usuarios pueden marcar.</span><span class="sxs-lookup"><span data-stu-id="94c78-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="94c78-145">Por ejemplo, si los usuarios pueden marcar el código de país, el código de área y, a continuación, el número de teléfono, significa que su plan de marcado debe tener una regla de normalización para controlar los números de teléfono como esta:</span><span class="sxs-lookup"><span data-stu-id="94c78-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="94c78-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="94c78-146">12065551219</span></span>
    
    <span data-ttu-id="94c78-147">Sin embargo, si escribe un número de teléfono incorrecto (por ejemplo, dejando fuera del dígito final), se producirá un error de test-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="94c78-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="94c78-148">No es porque el plan de marcado es defectuoso, pero ya ha escrito un número de teléfono que no se puede interpretar.</span><span class="sxs-lookup"><span data-stu-id="94c78-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

