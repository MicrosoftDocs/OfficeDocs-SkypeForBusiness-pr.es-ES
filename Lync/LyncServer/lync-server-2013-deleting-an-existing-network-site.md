---
title: 'Lync Server 2013: eliminar un sitio de red existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b9db3328ef79dcbbd95592a7bb3149c3d6f64a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="b5b6f-102">Eliminación de un sitio de red existente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5b6f-102">Deleting an existing network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5b6f-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b5b6f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b5b6f-104">Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="b5b6f-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="b5b6f-105">Puede usar el panel de control de Lync Server 2013 para configurar sitios y asociarlos con regiones.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-105">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="b5b6f-106">Por ejemplo, una región de red para Norteamérica se podría asociar con sitios de red como Chicago, Redmond y Vancouver.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="b5b6f-107">Debe crearse un sitio de red CAC para cada sitio de una organización, incluso aunque no tenga limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="b5b6f-108">En el panel de control de Lync Server, puede crear, modificar y eliminar sitios de red.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="b5b6f-109">Utilice el procedimiento siguiente para eliminar un sitio de red existente.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-109">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="b5b6f-110">Para obtener información detallada sobre cómo crear o modificar sitios de red, vea [crear o modificar sitios de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span><span class="sxs-lookup"><span data-stu-id="b5b6f-110">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="b5b6f-111">Para eliminar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="b5b6f-111">To delete a network site</span></span>

1.  <span data-ttu-id="b5b6f-112">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b5b6f-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b5b6f-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5b6f-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b5b6f-115">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="b5b6f-116">En la página **Sitio**, haga clic en el sitio que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-116">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b5b6f-p103">Puede eliminar más de un sitio en la misma operación. Para hacerlo, pulse CTRL y seleccione varios sitios manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los sitios, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-p103">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="b5b6f-120">En el menú **Editar**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="b5b6f-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-121">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b5b6f-p104">No se puede eliminar un sitio de red si está asociado con la subred de una red. Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error. Para ver si un sitio está asociado con alguna subred, haga clic en el sitio y, a continuación, haga clic en <STRONG>Mostrar detalles</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b5b6f-p104">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

