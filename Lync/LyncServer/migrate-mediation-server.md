---
title: Migrar el servidor de mediación
description: Migre el servidor de mediación.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31cc4c95f0e9c86b48594238218db22f3ec1a387
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570336"
---
# <a name="migrate-mediation-server"></a><span data-ttu-id="c63f5-103">Migrar el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="c63f5-103">Migrate Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c63f5-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c63f5-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c63f5-105">El servidor de mediación se combina en su topología piloto de Lync Server 2013 al ejecutar el Asistente de combinación.</span><span class="sxs-lookup"><span data-stu-id="c63f5-105">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="c63f5-106">No obstante, puede configurar el servidor de mediación de Lync Server 2013 después de migrar todos los usuarios porque un grupo de servidores de Office Communications Server 2007 R2 no puede comunicarse con un servidor de mediación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c63f5-106">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="c63f5-107">Durante la migración en paralelo, el grupo de servidores de Lync Server 2013 se comunica con el servidor de mediación de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c63f5-107">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="c63f5-108">Cuando configure el servidor de mediación de Lync Server 2013, también debe actualizar o reemplazar las puertas de enlace de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c63f5-108">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="c63f5-109">Las puertas de enlace de Office Communications Server 2007 R2 no admiten el servidor de mediación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c63f5-109">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="c63f5-110">Debe implementar puertas de enlace que estén certificadas para Lync Server 2013 y asociarlas con el servidor de mediación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c63f5-110">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="c63f5-111">Este paso es necesario para poder retirar por completo la implementación de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c63f5-111">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="c63f5-112">En los temas de esta sección se describen las tareas de configuración que debe realizar una vez que haya completado la migración del servidor de mediación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c63f5-112">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="c63f5-113">La transición del servidor de mediación combinado a un servidor de mediación independiente es una tarea opcional.</span><span class="sxs-lookup"><span data-stu-id="c63f5-113">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="c63f5-114">Configurar el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="c63f5-114">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="c63f5-115">Cambiar las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c63f5-115">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="c63f5-116">Transición de un servidor de mediación combinado a un servidor de mediación independiente (opcional)</span><span class="sxs-lookup"><span data-stu-id="c63f5-116">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

