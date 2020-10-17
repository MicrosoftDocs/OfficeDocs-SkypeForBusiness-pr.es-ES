---
title: Habilitar o deshabilitar el archivado de sesiones de mensajería instantánea o de conferencia
description: Habilitar o deshabilitar el archivado de sesiones de mensajería instantánea o de conferencia.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9861024bbd4f4a1558287139a37559f782fcf008
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546536"
---
# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="5bc30-103">Habilitar o deshabilitar el archivado de sesiones de mensajería instantánea o de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bc30-103">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bc30-104">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="5bc30-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="5bc30-105">En el panel de control de Lync Server 2013, se usan configuraciones de archivado para habilitar y deshabilitar el archivado de mensajería instantánea, sesiones de conferencia o ambos.</span><span class="sxs-lookup"><span data-stu-id="5bc30-105">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="5bc30-106">Esto incluye las siguientes configuraciones de archivado:</span><span class="sxs-lookup"><span data-stu-id="5bc30-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="5bc30-107">Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5bc30-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="5bc30-108">Unas configuraciones en el nivel de sitio y de grupo que se pueden crear y usar para especificar cómo se implementa el archivado en sitios o grupos determinados.</span><span class="sxs-lookup"><span data-stu-id="5bc30-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="5bc30-109">Las configuraciones de archivado se instalan inicialmente al implementar el archivado, pero podrá cambiar, agregar y eliminar las configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="5bc30-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="5bc30-110">Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="5bc30-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5bc30-111">Para usar el archivado, debe configurar las directivas de archivado para especificar si desea habilitar el archivado para las comunicaciones internas, para las comunicaciones externas o para los usuarios hospedados en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5bc30-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="5bc30-112">De forma predeterminada, el archivado no está habilitado ni para la comunicación interna ni para la externa.</span><span class="sxs-lookup"><span data-stu-id="5bc30-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="5bc30-113">Antes de habilitar el archivado en las directivas, debe especificar la configuración de archivado pertinente para su implementación y, de manera opcional, para sitios y grupos específicos, como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="5bc30-113">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="5bc30-114">Para obtener más información sobre cómo habilitar el archivado, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuración y asignación de directivas de archivado en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="5bc30-114">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="5bc30-115">Si decide que después de implementar el archivado desea usar la integración de Microsoft Exchange para almacenar los datos y archivos de archivado en servidores de Exchange 2013 y que todos los usuarios estén hospedados en los servidores de Exchange 2013, debe quitar la configuración de la base de datos de SQL Server de la topología.</span><span class="sxs-lookup"><span data-stu-id="5bc30-115">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="5bc30-116">Debe usar el generador de topologías para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="5bc30-116">You must use Topology Builder to do this.</span></span> <span data-ttu-id="5bc30-117">Para obtener más información, consulte <A href="lync-server-2013-changing-archiving-database-options.md">cambiar las opciones de base de datos de archivado en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="5bc30-117">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="5bc30-118">Procedimiento para habilitar o deshabilitar el archivado de sesiones de MI o de conferencia</span><span class="sxs-lookup"><span data-stu-id="5bc30-118">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="5bc30-119">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5bc30-119">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5bc30-120">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5bc30-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5bc30-121">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5bc30-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5bc30-122">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="5bc30-122">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="5bc30-123">Seleccione la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y en **Mostrar detalles**, y luego siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5bc30-123">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="5bc30-124">Para habilitar el archivado solamente para las sesiones de MI, haga clic en **Archivar sesiones de mensajería instantánea**.</span><span class="sxs-lookup"><span data-stu-id="5bc30-124">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="5bc30-125">Para habilitar el archivado para las sesiones de mensajería instantánea y para las conferencias, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.</span><span class="sxs-lookup"><span data-stu-id="5bc30-125">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="5bc30-126">Para deshabilitar el archivado para la directiva, haga clic en **Deshabilitar archivado**.</span><span class="sxs-lookup"><span data-stu-id="5bc30-126">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="5bc30-127">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5bc30-127">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5bc30-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5bc30-128">See Also</span></span>


[<span data-ttu-id="5bc30-129">Administración de las opciones de configuración de archivado en Lync Server 2013 para la organización, los sitios y los grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="5bc30-129">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="5bc30-130">Configuración y asignación de directivas de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bc30-130">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

