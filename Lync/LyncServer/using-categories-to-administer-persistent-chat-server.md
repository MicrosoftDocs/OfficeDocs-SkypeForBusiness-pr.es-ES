---
title: Usar categorías para administrar el servidor de chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fed28ecc7c2698f4b320729c68de9c5d56b435b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="a2f9c-102">Usar categorías para administrar el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a2f9c-102">Using categories to administer Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2f9c-103">_**Última modificación del tema:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="a2f9c-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="a2f9c-104">La implementación del servidor de chat persistente puede alojar muchos salones de chat persistentes simultáneos.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="a2f9c-105">Los salones de chat pueden estar organizados jerárquicamente en un conjunto de categorías en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="a2f9c-106">Cada salón de chat pertenece a una categoría y hereda parte de la configuración de dicha categoría.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="a2f9c-107">Esta organización crea una estructura útil para identificar conversaciones según el fin del negocio y, asimismo, facilita la delegación y simplificación de la administración.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a2f9c-108">Aunque muchas de las características de administración de los salones de chat están disponibles en equipos que ejecutan una conversación persistente (cliente de Lync) para el usuario, los administradores de chat persistentes (en el rol <STRONG>cspersistentchatadministrator</STRONG> ) deben usar el panel de control de Lync Server o Cmdlets de Windows PowerShell para crear o administrar categorías.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="a2f9c-109">Los administradores de chat persistentes usan el panel de control de Lync Server o los cmdlets de Windows PowerShell para crear y administrar categorías, así como para diseñar el acceso a los salones de chat para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="a2f9c-110">Los administradores de salones de chat persistentes, que tienen la capacidad de administrar una o más salas de chat, pueden usar el cliente de Lync para iniciar una aplicación Web de administración de salas para crear y administrar salas (o para que los clientes puedan crear soluciones personalizadas y flujos de trabajo que se invocarán).</span><span class="sxs-lookup"><span data-stu-id="a2f9c-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="a2f9c-111">Los administradores de chat persistentes también pueden usar el panel de control de Lync Server o los cmdlets de Windows PowerShell para crear y administrar salas.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a2f9c-112">Un salón de chat persistente no puede tener el mismo nombre que una categoría de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="a2f9c-p103">Los administradores de los salones de chat pueden realizar cambios en todas las propiedades del salón de chat, salvo para cambiar la categoría del salón. No se les puede impedir ejecutar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2f9c-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="a2f9c-115">Deshabilitar un salón de chat</span><span class="sxs-lookup"><span data-stu-id="a2f9c-115">Disabling a chat room</span></span>

  - <span data-ttu-id="a2f9c-116">Cambiar el nombre de un salón de chat</span><span class="sxs-lookup"><span data-stu-id="a2f9c-116">Changing a chat room name</span></span>

  - <span data-ttu-id="a2f9c-117">Cambiar la descripción de un salón de chat</span><span class="sxs-lookup"><span data-stu-id="a2f9c-117">Changing a chat room description</span></span>

  - <span data-ttu-id="a2f9c-118">Cambiar el tipo de salón de chat (Auditorio o Normal)</span><span class="sxs-lookup"><span data-stu-id="a2f9c-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="a2f9c-119">Cambiar la privacidad de un salón (abierto, cerrado o secreto)</span><span class="sxs-lookup"><span data-stu-id="a2f9c-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="a2f9c-120">Agregar o quitar miembros</span><span class="sxs-lookup"><span data-stu-id="a2f9c-120">Adding or removing members</span></span>

  - <span data-ttu-id="a2f9c-121">Agregar o quitar administradores de salones de chat</span><span class="sxs-lookup"><span data-stu-id="a2f9c-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="a2f9c-122">Agregar o quitar un complemento</span><span class="sxs-lookup"><span data-stu-id="a2f9c-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="a2f9c-123">Cambiar configuraciones como invitaciones (de acuerdo con lo permitido por la categoría)</span><span class="sxs-lookup"><span data-stu-id="a2f9c-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="a2f9c-124">Administración delegada</span><span class="sxs-lookup"><span data-stu-id="a2f9c-124">Delegated Administration</span></span>

<span data-ttu-id="a2f9c-125">Crear y administrar salones de chat persistentes es mucho más fácil con el uso correcto de categorías.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="a2f9c-126">Un administrador de chat persistente puede definir **AllowedMembers** y **creadores** de cada categoría, y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salones de chat creados en la categoría.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="a2f9c-127">Los administradores de chats persistentes crean y administran categorías mediante el panel de control de Lync Server o los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="a2f9c-p105">Los usuarios, las unidades organizativas (UO) y los grupos de usuarios que se identifican como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría. Después de crear la categoría, pueden elegir usuarios, UO y grupos de usuarios en la lista de **miembros permitidos** de la categoría como administradores y miembros del salón de chat para administrar el salón y participar en él.</span><span class="sxs-lookup"><span data-stu-id="a2f9c-p105">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category. After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="a2f9c-130">Los salones de chat creados en una categoría respetan las directivas y la configuración exigidas por la categoría (como quién puede estar en la pertenencia de la sala, quién puede administrar el salón, si se permiten las cargas de archivos, si se han enviado invitaciones, etc.).</span><span class="sxs-lookup"><span data-stu-id="a2f9c-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

