---
title: 'Lync Server 2013: configurar opciones de archivado para un grupo de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25d658eb8a2ada7a7c797406faf5224f134eedc4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502297"
---
# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="70d2a-102">Configuración de opciones de archivado para un grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d2a-102">Configuring Archiving options for a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70d2a-103">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="70d2a-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="70d2a-p101">Puede especificar las opciones de archivado que se aplican a grupos de servidores específicos al crear y configurar las opciones en una configuración de archivado para cada uno de estos grupos de servidores. La configuración de un grupo de servidores anula la configuración global y de sitio, pero únicamente para el grupo de servidores especificad en la configuración del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="70d2a-p101">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="70d2a-106">Para obtener más información sobre cómo funcionan las configuraciones de archivado, incluida la jerarquía para las configuraciones globales, de sitio y de grupo, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, implementación o operaciones.</span><span class="sxs-lookup"><span data-stu-id="70d2a-106">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70d2a-107">Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado.</span><span class="sxs-lookup"><span data-stu-id="70d2a-107">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="70d2a-108">Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="70d2a-108">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="70d2a-109">Para configurar las opciones de archivado en el nivel de grupo</span><span class="sxs-lookup"><span data-stu-id="70d2a-109">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="70d2a-110">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="70d2a-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="70d2a-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70d2a-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="70d2a-112">Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="70d2a-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="70d2a-113">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="70d2a-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="70d2a-114">En la página **Configuración de archivado**, haga clic en **Nuevo** y en **Directiva de grupo**.</span><span class="sxs-lookup"><span data-stu-id="70d2a-114">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="70d2a-115">En **Seleccione un servicio**, seleccione el grupo de servidores que desea configurar para el archivado.</span><span class="sxs-lookup"><span data-stu-id="70d2a-115">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="70d2a-116">En **Nueva configuración de archivado**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="70d2a-116">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="70d2a-117">**Deshabilitar archivado**</span><span class="sxs-lookup"><span data-stu-id="70d2a-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="70d2a-118">**Archivar sesiones de mensajería instantánea**</span><span class="sxs-lookup"><span data-stu-id="70d2a-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="70d2a-119">**Archivar sesiones de MI y conferencias**</span><span class="sxs-lookup"><span data-stu-id="70d2a-119">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="70d2a-120">Además, en la página **Nueva configuración de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70d2a-120">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="70d2a-121">Para bloquear la actividad cuando el archivado no está disponible, active la casilla  \*\*Bloquear las sesiones de mensajería instantánea (MI) o conferencias si se produce algún error en el archivado \*\*.</span><span class="sxs-lookup"><span data-stu-id="70d2a-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="70d2a-122">Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="70d2a-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="70d2a-123">Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="70d2a-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="70d2a-124">Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.</span><span class="sxs-lookup"><span data-stu-id="70d2a-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="70d2a-125">Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.</span><span class="sxs-lookup"><span data-stu-id="70d2a-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="70d2a-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="70d2a-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

