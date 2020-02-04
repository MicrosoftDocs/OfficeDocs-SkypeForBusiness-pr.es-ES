---
title: 'Lync Server 2013: ver información de un plan de marcado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial plan information
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49733587
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a83de5daf33764dd08be9c08141d338e73a675d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-dial-plan-information-in-lync-server-2013"></a><span data-ttu-id="231f8-102">Ver información de un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="231f8-102">View dial plan information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="231f8-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="231f8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="231f8-104">Para ver la información de un plan de marcado existente, siga los pasos que se indican en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="231f8-104">To view information for an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="231f8-105">Si desea crear un plan de marcado nuevo, consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="231f8-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-view-information-about-a-dial-plan-from-lync-server-control-panel"></a><span data-ttu-id="231f8-106">Para ver la información sobre un plan de marcado desde el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="231f8-106">To view information about a dial plan from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="231f8-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="231f8-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="231f8-108">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="231f8-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="231f8-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="231f8-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="231f8-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="231f8-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="231f8-111">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Plan de marcado**.</span><span class="sxs-lookup"><span data-stu-id="231f8-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="231f8-112">En la página **Plan de marcado**, haga doble clic en el nombre del plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="231f8-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="231f8-113">Solo puede ver la información de un plan de marcado cada vez.</span><span class="sxs-lookup"><span data-stu-id="231f8-113">You can view information for only one dial plan at a time.</span></span>

    
    </div>

</div>

<div>

## <a name="to-view-dial-plans-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="231f8-114">Para ver los planes de marcado mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="231f8-114">To view dial plans by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="231f8-115">Los planes de marcado se pueden ver con la interfaz de línea de comandos de Windows PowerShell y el cmdlet **Get-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="231f8-115">Dial plans can be viewed by using the Windows PowerShell command-line interface and the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="231f8-116">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="231f8-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="231f8-117">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="231f8-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="231f8-118">Para ver información sobre todos los planes de marcado, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="231f8-118">To view information about all your dial plans, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="231f8-119">Ese comando devolverá información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="231f8-119">That command will return information similar to this:</span></span>
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="231f8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="231f8-120">See Also</span></span>


[<span data-ttu-id="231f8-121">Crear un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="231f8-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="231f8-122">Modificar un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="231f8-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

