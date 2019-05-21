---
title: Seleccionar los miembros permitidos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Crear y administrar salones de chat persistentes es mucho más fácil con el uso correcto de categorías. Un administrador de chat persistente puede definir AllowedMembers y creadores de cada categoría, y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salones de chat creados en la categoría. Los administradores de chats persistentes crean y administran categorías con el panel de control o los cmdlets de Windows PowerShell.
ms.openlocfilehash: dedc022853738ad02b4da2ce0ab2cdc7ccbee576
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282255"
---
# <a name="select-allowed-members"></a><span data-ttu-id="0e19a-105">Seleccionar los miembros permitidos</span><span class="sxs-lookup"><span data-stu-id="0e19a-105">Select Allowed Members</span></span>

<span data-ttu-id="0e19a-106">Crear y administrar salones de chat persistentes es mucho más fácil con el uso correcto de categorías.</span><span class="sxs-lookup"><span data-stu-id="0e19a-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="0e19a-107">Un administrador de chat persistente puede definir **AllowedMembers** y **creadores** de cada categoría, y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salones de chat creados en la categoría.</span><span class="sxs-lookup"><span data-stu-id="0e19a-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="0e19a-108">Los administradores de chats persistentes crean y administran categorías con el panel de control o los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e19a-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="0e19a-109">Los usuarios, las unidades organizativas (UO) y los grupos de usuarios que se identifican como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría.</span><span class="sxs-lookup"><span data-stu-id="0e19a-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="0e19a-110">Después de crear la categoría, pueden elegir usuarios, unidades organizativas y grupos de usuarios de la lista de **AllowedMembers** de la categoría como administradores y miembros de los salones de chat para administrar y participar en el salón.</span><span class="sxs-lookup"><span data-stu-id="0e19a-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="0e19a-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="0e19a-111">Tasks that you can perform</span></span>

<span data-ttu-id="0e19a-112">En la página **Seleccionar los miembros permitidos** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="0e19a-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="0e19a-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="0e19a-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="0e19a-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="0e19a-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="0e19a-115">Para obtener más información sobre los distintos procedimientos que puede realizar con el panel de control de Skype empresarial Server, consulte [Manage Skype empresarial server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="0e19a-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="0e19a-116">Configuración de las categorías de los salones de chat</span><span class="sxs-lookup"><span data-stu-id="0e19a-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="0e19a-117">En **pertenencia**, en la sección **miembros permitidos** , agregar o quitar usuarios y otros principios de los servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, etc.) que se pueden agregar como miembros de salones de chat pertenece a la categoría.</span><span class="sxs-lookup"><span data-stu-id="0e19a-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="0e19a-118">Las entidades de seguridad permitidas por una categoría pueden buscar los salones de la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón podrán encontrarlo en el directorio).</span><span class="sxs-lookup"><span data-stu-id="0e19a-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="0e19a-119">Para obtener más información sobre las funciones y características del servidor de chat persistentes, vea [información general sobre el servidor de chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="0e19a-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="0e19a-120">Para obtener más información sobre cómo trabajar con configuraciones de servidor de chat persistentes, vea [configurar el servidor de chat persistente](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) en la documentación de implementación y [administrar Lync Server 2013, servidor de chat persistente](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="0e19a-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e19a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e19a-121">See also</span></span>

[<span data-ttu-id="0e19a-122">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="0e19a-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
