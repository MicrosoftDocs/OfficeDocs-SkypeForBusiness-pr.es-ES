---
title: 'Lync Server 2013: habilitar el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20cd0f7792f8db2cf1b2d817bfe79ed6d6b16fce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="a50c4-102">Habilitar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a50c4-102">Enabling call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a50c4-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a50c4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a50c4-104">El control de admisión de llamadas (CAC) es una red de regiones, sitios y subredes que permiten colocar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible.</span><span class="sxs-lookup"><span data-stu-id="a50c4-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="a50c4-105">Después de configurar la red CAC, debe habilitar CAC para exigir las limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="a50c4-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="a50c4-106">Puede usar el panel de control de Lync Server para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="a50c4-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="a50c4-107">Para habilitar CAC desde el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="a50c4-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a50c4-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="a50c4-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a50c4-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a50c4-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a50c4-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a50c4-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a50c4-111">En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **global**.</span><span class="sxs-lookup"><span data-stu-id="a50c4-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="a50c4-112">En la página **global** , haga clic en la configuración **global** .</span><span class="sxs-lookup"><span data-stu-id="a50c4-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a50c4-113">Solo se puede configurar una red para cualquier implementación de Microsoft Lync Server 2013, por lo que nunca habrá más de una configuración de red en la lista.</span><span class="sxs-lookup"><span data-stu-id="a50c4-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="a50c4-114">No puede cambiar el nombre de la configuración global.</span><span class="sxs-lookup"><span data-stu-id="a50c4-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="a50c4-115">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="a50c4-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="a50c4-116">En la página **Editar configuración global** , active la casilla **Habilitar control de admisión de llamadas** y, a continuación, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a50c4-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="a50c4-117">Al hacer clic en **confirmar**, se ejecuta una prueba de la configuración.</span><span class="sxs-lookup"><span data-stu-id="a50c4-117">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="a50c4-118">Se cerrará el cuadro de diálogo **Editar configuración global** y volverá a la página **global** .</span><span class="sxs-lookup"><span data-stu-id="a50c4-118">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="a50c4-119">Recibirá una advertencia si se detectan errores o incoherencias en la configuración de red que le impedirán que funcione correctamente (por ejemplo, si cada región no está conectada a ninguna otra región a través de una ruta interregion).</span><span class="sxs-lookup"><span data-stu-id="a50c4-119">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="a50c4-120">Si realiza cambios en la configuración de red, puede volver a ejecutar la comprobación de validación abriendo la configuración global y haciendo clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a50c4-120">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="a50c4-121">No es necesario deshabilitar CAC en primer lugar: deje la casilla activada y haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a50c4-121">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="a50c4-122">Puede hacerlo en cualquier momento sin realizar cambios en la configuración.</span><span class="sxs-lookup"><span data-stu-id="a50c4-122">You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a50c4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a50c4-123">See Also</span></span>


[<span data-ttu-id="a50c4-124">Información general sobre el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a50c4-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="a50c4-125">Planear el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a50c4-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="a50c4-126">Configurar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a50c4-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="a50c4-127">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a50c4-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="a50c4-128">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a50c4-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="a50c4-129">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a50c4-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

