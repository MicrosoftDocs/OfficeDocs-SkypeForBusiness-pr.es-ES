---
title: 'Lync Server 2013: probar el número de teléfono con una directiva de voz'
description: 'Lync Server 2013: probar el número de teléfono con una directiva de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a6523e7657bd4c30c23909bb02e2569b6067298
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548036"
---
# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="c00f2-103">Probar el número de teléfono con una directiva de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c00f2-103">Test telephone number against a voice policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c00f2-104">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="c00f2-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c00f2-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="c00f2-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c00f2-106">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="c00f2-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c00f2-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="c00f2-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c00f2-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c00f2-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c00f2-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="c00f2-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c00f2-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c00f2-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c00f2-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="c00f2-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="c00f2-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c00f2-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c00f2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c00f2-113">Description</span></span>

<span data-ttu-id="c00f2-114">La capacidad de los usuarios de Enterprise Voice de realizar llamadas salientes telefónicas a través de las bisagras de la red telefónica conmutada (RTC) en gran parte, en tres cosas:</span><span class="sxs-lookup"><span data-stu-id="c00f2-114">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="c00f2-115">La Directiva de voz asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="c00f2-115">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="c00f2-116">Rutas de voz usadas para enrutar las llamadas de Lync Server a la red RTC.</span><span class="sxs-lookup"><span data-stu-id="c00f2-116">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="c00f2-117">Uso de RTC, una propiedad de Lync Server que conecta una directiva de voz a una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="c00f2-117">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="c00f2-118">El uso de RTC es especialmente importante: es la propiedad que conecta una directiva de voz a una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="c00f2-118">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="c00f2-119">(Se dice que una directiva de voz y una ruta de voz están conectadas si tienen como mínimo un uso de RTC en común). Las directivas de voz se pueden configurar sin especificar un uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="c00f2-119">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="c00f2-120">En ese caso, los usuarios a los que se les asignó esta Directiva no podrán realizar llamadas salientes a través de la red RTC.</span><span class="sxs-lookup"><span data-stu-id="c00f2-120">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="c00f2-121">Del mismo modo, las rutas de voz que no tienen al menos un uso de RTC especificado no podrán enrutar las llamadas a la red RTC.</span><span class="sxs-lookup"><span data-stu-id="c00f2-121">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="c00f2-122">El cmdlet Test-CsVoicePolicy comprueba que una directiva de voz determinada tiene un uso de RTC y que el uso se comparte con al menos una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="c00f2-122">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="c00f2-123">Si la comprobación ejecutada por Test-CsVoicePolicy se realiza correctamente, el cmdlet devolverá el nombre de la primera ruta de voz válida que encuentre y también el nombre del uso de RTC que conecta la Directiva a la ruta.</span><span class="sxs-lookup"><span data-stu-id="c00f2-123">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c00f2-124">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="c00f2-124">Running the test</span></span>

<span data-ttu-id="c00f2-125">Para ejecutar el cmdlet Test-CsVoicePolicy, primero debe usar el cmdlet Get-CsVoicePolicy para recuperar una instancia de la Directiva de voz que se va a probar; a continuación, esa instancia se debe canalizar a test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="c00f2-125">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="c00f2-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c00f2-126">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="c00f2-127">Tenga en cuenta que este comando, que no usa Get-CsVoicePolicy para recuperar una instancia de la Directiva de voz, producirá un error:</span><span class="sxs-lookup"><span data-stu-id="c00f2-127">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="c00f2-128">Si desea comprobar todas las directivas de voz en un número de teléfono especificado, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c00f2-128">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="c00f2-129">Tenga en cuenta que el TargetNumber debe especificarse con el formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="c00f2-129">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="c00f2-130">Test-CsVoicePolicy no intentará normalizar ni traducir los números de teléfono al formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="c00f2-130">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="c00f2-131">Para obtener más información, consulte la documentación de ayuda del cmdlet Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="c00f2-131">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c00f2-132">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="c00f2-132">Determining success or failure</span></span>

<span data-ttu-id="c00f2-133">Si la Directiva de voz puede encontrar tanto una ruta de voz coincidentes como un uso de RTC que coincida, se mostrarán en pantalla tanto la ruta como el uso:</span><span class="sxs-lookup"><span data-stu-id="c00f2-133">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="c00f2-134">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="c00f2-134">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="c00f2-135">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="c00f2-135">\------------------ -------------</span></span>

<span data-ttu-id="c00f2-136">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="c00f2-136">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="c00f2-137">Si no se puede encontrar una ruta de voz adecuada o un uso de RTC adecuado, los valores de la propiedad en blanco se mostrarán en la pantalla:</span><span class="sxs-lookup"><span data-stu-id="c00f2-137">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="c00f2-138">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="c00f2-138">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="c00f2-139">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="c00f2-139">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c00f2-140">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="c00f2-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="c00f2-141">Si Test-CsVoicePolicy no devuelve una coincidencia que podría significar que la Directiva de voz no comparte el uso de RTC con una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="c00f2-141">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="c00f2-142">Para comprobar que, use un cmdlet similar al siguiente para comprobar que los usos de RTC asignados a la Directiva de voz:</span><span class="sxs-lookup"><span data-stu-id="c00f2-142">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="c00f2-143">A continuación, ejecute este comando para determinar los usos de RTC que se asignan a cada una de las rutas de voz:</span><span class="sxs-lookup"><span data-stu-id="c00f2-143">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="c00f2-144">Si ve alguna coincidencia (es decir, si ve una o varias rutas de voz que comparten al menos un uso de RTC con la Directiva de voz), debe ejecutar el cmdlet Test-CsVoiceRoute para comprobar que la ruta de voz puede marcar el número de teléfono proporcionado.</span><span class="sxs-lookup"><span data-stu-id="c00f2-144">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c00f2-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c00f2-145">See Also</span></span>


[<span data-ttu-id="c00f2-146">Test-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="c00f2-146">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

