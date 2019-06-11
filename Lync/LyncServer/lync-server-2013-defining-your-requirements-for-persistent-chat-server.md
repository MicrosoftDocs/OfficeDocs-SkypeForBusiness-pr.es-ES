---
title: 'Lync Server 2013: Definición de los requisitos para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68f9195a91a4f8334933d1fce7ffd3a5dceb564c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="9422a-102">Definición de los requisitos de la organización para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9422a-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9422a-103">_**Última modificación del tema:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="9422a-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="9422a-104">Antes de implementar un servidor de chat persistente para su organización, es esencial que considere las siguientes preguntas clave para optimizar la implementación:</span><span class="sxs-lookup"><span data-stu-id="9422a-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="9422a-105">¿Quién (Perfil de usuario) debe estar habilitado para el servidor de chat persistente?</span><span class="sxs-lookup"><span data-stu-id="9422a-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="9422a-106">El servidor de chat persistente está habilitado por una directiva que se puede establecer en un nivel global, de sitio, de grupo o de usuario.</span><span class="sxs-lookup"><span data-stu-id="9422a-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="9422a-107">¿Cuántos usuarios deben estar habilitados para el servidor de chat persistente?</span><span class="sxs-lookup"><span data-stu-id="9422a-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="9422a-108">El servidor de chat persistente admite usuarios de 150.000 aprovisionados (habilitados por la Directiva) y un máximo de 80.000 usuarios simultáneos que usen el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9422a-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="9422a-109">Un único servidor de chat persistente puede admitir 20 000 usuarios conectados y un único grupo de servidores de chat persistente puede tener hasta 4 servidores activos para un total de 80 000 usuarios conectados de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="9422a-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="9422a-110">¿Va a migrar desde una versión anterior del servidor de chat de grupo o va a implementar un servidor de chat persistente por primera vez?</span><span class="sxs-lookup"><span data-stu-id="9422a-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="9422a-111">¿Hay requisitos de cumplimiento?</span><span class="sxs-lookup"><span data-stu-id="9422a-111">Are there compliance requirements?</span></span> <span data-ttu-id="9422a-112">El servidor de chat persistente admite el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9422a-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="9422a-113">El servicio de cumplimiento se ejecuta en el servidor front-end del servidor de chat persistente, a diferencia del requisito de un equipo independiente en las implementaciones anteriores del servidor de chat de grupo.</span><span class="sxs-lookup"><span data-stu-id="9422a-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="9422a-114">El cumplimiento es opcional y, si se elige, requiere una base de datos de cumplimiento que se debe configurar para almacenar los datos y eventos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9422a-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="9422a-115">Es posible que también desee configurar un adaptador para que tome los datos de la base de datos de cumplimiento y los convierta a otro formato (como archivos XML o archivos hospedados por Exchange).</span><span class="sxs-lookup"><span data-stu-id="9422a-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="9422a-116">¿Cómo desea controlar los ámbitos, los límites éticos y el acceso?</span><span class="sxs-lookup"><span data-stu-id="9422a-116">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="9422a-117">Puede definir **categorías** para separar estos límites y elegir quién está permitido en las salas que se crean en cada una de estas categorías.</span><span class="sxs-lookup"><span data-stu-id="9422a-117">You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="9422a-118">¿Cómo desea controlar quién puede crear salones?</span><span class="sxs-lookup"><span data-stu-id="9422a-118">How do you want to control who can create rooms?</span></span> <span data-ttu-id="9422a-119">Puede configurar **creadores**, según sus categorías, que puedan crear salas.</span><span class="sxs-lookup"><span data-stu-id="9422a-119">You can configure **Creators**, appropriate to your categories, who can create rooms.</span></span> <span data-ttu-id="9422a-120">Los creadores pueden asignar otros miembros como **administradores del salón de chat** para la administración continua de las salas (agregando o quitando miembros adicionales), según el ámbito de **AllowedMembers/DeniedMembers** configurado por la categoría.</span><span class="sxs-lookup"><span data-stu-id="9422a-120">Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="9422a-121">¿Cómo desea crear salas?</span><span class="sxs-lookup"><span data-stu-id="9422a-121">How do you want to create rooms?</span></span> <span data-ttu-id="9422a-122">El servidor de chat persistente proporciona una característica basada en la web para la creación y administración de salas.</span><span class="sxs-lookup"><span data-stu-id="9422a-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="9422a-123">Esto se puede iniciar desde el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9422a-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="9422a-124">Puede definir una solución personalizada (mediante el kit de desarrollo de software (SDK) del servidor de chat persistente) que implementa los requisitos y los flujos de trabajo de su empresa, y configurar el servidor de chat persistente para dirigir a los usuarios a su solución personalizada.</span><span class="sxs-lookup"><span data-stu-id="9422a-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="9422a-125">¿Qué tipo de complementos desea suministrar?</span><span class="sxs-lookup"><span data-stu-id="9422a-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="9422a-126">\*\*\*\* Los complementos mejoran la experiencia en la sala aprovechando el panel de extensibilidad en el cliente de Lync 2013 para proporcionar contexto que sea relevante para el salón.</span><span class="sxs-lookup"><span data-stu-id="9422a-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="9422a-127">Puede elegir qué complementos generales podrían ser más útiles (por ejemplo, el sitio web de la compañía, los documentos de colaboración interna, etc.).</span><span class="sxs-lookup"><span data-stu-id="9422a-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="9422a-128">Los directores del salón de chat pueden elegir uno de los complementos registrados y asociarlo a los salones, si así lo desean.</span><span class="sxs-lookup"><span data-stu-id="9422a-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="9422a-129">¿Qué tipo de requisitos de alta disponibilidad y recuperación ante desastres tiene?</span><span class="sxs-lookup"><span data-stu-id="9422a-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="9422a-130">El servidor de chat persistente admite el reflejo de SQL Server y el clúster de SQL Server para ofrecer alta disponibilidad y admite hasta 8 servidores (4 activos y 4 en espera) en un grupo expandido con el trasvase de registros de SQL Server para la recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="9422a-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="9422a-131">¿Dispone de requisitos de regulación?</span><span class="sxs-lookup"><span data-stu-id="9422a-131">Are there regulatory requirements?</span></span> <span data-ttu-id="9422a-132">Si su empresa se encuentra en un país o una región donde los datos deben conservarse dentro del país, es posible que tenga que implementar varios grupos de servidores de chat persistentes, cada uno local en una geografía específica.</span><span class="sxs-lookup"><span data-stu-id="9422a-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="9422a-133">Un salón, una categoría o un complemento no abarcan agrupaciones: solo pertenece a un grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9422a-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="9422a-134">Puede administrar el conjunto de categorías, complementos y salas para cada grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9422a-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="9422a-135">Los usuarios se pueden configurar para que tengan acceso a salas en uno o más grupos de la categoría AllowedMembers ámbito o ámbito de suscripción de la sala, según el diseño de las categorías.</span><span class="sxs-lookup"><span data-stu-id="9422a-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9422a-136">Tener varios grupos de servidores de chat persistentes no le da más escala (todavía puede tener solo 80.000 usuarios conectados al mismo tiempo en todos los grupos de servidores de chat persistentes).</span><span class="sxs-lookup"><span data-stu-id="9422a-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="9422a-137">El motivo principal por el que se admiten varios grupos de servidores de chat persistentes es apoyar problemas normativos.</span><span class="sxs-lookup"><span data-stu-id="9422a-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

