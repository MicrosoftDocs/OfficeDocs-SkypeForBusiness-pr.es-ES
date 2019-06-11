---
title: 'Lync Server 2013: crear o modificar regiones de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3ca5d44fd2278ffee8a3e9dd4494575cc64c65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="e924d-102">Crear o modificar regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e924d-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e924d-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e924d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e924d-104">Una región de red interconecta varias partes de una red en varias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="e924d-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="e924d-105">Cada región de la red debe estar asociada con un sitio central.</span><span class="sxs-lookup"><span data-stu-id="e924d-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="e924d-106">El sitio central es el sitio del centro de datos en el que se está ejecutando el servicio de directivas de ancho de banda de control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="e924d-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="e924d-107">Puede usar el panel de control de Lync Server para configurar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="e924d-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="e924d-108">Las regiones de red incluyen opciones que determinan si se permiten rutas alternativas a través de Internet para conexiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="e924d-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="e924d-109">En el panel de control de Lync Server, puede crear, modificar o eliminar una región de red.</span><span class="sxs-lookup"><span data-stu-id="e924d-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="e924d-110">Use este tema para crear y modificar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="e924d-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="e924d-111">Para obtener más información sobre cómo eliminar regiones de red existentes, consulte [eliminar regiones de red existentes en Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="e924d-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="e924d-112">Para crear una región de red</span><span class="sxs-lookup"><span data-stu-id="e924d-112">To create a network region</span></span>

1.  <span data-ttu-id="e924d-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e924d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e924d-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e924d-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e924d-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e924d-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e924d-116">En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **región**.</span><span class="sxs-lookup"><span data-stu-id="e924d-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="e924d-117">En la página **región** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e924d-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="e924d-118">En la página **nueva región** , escriba un valor en el campo **nombre** .</span><span class="sxs-lookup"><span data-stu-id="e924d-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="e924d-119">Este valor debe ser único dentro de la implementación de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e924d-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="e924d-120">En la lista desplegable **sitio central** , seleccione el sitio central de esta región de red.</span><span class="sxs-lookup"><span data-stu-id="e924d-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="e924d-121">La casilla de verificación **Habilitar ruta alternativa de audio** está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e924d-121">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="e924d-122">Este campo determina si las llamadas de audio se redirigirán a través de una ruta de acceso alternativa si el ancho de banda adecuado no existe en la ruta de acceso principal.</span><span class="sxs-lookup"><span data-stu-id="e924d-122">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="e924d-123">Desactive esta casilla solo si necesita desactivar la descarga en Internet.</span><span class="sxs-lookup"><span data-stu-id="e924d-123">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="e924d-124">Si cualquiera de las llamadas va a ser de Internet, esta casilla debe estar activada, independientemente de la configuración del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="e924d-124">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="e924d-125">La casilla de verificación **Habilitar ruta alternativa de vídeo** está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e924d-125">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="e924d-126">Este campo determina si las videollamadas se redirigirán a través de una ruta alternativa si el ancho de banda adecuado no existe en la ruta de acceso principal.</span><span class="sxs-lookup"><span data-stu-id="e924d-126">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="e924d-127">Desactive esta casilla solo si necesita desactivar la descarga en Internet.</span><span class="sxs-lookup"><span data-stu-id="e924d-127">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="e924d-128">Si cualquiera de las llamadas va a ser de Internet, esta casilla debe estar activada, independientemente de la configuración del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="e924d-128">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="e924d-129">Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre esta región que no puede expresarse solo por el nombre.</span><span class="sxs-lookup"><span data-stu-id="e924d-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="e924d-130">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e924d-130">Click **Commit**.</span></span>

<span data-ttu-id="e924d-131">La tabla de **sitios asociados** no se usa para crear una región de red.</span><span class="sxs-lookup"><span data-stu-id="e924d-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="e924d-132">Al crear o modificar el sitio, se asocia un sitio con una región.</span><span class="sxs-lookup"><span data-stu-id="e924d-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="e924d-133">Para obtener más información, vea [crear o modificar sitios de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="e924d-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="e924d-134">Para modificar una región de red</span><span class="sxs-lookup"><span data-stu-id="e924d-134">To modify a network region</span></span>

1.  <span data-ttu-id="e924d-135">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e924d-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e924d-136">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e924d-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e924d-137">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e924d-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e924d-138">En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **región**.</span><span class="sxs-lookup"><span data-stu-id="e924d-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="e924d-139">En la página **región** , haga clic en la región que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="e924d-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="e924d-140">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e924d-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e924d-141">En la página **Editar región** , puede modificar la configuración para habilitar y deshabilitar rutas de audio y vídeo alternativas, y cambiar la descripción (para obtener información detallada, consulte la sección "para crear una región de red" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="e924d-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="e924d-142">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e924d-142">Click **Commit**.</span></span>

<span data-ttu-id="e924d-143">No puede modificar los **sitios asociados** en esta página.</span><span class="sxs-lookup"><span data-stu-id="e924d-143">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="e924d-144">La lista de sitios asociados se proporciona como referencia para que usted sepa qué sitios se verán afectados al modificar la configuración de la región.</span><span class="sxs-lookup"><span data-stu-id="e924d-144">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e924d-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="e924d-145">See Also</span></span>


[<span data-ttu-id="e924d-146">Eliminar regiones de red existentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e924d-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="e924d-147">Configurar regiones de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e924d-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="e924d-148">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e924d-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="e924d-149">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e924d-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="e924d-150">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e924d-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="e924d-151">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e924d-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

