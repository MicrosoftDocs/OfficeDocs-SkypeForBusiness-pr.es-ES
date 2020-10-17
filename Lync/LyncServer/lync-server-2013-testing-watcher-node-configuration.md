---
title: 'Lync Server 2013: probar la configuración de nodo de monitor'
description: 'Lync Server 2013: probar la configuración de nodo de monitor.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546846"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="a731b-103">Probar la configuración de nodo de monitor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a731b-103">Testing watcher node configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a731b-104">_**Última modificación del tema:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="a731b-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a731b-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="a731b-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a731b-106">Diario</span><span class="sxs-lookup"><span data-stu-id="a731b-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a731b-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="a731b-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a731b-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a731b-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a731b-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="a731b-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a731b-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a731b-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a731b-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsWatcherNodeConfiguration</strong> .</span><span class="sxs-lookup"><span data-stu-id="a731b-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="a731b-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a731b-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a731b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a731b-113">Description</span></span>

<span data-ttu-id="a731b-114">Si usa Microsoft System Center Operations Manager para supervisar Lync Server 2013, tiene la opción de configurar "nodos de monitor": equipos que ejecutan transacciones sintéticas de forma periódica y automática, para comprobar que Lync Server funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="a731b-114">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="a731b-115">Los nodos de monitor se asignan a grupos y se administran mediante los cmdlets **CsWatcherNodeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a731b-115">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="a731b-116">Tenga en cuenta que no necesita instalar los nodos de monitor si está utilizando el System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a731b-116">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="a731b-117">Todavía puede supervisar el sistema sin usar nodos de monitor.</span><span class="sxs-lookup"><span data-stu-id="a731b-117">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="a731b-118">La única diferencia es que las transacciones sintéticas que desee ejecutar deben invocarse manualmente en lugar de invocarse de forma automática por parte de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a731b-118">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="a731b-119">El cmdlet **Test-CsWatcherNodeConfiguration** permite comprobar que un nodo de monitor se configuró correctamente y que se asigna a un grupo de servidores de Lync Server 2013 válido.</span><span class="sxs-lookup"><span data-stu-id="a731b-119">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="a731b-120">Tenga en cuenta que el cmdlet **Test-CsWatcherNodeConfiguration** debe ejecutarse en el nodo de monitor en sí.</span><span class="sxs-lookup"><span data-stu-id="a731b-120">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="a731b-121">El cmdlet no se puede ejecutar en equipos remotos.</span><span class="sxs-lookup"><span data-stu-id="a731b-121">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a731b-122">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="a731b-122">Running the test</span></span>

<span data-ttu-id="a731b-123">El siguiente comando comprueba las opciones de configuración de cada nodo de monitor que se usa en la organización.</span><span class="sxs-lookup"><span data-stu-id="a731b-123">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a731b-124">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="a731b-124">Determining success or failure</span></span>

<span data-ttu-id="a731b-125">El siguiente resultado de ejemplo correcto muestra un sistema con cuatro servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="a731b-125">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="a731b-126">Validación del grupo de destino atl-cs-001.litwareinc.com en la topología.</span><span class="sxs-lookup"><span data-stu-id="a731b-126">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="a731b-127">Correcto: el grupo de servidores de destino atl-cs-001.litwareinc.com existe en la topología.</span><span class="sxs-lookup"><span data-stu-id="a731b-127">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="a731b-128">Correcto: el grupo de servidores de destino atl-cs-001.litwareinc.com tiene instalado el rol de registrador.</span><span class="sxs-lookup"><span data-stu-id="a731b-128">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="a731b-129">Correcto: la versión del grupo de servidores de destino atl-cs-001.litwareinc.com es compatible.</span><span class="sxs-lookup"><span data-stu-id="a731b-129">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="a731b-130">Correcto: el número de puerto para 5061 grupo de servidores de destino atl-cs-001.litwareinc.com es correcto.</span><span class="sxs-lookup"><span data-stu-id="a731b-130">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="a731b-131">Comprobando si faltan grupos en la configuración de nodo de monitor iniciada.</span><span class="sxs-lookup"><span data-stu-id="a731b-131">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="a731b-132">Si se detecta algún error, se imprimirá.</span><span class="sxs-lookup"><span data-stu-id="a731b-132">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="a731b-133">Se ha completado la comprobación de los grupos que faltan en la configuración de nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="a731b-133">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="a731b-134">Se ha iniciado la comprobación de claves del registro para el nodo de monitor creado por la instalación del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="a731b-134">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="a731b-135">Si se detecta algún error, se imprimirá.</span><span class="sxs-lookup"><span data-stu-id="a731b-135">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="a731b-136">Comprobando las claves del registro de nodo de monitor creadas por la instalación del nodo de monitor ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="a731b-136">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="a731b-137">El tipo de autenticación detectado es Negotiate.</span><span class="sxs-lookup"><span data-stu-id="a731b-137">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="a731b-138">La existencia del SIP de la credencial del usuario de prueba se validó correctamente: user1@ atl-cs-001.litwareinc.com en el almacén de administración de credenciales.</span><span class="sxs-lookup"><span data-stu-id="a731b-138">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="a731b-139">La existencia del SIP de la credencial del usuario de prueba se validó correctamente: user2@ atl-cs-001.litwareinc.com en el almacén de administración de credenciales.</span><span class="sxs-lookup"><span data-stu-id="a731b-139">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="a731b-140">Comprobando si faltan grupos en la configuración de nodo de monitor iniciada.</span><span class="sxs-lookup"><span data-stu-id="a731b-140">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="a731b-141">Si se detecta algún error, se imprimirá.</span><span class="sxs-lookup"><span data-stu-id="a731b-141">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="a731b-142">ADVERTENCIA: el grupo de atl-cs-001.litwareinc.com tiene registrador</span><span class="sxs-lookup"><span data-stu-id="a731b-142">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="a731b-143">rol instalado, pero no hay ningún usuario de prueba configurado para él.</span><span class="sxs-lookup"><span data-stu-id="a731b-143">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="a731b-144">Se ha completado la comprobación de los grupos que faltan en la configuración de nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="a731b-144">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="a731b-145">Comprobando las claves del registro de nodo de monitor creadas por la instalación del nodo de monitor es</span><span class="sxs-lookup"><span data-stu-id="a731b-145">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="a731b-146">inicia.</span><span class="sxs-lookup"><span data-stu-id="a731b-146">started.</span></span> <span data-ttu-id="a731b-147">Si se detecta algún error, se imprimirá.</span><span class="sxs-lookup"><span data-stu-id="a731b-147">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="a731b-148">Test-CsWatcherNodeConfiguration: no se encuentra la clave del registro de mantenimiento en</span><span class="sxs-lookup"><span data-stu-id="a731b-148">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="a731b-149">Software \\ \\ de comunicaciones en tiempo real de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a731b-149">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="a731b-150">Asegúrese de que el nodo de monitor. msi es</span><span class="sxs-lookup"><span data-stu-id="a731b-150">Make sure watcher node .msi is</span></span>

<span data-ttu-id="a731b-151">instalado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a731b-151">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a731b-152">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="a731b-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="a731b-153">Estas son algunas de las razones comunes por las que **Test-CsWatcherNodeConfiguration** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="a731b-153">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="a731b-154">El nodo de monitor no está instalado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a731b-154">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="a731b-155">No hay usuarios de prueba configurados.</span><span class="sxs-lookup"><span data-stu-id="a731b-155">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a731b-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a731b-156">See Also</span></span>


[<span data-ttu-id="a731b-157">Get-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="a731b-157">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="a731b-158">New-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="a731b-158">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="a731b-159">Remove-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="a731b-159">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="a731b-160">Set-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="a731b-160">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

