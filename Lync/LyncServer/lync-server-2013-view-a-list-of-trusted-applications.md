---
title: 'Lync Server 2013: ver una lista de aplicaciones de confianza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8678ed12269f7f78d6d169b518e7f1208d92a7fd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="70e32-102">Ver una lista de aplicaciones de confianza en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70e32-102">View a list of trusted applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70e32-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="70e32-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="70e32-104">Puede usar el panel de control de Lync Server 2013 para ver una lista de las aplicaciones de confianza que ha implementado en su entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70e32-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="70e32-105">Una aplicación de confianza es una aplicación basada en el SDK de Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK en el que se confía en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70e32-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="70e32-106">Esta relación de confianza se resume en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="70e32-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="70e32-107">Las aplicaciones de confianza no son desafiadas para la autenticación por parte de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70e32-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="70e32-108">Lync Server no limita las aplicaciones de confianza para las transacciones SIP, las conexiones o las llamadas salientes del Protocolo de voz sobre Internet (VoIP).</span><span class="sxs-lookup"><span data-stu-id="70e32-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="70e32-109">Las aplicaciones de confianza pueden suplantar a cualquier usuario y pueden unirse a conferencias sin que aparezcan en las listas.</span><span class="sxs-lookup"><span data-stu-id="70e32-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="70e32-110">Las aplicaciones de confianza tienen alta disponibilidad y resistencia.</span><span class="sxs-lookup"><span data-stu-id="70e32-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="70e32-111">En el panel de control de Lync Server, puede ver el nombre de las aplicaciones, el grupo de servidores donde se ejecutan y el puerto que usan.</span><span class="sxs-lookup"><span data-stu-id="70e32-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="70e32-112">Para ver una lista de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="70e32-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="70e32-113">Desde una cuenta de usuario asignada al rol CsServerAdministrator, CsAdministrator, CsHelpDesk, o CsViewOnlyAdministrator , inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="70e32-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="70e32-114">Para obtener más información sobre los roles administrativos predefinidos disponibles en Lync Server 2013, vea [planeación del control de acceso basado en roles en Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="70e32-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="70e32-115">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70e32-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="70e32-116">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="70e32-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="70e32-117">En la barra de navegación izquierda, haga clic en **topología** y en **aplicación de confianza**.</span><span class="sxs-lookup"><span data-stu-id="70e32-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="70e32-118">En la página **aplicación de confianza** , haga clic en un encabezado de columna para ordenar las aplicaciones, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="70e32-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70e32-119">Consulta también</span><span class="sxs-lookup"><span data-stu-id="70e32-119">See Also</span></span>


[<span data-ttu-id="70e32-120">Administración de la topología de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70e32-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

