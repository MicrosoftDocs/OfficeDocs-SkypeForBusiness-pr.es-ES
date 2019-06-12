---
title: 'Lync Server 2013: comprobar el número de teléfono con una directiva de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7a1e24a07a0f6e1e985c9fc42f7468838074d3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="a8a13-102">Probar el número de teléfono en una directiva de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8a13-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8a13-103">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="a8a13-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8a13-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="a8a13-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a8a13-105">Cada mes</span><span class="sxs-lookup"><span data-stu-id="a8a13-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8a13-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="a8a13-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a8a13-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8a13-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8a13-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="a8a13-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a8a13-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a8a13-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a8a13-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="a8a13-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="a8a13-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a8a13-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a8a13-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8a13-112">Description</span></span>

<span data-ttu-id="a8a13-113">La capacidad de los usuarios de telefonía empresarial para hacer llamadas telefónicas salientes a través de las bisagras de la red de telefonía pública conmutada (RTC), en gran medida, en tres cosas:</span><span class="sxs-lookup"><span data-stu-id="a8a13-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="a8a13-114">La Directiva de voz asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="a8a13-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="a8a13-115">Rutas de voz usadas para enrutar llamadas desde Lync Server a la red PSTN.</span><span class="sxs-lookup"><span data-stu-id="a8a13-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="a8a13-116">El uso de RTC, una propiedad de Lync Server que conecta una directiva de voz a una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="a8a13-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="a8a13-117">El uso de RTC es especialmente importante: es la propiedad que conecta una directiva de voz a una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="a8a13-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="a8a13-118">(Se dice que una directiva de voz y una ruta de voz se conectan si tienen al menos un uso de RTC en común.) Las directivas de voz se pueden configurar sin especificar un uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="a8a13-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="a8a13-119">En ese caso, los usuarios a los que se les asignó esta Directiva no podrán hacer llamadas salientes a través de la red RTC.</span><span class="sxs-lookup"><span data-stu-id="a8a13-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="a8a13-120">Del mismo modo, las rutas de voz que no tengan al menos un uso de RTC especificado no podrán enrutar llamadas a la red PSTN.</span><span class="sxs-lookup"><span data-stu-id="a8a13-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="a8a13-121">El cmdlet test-CsVoicePolicy verifica que una directiva de voz determinada tiene un uso de RTC y que el uso se comparte con al menos una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="a8a13-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="a8a13-122">Si la comprobación ejecutada por test-CsVoicePolicy se realiza correctamente, el cmdlet devolverá el nombre de la primera ruta de voz válida que encuentre, así como el nombre del uso de RTC que conecta la Directiva a la ruta.</span><span class="sxs-lookup"><span data-stu-id="a8a13-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a8a13-123">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="a8a13-123">Running the test</span></span>

<span data-ttu-id="a8a13-124">Para ejecutar el cmdlet test-CsVoicePolicy primero debe usar el cmdlet Get-CsVoicePolicy para recuperar una instancia de la Directiva de voz que se va a probar; después, se debe canalizar esa instancia a test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="a8a13-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="a8a13-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a8a13-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="a8a13-126">Tenga en cuenta que este comando, que no usa Get-CsVoicePolicy para recuperar una instancia de la Directiva de voz, producirá un error:</span><span class="sxs-lookup"><span data-stu-id="a8a13-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="a8a13-127">Si desea comprobar todas las directivas de voz en función de un número de teléfono especificado, use un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="a8a13-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="a8a13-128">Ten en cuenta que la TargetNumber debe especificarse con el formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="a8a13-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="a8a13-129">Test-CsVoicePolicy no intentará normalizar ni traducir números de teléfono al formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="a8a13-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="a8a13-130">Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="a8a13-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a8a13-131">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="a8a13-131">Determining success or failure</span></span>

<span data-ttu-id="a8a13-132">Si la Directiva de voz puede encontrar tanto una ruta de voz coincidente como un uso de RTC correspondiente, la ruta y el uso se mostrarán en pantalla:</span><span class="sxs-lookup"><span data-stu-id="a8a13-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="a8a13-133">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="a8a13-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="a8a13-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="a8a13-134"></span></span>

<span data-ttu-id="a8a13-135">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="a8a13-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="a8a13-136">Si no se puede encontrar una ruta de voz adecuada o un uso de RTC adecuado, los valores de la propiedad en blanco se mostrarán en pantalla:</span><span class="sxs-lookup"><span data-stu-id="a8a13-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="a8a13-137">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="a8a13-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="a8a13-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="a8a13-138"></span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a8a13-139">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="a8a13-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="a8a13-140">Si prueba-CsVoicePolicy no devuelve una coincidencia, esto podría significar que la Directiva de voz no comparte un uso de RTC con una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="a8a13-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="a8a13-141">Para comprobar que, use un cmdlet similar al siguiente para comprobar que se han asignado usos de RTC a la Directiva de voz:</span><span class="sxs-lookup"><span data-stu-id="a8a13-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="a8a13-142">A continuación, ejecute este comando para determinar los usos de RTC que se asignan a cada una de sus rutas de voz:</span><span class="sxs-lookup"><span data-stu-id="a8a13-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="a8a13-143">Si ve alguna coincidencia (es decir, si ve una o varias rutas de voz que comparten al menos un uso de la RTC con su Directiva de voz), debe ejecutar el cmdlet test-CsVoiceRoute para comprobar que la ruta de voz puede marcar el número de teléfono suministrado.</span><span class="sxs-lookup"><span data-stu-id="a8a13-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a8a13-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8a13-144">See Also</span></span>


[<span data-ttu-id="a8a13-145">Test-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="a8a13-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

