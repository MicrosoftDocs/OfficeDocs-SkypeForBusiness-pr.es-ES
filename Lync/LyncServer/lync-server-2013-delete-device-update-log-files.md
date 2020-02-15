---
title: 'Lync Server 2013: eliminar archivos de registro de actualización de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f5b8ed6d087bb7b80ba93aead7c3ab530c82000
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="bbff0-102">Eliminar los archivos de registro de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbff0-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbff0-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bbff0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bbff0-104">El servicio Web Device Update mantiene una amplia colección de archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="bbff0-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="bbff0-105">Esta colección incluye tanto los registros de auditoría realizados por el propio servicio como los archivos de registro cargados desde los dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="bbff0-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="bbff0-106">Para evitar que el servidor se rellene con los registros del servicio Web de actualización de dispositivos, probablemente querrá eliminar los archivos de registro que han estado en el plazo de un determinado número de días.</span><span class="sxs-lookup"><span data-stu-id="bbff0-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="bbff0-107">Establezca este número de días en función de la actividad de actualización y del número de dispositivos cliente de la organización, mediante el uso del panel de control de Lync Server o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bbff0-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="bbff0-108">Para borrar el registro de actualización de dispositivos mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="bbff0-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bbff0-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bbff0-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bbff0-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bbff0-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="bbff0-111">En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de registros de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="bbff0-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="bbff0-112">En la página **Configuración de registros de dispositivos**, haga doble clic en la configuración que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="bbff0-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="bbff0-113">En el cuadro de diálogo **Editar configuración de registro** , en **número de días que se mantendrán los archivos de registro (1-365)**, especifique un número de días.</span><span class="sxs-lookup"><span data-stu-id="bbff0-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="bbff0-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="bbff0-114">Click **Commit**.</span></span> <span data-ttu-id="bbff0-115">Se eliminan todos los archivos que han estado en el servidor durante un número de días mayor que el especificado.</span><span class="sxs-lookup"><span data-stu-id="bbff0-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="bbff0-116">Esta configuración se aplicará a esta configuración hasta que la cambie.</span><span class="sxs-lookup"><span data-stu-id="bbff0-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="bbff0-117">Borrado del registro de actualización de dispositivos con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbff0-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bbff0-118">Puede borrar los registros de actualización de dispositivos con Windows PowerShell y el cmdlet **Clear-CsDeviceUpdateLog** .</span><span class="sxs-lookup"><span data-stu-id="bbff0-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="bbff0-119">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbff0-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bbff0-120">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="bbff0-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="bbff0-121">Para borrar los registros de actualización de dispositivos en un servidor</span><span class="sxs-lookup"><span data-stu-id="bbff0-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="bbff0-122">El siguiente comando borra el registro de actualización de dispositivos en el servidor Web atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="bbff0-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="bbff0-123">Todas las entradas de registro que tengan más de 10 días de antigüedad (el valor especificado por el parámetro DaysBack) se quitarán del registro.</span><span class="sxs-lookup"><span data-stu-id="bbff0-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="bbff0-124">Para borrar todos los registros de actualización de dispositivos</span><span class="sxs-lookup"><span data-stu-id="bbff0-124">To clear all device update logs</span></span>

  - <span data-ttu-id="bbff0-125">Este comando quita las entradas obsoletas (en este ejemplo, las entradas de más de 10 días de antigüedad) de todos los registros de actualización de dispositivos que se usan actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="bbff0-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="bbff0-126">Para obtener más información, consulte el tema de ayuda para el cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .</span><span class="sxs-lookup"><span data-stu-id="bbff0-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

