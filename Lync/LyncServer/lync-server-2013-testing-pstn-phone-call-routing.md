---
title: 'Lync Server 2013: probar el enrutamiento de llamadas de teléfono RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b831aef01d80a0d68a0eea06f429502026b7ccb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="2b105-102">Probar el enrutamiento de llamadas de teléfono RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b105-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b105-103">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="2b105-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b105-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="2b105-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2b105-105">Diario</span><span class="sxs-lookup"><span data-stu-id="2b105-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b105-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="2b105-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2b105-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b105-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b105-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="2b105-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2b105-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2b105-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2b105-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsInterTrunkRouting</strong> .</span><span class="sxs-lookup"><span data-stu-id="2b105-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="2b105-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b105-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2b105-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b105-112">Description</span></span>

<span data-ttu-id="2b105-113">El cmdlet **Test-CsInterTrunkRouting** comprueba que las llamadas se pueden enrutar desde un SIP a otro.</span><span class="sxs-lookup"><span data-stu-id="2b105-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="2b105-114">Para ello, el cmdlet recibe un número de teléfono y una configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="2b105-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="2b105-115">**Test-CsInterTrunkRouting** , a continuación, notificará las rutas de coincidencia y los usos de RTC coincidentes para el número especificado.</span><span class="sxs-lookup"><span data-stu-id="2b105-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="2b105-116">Tenga en cuenta que las llamadas pueden enrutarse entre líneas troncales solo si estas líneas tienen un patrón de número que coincide con el número telefónico especificado y solo si las líneas troncales comparten por lo menos un uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="2b105-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2b105-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="2b105-117">Running the test</span></span>

<span data-ttu-id="2b105-118">Los comandos que se muestran a continuación devuelven las rutas de coincidencia y los usos de teléfono coincidentes que permiten a los usuarios llamar al número de teléfono 1-206-555-1219 con los valores de configuración del tronco para el sitio de Redmond.</span><span class="sxs-lookup"><span data-stu-id="2b105-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2b105-119">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="2b105-119">Determining success or failure</span></span>

<span data-ttu-id="2b105-120">Si las llamadas se pueden enrutar desde un SIP a otro, recibirá un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b105-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="2b105-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="2b105-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="2b105-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="2b105-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="2b105-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="2b105-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="2b105-124">Si la prueba no se realizó correctamente, recibirá un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b105-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="2b105-125">Test-CsInterTrunkRouting: no se puede procesar la transformación de argumentos en el parámetro</span><span class="sxs-lookup"><span data-stu-id="2b105-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="2b105-126">"TrunkConfiguration".</span><span class="sxs-lookup"><span data-stu-id="2b105-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="2b105-127">TrunkConfigurationsetting (parámetro) no válido.</span><span class="sxs-lookup"><span data-stu-id="2b105-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="2b105-128">Especificar un</span><span class="sxs-lookup"><span data-stu-id="2b105-128">Specify a</span></span>

<span data-ttu-id="2b105-129">valor válido (parámetro) y, a continuación, vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="2b105-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="2b105-130">En la línea: 1 carácter: 79</span><span class="sxs-lookup"><span data-stu-id="2b105-130">At line:1 char:79</span></span>

<span data-ttu-id="2b105-131">\+Test-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="2b105-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="2b105-132">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="2b105-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="2b105-133">\+CategoryInfo: InvalidData: (:) \[Test-CsInterTrunkRouting\], par</span><span class="sxs-lookup"><span data-stu-id="2b105-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="2b105-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="2b105-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="2b105-135">\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="2b105-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="2b105-136">The. Management. Voice. cmdlets. TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="2b105-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2b105-137">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="2b105-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="2b105-138">Estas son algunas de las razones comunes por las que **Test-CsInterTrunkRouting** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="2b105-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="2b105-139">Ha especificado parámetros no válidos.</span><span class="sxs-lookup"><span data-stu-id="2b105-139">You specified invalid parameters.</span></span> <span data-ttu-id="2b105-140">Es posible que el tronco no se haya configurado correctamente y que el número de destino especificado sea incorrecto o no sea válido.</span><span class="sxs-lookup"><span data-stu-id="2b105-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b105-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b105-141">See Also</span></span>


[<span data-ttu-id="2b105-142">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="2b105-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="2b105-143">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="2b105-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

