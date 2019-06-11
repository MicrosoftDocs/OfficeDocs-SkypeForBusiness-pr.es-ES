---
title: 'Lync Server 2013: eliminar vínculos de la región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a097626f6e5eb5de8e3503baab0f1ab9ce462549
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="b2485-102">Eliminar vínculos de regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2485-102">Deleting network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2485-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b2485-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b2485-104">Puede configurar vínculos entre dos regiones de red como parte de control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="b2485-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="b2485-105">Las regiones dentro de una red están vinculadas a través de la conectividad de red de área extensa (WAN).</span><span class="sxs-lookup"><span data-stu-id="b2485-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="b2485-106">Puede usar el panel de control de Lync Server para eliminar un vínculo existente entre dos regiones de red.</span><span class="sxs-lookup"><span data-stu-id="b2485-106">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="b2485-107">Para obtener más información sobre cómo crear o modificar el vínculo región de red, consulte [configuración de vínculos de regiones de red en Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="b2485-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="b2485-108">Para eliminar un vínculo a una región de red</span><span class="sxs-lookup"><span data-stu-id="b2485-108">To delete a network region link</span></span>

1.  <span data-ttu-id="b2485-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b2485-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b2485-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b2485-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b2485-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b2485-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b2485-112">En la barra de navegación izquierda, haga clic en **configuración de red** y, a continuación, en **vínculo de región**.</span><span class="sxs-lookup"><span data-stu-id="b2485-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="b2485-113">En la página vínculo de la **región** , haga clic en el vínculo de la región que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="b2485-113">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2485-114">Puedes eliminar más de un vínculo de región a la vez.</span><span class="sxs-lookup"><span data-stu-id="b2485-114">You can delete more than one region link at a time.</span></span> <span data-ttu-id="b2485-115">Para ello, presione CTRL y seleccione varios vínculos de región mientras mantiene presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="b2485-115">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="b2485-116">O bien, para seleccionar todos los vínculos de la región, haga clic en <STRONG>seleccionar todo</STRONG> en el menú <STRONG>edición</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="b2485-116">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="b2485-117">En el menú **Editar** , seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="b2485-117">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="b2485-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b2485-118">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2485-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2485-119">See Also</span></span>


[<span data-ttu-id="b2485-120">Configuración de vínculos de regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2485-120">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

