---
title: 'Lync Server 2013: Ver registros de uso de RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6c6ca5761959b8b98cb4eb6a8f17e87c543e788
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="4fe15-102">Ver los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fe15-102">View PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fe15-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4fe15-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4fe15-104">Un registro de uso de la red telefónica conmutada (RTC) especifica una clase de llamada (por ejemplo, interna, local o de larga distancia) que pueden realizar varios usuarios o grupos de usuarios en una organización.</span><span class="sxs-lookup"><span data-stu-id="4fe15-104">A public switched telephone network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="4fe15-105">Para obtener más información, consulte [registros de uso de RTC en Lync Server 2013](lync-server-2013-pstn-usage-records.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="4fe15-105">For details, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) in the Planning documentation.</span></span>

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a><span data-ttu-id="4fe15-106">Para ver un registro de uso de RTC mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="4fe15-106">To view a PSTN usage record by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4fe15-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4fe15-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4fe15-108">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4fe15-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4fe15-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4fe15-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4fe15-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4fe15-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4fe15-111">En la barra de navegación izquierda, haga clic en **enrutamiento de voz** y, a continuación, en **uso de RTC**.</span><span class="sxs-lookup"><span data-stu-id="4fe15-111">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

4.  <span data-ttu-id="4fe15-112">En la página **uso de RTC** , resalte el registro de uso de RTC que desee ver, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="4fe15-112">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4fe15-113">Una página de solo lectura del registro de uso de RTC seleccionado muestra las rutas asociadas y las directivas de voz asociadas.</span><span class="sxs-lookup"><span data-stu-id="4fe15-113">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4fe15-114">Ver la información de uso de RTC mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fe15-114">Viewing PSTN Usage Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4fe15-115">También puede ver los usos de RTC con Windows PowerShell y el cmdlet **Get-CsPstnUsage** .</span><span class="sxs-lookup"><span data-stu-id="4fe15-115">You can also view PSTN usages by using Windows PowerShell and the **Get-CsPstnUsage** cmdlet.</span></span> <span data-ttu-id="4fe15-116">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fe15-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4fe15-117">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="4fe15-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4fe15-118">Para ver la información de uso de RTC con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fe15-118">To view PSTN usage information by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="4fe15-119">Para ver información sobre todos los usos de RTC, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="4fe15-119">To view information about all of your PSTN usages, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsPstnUsage
    
    <span data-ttu-id="4fe15-120">Este comando devuelve información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4fe15-120">This command returns information similar to the following:</span></span>
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

<span data-ttu-id="4fe15-121">Para obtener más información, consulte [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span><span class="sxs-lookup"><span data-stu-id="4fe15-121">For details, see [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4fe15-122">Consulta también</span><span class="sxs-lookup"><span data-stu-id="4fe15-122">See Also</span></span>


[<span data-ttu-id="4fe15-123">Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fe15-123">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="4fe15-124">Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fe15-124">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

