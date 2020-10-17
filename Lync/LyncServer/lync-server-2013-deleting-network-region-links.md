---
title: 'Lync Server 2013: eliminación de vínculos de región de red'
description: 'Lync Server 2013: eliminación de vínculos de región de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a17c1ec64460e0f7cb447597f94aadd7fd2a9ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545336"
---
# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="ea199-103">Eliminación de vínculos de regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea199-103">Deleting network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea199-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ea199-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ea199-105">Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ea199-105">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="ea199-106">Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN).</span><span class="sxs-lookup"><span data-stu-id="ea199-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="ea199-107">Puede usar el panel de control de Lync Server para eliminar un vínculo existente entre dos regiones de red.</span><span class="sxs-lookup"><span data-stu-id="ea199-107">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="ea199-108">Para obtener información detallada sobre cómo crear o modificar el vínculo de región de red, consulte [configuración de vínculos de región de red en Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="ea199-108">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="ea199-109">Para eliminar un vínculo de región de red</span><span class="sxs-lookup"><span data-stu-id="ea199-109">To delete a network region link</span></span>

1.  <span data-ttu-id="ea199-110">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ea199-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ea199-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea199-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ea199-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ea199-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ea199-113">En la barra de navegación izquierda, haga clic en **Configuración de red** y luego en **Vínculo de región**.</span><span class="sxs-lookup"><span data-stu-id="ea199-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="ea199-114">En la página **Vínculo de región**, haga clic en el vínculo de región que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="ea199-114">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea199-p103">Se pueden eliminar varios vínculos de región a la vez. Para hacerlo, presione CTRL y seleccione varios vínculos de regiones mientras mantiene presionada la tecla CTRL. O, para seleccionar todos los vínculos de región, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ea199-p103">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="ea199-118">En el menú **Editar** seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ea199-118">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="ea199-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ea199-119">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea199-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea199-120">See Also</span></span>


[<span data-ttu-id="ea199-121">Configuración de vínculos de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea199-121">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

