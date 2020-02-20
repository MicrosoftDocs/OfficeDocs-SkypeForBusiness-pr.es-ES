---
title: 'Lync Server 2013: eliminar regiones de red existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b94b3614dcf2b09ab96b2deede70554f1d3e6f50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="bdec0-102">Eliminación de regiones de red existentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdec0-102">Deleting existing network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdec0-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bdec0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bdec0-104">Una región de red interconecta varias partes de una red a través de varias zonas geográficas.</span><span class="sxs-lookup"><span data-stu-id="bdec0-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="bdec0-105">Cada región de red debe asociarse con un sitio central.</span><span class="sxs-lookup"><span data-stu-id="bdec0-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="bdec0-106">El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda de CAC (servicio de control de admisión de llamadas).</span><span class="sxs-lookup"><span data-stu-id="bdec0-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="bdec0-107">Puede usar el panel de control de Lync Server para configurar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="bdec0-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="bdec0-108">Las regiones de red incluyen valores de configuración que determinan si se permiten las rutas alterativas a través de Internet para las conexiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="bdec0-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="bdec0-109">Desde el panel de control de Lync Server, puede crear, modificar o eliminar una región de red.</span><span class="sxs-lookup"><span data-stu-id="bdec0-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="bdec0-110">Use este tema para eliminar regiones de red existentes.</span><span class="sxs-lookup"><span data-stu-id="bdec0-110">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="bdec0-111">Para obtener información detallada acerca de la creación o modificación de regiones de red existentes, consulte [creación o modificación de regiones de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="bdec0-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="bdec0-112">Para eliminar una región de red:</span><span class="sxs-lookup"><span data-stu-id="bdec0-112">To delete a network region</span></span>

1.  <span data-ttu-id="bdec0-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="bdec0-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bdec0-114">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bdec0-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bdec0-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bdec0-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bdec0-116">En la barra de navegación izquierda, haga clic en **Configuración de red** y en **Región**.</span><span class="sxs-lookup"><span data-stu-id="bdec0-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="bdec0-117">En la página **Región**, haga clic en la región que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="bdec0-117">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bdec0-p103">Si lo desea, puede eliminar varias regiones en la misma operación. Para ello, presione Ctrl y seleccione varias regiones mientras mantiene presionada esta tecla. O bien, para seleccionar todas las regiones, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bdec0-p103">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="bdec0-121">En el menú **Editar**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="bdec0-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="bdec0-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bdec0-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="bdec0-p104">No se puede quitar una región si está asociada a un sitio de red. Si lo intenta, recibirá un mensaje de error. Para ver si una región está asociada a algún sitio, seleccione la región y haga clic en <STRONG>Mostrar detalles</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bdec0-p104">A network region cannot be removed if it is associated with a network site. If you attempt to remove a region associated with a site you will receive an error message. To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bdec0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdec0-126">See Also</span></span>


[<span data-ttu-id="bdec0-127">Creación o modificación de regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdec0-127">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

