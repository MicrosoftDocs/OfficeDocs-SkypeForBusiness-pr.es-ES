---
title: Introducción a la pertenencia al chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e525d93e58e73304b9d3a26248418c88b5e9ea79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="42b52-102">Introducción a la pertenencia al chat persistente</span><span class="sxs-lookup"><span data-stu-id="42b52-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42b52-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="42b52-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="42b52-104">El acceso de usuarios a salas de chat persistentes lo administran los miembros. los usuarios deben ser miembros de un salón de chat para poder publicar y leer mensajes.</span><span class="sxs-lookup"><span data-stu-id="42b52-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="42b52-105">Solo \*\*\*\* los moderadores que tienen una afiliación designada con salones de chat pueden usar la **publicación en salas de Auditorio**.</span><span class="sxs-lookup"><span data-stu-id="42b52-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="42b52-106">Un auditorio es un tipo de salón de chat (el otro es **normal**), en el que solo los moderadores pueden publicar y cualquier persona puede leer.</span><span class="sxs-lookup"><span data-stu-id="42b52-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="42b52-107">Además, los salones de chat persistente funcionan conforme a las normas de una categoría.</span><span class="sxs-lookup"><span data-stu-id="42b52-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="42b52-108">Para obtener más información acerca de las categorías, vea [administrar categorías, salas y complementos en Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), así como las secciones "Cómo funciona el ámbito de la categoría" y "estrategias de categorías de sala" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="42b52-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="42b52-109">Un administrador de chat persistente puede crear y administrar categorías de salones de chat.</span><span class="sxs-lookup"><span data-stu-id="42b52-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="42b52-110">Como parte de la creación y administración de categorías de salones de chat, el administrador de chat persistente puede configurar principales (grupos de servicios de dominio de Active Directory, contenedores y usuarios) que tienen acceso a miembros o creadores de salones de chat de una determinada categoría.</span><span class="sxs-lookup"><span data-stu-id="42b52-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="42b52-111">Servicios de dominio de Active Directory y chat persistente</span><span class="sxs-lookup"><span data-stu-id="42b52-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="42b52-112">El servidor de chat persistente depende de Active Directory para el grupo de usuarios internos de la conversación persistente.</span><span class="sxs-lookup"><span data-stu-id="42b52-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="42b52-113">Después de instalar chat persistente (cliente), puede agregar dominios de usuarios y grupos de usuarios a la categoría sala.</span><span class="sxs-lookup"><span data-stu-id="42b52-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="42b52-114">Después, puede agregar estos usuarios y grupos a la pertenencia de las categorías de su sala.</span><span class="sxs-lookup"><span data-stu-id="42b52-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="42b52-115">Debes asegurarte de que no haya nombres duplicados para los usuarios que deseen realizar cambios en sus salones de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="42b52-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="42b52-116">Si existen nombres de usuario duplicados, cámbielos por otros nombres para desbloquear a los usuarios para que no realicen esos cambios.</span><span class="sxs-lookup"><span data-stu-id="42b52-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="42b52-117">Si un usuario tiene nombres duplicados en Active Directory e intenta realizar cambios en sus salas, aparece un mensaje de error que solicita al usuario que se ponga en contacto con el administrador para que lo resuelva.</span><span class="sxs-lookup"><span data-stu-id="42b52-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="42b52-118">Cómo funciona el ámbito de la categoría</span><span class="sxs-lookup"><span data-stu-id="42b52-118">How Category Scoping Works</span></span>

<span data-ttu-id="42b52-119">Una categoría especifica todos los usuarios y grupos que pueden ser miembros de una lista de miembros de un salón de chat persistente en esa categoría, en función de su propiedad **AllowedMembers** .</span><span class="sxs-lookup"><span data-stu-id="42b52-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="42b52-120">Por ejemplo, si establece la **AllowedMembers** de la categoría en contoso.com, puede agregar cualquier grupo o usuario de *contoso* como miembro a los salones de chat de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="42b52-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="42b52-121">Si establece las **AllowedMembers** en una categoría para las *ventas*, solo se pueden agregar grupos y usuarios de esta lista de distribución como miembros de los salones de chat de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="42b52-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="42b52-122">De forma similar \*\*\*\* , la propiedad Creators te permite controlar quién puede crear salones de chat en esa categoría.</span><span class="sxs-lookup"><span data-stu-id="42b52-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="42b52-123">Una vez que se crea el salón de chat, cualquier persona del grupo **AllowedMembers** se puede designar como **Administrador** para las operaciones de administración continuas en las salas (por ejemplo, cambios de miembros y aprobaciones).</span><span class="sxs-lookup"><span data-stu-id="42b52-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="42b52-124">La definición de **AllowedMembers** y **creadores** de una categoría tiene las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="42b52-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="42b52-125">Todos los salones de chat de esta categoría están vinculados por las restricciones establecidas en el nivel de categoría.</span><span class="sxs-lookup"><span data-stu-id="42b52-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="42b52-126">Puedes usarlo para separar los salones de chat según las necesidades empresariales y las políticas de acceso.</span><span class="sxs-lookup"><span data-stu-id="42b52-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="42b52-127">Un usuario que se encuentra en la lista de **creadores** puede crear nuevos salones de chat en esa categoría.</span><span class="sxs-lookup"><span data-stu-id="42b52-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="42b52-128">Si desea implementar un sistema en el que un número restringido de personal de la organización puede crear salones de chat, este control se puede usar para cumplir con ese requisito.</span><span class="sxs-lookup"><span data-stu-id="42b52-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="42b52-129">Estrategias de categoría de sala</span><span class="sxs-lookup"><span data-stu-id="42b52-129">Room Category Strategies</span></span>

<span data-ttu-id="42b52-130">El **AllowedMembers** de una categoría debe incluir todos los usuarios que usarán cualquier salón de chat persistente en esta categoría.</span><span class="sxs-lookup"><span data-stu-id="42b52-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="42b52-131">En función de sus requisitos para proteger los datos empresariales y garantizar el nivel adecuado de acceso, es posible que desee definir una o más categorías para especificar quién puede buscar y participar en salas.</span><span class="sxs-lookup"><span data-stu-id="42b52-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="42b52-132">Si desea permitir que solo un conjunto de usuarios determinado (un helpdesk central o solo empleados de tiempo completo) creen salas, puede definir el ámbito de los **creadores** de una categoría para satisfacer ese requisito.</span><span class="sxs-lookup"><span data-stu-id="42b52-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="42b52-133">Las categorías también se pueden usar para crear paredes éticas.</span><span class="sxs-lookup"><span data-stu-id="42b52-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="42b52-134">Las paredes éticas evitan conflictos de intereses en una organización.</span><span class="sxs-lookup"><span data-stu-id="42b52-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="42b52-135">Por ejemplo, un administrador puede crear salones de chat en una categoría solo para operadores, mientras que los salones de chat de otra categoría solo pueden ser usados por analistas.</span><span class="sxs-lookup"><span data-stu-id="42b52-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42b52-136">En Lync Server 2013, el servidor de chat persistente no es compatible con el acceso a usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="42b52-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="42b52-137">Si hay chats de usuarios federados en versiones anteriores de un servidor de chat persistente, se migrarán.</span><span class="sxs-lookup"><span data-stu-id="42b52-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="42b52-138">Los usuarios federados se agregan como principales deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="42b52-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="42b52-139">Restringir los miembros a grupos de usuarios</span><span class="sxs-lookup"><span data-stu-id="42b52-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="42b52-140">Cuando agregue un dominio a una categoría, los grupos de usuarios cuyos objetos de grupo están disponibles en ese dominio estarán disponibles para que pueda especificarlos como miembros de las salas de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="42b52-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="42b52-141">Como regla general, le recomendamos que use contenedores de Active Directory, como dominios y unidades organizativas, para definir el **AllowedMembers** y los **creadores**de una categoría.</span><span class="sxs-lookup"><span data-stu-id="42b52-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="42b52-142">Puede agregar objetos desde cualquier dominio a una lista de **AllowedMembers** o **creadores** .</span><span class="sxs-lookup"><span data-stu-id="42b52-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="42b52-143">Solo se pueden agregar a las habitaciones de esa categoría los objetos de la lista **AllowedMembers** o **creadores** .</span><span class="sxs-lookup"><span data-stu-id="42b52-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

