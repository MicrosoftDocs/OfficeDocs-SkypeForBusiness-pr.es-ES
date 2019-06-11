---
title: Migrar servidor de mediación
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fc35a7641b4acb42578ec4e75375e171ae905e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="d8e66-102">Migrar servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="d8e66-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8e66-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d8e66-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d8e66-104">El servidor de mediación se combina en su topología piloto de Lync Server 2013 cuando ejecuta el Asistente de combinación.</span><span class="sxs-lookup"><span data-stu-id="d8e66-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="d8e66-105">Puede configurar el servidor de mediación de Lync Server 2013, sin embargo, después de migrar a todos los usuarios, porque un grupo de Office Communications Server 2007 R2 no se puede comunicar con un servidor de mediación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8e66-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="d8e66-106">Durante la migración en paralelo, el grupo de Lync Server 2013 se comunica con el servidor de mediación de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d8e66-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="d8e66-107">Al configurar el servidor de mediación de Lync Server 2013, también debe actualizar o reemplazar las puertas de enlace de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d8e66-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="d8e66-108">Las puertas de enlace de Office Communications Server 2007 R2 no son compatibles con el servidor de mediación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8e66-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="d8e66-109">Debe implementar puertas de enlace que estén certificadas para Lync Server 2013 y asociarlas con el servidor de mediación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8e66-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="d8e66-110">Este paso es necesario para poder retirar por completo la implementación de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d8e66-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="d8e66-111">En los temas de esta sección se describen las tareas de configuración que necesita realizar después de completar la migración del servidor de mediación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8e66-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="d8e66-112">Realizar una transición entre el servidor de mediación que se encuentra en un servidor de mediación independiente es una tarea opcional.</span><span class="sxs-lookup"><span data-stu-id="d8e66-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="d8e66-113">Configurar servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="d8e66-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="d8e66-114">Cambiar las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8e66-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="d8e66-115">Transición de un servidor de mediación en un servidor de mediación independiente (opcional)</span><span class="sxs-lookup"><span data-stu-id="d8e66-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

