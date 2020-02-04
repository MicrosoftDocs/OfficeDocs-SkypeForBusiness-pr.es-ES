---
title: Habilitar o deshabilitar el archivado de mensajes instantáneos o sesiones de conferencia
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
ms.openlocfilehash: be9782bfa73f30fbefaec0a51d91024b3c40ba55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="b81f0-102">Habilitar o deshabilitar el archivado de sesiones de mensajería instantánea o de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b81f0-102">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b81f0-103">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="b81f0-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="b81f0-104">En el panel de control de Lync Server 2013, puede usar las configuraciones de archivado para habilitar y deshabilitar el archivado de mensajes instantáneos, sesiones de conferencia o ambos.</span><span class="sxs-lookup"><span data-stu-id="b81f0-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="b81f0-105">Esto incluye las siguientes configuraciones de archivado:</span><span class="sxs-lookup"><span data-stu-id="b81f0-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="b81f0-106">Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b81f0-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="b81f0-107">Configuraciones de nivel de sitio y de grupo opcionales que puede crear y usar para especificar cómo se implementa el archivado para grupos o sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="b81f0-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="b81f0-108">Inicialmente, debe configurar las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b81f0-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="b81f0-109">Para obtener detalles sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="b81f0-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b81f0-110">Para usar el archivado, debe configurar las directivas de archivado para especificar si desea habilitar el archivado de las comunicaciones internas, de las comunicaciones externas o de ambos para los usuarios alojados en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b81f0-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="b81f0-111">De forma predeterminada, el archivado no está habilitado para las comunicaciones internas o externas.</span><span class="sxs-lookup"><span data-stu-id="b81f0-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="b81f0-112">Antes de habilitar el archivado en cualquier directiva, debe especificar las configuraciones de archivado apropiadas para su implementación y, opcionalmente, para determinados sitios y grupos, tal y como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="b81f0-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="b81f0-113">Para obtener más información sobre cómo habilitar el archivado, vea <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar y asignar directivas de archivado en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="b81f0-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="b81f0-114">Si decide que después de implementar el archivado desea usar la integración de Microsoft Exchange para almacenar datos y archivos en servidores de Exchange 2013 y todos los usuarios están alojados en los servidores de Exchange 2013, debe quitar la configuración de la base de datos de SQL Server desde su topología.</span><span class="sxs-lookup"><span data-stu-id="b81f0-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="b81f0-115">Para ello, debe usar el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="b81f0-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="b81f0-116">Para obtener más información, vea <A href="lync-server-2013-changing-archiving-database-options.md">cambiar las opciones de base de datos de archivado en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="b81f0-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="b81f0-117">Para habilitar o deshabilitar el archivado de mensajes instantáneos o sesiones de conferencia</span><span class="sxs-lookup"><span data-stu-id="b81f0-117">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="b81f0-118">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b81f0-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b81f0-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b81f0-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b81f0-120">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b81f0-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b81f0-121">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="b81f0-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="b81f0-122">Seleccione la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y en **Mostrar detalles**, y luego siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b81f0-122">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="b81f0-123">Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.</span><span class="sxs-lookup"><span data-stu-id="b81f0-123">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="b81f0-124">Para habilitar el archivado para las sesiones de MI y de conferencia, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.</span><span class="sxs-lookup"><span data-stu-id="b81f0-124">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="b81f0-125">A fin de deshabilitar el archivado de la directiva, haga clic en **Deshabilitar archivado**.</span><span class="sxs-lookup"><span data-stu-id="b81f0-125">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="b81f0-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b81f0-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b81f0-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b81f0-127">See Also</span></span>


[<span data-ttu-id="b81f0-128">Administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos</span><span class="sxs-lookup"><span data-stu-id="b81f0-128">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="b81f0-129">Configurar y asignar directivas de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b81f0-129">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

