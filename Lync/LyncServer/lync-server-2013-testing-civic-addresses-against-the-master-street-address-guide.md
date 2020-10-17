---
title: Prueba de direcciones cívicas con la guía de dirección principal
description: Prueba de direcciones cívicas con la guía de dirección principal.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16e0d721b70e3db175b2d23ddee6f59d13a13c4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560706"
---
# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="bee58-103">Comprobación de direcciones cívicas con la guía de dirección de Master Street en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bee58-103">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bee58-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="bee58-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bee58-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="bee58-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bee58-106">Diario</span><span class="sxs-lookup"><span data-stu-id="bee58-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bee58-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="bee58-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bee58-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bee58-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bee58-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="bee58-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bee58-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bee58-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bee58-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="bee58-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="bee58-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bee58-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bee58-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="bee58-113">Description</span></span>

<span data-ttu-id="bee58-114">El cmdlet Test-CsLisCivicAddress se usa para comprobar las ubicaciones que se agregaron a la base de datos del servicio de información de ubicaciones (LIS).</span><span class="sxs-lookup"><span data-stu-id="bee58-114">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="bee58-115">El cmdlet de funciona comparando las ubicaciones con las ubicaciones que se encuentran en la guía de direcciones maestras (MSAG) que pertenece a su proveedor de enrutamiento de red E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="bee58-115">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="bee58-116">Si no tiene un proveedor de enrutamiento de red o si no se puede obtener acceso al proveedor, se producirá un error en las pruebas.</span><span class="sxs-lookup"><span data-stu-id="bee58-116">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="bee58-117">Si agrega el parámetro switch opcional UpdateValidationStatus a su comando, la propiedad de base de datos MSAGValid correspondiente se establecerá en true para cada dirección que pase la prueba.</span><span class="sxs-lookup"><span data-stu-id="bee58-117">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bee58-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="bee58-118">Running the test</span></span>

<span data-ttu-id="bee58-119">El cmdlet Test-CsLisCivicAddress se puede usar para probar direcciones individuales o para probar varias direcciones.</span><span class="sxs-lookup"><span data-stu-id="bee58-119">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="bee58-120">Por ejemplo, este comando comprueba una única dirección que se encuentra en Redmond, WA:</span><span class="sxs-lookup"><span data-stu-id="bee58-120">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="bee58-121">Por comparación, este comando comprueba todas las direcciones que se encuentran actualmente en la base de datos de LIS:</span><span class="sxs-lookup"><span data-stu-id="bee58-121">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="bee58-122">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="bee58-122">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bee58-123">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="bee58-123">Determining success or failure</span></span>

<span data-ttu-id="bee58-124">Test-CsLisCivicAddress notificará la operación correcta o incorrecta para las direcciones suministradas.</span><span class="sxs-lookup"><span data-stu-id="bee58-124">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="bee58-125">Se producirá un error en una prueba de dirección si no se encuentra la dirección o si no se puede establecer contacto con el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="bee58-125">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bee58-126">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="bee58-126">Reasons why the test might have failed</span></span>

<span data-ttu-id="bee58-127">Estas son algunas de las razones comunes por las que Test-CsLisCivicAddress podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="bee58-127">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="bee58-128">Es posible que el proveedor de servicios LIS no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="bee58-128">The LIS service provider might not be available.</span></span> <span data-ttu-id="bee58-129">Para recuperar la dirección URL de su proveedor de servicios de LIS, ejecute el cmdlet Get-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="bee58-129">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="bee58-130">A continuación, puede hacer ping a esa dirección URL para comprobar que el proveedor de servicios está disponible.</span><span class="sxs-lookup"><span data-stu-id="bee58-130">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

