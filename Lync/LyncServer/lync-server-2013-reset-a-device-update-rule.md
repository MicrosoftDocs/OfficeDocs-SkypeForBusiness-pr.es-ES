---
title: 'Lync Server 2013: restablecer una regla de actualización de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68162e0661090ac57bfaacecfd22eea1261911e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="21fe5-102">Restablecer una regla de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21fe5-102">Reset a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21fe5-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="21fe5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="21fe5-104">Si no le gusta la forma en que una actualización funciona en sus dispositivos de prueba, puede restablecer la regla de actualización de dispositivos, que elimina el estado pendiente de la regla y desinstala la actualización de los dispositivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="21fe5-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="21fe5-105">Puede quitar una regla de actualización de dispositivos mediante el panel de control de Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21fe5-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="21fe5-106">Para desinstalar una regla que ya haya aprobado (es decir, que esté implementada), restáurela.</span><span class="sxs-lookup"><span data-stu-id="21fe5-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="21fe5-107">Para obtener más información, consulte <A href="lync-server-2013-restore-a-device-update-rule.md">restaurar una regla de actualización de dispositivos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="21fe5-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="21fe5-108">Para restablecer una regla de actualización de dispositivos mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="21fe5-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="21fe5-109">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="21fe5-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="21fe5-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21fe5-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="21fe5-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="21fe5-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="21fe5-112">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, en el botón de navegación **actualización de dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="21fe5-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="21fe5-113">En la página **actualización de dispositivo** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="21fe5-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="21fe5-114">Para restablecer una regla, seleccione la regla que desea restablecer.</span><span class="sxs-lookup"><span data-stu-id="21fe5-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="21fe5-115">Para restablecer todas las reglas, en el menú **edición** , haga clic en **seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="21fe5-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="21fe5-116">Para restablecer todas las reglas de una marca, use el menú columna de **marca** .</span><span class="sxs-lookup"><span data-stu-id="21fe5-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="21fe5-117">Haga clic en **acción**y, a continuación, en **Cancelar actualizaciones pendientes**.</span><span class="sxs-lookup"><span data-stu-id="21fe5-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="21fe5-118">Si está seguro de que nunca deseará implementar las reglas de actualización de dispositivos que ha cancelado, es posible que quiera eliminarlas.</span><span class="sxs-lookup"><span data-stu-id="21fe5-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="21fe5-119">Para obtener más información, consulte <A href="lync-server-2013-remove-a-device-update-rule.md">quitar una regla de actualización de dispositivos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="21fe5-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="21fe5-120">Restablecimiento de una regla de actualización de dispositivos mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21fe5-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="21fe5-121">Las reglas de actualización de dispositivos también se pueden restablecer mediante Windows PowerShell y el cmdlet **RESET-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="21fe5-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="21fe5-122">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21fe5-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="21fe5-123">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="21fe5-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="21fe5-124">Para restablecer una regla de actualización de dispositivos específica en un servidor</span><span class="sxs-lookup"><span data-stu-id="21fe5-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="21fe5-125">El siguiente comando restablece la regla de actualización de dispositivos d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 en el servidor Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="21fe5-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="21fe5-126">Para restablecer todas las reglas de actualización de dispositivos en un servidor</span><span class="sxs-lookup"><span data-stu-id="21fe5-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="21fe5-127">Este comando restablece todas las reglas de actualización de dispositivos en el servidor Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="21fe5-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="21fe5-128">Para restablecer todas las reglas de actualización de dispositivos que tienen una marca específica</span><span class="sxs-lookup"><span data-stu-id="21fe5-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="21fe5-129">En este ejemplo, se restablecen todas las actualizaciones de dispositivos en toda la organización que tienen una marca igual a Microsoft:</span><span class="sxs-lookup"><span data-stu-id="21fe5-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="21fe5-130">Para obtener más información, consulte el tema de ayuda para el cmdlet [RESET-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="21fe5-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21fe5-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="21fe5-131">See Also</span></span>


[<span data-ttu-id="21fe5-132">Aprobar una regla de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21fe5-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

