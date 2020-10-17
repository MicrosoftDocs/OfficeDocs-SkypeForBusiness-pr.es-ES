---
title: 'Lync Server 2013: comprobación de los servicios de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74a24818094d7de0edc4627f987464df048315f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519017"
---
# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="7317e-102">Probar los servicios de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7317e-102">Testing Lync Server services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7317e-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7317e-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7317e-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="7317e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7317e-105">Diario</span><span class="sxs-lookup"><span data-stu-id="7317e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7317e-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="7317e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7317e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7317e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7317e-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="7317e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7317e-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7317e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7317e-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7317e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="7317e-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7317e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7317e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7317e-112">Description</span></span>

<span data-ttu-id="7317e-113">Test-CsComputer comprueba el estado de todos los servicios de Lync Server 2013 que se ejecutan en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="7317e-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="7317e-114">(Test-CsComputer solo se puede ejecutar de forma local, no se puede ejecutar desde una instancia remota de Windows PowerShell). El cmdlet también comprueba si los puertos de Firewall adecuados están abiertos en el equipo y determina si los grupos de Active Directory que se crearon al instalar Lync Server 2013 se agregaron a los grupos locales correspondientes.</span><span class="sxs-lookup"><span data-stu-id="7317e-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="7317e-115">Por ejemplo, Test-CsComputer comprobará que el grupo de Active Directory RTCUniversalUserAdmins se agregó al grupo administradores.</span><span class="sxs-lookup"><span data-stu-id="7317e-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="7317e-116">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="7317e-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7317e-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="7317e-117">Running the test</span></span>

<span data-ttu-id="7317e-118">El cmdlet Test-CsComputer solo puede ejecutarse en el equipo local, no puede llamar a Test-CsComputer desde una instancia remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7317e-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="7317e-119">De forma predeterminada, Test-CsComputer muestra muy poco resultado en pantalla, en su lugar la información devuelta por el cmdlet se escribe en un archivo HTML.</span><span class="sxs-lookup"><span data-stu-id="7317e-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="7317e-120">Por ello, se recomienda incluir el parámetro verbose y el parámetro Report en cualquier momento que se ejecute test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7317e-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="7317e-121">El parámetro verbose proporcionará un resultado ligeramente más detallado en pantalla mientras se ejecuta el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7317e-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="7317e-122">El parámetro Report permite especificar una ruta de acceso de archivo y un nombre de archivo para el archivo HTML generado por test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7317e-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="7317e-123">Si no incluye el parámetro de informe, el archivo HTML se guardará automáticamente en la carpeta de usuarios y se le asignará un nombre similar al siguiente: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span><span class="sxs-lookup"><span data-stu-id="7317e-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="7317e-124">El siguiente comando de ejemplo ejecuta Test-CsComputer y guarda el resultado en un archivo denominado C: \\ Logs \\ComputerTest.html:</span><span class="sxs-lookup"><span data-stu-id="7317e-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="7317e-125">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="7317e-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7317e-126">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="7317e-126">Determining success or failure</span></span>

<span data-ttu-id="7317e-127">Debido al número de comprobaciones de comprobación que realiza, Test-CsComputer no devuelven una simple **yes, la prueba se realizó correctamente** o **no, la prueba produjo un error**.</span><span class="sxs-lookup"><span data-stu-id="7317e-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="7317e-128">En su lugar, tiene que ver el archivo HTML generado con Internet Explorer para determinar si cada prueba se ha realizado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="7317e-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7317e-129">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="7317e-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="7317e-130">Estas son algunas de las razones comunes por las que Test-CsComputer podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="7317e-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="7317e-131">Es posible que el equipo de prueba no esté habilitado para su uso con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7317e-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="7317e-132">Esto puede ocurrir si los servicios o los roles de servidor de Lync Server en el equipo han cambiado y no se ejecutó el cmdlet Enable-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7317e-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="7317e-133">Para solucionar este problema, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7317e-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="7317e-134">Es posible que la replicación no esté actualizada en el equipo de prueba.</span><span class="sxs-lookup"><span data-stu-id="7317e-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="7317e-135">Puede comprobar el estado de replicación actual de un equipo ejecutando el cmdlet Get-CsManagementStoreReplicationStatus:</span><span class="sxs-lookup"><span data-stu-id="7317e-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="7317e-136">Si el estado de replicación no está actualizado, puede forzar la replicación manualmente mediante un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="7317e-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="7317e-137">Es posible que la topología tenga que estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="7317e-137">The topology might have to be enabled.</span></span> <span data-ttu-id="7317e-138">Si cambia la topología de Lync Server (cambios que pueden afectar al equipo local), debe habilitar la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="7317e-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="7317e-139">Puede habilitar la topología en cualquier momento si ejecuta este comando:</span><span class="sxs-lookup"><span data-stu-id="7317e-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

