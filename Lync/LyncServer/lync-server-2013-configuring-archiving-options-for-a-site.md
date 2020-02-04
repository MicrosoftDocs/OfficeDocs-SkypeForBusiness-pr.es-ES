---
title: 'Lync Server 2013: configuración de las opciones de archivado de un sitio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb2b70242388ca00a7bf43ec535ae1231fb77644
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="64bbb-102">Configuración de las opciones de archivado de un sitio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64bbb-102">Configuring Archiving options for a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64bbb-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="64bbb-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="64bbb-104">Puede especificar las opciones de archivado que se aplicarán a sitios específicos mediante la creación y la configuración de las opciones de una configuración de archivado para cada uno de esos sitios.</span><span class="sxs-lookup"><span data-stu-id="64bbb-104">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites.</span></span> <span data-ttu-id="64bbb-105">Una configuración de sitio reemplaza la configuración global, pero solo para el sitio especificado en la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="64bbb-105">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> <span data-ttu-id="64bbb-106">Las configuraciones de grupo invalidan las configuraciones del sitio</span><span class="sxs-lookup"><span data-stu-id="64bbb-106">Pool configurations override site configurations</span></span>

<span data-ttu-id="64bbb-107">Para obtener detalles sobre cómo funcionan las configuraciones de archivado, incluida la jerarquía para las configuraciones globales, de sitio y de grupo, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="64bbb-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64bbb-108">Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado.</span><span class="sxs-lookup"><span data-stu-id="64bbb-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="64bbb-109">Para habilitar el archivado, es necesario especificar directivas de archivado para controlar el archivado de comunicaciones internas y externas en el nivel global y, si es adecuado, en los niveles de sitio y usuario.</span><span class="sxs-lookup"><span data-stu-id="64bbb-109">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="64bbb-110">Si configura directivas de nivel de usuario, también deberá asignar directivas a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="64bbb-110">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="64bbb-111">Para obtener más información sobre cómo crear y configurar directivas de archivado, vea <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">administrar el archivado de comunicaciones internas y externas en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="64bbb-111">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="64bbb-112">Para configurar las opciones de archivado en el nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="64bbb-112">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="64bbb-113">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="64bbb-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="64bbb-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64bbb-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="64bbb-115">Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="64bbb-115">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="64bbb-116">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="64bbb-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="64bbb-117">En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, en **Configuración de sitio**.</span><span class="sxs-lookup"><span data-stu-id="64bbb-117">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="64bbb-118">En **Seleccionar un sitio**, seleccione el sitio que necesita configurar para el archivado.</span><span class="sxs-lookup"><span data-stu-id="64bbb-118">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="64bbb-119">En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="64bbb-119">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="64bbb-120">Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.</span><span class="sxs-lookup"><span data-stu-id="64bbb-120">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="64bbb-121">Para habilitar el archivado tanto para las sesiones de mensajería instantánea (MI) y las conferencias, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.</span><span class="sxs-lookup"><span data-stu-id="64bbb-121">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="64bbb-122">A fin de deshabilitar el archivado de la directiva, haga clic en **Deshabilitar archivado**.</span><span class="sxs-lookup"><span data-stu-id="64bbb-122">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="64bbb-123">Además, en **Nueva configuración de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="64bbb-123">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="64bbb-124">Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.</span><span class="sxs-lookup"><span data-stu-id="64bbb-124">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="64bbb-125">Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="64bbb-125">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="64bbb-126">Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="64bbb-126">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="64bbb-127">Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.</span><span class="sxs-lookup"><span data-stu-id="64bbb-127">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="64bbb-128">Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.</span><span class="sxs-lookup"><span data-stu-id="64bbb-128">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="64bbb-129">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="64bbb-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

