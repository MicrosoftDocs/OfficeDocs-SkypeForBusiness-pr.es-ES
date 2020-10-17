---
title: 'Lync Server 2013: probar la activación del servicio y los permisos de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92e29cafcfac7a74e43617841a174653f6072c5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530527"
---
# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="ac2eb-102">Probar la activación del servicio y los permisos de grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac2eb-102">Testing service activation and group permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac2eb-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ac2eb-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac2eb-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="ac2eb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ac2eb-105">Diario</span><span class="sxs-lookup"><span data-stu-id="ac2eb-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac2eb-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="ac2eb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ac2eb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac2eb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac2eb-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="ac2eb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ac2eb-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ac2eb-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="ac2eb-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ac2eb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ac2eb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac2eb-112">Description</span></span>

<span data-ttu-id="ac2eb-113">El cmdlet Test-CsTopology permite comprobar que Lync Server 2013 funciona correctamente en un ámbito global.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-113">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="ac2eb-114">De forma predeterminada, el cmdlet comprueba toda la infraestructura de Lync Server, comprobando que los servicios necesarios se están ejecutando y que se han establecido los permisos adecuados para estos servicios y para los grupos de seguridad universal que se crean al instalar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-114">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="ac2eb-115">Además de comprobar la validez de la instalación de Lync Server, Test-CsTopology también le permite comprobar la validez de un servicio específico.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-115">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="ac2eb-116">Por ejemplo, este comando comprueba el estado del servidor de conferencia A/V en el grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="ac2eb-116">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ac2eb-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="ac2eb-117">Running the test</span></span>

<span data-ttu-id="ac2eb-118">De forma predeterminada, Test-CsTopology muestra muy poco resultados en pantalla.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-118">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="ac2eb-119">En su lugar, la información devuelta por el cmdlet se escribe en un archivo HTML.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-119">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="ac2eb-120">El parámetro Report permite especificar una ruta de acceso de archivo y un nombre de archivo para el archivo HTML generado por test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-120">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="ac2eb-121">Si no incluye el parámetro de informe, el archivo HTML se guardará automáticamente en la carpeta de usuarios y se le asignará un nombre similar al siguiente: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-121">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="ac2eb-122">El siguiente comando de ejemplo ejecuta Test-CsTopology y guarda el resultado en un archivo denominado C: \\ Logs \\ComputerTest.html:</span><span class="sxs-lookup"><span data-stu-id="ac2eb-122">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="ac2eb-123">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .</span><span class="sxs-lookup"><span data-stu-id="ac2eb-123">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ac2eb-124">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="ac2eb-124">Determining success or failure</span></span>

<span data-ttu-id="ac2eb-125">A diferencia de la mayoría de los cmdlets test, Test-CsTopology informa de que la operación se ha realizado correctamente o con errores.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-125">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="ac2eb-126">En parte, esto es debido a la gran cantidad de comprobaciones de comprobación que el cmdlet debe realizar cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-126">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="ac2eb-127">En su lugar, los datos se guardan en un informe HTML que, a continuación, se puede ver con Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-127">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ac2eb-128">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="ac2eb-128">Reasons why the test might have failed</span></span>

<span data-ttu-id="ac2eb-129">Estas son algunas de las razones comunes por las que Test-CsTopology podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="ac2eb-129">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="ac2eb-130">Es posible que la replicación no esté actualizada en el equipo de prueba.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-130">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="ac2eb-131">Puede comprobar el estado de replicación actual de un equipo ejecutando el cmdlet Get-CsManagementStoreReplicationStatus:</span><span class="sxs-lookup"><span data-stu-id="ac2eb-131">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="ac2eb-132">Si el estado de replicación no está actualizado, puede forzar la replicación manualmente mediante un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="ac2eb-132">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="ac2eb-133">Es posible que la topología tenga que estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-133">The topology might have to be enabled.</span></span> <span data-ttu-id="ac2eb-134">Si cambia la topología de Lync Server (cambios que pueden afectar al equipo local), debe habilitar la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="ac2eb-134">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="ac2eb-135">Puede habilitar la topología en cualquier momento si ejecuta este comando:</span><span class="sxs-lookup"><span data-stu-id="ac2eb-135">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

