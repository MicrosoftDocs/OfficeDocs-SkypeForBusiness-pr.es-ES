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
description: Crear y administrar salas de chat persistente es mucho más fácil con el uso correcto de categorías. Un administrador de chat persistente puede definir AllowedMembers y Creators para cada categoría y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat creados en la categoría. Los administradores de chat persistente crean y administran categorías mediante el panel de control o Windows PowerShell cmdlets.
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829140"
---
# <a name="select-allowed-members"></a><span data-ttu-id="7b601-105">Seleccionar los miembros permitidos</span><span class="sxs-lookup"><span data-stu-id="7b601-105">Select Allowed Members</span></span>

<span data-ttu-id="7b601-106">Crear y administrar salas de chat persistente es mucho más fácil con el uso correcto de categorías.</span><span class="sxs-lookup"><span data-stu-id="7b601-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="7b601-107">Un administrador de chat persistente puede definir **AllowedMembers** y Creators para cada categoría y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat **creados** en la categoría.</span><span class="sxs-lookup"><span data-stu-id="7b601-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="7b601-108">Los administradores de chat persistente crean y administran categorías mediante el panel de control o Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7b601-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="7b601-109">Los usuarios, las unidades organizativas (OU) y los grupos de usuarios identificados como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría.</span><span class="sxs-lookup"><span data-stu-id="7b601-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="7b601-110">Una vez creada la categoría, pueden elegir usuarios, us y grupos de usuarios de la lista **AllowedMembers** de la categoría como administradores y miembros del salón de chat para administrar y participar en el salón.</span><span class="sxs-lookup"><span data-stu-id="7b601-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="7b601-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="7b601-111">Tasks that you can perform</span></span>

<span data-ttu-id="7b601-112">Puede realizar las siguientes tareas en la página **Seleccionar los miembros permitidos**:</span><span class="sxs-lookup"><span data-stu-id="7b601-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="7b601-113">Configurar categorías</span><span class="sxs-lookup"><span data-stu-id="7b601-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="7b601-114">Nuevas características de servidor de conversaciones en grupo</span><span class="sxs-lookup"><span data-stu-id="7b601-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="7b601-115">Para obtener más información sobre los distintos procedimientos que puede realizar con el Panel de control de Skype Empresarial Server, consulte Administrar Skype Empresarial [Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="7b601-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="7b601-116">Para configurar categorías para salones de chat</span><span class="sxs-lookup"><span data-stu-id="7b601-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="7b601-117">En Pertenencia **,** en la sección Miembros permitidos, agregue o quite usuarios y otras entidades de seguridad de Servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, entre otros) que puedan agregarse como miembros de los salón de chat que pertenecen a la categoría. </span><span class="sxs-lookup"><span data-stu-id="7b601-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="7b601-118">Los elementos principales permitidos por una categoría pueden buscar salones en la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón pueden buscarlo en el directorio).</span><span class="sxs-lookup"><span data-stu-id="7b601-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="7b601-119">Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte Información general sobre el servidor [de chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="7b601-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="7b601-120">Para obtener más información sobre cómo trabajar con configuraciones de servidor de chat persistente, consulte [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="7b601-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b601-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b601-121">See also</span></span>

[<span data-ttu-id="7b601-122">Descripción de la pertenencia al chat persistente</span><span class="sxs-lookup"><span data-stu-id="7b601-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
