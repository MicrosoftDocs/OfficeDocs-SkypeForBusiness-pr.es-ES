---
title: 'Lync Server 2013: quitar una regla de actualización de dispositivo'
description: 'Lync Server 2013: quitar una regla de actualización de dispositivos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f0ed7436331377200a5b8719cf32a8195179402
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555786"
---
# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="57e17-103">Quitar una regla de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57e17-103">Remove a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57e17-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="57e17-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="57e17-105">Al quitar una regla de actualización de dispositivo, ésta se desconecta permanentemente de la cola de actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="57e17-105">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="57e17-106">La eliminación de una regla es diferente de la desinstalación de una actualización de los dispositivos de su implementación o de los dispositivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="57e17-106">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="57e17-107">Para desinstalar una actualización aprobada desde su implementación, *restaure* la regla de actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="57e17-107">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="57e17-108">Para obtener más información, consulte [restaurar una regla de actualización de dispositivos en Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="57e17-108">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="57e17-109">Para desinstalar una actualización que no haya aprobado de sus dispositivos de prueba, debe *restablecerla* .</span><span class="sxs-lookup"><span data-stu-id="57e17-109">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="57e17-110">Para obtener más información, consulte [restablecer una regla de actualización de dispositivos en Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="57e17-110">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="57e17-111">Puede quitar una regla de actualización de dispositivos mediante el panel de control de Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57e17-111">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="57e17-112">Para quitar reglas de actualización de dispositivos mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="57e17-112">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="57e17-113">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="57e17-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="57e17-114">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57e17-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="57e17-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="57e17-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="57e17-116">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, en el botón de navegación **actualización de dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="57e17-116">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="57e17-117">En la página **actualización de dispositivo** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="57e17-117">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="57e17-118">Para quitar una regla, seleccione la regla que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="57e17-118">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="57e17-119">Para quitar todas las reglas, haga clic en el menú **Editar** y, a continuación, haga clic en **seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="57e17-119">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="57e17-120">Haga clic en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="57e17-120">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="57e17-121">Eliminación de reglas de actualización de dispositivos mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="57e17-121">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="57e17-122">Las reglas de actualización de dispositivos también se pueden quitar con Windows PowerShell y el cmdlet **Remove-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="57e17-122">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="57e17-123">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57e17-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="57e17-124">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="57e17-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="57e17-125">Para quitar una regla de actualización de dispositivos única de un servidor</span><span class="sxs-lookup"><span data-stu-id="57e17-125">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="57e17-126">El siguiente comando quita la regla de actualización de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 del servidor Web en atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="57e17-126">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="57e17-127">Para quitar todas las reglas de actualización de dispositivos de un servidor</span><span class="sxs-lookup"><span data-stu-id="57e17-127">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="57e17-128">Este comando quita todas las reglas de actualización de dispositivos del servidor Web de atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="57e17-128">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="57e17-129">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="57e17-129">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57e17-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57e17-130">See Also</span></span>


[<span data-ttu-id="57e17-131">Aprobar una regla de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57e17-131">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

