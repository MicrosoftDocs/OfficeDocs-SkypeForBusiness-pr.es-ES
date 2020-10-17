---
title: 'Lync Server 2013: configurar opciones de archivado para un sitio'
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
ms.openlocfilehash: 9a4e1a6480102c9cc4fe13e2cf651e0ab14bae7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502277"
---
# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="af063-102">Configurar las opciones de archivado para un sitio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af063-102">Configuring Archiving options for a site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af063-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="af063-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="af063-104">Puede especificar las opciones de archivado que se aplicarán a sitios específicos creando y configurando opciones en una configuración de archivado para cada uno de esos sitios.</span><span class="sxs-lookup"><span data-stu-id="af063-104">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites.</span></span> <span data-ttu-id="af063-105">Una configuración de sitio invalida la configuración global, pero solo para el sitio especificado en la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="af063-105">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> <span data-ttu-id="af063-106">Las configuraciones de grupo invalidan las configuraciones de sitio</span><span class="sxs-lookup"><span data-stu-id="af063-106">Pool configurations override site configurations</span></span>

<span data-ttu-id="af063-107">Para obtener más información sobre cómo funcionan las configuraciones de archivado, incluida la jerarquía para las configuraciones globales, de sitio y de grupo, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, implementación o operaciones.</span><span class="sxs-lookup"><span data-stu-id="af063-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af063-108">Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado.</span><span class="sxs-lookup"><span data-stu-id="af063-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af063-109">Para habilitar el archivado, debe especificar las directivas de archivado para controlar el archivado de las comunicaciones internas y externas a nivel global y, si procede, en los niveles de sitio y usuario.</span><span class="sxs-lookup"><span data-stu-id="af063-109">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="af063-110">Si configura directivas de nivel de usuario, también debe asignar las directivas de usuario a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="af063-110">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="af063-111">Para obtener más información sobre cómo crear y configurar las directivas de archivado, consulte <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing The external and external Communications in Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="af063-111">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="af063-112">Para configurar las opciones de archivado en el nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="af063-112">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="af063-113">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="af063-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="af063-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af063-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="af063-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="af063-115">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="af063-116">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="af063-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="af063-117">En la página **configuración de archivado** , haga clic en **nuevo**y, a continuación, haga clic en **configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="af063-117">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="af063-118">En **Seleccionar un sitio**, seleccione el sitio que debe configurarse para el archivado.</span><span class="sxs-lookup"><span data-stu-id="af063-118">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="af063-119">En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="af063-119">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="af063-120">Para habilitar el archivado solo para las sesiones de mensajería instantánea, haga clic en **Archivar sesiones de mensajería instantánea**.</span><span class="sxs-lookup"><span data-stu-id="af063-120">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="af063-121">Para habilitar el archivado de sesiones de mensajería instantánea y conferencias, haga clic en **archivar sesiones de mensajería instantánea y conferencias web**.</span><span class="sxs-lookup"><span data-stu-id="af063-121">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="af063-122">Para deshabilitar el archivado para la directiva, haga clic en **Deshabilitar archivado**.</span><span class="sxs-lookup"><span data-stu-id="af063-122">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="af063-123">Además, en **Nueva configuración de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af063-123">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="af063-124">Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.</span><span class="sxs-lookup"><span data-stu-id="af063-124">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="af063-125">Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="af063-125">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="af063-126">Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="af063-126">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="af063-127">Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.</span><span class="sxs-lookup"><span data-stu-id="af063-127">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="af063-128">Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.</span><span class="sxs-lookup"><span data-stu-id="af063-128">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="af063-129">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="af063-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

