---
title: 'Lync Server 2013: aprobar una regla de actualización de dispositivo'
description: 'Lync Server 2013: aprobar una regla de actualización de dispositivo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 127d16dad6329e952b9033db07ac2f4a4fe9112c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550726"
---
# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="81ff5-103">Aprobar una regla de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81ff5-103">Approve a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81ff5-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="81ff5-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="81ff5-105">Después de importar una regla de actualización de dispositivos, se instala en los dispositivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="81ff5-105">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="81ff5-106">Si las pruebas se realizan correctamente y desea implementar la actualización en su organización, puede aprobarla mediante el panel de control de Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81ff5-106">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="81ff5-107">Para aprobar una regla de actualización de dispositivos mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="81ff5-107">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="81ff5-108">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="81ff5-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="81ff5-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="81ff5-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="81ff5-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="81ff5-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="81ff5-111">En la página **actualización de dispositivo** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="81ff5-111">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="81ff5-112">Para aprobar una regla, seleccione esa regla.</span><span class="sxs-lookup"><span data-stu-id="81ff5-112">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="81ff5-113">Para aprobar todas las reglas, haga clic en **Editar**y, a continuación, haga clic en **seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="81ff5-113">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="81ff5-114">Haga clic en **acción**y, a continuación, en **aprobar**.</span><span class="sxs-lookup"><span data-stu-id="81ff5-114">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="81ff5-115">Aprobación de una regla de actualización de dispositivos mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="81ff5-115">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="81ff5-116">Las reglas de actualización de dispositivos también pueden aprobarse con Windows PowerShell y el cmdlet **Approven-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="81ff5-116">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="81ff5-117">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81ff5-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81ff5-118">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="81ff5-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="81ff5-119">Para aprobar una única regla de actualización de dispositivos</span><span class="sxs-lookup"><span data-stu-id="81ff5-119">To approve a single device update rule</span></span>

  - <span data-ttu-id="81ff5-120">El siguiente comando aprueba la regla de actualización de dispositivos d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 que se encuentra en el servidor Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="81ff5-120">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="81ff5-121">Para aprobar varias reglas de actualización de dispositivos</span><span class="sxs-lookup"><span data-stu-id="81ff5-121">To approve multiple device update rules</span></span>

  - <span data-ttu-id="81ff5-122">Este comando aprueba todas las reglas de actualización de dispositivos para los dispositivos marcados por Microsoft:</span><span class="sxs-lookup"><span data-stu-id="81ff5-122">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="81ff5-123">Para obtener más información, consulte el tema de ayuda para el cmdlet [APPROVE-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="81ff5-123">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81ff5-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81ff5-124">See Also</span></span>


[<span data-ttu-id="81ff5-125">Importar reglas de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81ff5-125">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="81ff5-126">Restaurar una regla de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81ff5-126">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

