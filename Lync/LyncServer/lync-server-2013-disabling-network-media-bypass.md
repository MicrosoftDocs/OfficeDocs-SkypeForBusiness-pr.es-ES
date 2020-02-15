---
title: 'Lync Server 2013: deshabilitar el desvío de medios de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58bf551f94bc6b3ba919437730841f54dd01e291
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="7fe3d-102">Deshabilitar el desvío de medios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fe3d-102">Disabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fe3d-103">_**Última modificación del tema:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="7fe3d-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="7fe3d-104">La configuración del desvío de medios se aplica globalmente en una implementación de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7fe3d-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="7fe3d-105">Con el desvío de medios, las llamadas pueden omitir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="7fe3d-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="7fe3d-106">Para obtener información detallada sobre Cuándo usar la omisión de medios, consulte [planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la sección planeación. Puede deshabilitar la omisión de medios en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7fe3d-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="7fe3d-107">Para obtener más información sobre cómo habilitar y configurar la omisión de datos, consulte [Habilitar el desvío de medios de red en Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="7fe3d-107">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="7fe3d-108">Para deshabilitar el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="7fe3d-108">To disable media bypass</span></span>

1.  <span data-ttu-id="7fe3d-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="7fe3d-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7fe3d-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7fe3d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7fe3d-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7fe3d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7fe3d-112">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Global**.</span><span class="sxs-lookup"><span data-stu-id="7fe3d-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="7fe3d-p103">En la página **Global**, haga clic en la configuración **Global**. En todos los casos hay solo una configuración y siempre se llama Global.</span><span class="sxs-lookup"><span data-stu-id="7fe3d-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="7fe3d-115">En el menú **Editar**, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="7fe3d-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="7fe3d-116">En la página  \*\*Editar configuración global \*\*, desactive la casilla  \*\*Habilitar desvío de medios \*\*.</span><span class="sxs-lookup"><span data-stu-id="7fe3d-116">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="7fe3d-117">Haga clic en  \*\*Confirmar \*\* para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="7fe3d-117">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7fe3d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fe3d-118">See Also</span></span>


[<span data-ttu-id="7fe3d-119">Habilitación del desvío de medios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fe3d-119">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

