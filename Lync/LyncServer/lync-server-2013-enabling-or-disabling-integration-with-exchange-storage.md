---
title: 'Lync Server 2013: habilitar o deshabilitar la integración con el almacenamiento de Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc219e06e0d9bb6f7d76d4d08aef991c525b3aaf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a><span data-ttu-id="f7b0c-102">Habilitación o deshabilitación de la integración de Lync Server 2013 con almacenamiento de Exchange</span><span class="sxs-lookup"><span data-stu-id="f7b0c-102">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7b0c-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="f7b0c-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="f7b0c-104">En el panel de control de Lync Server 2013, se usan configuraciones de archivado para habilitar y deshabilitar la integración con el almacenamiento de Exchange.</span><span class="sxs-lookup"><span data-stu-id="f7b0c-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable integration with Exchange storage.</span></span> <span data-ttu-id="f7b0c-105">Esto incluye las siguientes configuraciones de archivado:</span><span class="sxs-lookup"><span data-stu-id="f7b0c-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="f7b0c-106">Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f7b0c-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="f7b0c-107">Unas configuraciones en el nivel de sitio y de grupo que se pueden crear y usar para especificar cómo se implementa el archivado en sitios o grupos determinados.</span><span class="sxs-lookup"><span data-stu-id="f7b0c-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="f7b0c-108">Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="f7b0c-108">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="f7b0c-109">Para habilitar o deshabilitar la integración con el almacenamiento de Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="f7b0c-109">To enable or disable integration with Microsoft Exchange storage</span></span>

1.  <span data-ttu-id="f7b0c-110">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f7b0c-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f7b0c-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f7b0c-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f7b0c-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f7b0c-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f7b0c-113">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="f7b0c-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="f7b0c-114">Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada de la lista de configuraciones de archivado, en **Editar** y en **Mostrar detalles**. A continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7b0c-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="f7b0c-115">Para habilitar la integración con el almacenamiento de Exchange 2013, active la casilla de verificación **integración de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="f7b0c-115">To enable integration with Exchange 2013 storage, select the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="f7b0c-116">Para deshabilitar la integración con el almacenamiento de Exchange 2013, desactive la casilla de verificación **integración de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="f7b0c-116">To disable integration with Exchange 2013 storage, clear the **Microsoft Exchange integration** check box.</span></span>

5.  <span data-ttu-id="f7b0c-117">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f7b0c-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7b0c-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="f7b0c-118">See Also</span></span>


[<span data-ttu-id="f7b0c-119">Cómo funciona el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7b0c-119">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="f7b0c-120">Administración de las opciones de configuración de archivado en Lync Server 2013 para la organización, los sitios y los grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="f7b0c-120">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

