---
title: 'Lync Server 2013: quitar una regla de actualización de dispositivo'
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
ms.openlocfilehash: 8d367c507ea2e8871231248b1f29d7d033dedbe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="9f435-102">Quitar una regla de actualización de dispositivo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f435-102">Remove a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f435-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9f435-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9f435-104">Al quitar una regla de actualización de dispositivo, se sacará de él permanentemente de la cola de actualizaciones de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9f435-104">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="9f435-105">Quitar una regla es diferente de desinstalar una actualización de los dispositivos de su implementación o de su dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="9f435-105">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="9f435-106">Para desinstalar una actualización aprobada de su implementación, *restaure* la regla de actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9f435-106">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="9f435-107">Para obtener más información, consulte [restaurar una regla de actualización de dispositivos en Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="9f435-107">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="9f435-108">Para desinstalar una actualización que no haya aprobado de sus dispositivos de prueba, puede *restablecerla* .</span><span class="sxs-lookup"><span data-stu-id="9f435-108">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="9f435-109">Para obtener más información, consulte [restablecer una regla de actualización de dispositivo en Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="9f435-109">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="9f435-110">Puede quitar una regla de actualización de dispositivo con el panel de control de Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f435-110">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="9f435-111">Para quitar las reglas de actualización de dispositivos mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="9f435-111">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9f435-112">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9f435-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9f435-113">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f435-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9f435-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9f435-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9f435-115">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **actualización de dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="9f435-115">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="9f435-116">En la página **actualización de dispositivo** , siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="9f435-116">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9f435-117">Para quitar una regla, seleccione la que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="9f435-117">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="9f435-118">Para quitar todas las reglas, haga clic en el menú **Editar** y, a continuación, haga clic en **seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="9f435-118">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="9f435-119">Haga clic en **Editar** y después en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="9f435-119">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9f435-120">Quitar las reglas de actualización de dispositivos mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f435-120">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9f435-121">Las reglas de actualización de dispositivos también se pueden quitar con Windows PowerShell y el cmdlet **Remove-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="9f435-121">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="9f435-122">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f435-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9f435-123">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="9f435-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="9f435-124">Para quitar una regla de actualización de un solo dispositivo de un servidor</span><span class="sxs-lookup"><span data-stu-id="9f435-124">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="9f435-125">El siguiente comando quita la regla de actualización de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 del servidor Web en atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="9f435-125">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="9f435-126">Para quitar todas las reglas de actualización de dispositivos de un servidor</span><span class="sxs-lookup"><span data-stu-id="9f435-126">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="9f435-127">Este comando quita todas las reglas de actualización de dispositivos del servidor Web en atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="9f435-127">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="9f435-128">Para obtener más información, vea el tema de ayuda sobre el cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="9f435-128">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9f435-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f435-129">See Also</span></span>


[<span data-ttu-id="9f435-130">Aprobar una regla de actualización de dispositivo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f435-130">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

