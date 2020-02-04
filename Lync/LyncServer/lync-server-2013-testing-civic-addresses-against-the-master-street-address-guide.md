---
title: Comprobación de direcciones de cívica con la guía de dirección principal
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
ms.openlocfilehash: 37d6aa1443dc2e062aa099237d9b25f2b33e32b2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="040c2-102">Comprobación de direcciones de cívica con la guía de dirección principal de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="040c2-102">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="040c2-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="040c2-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="040c2-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="040c2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="040c2-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="040c2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040c2-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="040c2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="040c2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="040c2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040c2-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="040c2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="040c2-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="040c2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="040c2-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="040c2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="040c2-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="040c2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="040c2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="040c2-112">Description</span></span>

<span data-ttu-id="040c2-113">El cmdlet test-CsLisCivicAddress se usa para comprobar las ubicaciones que se han agregado a la base de datos del servicio de información de ubicación (LIS).</span><span class="sxs-lookup"><span data-stu-id="040c2-113">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="040c2-114">El cmdlet compara las ubicaciones con las ubicaciones que se encuentran en la guía de dirección principal (MSAG) que pertenece a su proveedor de enrutamiento de red E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="040c2-114">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="040c2-115">Si no tiene un proveedor de enrutamiento de red o si no se puede comunicar con el proveedor, las pruebas no se realizarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="040c2-115">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="040c2-116">Si agrega el parámetro de modificador opcional UpdateValidationStatus a su comando, la propiedad de base de datos de MSAGValid correspondiente se establecerá en true para cada dirección que pase la prueba.</span><span class="sxs-lookup"><span data-stu-id="040c2-116">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="040c2-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="040c2-117">Running the test</span></span>

<span data-ttu-id="040c2-118">El cmdlet test-CsLisCivicAddress se puede usar para probar direcciones individuales o para probar varias direcciones.</span><span class="sxs-lookup"><span data-stu-id="040c2-118">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="040c2-119">Por ejemplo, este comando comprueba una única dirección que se encuentra en Redmond, WA:</span><span class="sxs-lookup"><span data-stu-id="040c2-119">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="040c2-120">Por comparación, este comando prueba todas las direcciones que se encuentran en la base de datos de LIS:</span><span class="sxs-lookup"><span data-stu-id="040c2-120">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="040c2-121">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="040c2-121">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="040c2-122">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="040c2-122">Determining success or failure</span></span>

<span data-ttu-id="040c2-123">Test-CsLisCivicAddress notificará el éxito o el fracaso de las direcciones suministradas.</span><span class="sxs-lookup"><span data-stu-id="040c2-123">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="040c2-124">Se producirá un error en una prueba de dirección si no se puede encontrar la dirección o si no se puede contactar con el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="040c2-124">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="040c2-125">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="040c2-125">Reasons why the test might have failed</span></span>

<span data-ttu-id="040c2-126">Estas son algunas de las razones comunes por las que test-CsLisCivicAddress podría fallar:</span><span class="sxs-lookup"><span data-stu-id="040c2-126">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="040c2-127">Es posible que el proveedor de servicios LIS no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="040c2-127">The LIS service provider might not be available.</span></span> <span data-ttu-id="040c2-128">Para recuperar la dirección URL de su proveedor de servicios LIS, ejecute el cmdlet Get-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="040c2-128">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="040c2-129">Después, puede hacer ping a esa dirección URL para comprobar que el proveedor de servicios está disponible.</span><span class="sxs-lookup"><span data-stu-id="040c2-129">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

