---
title: Seleccionar los miembros permitidos
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Creación y administración de salas de Chat persistentes es mucho más fácil con el uso correcto de las categorías. Un administrador de charla persistente puede definir AllowedMembers y creadores de cada categoría y también puede definir la configuración de salón de chat y comportamientos que se aplicarán a todos los salones de chat creados en la categoría. Los administradores de charla persistente crear y administrar categorías mediante el panel de control o los cmdlets de Windows PowerShell.
ms.openlocfilehash: 3ced3c26147038cfaba23a8e532982fcf8810592
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="select-allowed-members"></a><span data-ttu-id="77e80-105">Seleccionar los miembros permitidos</span><span class="sxs-lookup"><span data-stu-id="77e80-105">Select Allowed Members</span></span>
 
<span data-ttu-id="77e80-106">Creación y administración de salas de Chat persistentes es mucho más fácil con el uso correcto de las categorías.</span><span class="sxs-lookup"><span data-stu-id="77e80-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="77e80-107">Un administrador de charla persistente puede definir **AllowedMembers** y **creadores** de cada categoría y también puede definir la configuración de salón de chat y comportamientos que se aplicarán a todos los salones de chat creados en la categoría.</span><span class="sxs-lookup"><span data-stu-id="77e80-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="77e80-108">Los administradores de charla persistente crear y administrar categorías mediante el panel de control o los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e80-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
<span data-ttu-id="77e80-109">Los usuarios, las unidades organizativas (UO) y los grupos de usuarios que se identifican como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría.</span><span class="sxs-lookup"><span data-stu-id="77e80-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="77e80-110">Después de crea la categoría, pueden elegir usuarios, unidades organizativas y grupos de usuarios de la lista de **AllowedMembers** de la categoría como administradores de salón de chat y miembros para administrar y participar en el salón.</span><span class="sxs-lookup"><span data-stu-id="77e80-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="77e80-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="77e80-111">Tasks that you can perform</span></span>

<span data-ttu-id="77e80-112">En la página **Seleccionar los miembros permitidos** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="77e80-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>
  
- [<span data-ttu-id="77e80-113">Configurar categorías</span><span class="sxs-lookup"><span data-stu-id="77e80-113">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="77e80-114">Nuevas características de servidor de charla persistente</span><span class="sxs-lookup"><span data-stu-id="77e80-114">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
<span data-ttu-id="77e80-115">Para obtener más información acerca de los distintos procedimientos que se pueden realizar utilizando el Skype para Business Server Control Panel, vea [Administrar Skype para Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="77e80-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="77e80-116">Para configurar categorías para salones de chat</span><span class="sxs-lookup"><span data-stu-id="77e80-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="77e80-117">En la **pertenencia**, en la sección **miembros permitidos** , agregar o quitar usuarios y otras entidades de servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas etc.) que pueden agregarse como miembros de las salas de chat pertenecientes a la categoría.</span><span class="sxs-lookup"><span data-stu-id="77e80-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="77e80-118">Las entidades de seguridad permitidas por una categoría pueden buscar los salones de la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón podrán encontrarlo en el directorio).</span><span class="sxs-lookup"><span data-stu-id="77e80-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
  
### 

<span data-ttu-id="77e80-119">Para obtener más información acerca de capacidades y características de servidor de charla persistente, vea [Resumen de servidor persistente de charla](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) en la documentación de planeamiento.</span><span class="sxs-lookup"><span data-stu-id="77e80-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="77e80-120">Para obtener más información acerca de cómo trabajar con configuraciones de servidor de charla persistente, consulte [Configuración de servidor de charla persistente](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) en la documentación sobre la implementación y [administración de Lync Server 2013, servidor de Chat persistente](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="77e80-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="77e80-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="77e80-121">See also</span></span>

#### 

[<span data-ttu-id="77e80-122">Descripción de la pertenencia de Chat persistentes</span><span class="sxs-lookup"><span data-stu-id="77e80-122">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

