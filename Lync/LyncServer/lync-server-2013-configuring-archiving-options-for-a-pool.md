---
title: 'Lync Server 2013: configuración de las opciones de archivado de un grupo'
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
ms.openlocfilehash: f63f20dc0ae80584c1eac4489a07925e90fe3e29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="4a1bf-102">Configuración de las opciones de archivado de un grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a1bf-102">Configuring Archiving options for a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a1bf-103">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="4a1bf-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="4a1bf-104">Puede especificar las opciones de archivado que se aplicarán a agrupaciones específicas mediante la creación y la configuración de las opciones de una configuración de archivado para cada uno de esos grupos.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-104">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools.</span></span> <span data-ttu-id="4a1bf-105">Una configuración de grupo reemplaza la configuración global y de sitio, pero solo para el grupo especificado en la configuración de grupo.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-105">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="4a1bf-106">Para obtener detalles sobre cómo funcionan las configuraciones de archivado, incluida la jerarquía para las configuraciones globales, de sitio y de grupo, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-106">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a1bf-107">Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-107">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="4a1bf-108">Para obtener información detallada, vea <A href="lync-server-2013-configuring-archiving-options.md">configuración de las opciones de archivado en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-108">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="4a1bf-109">Para configurar las opciones de archivado en el nivel de grupo</span><span class="sxs-lookup"><span data-stu-id="4a1bf-109">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="4a1bf-110">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4a1bf-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="4a1bf-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4a1bf-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4a1bf-113">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="4a1bf-114">En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, haga clic en **Configuración de grupo**.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-114">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="4a1bf-115">En **Seleccionar un servicio**, seleccione el grupo que desea configurar para el archivado.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-115">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="4a1bf-116">En **Nueva configuración de archivado**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4a1bf-116">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="4a1bf-117">**Deshabilitar archivado**</span><span class="sxs-lookup"><span data-stu-id="4a1bf-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="4a1bf-118">**Archivar sesiones de mensajería instantánea (MI)**</span><span class="sxs-lookup"><span data-stu-id="4a1bf-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="4a1bf-119">**Archivar sesiones de mensajería instantánea (MI) y conferencias web**</span><span class="sxs-lookup"><span data-stu-id="4a1bf-119">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="4a1bf-120">Además, en la página **Nueva configuración de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a1bf-120">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="4a1bf-121">Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="4a1bf-122">Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="4a1bf-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="4a1bf-123">Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4a1bf-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="4a1bf-124">Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="4a1bf-125">Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="4a1bf-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4a1bf-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

