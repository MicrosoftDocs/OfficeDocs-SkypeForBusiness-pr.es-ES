---
title: 'Lync Server 2013: comprobar las reglas de normalización de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487415fccc1e779daa476a4e76aa99a891f6b7fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="421ea-102">Comprobar las reglas de normalización de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="421ea-102">Check voice normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="421ea-103">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="421ea-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="421ea-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="421ea-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="421ea-105">Cada mes</span><span class="sxs-lookup"><span data-stu-id="421ea-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="421ea-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="421ea-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="421ea-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="421ea-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="421ea-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="421ea-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="421ea-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="421ea-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="421ea-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="421ea-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="421ea-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="421ea-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="421ea-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="421ea-112">Description</span></span>

<span data-ttu-id="421ea-113">Las reglas de normalización de voz se usan para convertir un número de teléfono marcado por un usuario (por ejemplo, 2065551219) al formato E. 164 que usa Lync Server (+ 12065551219).</span><span class="sxs-lookup"><span data-stu-id="421ea-113">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="421ea-114">Por ejemplo, si los usuarios tienen el hábito de marcar un número de teléfono sin incluir el prefijo internacional o el código de área (por ejemplo, 5551219), debe tener una regla de normalización de voz que pueda convertir ese número al formato E. 164: + 12065551219.</span><span class="sxs-lookup"><span data-stu-id="421ea-114">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="421ea-115">Sin dicha regla, el usuario no podrá llamar al 555-1219.</span><span class="sxs-lookup"><span data-stu-id="421ea-115">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="421ea-116">El cmdlet test-CsVoiceNormalizationRule comprueba que una regla de normalización de voz especificada puede convertir correctamente un número de teléfono especificado.</span><span class="sxs-lookup"><span data-stu-id="421ea-116">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="421ea-117">Por ejemplo, este comando comprueba si la regla de normalización NoAreaCode puede normalizar y convertir la cadena de marcado 5551219.</span><span class="sxs-lookup"><span data-stu-id="421ea-117">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="421ea-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="421ea-118">Running the test</span></span>

<span data-ttu-id="421ea-119">Para ejecutar el cmdlet test-CsVoiceNormalizationRule, primero debe usar el cmdlet Get-CsVoiceNormalizationRule para recuperar una instancia de la regla que se está probando y, a continuación, canalizar esa instancia para probar-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="421ea-119">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="421ea-120">La sintaxis es similar a esta:</span><span class="sxs-lookup"><span data-stu-id="421ea-120">Syntax similar to this won't work:</span></span>

<span data-ttu-id="421ea-121">Test-CsVoiceNormalizationRule-DialedNumber "12065551219"-NormalizationRule "global/prefix All"</span><span class="sxs-lookup"><span data-stu-id="421ea-121">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="421ea-122">En su lugar, use una sintaxis como la siguiente, que combina los cmdlets Get-CsVoiceNormalizationRule y test-CsVoiceNormalizationRule:</span><span class="sxs-lookup"><span data-stu-id="421ea-122">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="421ea-123">Get-CsVoiceNormalizationRule-Identity "global/prefix All" | Prueba-CsVoiceNormalizationRule-DialedNumber "12065551219"</span><span class="sxs-lookup"><span data-stu-id="421ea-123">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="421ea-124">.</span><span class="sxs-lookup"><span data-stu-id="421ea-124"></span></span> <span data-ttu-id="421ea-125">También puede usar este método para recuperar una instancia de una regla y, a continuación, probarla con un número de teléfono especificado:</span><span class="sxs-lookup"><span data-stu-id="421ea-125">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="421ea-126">Escriba el valor del parámetro DialedNumber exactamente como espera que se marque ese número.</span><span class="sxs-lookup"><span data-stu-id="421ea-126">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="421ea-127">Por ejemplo, si se supone que la regla de normalización de voz especificada agrega automáticamente el prefijo internacional (el 1 en el valor 12065551219), debe omitir el prefijo internacional:</span><span class="sxs-lookup"><span data-stu-id="421ea-127">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="421ea-128">Si la regla está configurada correctamente, se agregará automáticamente el prefijo internacional al traducir el número al formato E. 164 usado por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="421ea-128">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="421ea-129">Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="421ea-129">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="421ea-130">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="421ea-130">Determining success or failure</span></span>

<span data-ttu-id="421ea-131">Si la regla de normalización de voz especificada puede traducir el número suministrado, el número traducido se mostrará en pantalla:</span><span class="sxs-lookup"><span data-stu-id="421ea-131">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="421ea-132">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="421ea-132">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="421ea-133">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="421ea-133">\+12065551219</span></span>

<span data-ttu-id="421ea-134">Si se produce un error en la prueba, se devolverá un número traducido en blanco:</span><span class="sxs-lookup"><span data-stu-id="421ea-134">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="421ea-135">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="421ea-135">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="421ea-136">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="421ea-136">Reasons why the test might have failed</span></span>

<span data-ttu-id="421ea-137">Si la prueba-CsVoiceNormalizationRule devuelve un número traducido que significa que la regla de normalización de voz especificada no pudo traducir el número de teléfono suministrado al formato E. 164 usado por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="421ea-137">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="421ea-138">Para verificar que, primero, asegúrate de escribir el número de teléfono correctamente.</span><span class="sxs-lookup"><span data-stu-id="421ea-138">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="421ea-139">Por ejemplo, esperamos que su regla de normalización de voz tenga problemas para traducir un número parecido a este:</span><span class="sxs-lookup"><span data-stu-id="421ea-139">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="421ea-140">Suponiendo que el número se haya introducido correctamente, el siguiente paso debe comprobar que la regla de normalización especificada está diseñada para controlar ese número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="421ea-140">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="421ea-141">Por ejemplo, una regla de normalización podría estar diseñada para controlar el formato 12065551219, pero una segunda regla podría estar diseñada para controlar el número 2065551219.</span><span class="sxs-lookup"><span data-stu-id="421ea-141">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="421ea-142">(Es decir, el mismo número de teléfono, menos el prefijo internacional 1 al principio). Para obtener información detallada sobre una regla de normalización de voz, ejecute un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="421ea-142">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="421ea-143">Para obtener información detallada sobre todas las reglas de normalización de voz, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="421ea-143">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="421ea-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="421ea-144">See Also</span></span>


[<span data-ttu-id="421ea-145">Test-CsVoiceNormalizationRule</span><span class="sxs-lookup"><span data-stu-id="421ea-145">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

