---
title: Seleccionar los miembros permitidos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Creación y administración de salas de Chat persistente es mucho más sencillo con el uso correcto de las categorías. Un administrador de Chat persistente puede definir AllowedMembers y Creators para cada categoría y también se puede definir la configuración predeterminada de salón de chat y comportamientos que se aplicará a todos los salones de chat creados en la categoría. Los administradores de charla persistente crear y administrar las categorías mediante el panel de control o los cmdlets de Windows PowerShell.
ms.openlocfilehash: d7dcb2b6b3fb8712acfb6c35b134a4b15441454d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924629"
---
# <a name="select-allowed-members"></a><span data-ttu-id="b52b1-105">Seleccionar los miembros permitidos</span><span class="sxs-lookup"><span data-stu-id="b52b1-105">Select Allowed Members</span></span>

<span data-ttu-id="b52b1-106">Creación y administración de salas de Chat persistente es mucho más sencillo con el uso correcto de las categorías.</span><span class="sxs-lookup"><span data-stu-id="b52b1-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="b52b1-107">Un administrador de Chat persistente puede definir **AllowedMembers** y **Creators** para cada categoría y también se puede definir la configuración predeterminada de salón de chat y comportamientos que se aplicará a todos los salones de chat creados en la categoría.</span><span class="sxs-lookup"><span data-stu-id="b52b1-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="b52b1-108">Los administradores de charla persistente crear y administrar las categorías mediante el panel de control o los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b52b1-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="b52b1-109">Los usuarios, las unidades organizativas (UO) y los grupos de usuarios que se identifican como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría.</span><span class="sxs-lookup"><span data-stu-id="b52b1-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="b52b1-110">Después de crea la categoría, pueden elegir usuarios, unidades organizativas y grupos de usuarios de la lista de la categoría **AllowedMembers** como administradores de salones de chat y miembros para administrar y participar en el salón.</span><span class="sxs-lookup"><span data-stu-id="b52b1-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="b52b1-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="b52b1-111">Tasks that you can perform</span></span>

<span data-ttu-id="b52b1-112">En la página **Seleccionar los miembros permitidos** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="b52b1-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="b52b1-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="b52b1-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="b52b1-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="b52b1-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="b52b1-115">Para obtener información detallada sobre los distintos procedimientos que puede realizar mediante el uso de la Skype para el Panel de Control de servidor empresarial, vea [Administrar Skype para Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="b52b1-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="b52b1-116">Configuración de las categorías de los salones de chat</span><span class="sxs-lookup"><span data-stu-id="b52b1-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="b52b1-117">En **pertenencia**, en la sección **miembros permitidos** , agregue o quite usuarios y otras entidades de seguridad de los servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas y así sucesivamente) que se permiten que se agregará como miembros de los salones de chat que pertenecen a la categoría.</span><span class="sxs-lookup"><span data-stu-id="b52b1-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="b52b1-118">Las entidades de seguridad permitidas por una categoría pueden buscar los salones de la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón podrán encontrarlo en el directorio).</span><span class="sxs-lookup"><span data-stu-id="b52b1-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="b52b1-119">Para obtener información detallada sobre las características de servidor de Chat persistente y funciones, consulte [Información general de Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="b52b1-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="b52b1-120">Para obtener información detallada sobre cómo trabajar con las configuraciones de servidor de Chat persistente, consulte [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) en la documentación de implementación y [administración de Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="b52b1-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="b52b1-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b52b1-121">See also</span></span>

[<span data-ttu-id="b52b1-122">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="b52b1-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
