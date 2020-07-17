---
title: Descripción de la pertenencia al chat persistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400866812ab2d5efb12960dc3c2f37c2fcb8eb45
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="4b07e-102">Descripción de la pertenencia al chat persistente</span><span class="sxs-lookup"><span data-stu-id="4b07e-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b07e-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4b07e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4b07e-104">El acceso de los usuarios a los salones de chat persistente se administra por suscripción; los usuarios deben ser miembros de un salón de chat para poder publicar y leer mensajes.</span><span class="sxs-lookup"><span data-stu-id="4b07e-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="4b07e-105">Solo los **moderadores** que tengan una afiliación designada a los salones de chat pueden **publicar en salones de Auditorio**.</span><span class="sxs-lookup"><span data-stu-id="4b07e-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="4b07e-106">Un Auditorio es un tipo de salón de chat (el otro es **Normal**), en el que solo los moderadores pueden publicar y todos pueden leer.</span><span class="sxs-lookup"><span data-stu-id="4b07e-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="4b07e-107">Además, los salones de chat persistente funcionan según las reglas de una categoría.</span><span class="sxs-lookup"><span data-stu-id="4b07e-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="4b07e-108">Para obtener más información sobre las categorías, vea [administrar categorías, salones y complementos en Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), así como las secciones "Cómo funciona el ámbito de la categoría" y "estrategias de categoría de sala" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="4b07e-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="4b07e-109">Un administrador de chat persistente puede crear y administrar categorías de salones de chat.</span><span class="sxs-lookup"><span data-stu-id="4b07e-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="4b07e-110">Como parte de la creación y la administración de categorías de salones de chat, el administrador de chat persistente puede configurar entidades de identidad (grupos de servicios de dominio de Active Directory, contenedores y usuarios) que tienen acceso a miembros o creadores de salones de chat de una categoría determinada.</span><span class="sxs-lookup"><span data-stu-id="4b07e-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="4b07e-111">Servicios de dominio de Active Directory y chat persistente</span><span class="sxs-lookup"><span data-stu-id="4b07e-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="4b07e-112">El servidor de chat persistente depende de Active Directory para el grupo de usuarios de chat persistente internos.</span><span class="sxs-lookup"><span data-stu-id="4b07e-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="4b07e-113">Después de instalar chat persistente (cliente), puede agregar dominios de usuarios y grupos de usuarios a la categoría de salón.</span><span class="sxs-lookup"><span data-stu-id="4b07e-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="4b07e-114">Puede agregar estos usuarios y grupos a la pertenencia de las categorías de salón.</span><span class="sxs-lookup"><span data-stu-id="4b07e-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4b07e-115">Debe asegurarse de que no haya nombres duplicados para los usuarios que deseen realizar cambios en sus salones de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4b07e-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="4b07e-116">Si hubiera nombres de usuario duplicados, cámbielos por nombres diferentes para permitir a dichos usuarios realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="4b07e-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="4b07e-117">Si un usuario tiene nombres duplicados en Active Directory e intenta realizar cambios en sus salas, aparece un mensaje de error que solicita al usuario que se ponga en contacto con el administrador para que lo resuelva.</span><span class="sxs-lookup"><span data-stu-id="4b07e-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="4b07e-118">Funcionamiento del ámbito de categoría</span><span class="sxs-lookup"><span data-stu-id="4b07e-118">How Category Scoping Works</span></span>

<span data-ttu-id="4b07e-119">Una categoría especifica todos los usuarios y grupos que pueden ser miembros de una lista de pertenencia de un salón de chat persistente en esa categoría, en función de su propiedad **miembros permitidos** .</span><span class="sxs-lookup"><span data-stu-id="4b07e-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="4b07e-120">Por ejemplo, si establece el **miembros permitidos** de la categoría en contoso.com, puede agregar cualquier grupo o usuario de *contoso* como miembro a los salones de chat de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="4b07e-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="4b07e-121">Si establece el valor de **AllowedMembers** de una categoría en *Sales*, solo los grupos y usuarios de esta lista de distribución se pueden agregar como miembros a los salones de chat de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="4b07e-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="4b07e-122">De forma similar, la propiedad **Creators** permite controlar quién puede crear salones de chat en esa categoría.</span><span class="sxs-lookup"><span data-stu-id="4b07e-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="4b07e-123">Una vez creado el salón de chat, todos los miembros del grupo **AllowedMembers** pueden designarse como **Administrator** para las operaciones de administración continuadas en los salones (por ejemplo, cambios y aprobaciones de pertenencia como miembro).</span><span class="sxs-lookup"><span data-stu-id="4b07e-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="4b07e-124">Definir **AllowedMembers** y **Creators** para una categoría tiene las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="4b07e-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="4b07e-p107">Todos los salones de chat de esta categoría se rigen por las restricciones establecidas en el nivel de la categoría. Puede usarlo para segregar salones de chat en función de las necesidades empresariales y las directivas de acceso.</span><span class="sxs-lookup"><span data-stu-id="4b07e-p107">All chat rooms in this category are bound by the restrictions set at the category level. You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="4b07e-p108">Un usuario de la lista **Creators** puede crear nuevos salones de chat en esa categoría. Si quiere implementar un sistema en el que un número restringido de personal de la organización pueda crear salones de chat, se puede usar este control para cumplir ese requisito.</span><span class="sxs-lookup"><span data-stu-id="4b07e-p108">A user who is in the **Creators** list can create new chat rooms in that category. If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="4b07e-129">Estrategias de categoría de salón</span><span class="sxs-lookup"><span data-stu-id="4b07e-129">Room Category Strategies</span></span>

<span data-ttu-id="4b07e-130">El **miembros permitidos** de una categoría debe incluir todos los usuarios que usarán cualquier salón de chat persistente en esta categoría.</span><span class="sxs-lookup"><span data-stu-id="4b07e-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="4b07e-131">En función de sus requisitos para proteger los datos empresariales y garantizar un nivel de acceso adecuado, quizás quiera definir una o varias categorías para especificar quién puede buscar salones y participar en ellos.</span><span class="sxs-lookup"><span data-stu-id="4b07e-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="4b07e-132">Si quiere permitir que solo un conjunto determinado de usuarios (departamento de soporte técnico central o solo empleados a tiempo completo) pueda crear salones, puede definir el ámbito de la lista **Creators** de una categoría para satisfacer ese requisito.</span><span class="sxs-lookup"><span data-stu-id="4b07e-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="4b07e-p110">Las categorías también se pueden usar para crear zonas de protección. Las zonas de protección evitan conflictos de intereses en una organización. Por ejemplo, un administrador puede crear salones de chat en una categoría solo para comerciales, mientras que los salones de chat de otra categoría son solo para analistas.</span><span class="sxs-lookup"><span data-stu-id="4b07e-p110">Categories can also be used to create ethical walls. Ethical walls prevent any conflict of interest in an organization. For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b07e-136">En Lync Server 2013, el servidor de chat persistente no es compatible con el acceso a usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="4b07e-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="4b07e-137">Si hay chats de usuarios federados en versiones anteriores del servidor de chat persistente, se migrarán.</span><span class="sxs-lookup"><span data-stu-id="4b07e-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="4b07e-138">Los usuarios federados se agregan como entidades deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="4b07e-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="4b07e-139">Restringir los miembros a grupos de usuarios</span><span class="sxs-lookup"><span data-stu-id="4b07e-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="4b07e-140">Cuando se agrega un dominio a una categoría, los grupos de usuarios cuyos objetos de grupo estén incluidos en dicho dominio estarán disponibles para que pueda especificarlos como miembros de los salones de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="4b07e-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="4b07e-141">Como regla general, se recomienda usar contenedores de Active Directory, como dominios y unidades organizativas, para definir **miembros permitidos** y **creadores**de una categoría.</span><span class="sxs-lookup"><span data-stu-id="4b07e-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="4b07e-142">Puede agregar objetos de cualquier dominio a una lista **AllowedMembers** o **Creators**.</span><span class="sxs-lookup"><span data-stu-id="4b07e-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="4b07e-143">Solo los objetos de la lista **AllowedMembers** o **Creators** se pueden agregar a los salones de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="4b07e-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

