---
title: Uso de categorías para administrar el servidor de chat persistente
description: Uso de categorías para administrar el servidor de chat persistente.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 181ecba944a042e3598b2964ad233590cf63349e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579546"
---
# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="9bfdc-103">Uso de categorías para administrar el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="9bfdc-103">Using categories to administer Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bfdc-104">_**Última modificación del tema:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="9bfdc-104">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="9bfdc-105">La implementación del servidor de chat persistente puede hospedar muchos salones de chat persistente simultáneos.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-105">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="9bfdc-106">Los salones de chat se pueden organizar en un conjunto de categorías en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-106">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="9bfdc-107">Cada salón de chat pertenece a una categoría, y hereda alguna configuración de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-107">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="9bfdc-108">Esta configuración crea una estructura útil para identificar conversaciones, en función de su propósito empresarial, y facilita la delegación y simplificación de la administración.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-108">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9bfdc-109">Aunque muchas de las características de administración de los salones de chat están disponibles en los equipos que ejecutan chat persistente (cliente de Lync) para el usuario, los administradores de chat persistente (en el rol <STRONG>cspersistentchatadministrator</STRONG> ) deben usar el panel de control de Lync Server o los cmdlets de Windows PowerShell para crear o administrar categorías.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-109">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="9bfdc-110">Los administradores de chat persistente usan el panel de control de Lync Server o los cmdlets de Windows PowerShell para crear y administrar categorías, así como para diseñar el acceso para los salones de chat para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-110">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="9bfdc-111">Los administradores de salones de chat persistente, que tienen la capacidad de administrar uno o más salones de chat, pueden usar el cliente de Lync para iniciar una aplicación Web de administración de salas para crear y administrar salones (o los clientes pueden crear soluciones personalizadas y flujos de trabajo que se invocarán).</span><span class="sxs-lookup"><span data-stu-id="9bfdc-111">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="9bfdc-112">Los administradores de chat persistente también pueden usar el panel de control de Lync Server o los cmdlets de Windows PowerShell para crear y administrar salones.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-112">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9bfdc-113">Un salón de chat persistente no puede tener el mismo nombre que una categoría de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-113">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="9bfdc-p103">Los administradores de salones pueden hacer cambios en todas las propiedades de salones de chat, excepto en la categoría del salón. No pueden tener restricciones para realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="9bfdc-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="9bfdc-116">Deshabilitar un salón de chat</span><span class="sxs-lookup"><span data-stu-id="9bfdc-116">Disabling a chat room</span></span>

  - <span data-ttu-id="9bfdc-117">Cambiar el nombre de un salón de chat</span><span class="sxs-lookup"><span data-stu-id="9bfdc-117">Changing a chat room name</span></span>

  - <span data-ttu-id="9bfdc-118">Cambiar la descripción de un salón de chat</span><span class="sxs-lookup"><span data-stu-id="9bfdc-118">Changing a chat room description</span></span>

  - <span data-ttu-id="9bfdc-119">Cambiar el tipo de salón de chat (Auditorio o Normal)</span><span class="sxs-lookup"><span data-stu-id="9bfdc-119">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="9bfdc-120">Cambiar la privacidad de un salón (abierto/cerrado/secreto)</span><span class="sxs-lookup"><span data-stu-id="9bfdc-120">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="9bfdc-121">Agregar o quitar miembros</span><span class="sxs-lookup"><span data-stu-id="9bfdc-121">Adding or removing members</span></span>

  - <span data-ttu-id="9bfdc-122">Agregar o quitar administradores de salones de chat</span><span class="sxs-lookup"><span data-stu-id="9bfdc-122">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="9bfdc-123">Agregar o quitar un complemento</span><span class="sxs-lookup"><span data-stu-id="9bfdc-123">Adding or removing an add-in</span></span>

  - <span data-ttu-id="9bfdc-124">Cambiar configuración, como invitaciones (según lo que permite la categoría)</span><span class="sxs-lookup"><span data-stu-id="9bfdc-124">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="9bfdc-125">Administración delegada</span><span class="sxs-lookup"><span data-stu-id="9bfdc-125">Delegated Administration</span></span>

<span data-ttu-id="9bfdc-126">La creación y administración de salones de chat persistente es mucho más sencilla con el uso correcto de las categorías.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-126">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="9bfdc-127">Un administrador de chat persistente puede definir **miembros permitidos** y **creadores** para cada categoría y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salones de chat creados en la categoría.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-127">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="9bfdc-128">Los administradores de chat persistente crean y administran categorías mediante el panel de control de Lync Server o los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-128">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="9bfdc-p105">Los usuarios, las unidades organizativas (OU) y los grupos de usuarios identificados como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría. Una vez creada la categoría, pueden elegir usuarios, OU y grupos de usuarios desde la lista de **miembrospermitidos** de la categoría como administradores de salones de chat y miembros para administrar y participar en el salón.</span><span class="sxs-lookup"><span data-stu-id="9bfdc-p105">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category. After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="9bfdc-131">Los salones de chat que se crean en una categoría respetan las directivas y la configuración que exige la categoría (por ejemplo, quién puede estar en la pertenencia de la sala, quién puede administrar el salón, si se permiten las cargas de archivos, si se envían invitaciones, etc.).</span><span class="sxs-lookup"><span data-stu-id="9bfdc-131">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

