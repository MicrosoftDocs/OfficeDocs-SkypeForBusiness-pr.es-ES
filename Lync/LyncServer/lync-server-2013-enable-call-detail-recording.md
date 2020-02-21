---
title: 'Lync Server 2013: habilitar el registro detallado de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d9227c1b3486ea20d6a1dc9c82311bfd17633bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="62286-102">Habilitar el registro detallado de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62286-102">Enable call detail recording in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62286-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="62286-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="62286-p101">El registro detallado de llamadas (CDR) registra la información de uso y diagnóstico sobre actividades punto a punto, incluida la mensajería instantánea, llamadas de voz sobre IP (VoIP), uso compartido de aplicaciones, transferencia de archivos y reuniones. Los datos de uso pueden servir para calcular el retorno de la inversión y los datos de diagnóstico se pueden usar para solucionar problemas de actividades punto a punto y reuniones.</span><span class="sxs-lookup"><span data-stu-id="62286-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="62286-106">Use el procedimiento siguiente para habilitar el registro detallado de llamadas (CDR) en toda la organización o en cada sitio de la organización.</span><span class="sxs-lookup"><span data-stu-id="62286-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62286-107">Para poder habilitar el CDR debe configurar la supervisión y una base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="62286-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="62286-108">Para obtener más información, consulte <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="62286-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="62286-109">Para habilitar CDR con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="62286-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="62286-110">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62286-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="62286-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62286-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="62286-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="62286-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="62286-113">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, en **Registro detallado de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="62286-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="62286-114">En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la lista, seleccione **Acción** y, a continuación, haga clic en **Habilitar CDR**.</span><span class="sxs-lookup"><span data-stu-id="62286-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="62286-115">CDR habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="62286-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="62286-116">Habilitación de CDR mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="62286-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="62286-117">Puede habilitar CDR mediante Windows PowerShell y el cmdlet **set-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="62286-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="62286-118">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62286-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="62286-119">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="62286-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="62286-120">Para habilitar CDR para una única ubicación</span><span class="sxs-lookup"><span data-stu-id="62286-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="62286-121">Para deshabilitar CDR, establezca el parámetro EnableCDR en True ($True).</span><span class="sxs-lookup"><span data-stu-id="62286-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="62286-122">Para deshabilitar CDR para una única ubicación</span><span class="sxs-lookup"><span data-stu-id="62286-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="62286-123">Para deshabilitar CDR, establezca el parámetro EnableCDR en False ($False).</span><span class="sxs-lookup"><span data-stu-id="62286-123">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="62286-124">La deshabilitación de CDR no desinstala la supervisión.</span><span class="sxs-lookup"><span data-stu-id="62286-124">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="62286-125">Pausa la recopilación y el almacenamiento de datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="62286-125">It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="62286-126">Utilizar un único comando para habilitar CDR en varias ubicaciones</span><span class="sxs-lookup"><span data-stu-id="62286-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="62286-127">Este comando habilita CDR para todos los parámetros de CDR que se encuentran actualmente en uso en su organización.</span><span class="sxs-lookup"><span data-stu-id="62286-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="62286-128">Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="62286-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62286-129">Consulta también</span><span class="sxs-lookup"><span data-stu-id="62286-129">See Also</span></span>


[<span data-ttu-id="62286-130">Planeación de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62286-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="62286-131">Implementación de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62286-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

