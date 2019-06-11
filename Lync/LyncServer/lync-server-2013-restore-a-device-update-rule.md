---
title: 'Lync Server 2013: restaurar una regla de actualización de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90eeb82e710b6ea65bc32184685497494dbef8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="68fa0-102">Restaurar una regla de actualización de dispositivo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68fa0-102">Restore a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68fa0-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="68fa0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="68fa0-104">Para desinstalar una regla de actualización de dispositivo de los dispositivos de su implementación, restáurela.</span><span class="sxs-lookup"><span data-stu-id="68fa0-104">To uninstall a device update rule from the devices in your deployment, restore it.</span></span> <span data-ttu-id="68fa0-105">Si restaura una regla de actualización de dispositivo, se desinstalará la actualización y se reinstalará la versión anterior de la regla.</span><span class="sxs-lookup"><span data-stu-id="68fa0-105">Restoring a device update rule both uninstalls the update and reinstalls the previous version of that rule.</span></span>

<span data-ttu-id="68fa0-106">Puede restaurar una regla de actualización de dispositivo con el panel de control de Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68fa0-106">You can restore a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="68fa0-107">Para restaurar las reglas de actualización de dispositivos mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="68fa0-107">To restore device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="68fa0-108">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="68fa0-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="68fa0-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68fa0-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="68fa0-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="68fa0-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="68fa0-111">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **actualización de dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="68fa0-111">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="68fa0-112">En la página **actualización de dispositivo** , siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="68fa0-112">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="68fa0-113">Para restaurar una regla, seleccione esa regla.</span><span class="sxs-lookup"><span data-stu-id="68fa0-113">To restore one rule, select that rule.</span></span>
    
      - <span data-ttu-id="68fa0-114">Para restaurar todas las reglas, haga clic en **Editar**y, a continuación, haga clic en **seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="68fa0-114">To restore all rules, click **Edit**, and then click **Select All**.</span></span>

5.  <span data-ttu-id="68fa0-115">Haga clic en el menú **acción** y, a continuación, haga clic en **restaurar**.</span><span class="sxs-lookup"><span data-stu-id="68fa0-115">Click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="68fa0-116">Restauración de reglas de actualización de dispositivos mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="68fa0-116">Restoring Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="68fa0-117">Las reglas de actualizaciones de dispositivos también se pueden restaurar mediante Windows PowerShell y el cmdlet **restore-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="68fa0-117">Device updates rules can also be restored by using Windows PowerShell and the **Restore-CsDeviceUpdateRule** cmdlet..</span></span> <span data-ttu-id="68fa0-118">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68fa0-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68fa0-119">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="68fa0-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a><span data-ttu-id="68fa0-120">Para restaurar una regla de actualización de un solo dispositivo en un servidor</span><span class="sxs-lookup"><span data-stu-id="68fa0-120">To restore a single device update rule on a server</span></span>

  - <span data-ttu-id="68fa0-121">El siguiente comando restaura la regla de actualización de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 en el servidor Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="68fa0-121">The following command restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="68fa0-122">Para restaurar todas las reglas de actualización de dispositivos en un servidor</span><span class="sxs-lookup"><span data-stu-id="68fa0-122">To restore all the device update rules on a server</span></span>

  - <span data-ttu-id="68fa0-123">Este comando restaura todas las reglas de actualización de dispositivos en el servidor Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="68fa0-123">This command restores all the device update rules on the web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

<span data-ttu-id="68fa0-124">Para obtener más información, consulte el tema de ayuda para el cmdlet [restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="68fa0-124">For details, see the Help topic for the [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

