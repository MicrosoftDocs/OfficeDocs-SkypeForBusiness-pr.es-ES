---
title: 'Lync Server 2013: comprobar las reglas de normalización de voz'
description: 'Lync Server 2013: Compruebe las reglas de normalización de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f68bbde24a3dc7d8e8214dcfe506d4b8112fbbb3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543536"
---
# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="6f940-103">Comprobar las reglas de normalización de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f940-103">Check voice normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f940-104">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="6f940-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f940-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="6f940-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6f940-106">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="6f940-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f940-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="6f940-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6f940-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f940-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f940-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="6f940-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6f940-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6f940-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6f940-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="6f940-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="6f940-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6f940-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6f940-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f940-113">Description</span></span>

<span data-ttu-id="6f940-114">Las reglas de normalización de voz se usan para convertir un número de teléfono marcado por un usuario (por ejemplo, 2065551219) al formato E. 164 que usa Lync Server (+ 12065551219).</span><span class="sxs-lookup"><span data-stu-id="6f940-114">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="6f940-115">Por ejemplo, si los usuarios tienen la costumbre de marcar un número de teléfono sin incluir el código de país o el código de área (por ejemplo, 5551219), debe tener una regla de normalización de voz que pueda convertir ese número al formato E. 164: + 12065551219.</span><span class="sxs-lookup"><span data-stu-id="6f940-115">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="6f940-116">Sin dicha regla, el usuario no podrá llamar a 555-1219.</span><span class="sxs-lookup"><span data-stu-id="6f940-116">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="6f940-117">El cmdlet Test-CsVoiceNormalizationRule comprueba que una regla de normalización de voz especificada puede convertir correctamente un número de teléfono especificado.</span><span class="sxs-lookup"><span data-stu-id="6f940-117">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="6f940-118">Por ejemplo, este comando comprueba si la regla de normalización global NoAreaCode puede normalizar y convertir la cadena de marcado 5551219.</span><span class="sxs-lookup"><span data-stu-id="6f940-118">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6f940-119">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="6f940-119">Running the test</span></span>

<span data-ttu-id="6f940-120">Para ejecutar el cmdlet Test-CsVoiceNormalizationRule, primero debe usar el cmdlet Get-CsVoiceNormalizationRule para recuperar una instancia de la regla que se está probando y, a continuación, canalizar esa instancia para probar-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="6f940-120">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="6f940-121">Una sintaxis similar a esta no funcionará:</span><span class="sxs-lookup"><span data-stu-id="6f940-121">Syntax similar to this won't work:</span></span>

<span data-ttu-id="6f940-122">Test-CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "global/prefix All"</span><span class="sxs-lookup"><span data-stu-id="6f940-122">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="6f940-123">En su lugar, use una sintaxis como la siguiente, que combina los cmdlets Get-CsVoiceNormalizationRule y Test-CsVoiceNormalizationRule:</span><span class="sxs-lookup"><span data-stu-id="6f940-123">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="6f940-124">Get-CsVoiceNormalizationRule-Identity "global/prefix All" | Test-CsVoiceNormalizationRule DialedNumber "12065551219"</span><span class="sxs-lookup"><span data-stu-id="6f940-124">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f940-125">.</span><span class="sxs-lookup"><span data-stu-id="6f940-125">.</span></span> <span data-ttu-id="6f940-126">También puede usar este método para recuperar una instancia de una regla y, a continuación, probar dicha regla con un número de teléfono especificado:</span><span class="sxs-lookup"><span data-stu-id="6f940-126">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="6f940-127">Escriba el valor del parámetro DialedNumber exactamente como esperaba que se marque como un número.</span><span class="sxs-lookup"><span data-stu-id="6f940-127">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="6f940-128">Por ejemplo, si se supone que la regla de normalización de voz especificada agrega automáticamente el código de país (el 1 inicial en el valor 12065551219), debe omitir el código de país:</span><span class="sxs-lookup"><span data-stu-id="6f940-128">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="6f940-129">Si la regla está correctamente configurada, se agregará automáticamente el código de país al traducir el número al formato E. 164 que usa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f940-129">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="6f940-130">Para obtener más información, consulte la documentación de ayuda del cmdlet Test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="6f940-130">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6f940-131">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="6f940-131">Determining success or failure</span></span>

<span data-ttu-id="6f940-132">Si la regla de normalización de voz especificada puede traducir el número proporcionado, el número traducido se mostrará en pantalla:</span><span class="sxs-lookup"><span data-stu-id="6f940-132">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="6f940-133">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="6f940-133">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="6f940-134">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="6f940-134">\+12065551219</span></span>

<span data-ttu-id="6f940-135">Si se produce un error en la prueba, se devolverá un número traducido en blanco:</span><span class="sxs-lookup"><span data-stu-id="6f940-135">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="6f940-136">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="6f940-136">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6f940-137">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="6f940-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="6f940-138">Si el Test-CsVoiceNormalizationRule devuelve un número convertido que significa que la regla de normalización de voz especificada no ha podido traducir el número de teléfono proporcionado en el formato E. 164 que usa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f940-138">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="6f940-139">Para comprobar que, primero debe asegurarse de que escribió el número de teléfono correctamente.</span><span class="sxs-lookup"><span data-stu-id="6f940-139">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="6f940-140">Por ejemplo, esperaría que la regla de normalización de voz tenga problemas para traducir un número similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f940-140">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="6f940-141">Si se ha escrito el número correctamente, el siguiente paso debe ser comprobar que la regla de normalización especificada está diseñada para controlar ese número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="6f940-141">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="6f940-142">Por ejemplo, una regla de normalización puede estar diseñada para controlar el formato 12065551219, pero una segunda regla puede estar diseñada para controlar el número 2065551219.</span><span class="sxs-lookup"><span data-stu-id="6f940-142">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="6f940-143">(Es decir, el mismo número de teléfono, menos el código de país 1 en el principio). Para obtener información detallada sobre una regla de normalización de voz, ejecute un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="6f940-143">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="6f940-144">Para obtener información detallada sobre todas las reglas de normalización de voz, ejecute este comando en su lugar:</span><span class="sxs-lookup"><span data-stu-id="6f940-144">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6f940-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f940-145">See Also</span></span>


[<span data-ttu-id="6f940-146">Test-CsVoiceNormalizationRule</span><span class="sxs-lookup"><span data-stu-id="6f940-146">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

