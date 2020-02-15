---
title: 'Lync Server 2013: creación o modificación de regiones de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04f85e4546d8cfa3154c2fc5a87676ff0377795b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="6c0cb-102">Creación o modificación de regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c0cb-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c0cb-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6c0cb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6c0cb-104">Una región de red interconecta varias partes de una red a través de varias zonas geográficas.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="6c0cb-105">Cada región de red debe asociarse con un sitio central.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="6c0cb-106">El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda de CAC (servicio de control de admisión de llamadas).</span><span class="sxs-lookup"><span data-stu-id="6c0cb-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="6c0cb-107">Puede usar el panel de control de Lync Server para configurar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="6c0cb-108">Las regiones de red incluyen valores de configuración que determinan si se permiten las rutas alterativas a través de Internet para las conexiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="6c0cb-109">Desde el panel de control de Lync Server, puede crear, modificar o eliminar una región de red.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="6c0cb-110">Siga este tema para crear y modificar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="6c0cb-111">Para obtener más información sobre cómo eliminar regiones de red existentes, consulte [eliminar regiones de red existentes en Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="6c0cb-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="6c0cb-112">Para crear una región de red</span><span class="sxs-lookup"><span data-stu-id="6c0cb-112">To create a network region</span></span>

1.  <span data-ttu-id="6c0cb-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6c0cb-114">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6c0cb-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6c0cb-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6c0cb-116">En la barra de navegación izquierda, haga clic en **Configuración de red** y en **Región**.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="6c0cb-117">En la página **Región**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="6c0cb-118">En la página **Región nueva**, escriba un valor en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="6c0cb-119">Este valor debe ser único dentro de la implementación de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="6c0cb-120">En la lista desplegable **Sitio central**, seleccione el sitio central para esta región de red.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="6c0cb-p104">La casilla  \*\*Habilitar ruta alternativa de audio \*\* está activada de forma predeterminada. Este campo determina si las llamadas de audio se enrutarán a través de una ruta de acceso alternativa cuando no exista un ancho de banda adecuado en la ruta de acceso principal. Desactívela solamente si necesita cancelar la descarga de Internet. Si alguna de las llamadas que realice se hará por Internet, esta casilla debe estar marcada, independientemente del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-p104">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="6c0cb-p105">La casilla  \*\*Habilitar ruta alternativa de vídeo \*\* está activada de forma predeterminada. Este campo determina si las llamadas de vídeo se enrutarán a través de una ruta de acceso alternativa cuando no exista un ancho de banda adecuado en la ruta de acceso principal. Desactívela solamente si necesita cancelar la descarga de Internet. Si alguna de las llamadas que realice se hará por Internet, esta casilla debe estar marcada, independientemente del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-p105">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="6c0cb-129">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre esta región aparte de lo que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="6c0cb-130">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-130">Click **Commit**.</span></span>

<span data-ttu-id="6c0cb-131">La tabla **Sitios asociados** no se usa para crear una región de red.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="6c0cb-132">Un sitio se asocia a una región cuando se crea o modifica el sitio.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="6c0cb-133">Para obtener más información, consulte [crear o modificar sitios de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="6c0cb-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="6c0cb-134">Para modificar una región de red</span><span class="sxs-lookup"><span data-stu-id="6c0cb-134">To modify a network region</span></span>

1.  <span data-ttu-id="6c0cb-135">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6c0cb-136">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6c0cb-137">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6c0cb-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6c0cb-138">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Región**.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="6c0cb-139">En la página **Región**, haga clic en el vínculo regional que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="6c0cb-140">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="6c0cb-141">En la página **Editar región**, puede modificar la configuración para habilitar y deshabilitar las rutas alternativas de audio y vídeo y modificar la descripción (para obtener información detallada, consulte la sección "Para crear una sección de red" de más arriba en este tema).</span><span class="sxs-lookup"><span data-stu-id="6c0cb-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="6c0cb-142">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-142">Click **Commit**.</span></span>

<span data-ttu-id="6c0cb-p108">En esta página, no se pueden modificar los **Sitios asociados**. La lista de sitios asociados se proporciona a modo de referencia, de forma que pueda saber los sitios que se verán afectados cuando modifique la configuración de la región.</span><span class="sxs-lookup"><span data-stu-id="6c0cb-p108">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c0cb-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c0cb-145">See Also</span></span>


[<span data-ttu-id="6c0cb-146">Eliminación de regiones de red existentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c0cb-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="6c0cb-147">Configurar regiones de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c0cb-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="6c0cb-148">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6c0cb-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="6c0cb-149">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6c0cb-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="6c0cb-150">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6c0cb-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="6c0cb-151">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6c0cb-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

