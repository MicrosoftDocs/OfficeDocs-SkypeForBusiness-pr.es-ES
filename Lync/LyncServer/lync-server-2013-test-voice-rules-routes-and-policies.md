---
title: 'Lync Server 2013: probar reglas, rutas y directivas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b3d0cec7e5bd127f5b69eba6956fc3c653cfa51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="9955e-102">Probar reglas, rutas y directivas de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9955e-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9955e-103">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9955e-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9955e-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="9955e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9955e-105">Cada mes</span><span class="sxs-lookup"><span data-stu-id="9955e-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9955e-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="9955e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9955e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9955e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9955e-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="9955e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9955e-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9955e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9955e-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="9955e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="9955e-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9955e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9955e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9955e-112">Description</span></span>

<span data-ttu-id="9955e-113">Cuando un usuario realiza una llamada, la ruta que la llamada toma para alcanzar su destino depende de las directivas y los planes de marcado asignados a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="9955e-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="9955e-114">Dada la dirección SIP de un usuario y un número de teléfono, el cmdlet test-CsVoiceUser verifica si el usuario en cuestión puede completar una llamada a ese número.</span><span class="sxs-lookup"><span data-stu-id="9955e-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="9955e-115">Si la prueba se realiza correctamente, test-CsVoiceUser devuelve lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9955e-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="9955e-116">El número traducido al formato E. 164 (según el plan de marcado del usuario)</span><span class="sxs-lookup"><span data-stu-id="9955e-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="9955e-117">Regla de normalización que proporcionó esa traducción</span><span class="sxs-lookup"><span data-stu-id="9955e-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="9955e-118">La ruta de voz usada (según la prioridad de la ruta);</span><span class="sxs-lookup"><span data-stu-id="9955e-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="9955e-119">El uso del teléfono que vinculó la Directiva de voz del usuario a la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="9955e-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="9955e-120">Prueba-CsVoiceUser le permite determinar si un número de teléfono específico se enrutará y se traducirá como se espera, y puede ayudarle a solucionar problemas relacionados con la llamada que experimentan los usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="9955e-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9955e-121">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="9955e-121">Running the test</span></span>

<span data-ttu-id="9955e-122">Al ejecutar el cmdlet test-CsVoiceUser, debe proporcionar dos datos: el número que se marca (DialedNumber) y la identidad de la cuenta de usuario que se está probando.</span><span class="sxs-lookup"><span data-stu-id="9955e-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="9955e-123">Por ejemplo, este comando prueba la capacidad del usuario que tiene la dirección SIP sip:kenmyer@litwareinc.com para hacer una llamada al número de teléfono + 1206555-1219:</span><span class="sxs-lookup"><span data-stu-id="9955e-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="9955e-124">El número de teléfono debe tener el formato que espera que se marque.</span><span class="sxs-lookup"><span data-stu-id="9955e-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="9955e-125">Por ejemplo, si los usuarios normalmente no marcan el 1 antes de hacer una llamada de larga distancia, debe usar este formato:</span><span class="sxs-lookup"><span data-stu-id="9955e-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="9955e-126">Por supuesto, en ese caso, la prueba fallará si no tiene una regla de normalización que pueda traducir correctamente el número 2065551219 en el formato de teléfono E. 164 que usa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9955e-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="9955e-127">Para obtener más información, vea el tema sobre el cmdlet New-CsVoiceNormalizationRule de la ayuda.</span><span class="sxs-lookup"><span data-stu-id="9955e-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="9955e-128">Si desea ejecutar esta misma prueba en cada una de sus cuentas de usuario, puede usar un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="9955e-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="9955e-129">Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="9955e-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9955e-130">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="9955e-130">Determining success or failure</span></span>

<span data-ttu-id="9955e-131">Si la prueba se completa correctamente (es decir, si el usuario puede hacer una llamada telefónica al número especificado), la salida mostrará información como el número de teléfono traducido y la regla de normalización correspondiente y la ruta de voz:</span><span class="sxs-lookup"><span data-stu-id="9955e-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="9955e-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="9955e-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="9955e-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="9955e-133"></span></span>

<span data-ttu-id="9955e-134">\+12065551219 unscripti...    LocalRoute local</span><span class="sxs-lookup"><span data-stu-id="9955e-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="9955e-135">Debido a las limitaciones de la pantalla de Windows PowerShell, al menos parte de la información devuelta (principalmente, la descripción completa de la regla de normalización correspondiente) podría no aparecer en pantalla.</span><span class="sxs-lookup"><span data-stu-id="9955e-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="9955e-136">Si solo le interesa el éxito o el fracaso de la prueba, esto podría no importarse.</span><span class="sxs-lookup"><span data-stu-id="9955e-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="9955e-137">Si prefiere ver los detalles completos de los datos devueltos, Canalice el resultado al cmdlet Format-List al ejecutar la prueba:</span><span class="sxs-lookup"><span data-stu-id="9955e-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="9955e-138">Eso mostrará la salida en un formato más fácil de obtener:</span><span class="sxs-lookup"><span data-stu-id="9955e-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="9955e-139">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="9955e-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="9955e-140">MatchingRule: Descripción =; Patrón = ^ (\\d{11}) $; Traducción = + $1;</span><span class="sxs-lookup"><span data-stu-id="9955e-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="9955e-141">Nombre = prefijo All; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="9955e-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="9955e-142">FirsMatchingRoute : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="9955e-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="9955e-143">MatchingUsage: local</span><span class="sxs-lookup"><span data-stu-id="9955e-143">MatchingUsage : Local</span></span>

<span data-ttu-id="9955e-144">Si la prueba no se realiza correctamente, test-CsVoiceUser devolverá un conjunto vacío de valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="9955e-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="9955e-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="9955e-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="9955e-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="9955e-146"></span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9955e-147">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="9955e-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="9955e-148">Hay varias razones por las que el cmdlet test-CsVoiceUser puede dar error: es posible que no haya una regla de normalización que pueda traducir el número de teléfono proporcionado.</span><span class="sxs-lookup"><span data-stu-id="9955e-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="9955e-149">Puede haber problemas con la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="9955e-149">There could be problems with the voice route.</span></span> <span data-ttu-id="9955e-150">Podría haber un problema de configuración con el plan de marcado asignado al usuario en cuestión.</span><span class="sxs-lookup"><span data-stu-id="9955e-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="9955e-151">Por eso, es posible que desee incluir el parámetro verbose al ejecutar el cmdlet test-CsVoiceUser:</span><span class="sxs-lookup"><span data-stu-id="9955e-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="9955e-152">Cuando se incluye el cmdlet detallado, test-CsVoiceUser emitirá una cuenta detallada de todos los pasos que se lleven a cabo al realizar las comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="9955e-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="9955e-153">Por ejemplo, es posible que vea pasos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="9955e-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="9955e-154">VERBOse: ubicar un usuario con la identidad "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="9955e-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="9955e-155">DETALLADO: cargando plan de marcado: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="9955e-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="9955e-156">Esta información adicional puede proporcionar consejos sobre los pasos que puede tomar para determinar la causa del error.</span><span class="sxs-lookup"><span data-stu-id="9955e-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="9955e-157">Por ejemplo, la salida detallada que se muestra aquí nos dice que al usuario que se está probando se le asignó el plan de marcado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="9955e-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="9955e-158">Si la prueba ha fallado, un paso siguiente lógico sería comprobar que RedmondDialPlan puede traducir el número de teléfono suministrado.</span><span class="sxs-lookup"><span data-stu-id="9955e-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9955e-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="9955e-159">See Also</span></span>


[<span data-ttu-id="9955e-160">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="9955e-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

