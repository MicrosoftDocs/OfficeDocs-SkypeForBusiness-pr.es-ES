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
ms.openlocfilehash: 4c36d88626288d96cb38242943df3bc055f6cbef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-4-merge-topologies"></a><span data-ttu-id="00d45-102">Fase 4: combinar topologías</span><span class="sxs-lookup"><span data-stu-id="00d45-102">Phase 4: Merge topologies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00d45-103">_**Última modificación del tema:** 2012-03-29_</span><span class="sxs-lookup"><span data-stu-id="00d45-103">_**Topic Last Modified:** 2012-03-29_</span></span>

<span data-ttu-id="00d45-104">Los siguientes temas describen los pasos necesarios para combinar los grupos de servidores de Microsoft Office Communications Server 2007 R2 con los grupos de servidores de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00d45-104">The following topics outline the steps needed to merge your Microsoft Office Communications Server 2007 R2 pools to Microsoft Lync Server 2013 pools.</span></span> <span data-ttu-id="00d45-105">En primer lugar, utilice el asistente para combinaciones del Generador de topologías para combinar la información de topología.</span><span class="sxs-lookup"><span data-stu-id="00d45-105">First, you use the Topology Builder Merge wizard to merge topology information.</span></span> <span data-ttu-id="00d45-106">Esta herramienta recopila información sobre el entorno de Office Communications Server 2007 R2, incluida la información del servidor perimetral, y la publica la información en una base de datos compartida con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00d45-106">This tool collects information about your Office Communications Server 2007 R2 environment, including Edge Server information, and publishes that information to a database shared with Lync Server 2013.</span></span> <span data-ttu-id="00d45-107">Después de publicar la topología combinada, el generador de topologías se usa para ver la información de topología de Office Communications Server 2007 R2 e información sobre la topología recién implementada de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00d45-107">After you publish the merged topology, Topology Builder is used to view the Office Communications Server 2007 R2 topology information and information about the newly deployed Lync Server 2013 topology.</span></span> <span data-ttu-id="00d45-108">Para finalizar, utilice los cmdlets del Shell de administración de Communications Server para importar directivas y valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="00d45-108">Finally, you use Lync Server Management Shell cmdlets to import policies and configuration settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="00d45-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="00d45-109">In This Section</span></span>

  - [<span data-ttu-id="00d45-110">Instalar el paquete de compatibilidad con versiones anteriores de WMI</span><span class="sxs-lookup"><span data-stu-id="00d45-110">Install WMI Backward Compatibility package</span></span>](install-wmi-backward-compatibility-package.md)

  - [<span data-ttu-id="00d45-111">Combinar mediante el Asistente de combinación del generador de topologías</span><span class="sxs-lookup"><span data-stu-id="00d45-111">Merge using Topology Builder Merge wizard</span></span>](merge-using-topology-builder-merge-wizard.md)

  - [<span data-ttu-id="00d45-112">Importación de directivas y parámetros</span><span class="sxs-lookup"><span data-stu-id="00d45-112">Import policies and settings</span></span>](import-policies-and-settings.md)

  - [<span data-ttu-id="00d45-113">Comprobar la información de la topología</span><span class="sxs-lookup"><span data-stu-id="00d45-113">Verify topology information</span></span>](verify-topology-information.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

