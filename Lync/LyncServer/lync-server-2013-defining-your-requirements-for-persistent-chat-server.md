---
title: 'Lync Server 2013: definición de los requisitos para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63e7af0dca758f6ac543bb0373d2cbb0d953ba0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504307"
---
# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="0f345-102">Definición de los requisitos de la organización para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f345-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f345-103">_**Última modificación del tema:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="0f345-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="0f345-104">Antes de implementar el servidor de chat persistente en su organización, es fundamental tener en cuenta las siguientes preguntas clave para optimizar la implementación:</span><span class="sxs-lookup"><span data-stu-id="0f345-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="0f345-105">¿Quién (Perfil de usuario) debe estar habilitado para el servidor de chat persistente?</span><span class="sxs-lookup"><span data-stu-id="0f345-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="0f345-106">El servidor de chat persistente está habilitado por una directiva que se puede establecer en un nivel global, de sitio, de grupo o de usuario.</span><span class="sxs-lookup"><span data-stu-id="0f345-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="0f345-107">¿Cuántos usuarios deben estar habilitados para el servidor de chat persistente?</span><span class="sxs-lookup"><span data-stu-id="0f345-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="0f345-108">El servidor de chat persistente admite usuarios aprovisionados de 150.000 (habilitados por directiva) y un máximo de 80.000 usuarios simultáneos que usan el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0f345-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="0f345-109">Un único servidor de chat persistente puede admitir 20.000 usuarios conectados y un solo grupo de servidores de chat persistente puede tener hasta 4 servidores activos para un total de 80.000 usuarios conectados simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="0f345-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="0f345-110">¿Va a migrar desde una versión anterior del servidor de chat en grupo o va a implementar el servidor de chat persistente por primera vez?</span><span class="sxs-lookup"><span data-stu-id="0f345-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="0f345-111">¿Hay requisitos de cumplimiento?</span><span class="sxs-lookup"><span data-stu-id="0f345-111">Are there compliance requirements?</span></span> <span data-ttu-id="0f345-112">El servidor de chat persistente admite el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="0f345-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="0f345-113">El servicio de cumplimiento se ejecuta en el servidor front-end del servidor de chat persistente, en lugar del requisito para un equipo independiente en las implementaciones anteriores del servidor de chat en grupo.</span><span class="sxs-lookup"><span data-stu-id="0f345-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="0f345-114">El cumplimiento es opcional y si se elige, requiere una base de datos de cumplimiento que debe configurarse para almacenar eventos y datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="0f345-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="0f345-115">Es posible que también desee configurar un adaptador para que tome los datos de la base de datos de cumplimiento y los convierta a otro formato (como archivos XML o archivos hospedados por Exchange).</span><span class="sxs-lookup"><span data-stu-id="0f345-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="0f345-p104">¿Cómo desea controlar los ámbitos, los límites éticos y el acceso? Puede definir **Categorías** para segregar estos límites y elegir quién puede estar en salones que se crean en cada una de estas categorías.</span><span class="sxs-lookup"><span data-stu-id="0f345-p104">How do you want to control scopes, ethical boundaries, and access? You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="0f345-p105">¿Qué desea para controlar quién puede crear salones? Puede configurar **Creadores**, correspondientes a las categorías, que pueden crear salones. Los creadores pueden asignar otros miembros como **Administradores de salones de chat** para la administración continua de los salones (agregar o quitar miembros adicionales), según el ámbito de **AllowedMembers/DeniedMembers** configurado por la categoría.</span><span class="sxs-lookup"><span data-stu-id="0f345-p105">How do you want to control who can create rooms? You can configure **Creators**, appropriate to your categories, who can create rooms. Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="0f345-121">¿Cómo desea crear los salones?</span><span class="sxs-lookup"><span data-stu-id="0f345-121">How do you want to create rooms?</span></span> <span data-ttu-id="0f345-122">El servidor de chat persistente proporciona una característica basada en web para la creación y administración de salas.</span><span class="sxs-lookup"><span data-stu-id="0f345-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="0f345-123">Puede iniciarse desde el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0f345-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="0f345-124">Puede definir una solución personalizada (usando el kit de desarrollo de software (SDK) del servidor de chat persistente) que implementa los requisitos de negocio y flujos de trabajo, y configura el servidor de chat persistente para dirigir a los usuarios a la solución personalizada.</span><span class="sxs-lookup"><span data-stu-id="0f345-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="0f345-125">¿Qué tipo de complemento desea suministrar?</span><span class="sxs-lookup"><span data-stu-id="0f345-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="0f345-126">Los **Complementos** mejoran la experiencia en el salón aprovechando el panel de extensibilidad en el cliente de Lync 2013 para proporcionar contexto que sea relevante para el salón.</span><span class="sxs-lookup"><span data-stu-id="0f345-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="0f345-127">Puede elegir qué complementos generales podrían ser más útiles (por ejemplo, el sitio web de la empresa, los documentos de colaboración interna, etc.).</span><span class="sxs-lookup"><span data-stu-id="0f345-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="0f345-128">Los administradores del salón de chat pueden elegir uno de los complementos registrados y asociarlo a sus salones, si lo desean.</span><span class="sxs-lookup"><span data-stu-id="0f345-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="0f345-129">¿Qué tipo de requisitos de alta disponibilidad y recuperación ante desastres tiene?</span><span class="sxs-lookup"><span data-stu-id="0f345-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="0f345-130">El servidor de chat persistente admite la creación de reflejos de SQL Server y la agrupación en clústeres de SQL Server para alta disponibilidad y admite hasta 8 servidores (4 activos y 4 en espera) en un grupo extendido con el trasvase de registros de SQL Server para la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="0f345-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="0f345-131">¿Existen requerimientos legales?</span><span class="sxs-lookup"><span data-stu-id="0f345-131">Are there regulatory requirements?</span></span> <span data-ttu-id="0f345-132">Si su empresa se encuentra en un país o región en el que los datos deben conservarse dentro del país, es posible que deba implementar varios grupos de servidores de chat persistente, cada uno de ellos local en una ubicación geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="0f345-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="0f345-133">Un salón, una categoría o un complemento no abarcan grupos; solo pertenece a un grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0f345-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="0f345-134">Puede administrar el conjunto de categorías, complementos y salas para cada grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0f345-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="0f345-135">Los usuarios se pueden configurar para que tengan acceso a los salones de uno o más grupos de servidores mediante el ámbito de categoría miembros permitidos o el ámbito de pertenencia de la sala, en función de cómo diseñe las categorías.</span><span class="sxs-lookup"><span data-stu-id="0f345-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0f345-136">Tener varios grupos de servidores de chat persistente no le da más escala (todavía puede tener sólo 80.000 usuarios conectados simultáneamente en todos los grupos de servidores de chat persistente).</span><span class="sxs-lookup"><span data-stu-id="0f345-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="0f345-137">La razón principal para admitir varios grupos de servidores de chat persistente es apoyar las cuestiones regulatorias.</span><span class="sxs-lookup"><span data-stu-id="0f345-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

