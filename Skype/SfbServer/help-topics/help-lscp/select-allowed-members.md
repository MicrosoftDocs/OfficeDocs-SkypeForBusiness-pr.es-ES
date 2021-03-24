---
title: Seleccionar los miembros permitidos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Crear y administrar salas de chat persistente es mucho más fácil con el uso correcto de categorías. Un administrador de chat persistente puede definir AllowedMembers y Creators para cada categoría y también puede definir la configuración y comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat creados en la categoría. Los administradores de chat persistente crean y administran categorías mediante el panel de control o Windows PowerShell cmdlets.
ms.openlocfilehash: 47abbec64f6799a85f3f6123a898eeae00becbdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107996"
---
# <a name="select-allowed-members"></a><span data-ttu-id="dd4c9-105">Seleccionar los miembros permitidos</span><span class="sxs-lookup"><span data-stu-id="dd4c9-105">Select Allowed Members</span></span>

<span data-ttu-id="dd4c9-106">Crear y administrar salas de chat persistente es mucho más fácil con el uso correcto de categorías.</span><span class="sxs-lookup"><span data-stu-id="dd4c9-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="dd4c9-107">Un administrador de chat persistente puede definir **AllowedMembers** y Creators para cada categoría y también puede definir la configuración y comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat **creados** en la categoría.</span><span class="sxs-lookup"><span data-stu-id="dd4c9-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="dd4c9-108">Los administradores de chat persistente crean y administran categorías mediante el panel de control o Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="dd4c9-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="dd4c9-109">Los usuarios, las unidades organizativas (OU) y los grupos de usuarios identificados como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría.</span><span class="sxs-lookup"><span data-stu-id="dd4c9-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="dd4c9-110">Una vez creada la categoría, pueden elegir usuarios, US y grupos de usuarios de la lista **AllowedMembers** de la categoría como administradores y miembros del salón de chat para administrar y participar en la sala.</span><span class="sxs-lookup"><span data-stu-id="dd4c9-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="dd4c9-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="dd4c9-111">Tasks that you can perform</span></span>

<span data-ttu-id="dd4c9-112">Puede realizar las siguientes tareas en la página **Seleccionar los miembros permitidos**:</span><span class="sxs-lookup"><span data-stu-id="dd4c9-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="dd4c9-113">Configurar categorías</span><span class="sxs-lookup"><span data-stu-id="dd4c9-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="dd4c9-114">Nuevas características de servidor de conversaciones en grupo</span><span class="sxs-lookup"><span data-stu-id="dd4c9-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="dd4c9-115">Para obtener información detallada sobre los diferentes procedimientos que puede realizar mediante el Panel de control de Skype Empresarial Server, vea [Manage Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="dd4c9-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="dd4c9-116">Para configurar categorías para salones de chat</span><span class="sxs-lookup"><span data-stu-id="dd4c9-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="dd4c9-117">En **Pertenencia**,  en la sección Miembros permitidos, agregue o quite usuarios y otras entidades de seguridad de servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, entre otras) que puedan agregarse como miembros de salas de chat pertenecientes a la categoría.</span><span class="sxs-lookup"><span data-stu-id="dd4c9-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="dd4c9-118">Los elementos principales permitidos por una categoría pueden buscar salones en la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón pueden buscarlo en el directorio).</span><span class="sxs-lookup"><span data-stu-id="dd4c9-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="dd4c9-119">Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="dd4c9-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="dd4c9-120">Para obtener más información sobre cómo trabajar con configuraciones de servidor de chat persistente, consulte [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) en la documentación sobre implementación y [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="dd4c9-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd4c9-121">Ver también</span><span class="sxs-lookup"><span data-stu-id="dd4c9-121">See also</span></span>

[<span data-ttu-id="dd4c9-122">Descripción de la pertenencia a chat persistente</span><span class="sxs-lookup"><span data-stu-id="dd4c9-122">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)