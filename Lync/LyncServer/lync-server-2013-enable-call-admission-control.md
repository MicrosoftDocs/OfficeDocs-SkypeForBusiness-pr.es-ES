---
title: 'Lync Server 2013: habilitar el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e129e109a62006d72b8b1db44c28effa8911e6c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528767"
---
# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="82006-102">Habilitar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82006-102">Enable call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82006-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="82006-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="82006-104">Después de configurar las opciones de red para la implementación del control de admisión de llamadas, debe habilitar el CAC para que se apliquen las directivas de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="82006-104">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="82006-105">Para obtener más información, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="82006-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="82006-106">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="82006-106">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="82006-107">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="82006-107">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="82006-108">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="82006-108">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="82006-109">Para habilitar el control de admisión de llamadas usando el shell de administración</span><span class="sxs-lookup"><span data-stu-id="82006-109">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="82006-110">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="82006-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="82006-p101">Ejecute el cmdlet Set-CsNetworkConfiguration para habilitar el CAC en su red. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="82006-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="82006-113">Si desea deshabilitar el CAC en la red, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="82006-113">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="82006-114">Para habilitar el control de admisión de llamadas usando el Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="82006-114">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="82006-115">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82006-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="82006-116">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="82006-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="82006-117">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="82006-117">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="82006-118">Haga clic en el botón de navegación **Global**.</span><span class="sxs-lookup"><span data-stu-id="82006-118">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="82006-119">Haga clic en **Global** en la lista y, a continuación, seleccione **Mostrar detalles** en el menú **Edición**.</span><span class="sxs-lookup"><span data-stu-id="82006-119">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="82006-120">En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="82006-120">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82006-121">Si desea deshabilitar el control de admisión de llamadas en toda la implementación, desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="82006-121">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="82006-122">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="82006-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

