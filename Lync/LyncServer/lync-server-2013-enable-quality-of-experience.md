---
title: 'Lync Server 2013: habilitar la calidad de la experiencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dbccfd145ad8143edab10f92a10901e626075e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="9412b-102">Habilitar la calidad de la experiencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9412b-102">Enable Quality of Experience in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9412b-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9412b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9412b-104">La calidad de la experiencia (QoE) registra datos numéricos que indican la calidad de los medios e información sobre los participantes, nombres de los dispositivos, controladores, direcciones IP y tipos de extremos que se usan en las llamadas y las sesiones.</span><span class="sxs-lookup"><span data-stu-id="9412b-104">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="9412b-105">Para obtener más información, vea [planeación de la supervisión en Lync Server 2013](lync-server-2013-planning-for-monitoring.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="9412b-105">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="9412b-106">Para habilitar QoE en toda la organización o en cada uno de sus sitios, realice el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="9412b-106">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9412b-107">Para habilitar QoE, en primer lugar necesita instalar el Servidor de supervisión y conectarlo a una base de datos back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="9412b-107">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="9412b-108">Para obtener más información, consulte <A href="lync-server-2013-deploying-monitoring.md">implementación de la supervisión en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9412b-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="9412b-109">Para habilitar QoE mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="9412b-109">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9412b-110">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9412b-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="9412b-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9412b-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9412b-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9412b-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9412b-113">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.</span><span class="sxs-lookup"><span data-stu-id="9412b-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="9412b-114">En la página **Datos de calidad de la experiencia**, haga clic en la colección adecuada de la tabla, en **Acción** y en **Habilitar QoE**.</span><span class="sxs-lookup"><span data-stu-id="9412b-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9412b-115">Habilitar QoE con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9412b-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9412b-116">Para habilitar a QoE, puede usar Windows PowerShell y el cmdlet **set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9412b-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="9412b-117">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9412b-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9412b-118">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="9412b-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="9412b-119">Para habilitar QoE para una sola ubicación:</span><span class="sxs-lookup"><span data-stu-id="9412b-119">To enable QoE for a single location</span></span>

  - <span data-ttu-id="9412b-120">Para habilitar QoE, defina el parámetro EnableQoE en True ($True).</span><span class="sxs-lookup"><span data-stu-id="9412b-120">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="9412b-121">Para deshabilitar QoE para una ubicación única:</span><span class="sxs-lookup"><span data-stu-id="9412b-121">To disable QoE for a single location</span></span>

  - <span data-ttu-id="9412b-p105">Para deshabilitar QoE, establezca el parámetro EnableQoE en False ($False). Así no se desinstala la supervisión. Se detiene la recopilación y el almacenaje de los datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="9412b-p105">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="9412b-125">Para habilitar QoE en varias ubicaciones con un comando único:</span><span class="sxs-lookup"><span data-stu-id="9412b-125">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="9412b-126">Este comando habilita QoE para todos los valores de configuración de QoE que se usan actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="9412b-126">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="9412b-127">Para obtener más información, consulte [set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="9412b-127">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9412b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9412b-128">See Also</span></span>


[<span data-ttu-id="9412b-129">Planeamiento de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9412b-129">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="9412b-130">Implementación de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9412b-130">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

