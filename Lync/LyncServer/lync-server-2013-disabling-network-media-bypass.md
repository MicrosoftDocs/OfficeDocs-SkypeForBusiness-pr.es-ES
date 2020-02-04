---
title: 'Lync Server 2013: deshabilitar la omisión de medios de red'
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
ms.openlocfilehash: 0457281a743d317e17a5fd0728e1a747b4d88271
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="97cf5-102">Deshabilitar la omisión de medios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97cf5-102">Disabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97cf5-103">_**Última modificación del tema:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="97cf5-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="97cf5-104">La configuración de omisión de medios se aplica globalmente en una implementación de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97cf5-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="97cf5-105">La omisión de medios permite que las llamadas omitan el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="97cf5-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="97cf5-106">Para obtener información sobre Cuándo usar la omisión de medios, consulte [planificación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la sección planificación. Puede deshabilitar la omisión de medios en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97cf5-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="97cf5-107">Para obtener más información sobre cómo habilitar y configurar el bypass medial, consulte [Habilitar el omisión de medios de red en Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="97cf5-107">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="97cf5-108">Para deshabilitar la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="97cf5-108">To disable media bypass</span></span>

1.  <span data-ttu-id="97cf5-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="97cf5-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="97cf5-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97cf5-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="97cf5-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="97cf5-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="97cf5-112">En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **global**.</span><span class="sxs-lookup"><span data-stu-id="97cf5-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="97cf5-113">En la página **global** , haga clic en la configuración **global** .</span><span class="sxs-lookup"><span data-stu-id="97cf5-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="97cf5-114">Siempre hay una sola configuración y siempre se denomina global.</span><span class="sxs-lookup"><span data-stu-id="97cf5-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="97cf5-115">En el menú **Editar** , haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="97cf5-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="97cf5-116">En la página **Editar configuración global** , desactive la casilla **Habilitar omisión de medios** .</span><span class="sxs-lookup"><span data-stu-id="97cf5-116">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="97cf5-117">Haga clic en **confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="97cf5-117">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="97cf5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="97cf5-118">See Also</span></span>


[<span data-ttu-id="97cf5-119">Habilitar el omisión de medios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97cf5-119">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

