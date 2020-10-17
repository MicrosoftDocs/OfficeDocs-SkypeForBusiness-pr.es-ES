---
title: 'Lync Server 2013: configuración de la directiva global para el archivado'
description: 'Lync Server 2013: configurar la directiva global para el archivado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8f8125f458c4269626e0b1c929f2acb1a8de0b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556866"
---
# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="123f0-103">Configuración de la directiva global para el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="123f0-103">Configuring the global policy for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="123f0-104">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="123f0-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="123f0-105">Cuando se implementan los servidores front-end, Lync Server crea una directiva global para el archivado.</span><span class="sxs-lookup"><span data-stu-id="123f0-105">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="123f0-106">De forma predeterminada, el archivado está deshabilitado en la directiva global.</span><span class="sxs-lookup"><span data-stu-id="123f0-106">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="123f0-107">La directiva global controla si el archivado está habilitado para las comunicaciones internas y externas para toda la implementación, a menos que Configure directivas de sitio o de usuario, que invalidan la directiva global o si usa la integración de Microsoft Exchange para algunos o todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="123f0-107">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="123f0-108">Si usa la integración de Microsoft Exchange, la directiva global no se aplica a los usuarios hospedados en Exchange 2013 y tienen los buzones que se colocan en In-Place en espera.</span><span class="sxs-lookup"><span data-stu-id="123f0-108">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="123f0-109">Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning Documentation, Deployment Documentation o Operations Documentation.</span><span class="sxs-lookup"><span data-stu-id="123f0-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="123f0-110">Si habilita la integración de Microsoft Exchange para su implementación, las directivas de Exchange In-Place retenciones controlan si el archivado está habilitado para los usuarios que están hospedados en Exchange 2013 y que sus buzones se colocan en In-Place suspensión.</span><span class="sxs-lookup"><span data-stu-id="123f0-110">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="123f0-111">Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="123f0-111">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="123f0-112">Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado.</span><span class="sxs-lookup"><span data-stu-id="123f0-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="123f0-113">Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="123f0-113">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="123f0-114">Para configurar la directiva global para el archivado al usar las bases de datos de archivado de Lync Server</span><span class="sxs-lookup"><span data-stu-id="123f0-114">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="123f0-115">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="123f0-115">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="123f0-116">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="123f0-116">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="123f0-117">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="123f0-117">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="123f0-118">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="123f0-118">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="123f0-119">En la página **Directiva de archivado** , haga clic en **global**, en **Editar**y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="123f0-119">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="123f0-120">En **Editar directiva de archivado - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="123f0-120">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="123f0-121">En **nombre**, si no desea usar el nombre predeterminado global, especifique un nuevo nombre para la directiva global.</span><span class="sxs-lookup"><span data-stu-id="123f0-121">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="123f0-122">En **Descripción**, proporcione información sobre la Directiva (por ejemplo, directiva global para *divisionName*).</span><span class="sxs-lookup"><span data-stu-id="123f0-122">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="123f0-123">Para controlar el archivado de las comunicaciones internas de todos los usuarios y sitios que no se controlan específicamente mediante una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="123f0-123">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="123f0-124">Para controlar el archivado de comunicaciones externas para todos los sitios y usuarios que no se controlan específicamente mediante una directiva de sitio o de usuario, Active o desactive la casilla **archivar comunicaciones externas** .</span><span class="sxs-lookup"><span data-stu-id="123f0-124">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="123f0-125">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="123f0-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

