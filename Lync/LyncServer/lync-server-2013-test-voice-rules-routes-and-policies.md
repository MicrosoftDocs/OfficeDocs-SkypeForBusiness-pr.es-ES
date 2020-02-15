---
title: 'Lync Server 2013: probar reglas, rutas y directivas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 689f591b416cdab6eb5d325a7dade2c54659d072
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42017891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="f5540-102">Probar reglas de voz, rutas y directivas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5540-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5540-103">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="f5540-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5540-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5540-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f5540-105">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="f5540-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5540-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="f5540-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f5540-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5540-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5540-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="f5540-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f5540-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f5540-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f5540-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="f5540-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="f5540-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f5540-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f5540-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5540-112">Description</span></span>

<span data-ttu-id="f5540-113">Cuando un usuario realiza una llamada telefónica, la ruta que toma la llamada para llegar a su destino depende de las directivas y los planes de marcado asignados a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="f5540-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="f5540-114">Según la dirección SIP de un usuario y un número de teléfono, el cmdlet test-CsVoiceUser comprueba si el usuario en cuestión puede completar una llamada a ese número.</span><span class="sxs-lookup"><span data-stu-id="f5540-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="f5540-115">Si la prueba es correcta, test-CsVoiceUser devuelve lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5540-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="f5540-116">El número convertido al formato E. 164 (basado en el plan de marcado del usuario)</span><span class="sxs-lookup"><span data-stu-id="f5540-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="f5540-117">La regla de normalización que suministró esa traducción</span><span class="sxs-lookup"><span data-stu-id="f5540-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="f5540-118">La ruta de voz usada (en función de la prioridad de ruta);</span><span class="sxs-lookup"><span data-stu-id="f5540-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="f5540-119">El uso del teléfono que vinculó la Directiva de voz del usuario a la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="f5540-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="f5540-120">Test-CsVoiceUser permite determinar si un número de teléfono específico se enrutará y traducirá como se esperaba, y puede ayudar a solucionar problemas relacionados con la llamada que experimentan los usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="f5540-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f5540-121">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="f5540-121">Running the test</span></span>

<span data-ttu-id="f5540-122">Al ejecutar el cmdlet test-CsVoiceUser, debe proporcionar dos datos: el número que se marca (DialedNumber) y la identidad de la cuenta de usuario que se está probando.</span><span class="sxs-lookup"><span data-stu-id="f5540-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="f5540-123">Por ejemplo, este comando comprueba la capacidad del usuario que tiene la dirección SIP sip:kenmyer@litwareinc.com para realizar una llamada al número de teléfono + 1206555-1219:</span><span class="sxs-lookup"><span data-stu-id="f5540-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="f5540-124">El número de teléfono debe tener el formato de la forma en que espera que se marque.</span><span class="sxs-lookup"><span data-stu-id="f5540-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="f5540-125">Por ejemplo, si los usuarios no suelen marcar el 1 antes de realizar una llamada de larga distancia, debe usar este formato:</span><span class="sxs-lookup"><span data-stu-id="f5540-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="f5540-126">Por supuesto, en ese caso, se producirá un error en la prueba si no tiene una regla de normalización que pueda traducir correctamente el número 2065551219 en el formato de teléfono E. 164 que usa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5540-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="f5540-127">Para obtener más información, consulte el cmdlet New-CsVoiceNormalizationRule del tema de ayuda.</span><span class="sxs-lookup"><span data-stu-id="f5540-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="f5540-128">Si desea ejecutar esta misma prueba en cada una de las cuentas de usuario, puede usar un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5540-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="f5540-129">Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="f5540-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f5540-130">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="f5540-130">Determining success or failure</span></span>

<span data-ttu-id="f5540-131">Si la prueba se completa correctamente (es decir, si el usuario puede realizar una llamada telefónica al número especificado), el resultado mostrará información como el número de teléfono convertido y la regla de normalización de coincidencia y la ruta de voz:</span><span class="sxs-lookup"><span data-stu-id="f5540-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="f5540-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="f5540-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="f5540-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="f5540-133">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="f5540-134">\+12065551219 descripti...    LocalRoute local</span><span class="sxs-lookup"><span data-stu-id="f5540-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="f5540-135">Debido a las limitaciones de la pantalla de Windows PowerShell, al menos parte de la información devuelta (más concretamente la descripción completa de la regla de normalización correspondiente) puede que no aparezca en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="f5540-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="f5540-136">Si solo le interesa el éxito o el fracaso de la prueba, esto podría no importarse.</span><span class="sxs-lookup"><span data-stu-id="f5540-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="f5540-137">Si prefiere ver los detalles completos de los datos devueltos, canalice la salida al cmdlet Format-List al ejecutar la prueba:</span><span class="sxs-lookup"><span data-stu-id="f5540-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="f5540-138">Esto mostrará el resultado en un formato más sencillo para el lector:</span><span class="sxs-lookup"><span data-stu-id="f5540-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="f5540-139">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="f5540-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="f5540-140">MatchingRule: Description =; Pattern = ^ (\\d{11}) $; Traducción = + $1;</span><span class="sxs-lookup"><span data-stu-id="f5540-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="f5540-141">Name = prefix All; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="f5540-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="f5540-142">FirsMatchingRoute: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="f5540-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="f5540-143">MatchingUsage: local</span><span class="sxs-lookup"><span data-stu-id="f5540-143">MatchingUsage : Local</span></span>

<span data-ttu-id="f5540-144">Si se produce un error en la prueba, test-CsVoiceUser devolverá un conjunto vacío de valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="f5540-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="f5540-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="f5540-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="f5540-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="f5540-146">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f5540-147">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="f5540-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="f5540-148">Existen varios motivos por los que el cmdlet test-CsVoiceUser puede fallar: puede que no haya una regla de normalización que pueda traducir el número de teléfono proporcionado.</span><span class="sxs-lookup"><span data-stu-id="f5540-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="f5540-149">Puede haber problemas con la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="f5540-149">There could be problems with the voice route.</span></span> <span data-ttu-id="f5540-150">Podría haber un problema de configuración con el plan de marcado asignado al usuario en cuestión.</span><span class="sxs-lookup"><span data-stu-id="f5540-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="f5540-151">Por ello, es posible que desee incluir el parámetro verbose cuando ejecute el cmdlet test-CsVoiceUser:</span><span class="sxs-lookup"><span data-stu-id="f5540-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="f5540-152">Cuando se incluye el cmdlet verbose, test-CsVoiceUser emitirá una cuenta detallada de todos los pasos que se emprenderán en la realización de las comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="f5540-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="f5540-153">Por ejemplo, podría ver pasos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="f5540-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="f5540-154">VERBOse: buscando el usuario con la identidad "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="f5540-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="f5540-155">DETALLADO: cargando plan de marcado: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="f5540-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="f5540-156">Esta información adicional puede proporcionar sugerencias en cuanto a los pasos que puede realizar para identificar la causa del error.</span><span class="sxs-lookup"><span data-stu-id="f5540-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="f5540-157">Por ejemplo, el resultado detallado que se muestra aquí nos dice que el usuario que se está probando se asignó al plan de marcado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="f5540-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="f5540-158">Si se ha producido un error en la prueba, un paso siguiente lógico sería comprobar que RedmondDialPlan puede traducir el número de teléfono proporcionado.</span><span class="sxs-lookup"><span data-stu-id="f5540-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5540-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5540-159">See Also</span></span>


[<span data-ttu-id="f5540-160">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="f5540-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

