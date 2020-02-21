---
title: 'Lync Server 2013: comprobar la configuración del tronco con un número de teléfono'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf9d53d8702fbd9e63ec05af2c4942538f7298e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="d247c-102">Comprobar la configuración del tronco con un número de teléfono en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d247c-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d247c-103">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="d247c-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d247c-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="d247c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d247c-105">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="d247c-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d247c-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="d247c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d247c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d247c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d247c-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="d247c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d247c-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d247c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d247c-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d247c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="d247c-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d247c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d247c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d247c-112">Description</span></span>

<span data-ttu-id="d247c-113">Los troncos SIP conectan la red de telefonía IP empresarial interna de Lync Server a cualquiera de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d247c-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="d247c-114">La red telefónica conmutada pública (RTC).</span><span class="sxs-lookup"><span data-stu-id="d247c-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="d247c-115">Una central de conmutación (PBX) de IP-Public.</span><span class="sxs-lookup"><span data-stu-id="d247c-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="d247c-116">Un controlador de borde de sesión (SBC).</span><span class="sxs-lookup"><span data-stu-id="d247c-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="d247c-117">El cmdlet test-CsTrunkConfiguration comprueba que un número de teléfono (como marcado por un usuario) se puede convertir a la red E. 164 y enrutarse a través de un tronco SIP especificado.</span><span class="sxs-lookup"><span data-stu-id="d247c-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d247c-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="d247c-118">Running the test</span></span>

<span data-ttu-id="d247c-119">Para ejecutar el cmdlet test-CsTrunkConfiguration, primero debe usar el cmdlet Get-CsTrunkConfiguration para recuperar una instancia de las opciones de configuración del tronco SIP; a continuación, esa instancia se canaliza a test-CsTrunkConfiguration:</span><span class="sxs-lookup"><span data-stu-id="d247c-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="d247c-120">Ejecutar test-CsTrunkConfiguration sin ejecutar primero Get-CsTrunkConfiguration no funcionará.</span><span class="sxs-lookup"><span data-stu-id="d247c-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="d247c-121">Por ejemplo, se producirá un error en este comando sin que se devuelva ningún dato:</span><span class="sxs-lookup"><span data-stu-id="d247c-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="d247c-122">Si tiene varias colecciones de opciones de configuración de tronco SIP, puede usar un comando similar al siguiente para al mismo tiempo probar cada recopilación con el mismo número de teléfono:</span><span class="sxs-lookup"><span data-stu-id="d247c-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="d247c-123">Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d247c-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d247c-124">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="d247c-124">Determining success or failure</span></span>

<span data-ttu-id="d247c-125">Si test-CsTrunkConfiguration puede realizar una llamada al número marcado, el número de teléfono convertido (con el formato E. 164) y la regla utilizada para convertir ese número de teléfono se mostrarán en pantalla:</span><span class="sxs-lookup"><span data-stu-id="d247c-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="d247c-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="d247c-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="d247c-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="d247c-127">\---------------- ------------</span></span>

<span data-ttu-id="d247c-128">\+12065551219 global/Redmond</span><span class="sxs-lookup"><span data-stu-id="d247c-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="d247c-129">Si se produce un error en la prueba, test-CsTrunkConfiguration devolverá valores de propiedad vacía:</span><span class="sxs-lookup"><span data-stu-id="d247c-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="d247c-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="d247c-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="d247c-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="d247c-131">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d247c-132">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="d247c-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="d247c-133">Si test-CsTrunkConfiguration no devuelve una coincidencia que normalmente significa que los valores de configuración del tronco que se están comprobando no tienen una regla de conversión de números de llamadas salientes capaz de convertir el número marcado al formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="d247c-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="d247c-134">Para recuperar las reglas de conversión asignadas a una colección de opciones de configuración de tronco, puede usar una sintaxis similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d247c-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="d247c-135">Que devuelve información similar a la siguiente para cada regla de conversión:</span><span class="sxs-lookup"><span data-stu-id="d247c-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="d247c-136">Descripción: números de teléfono sin código de país ni código de área.</span><span class="sxs-lookup"><span data-stu-id="d247c-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="d247c-137">Patrón: ^\\+ (\\d\*) $</span><span class="sxs-lookup"><span data-stu-id="d247c-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="d247c-138">Nombre: NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="d247c-138">Name : NoAreaCode</span></span>

<span data-ttu-id="d247c-139">En ese momento, debe comprobar el valor de la propiedad Pattern (que es una cadena de [expresión regular](https://go.microsoft.com/fwlink/?linkid=400464) ) para ver si alguna de las reglas de conversión está configurada para controlar el número marcado.</span><span class="sxs-lookup"><span data-stu-id="d247c-139">At that point, you check the value of the Pattern property (which is a [regular expression](https://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="d247c-140">Si no es así, tendrá que cambiar una de las reglas existentes (Set-CsOutboundTranslationRule) o usar el cmdlet New-CsOutboundTranslationRule para agregar una nueva regla a la colección.</span><span class="sxs-lookup"><span data-stu-id="d247c-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d247c-141">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d247c-141">See Also</span></span>


[<span data-ttu-id="d247c-142">Test-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="d247c-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

