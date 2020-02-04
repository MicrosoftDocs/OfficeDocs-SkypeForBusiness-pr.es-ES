---
title: 'Fase 4: combinar topologías'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 4: Merge topologies'
ms:assetid: 81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205044(v=OCS.15)
ms:contentKeyID: 48184668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624bbfa52c5d4ed963fda895e7af3a544f0f3733
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-4-merge-topologies"></a><span data-ttu-id="6f313-102">Fase 4: combinar topologías</span><span class="sxs-lookup"><span data-stu-id="6f313-102">Phase 4: Merge topologies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f313-103">_**Última modificación del tema:** 2012-03-29_</span><span class="sxs-lookup"><span data-stu-id="6f313-103">_**Topic Last Modified:** 2012-03-29_</span></span>

<span data-ttu-id="6f313-104">En los siguientes temas se describen los pasos necesarios para combinar los grupos de Microsoft Office Communications Server 2007 R2 con los grupos de servidores de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f313-104">The following topics outline the steps needed to merge your Microsoft Office Communications Server 2007 R2 pools to Microsoft Lync Server 2013 pools.</span></span> <span data-ttu-id="6f313-105">En primer lugar, use el Asistente para combinar el generador de topología para combinar la información de la topología.</span><span class="sxs-lookup"><span data-stu-id="6f313-105">First, you use the Topology Builder Merge wizard to merge topology information.</span></span> <span data-ttu-id="6f313-106">Esta herramienta recopila información sobre el entorno de Office Communications Server 2007 R2, incluida la información del servidor perimetral, y publica esa información en una base de datos compartida con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f313-106">This tool collects information about your Office Communications Server 2007 R2 environment, including Edge Server information, and publishes that information to a database shared with Lync Server 2013.</span></span> <span data-ttu-id="6f313-107">Después de publicar la topología combinada, el generador de topología se usa para ver la información de topología de Office Communications Server 2007 R2 e información sobre la topología recién implementada de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f313-107">After you publish the merged topology, Topology Builder is used to view the Office Communications Server 2007 R2 topology information and information about the newly deployed Lync Server 2013 topology.</span></span> <span data-ttu-id="6f313-108">Por último, use los cmdlets del shell de administración de Lync Server para importar directivas y opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="6f313-108">Finally, you use Lync Server Management Shell cmdlets to import policies and configuration settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6f313-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6f313-109">In This Section</span></span>

  - [<span data-ttu-id="6f313-110">Instalar el paquete de compatibilidad con versiones anteriores de WMI</span><span class="sxs-lookup"><span data-stu-id="6f313-110">Install WMI Backward Compatibility package</span></span>](install-wmi-backward-compatibility-package.md)

  - [<span data-ttu-id="6f313-111">Combinar mediante el Asistente para combinar generador de topología</span><span class="sxs-lookup"><span data-stu-id="6f313-111">Merge using Topology Builder Merge wizard</span></span>](merge-using-topology-builder-merge-wizard.md)

  - [<span data-ttu-id="6f313-112">Importar directivas y configuración</span><span class="sxs-lookup"><span data-stu-id="6f313-112">Import policies and settings</span></span>](import-policies-and-settings.md)

  - [<span data-ttu-id="6f313-113">Comprobar la información de la topología</span><span class="sxs-lookup"><span data-stu-id="6f313-113">Verify topology information</span></span>](verify-topology-information.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

