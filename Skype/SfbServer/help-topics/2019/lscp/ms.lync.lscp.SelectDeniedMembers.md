---
title: Seleccionar miembros denegados
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Un administrador de Chat persistente puede crear y administrar categorías de salón de chat. Como parte de la creación y administración de categorías de salón de chat, un administrador de Chat persistente puede configurar entidades de seguridad (los servicios de dominio de Active Directory grupos/contenedores o usuarios) que tienen acceso a ser miembros o los creadores de salones de chat de una categoría determinada. Un administrador de Chat persistente también puede agregar DeniedMembers a una categoría y se convierten en exclusiones explícitas a la lista de permitidos. DeniedMembers reemplazar lo que aparece en AllowedMembers.
ms.openlocfilehash: 98e57342296f181971c799bafa1b77eccd24b509
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2018
---
# <a name="select-denied-members"></a><span data-ttu-id="21eee-106">Seleccionar miembros denegados</span><span class="sxs-lookup"><span data-stu-id="21eee-106">Select Denied Members</span></span>
 
<span data-ttu-id="21eee-107">Un administrador de Chat persistente puede crear y administrar categorías de salón de chat.</span><span class="sxs-lookup"><span data-stu-id="21eee-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="21eee-108">Como parte de la creación y administración de categorías de salón de chat, un administrador de Chat persistente puede configurar entidades de seguridad (los servicios de dominio de Active Directory grupos/contenedores o usuarios) que tienen acceso a ser miembros o los creadores de salones de chat de una categoría determinada.</span><span class="sxs-lookup"><span data-stu-id="21eee-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="21eee-109">Un administrador de Chat persistente también puede agregar DeniedMembers a una categoría y se convierten en exclusiones explícitas a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="21eee-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="21eee-110">DeniedMembers reemplazar lo que aparece en AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="21eee-110">DeniedMembers override what's in AllowedMembers.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="21eee-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="21eee-111">Tasks that you can perform</span></span>

<span data-ttu-id="21eee-112">En la página **Seleccionar miembros denegados** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="21eee-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>
  
- [<span data-ttu-id="21eee-113">Configuración de categorías</span><span class="sxs-lookup"><span data-stu-id="21eee-113">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="21eee-114">Nuevas características de servidor de Chat en grupo</span><span class="sxs-lookup"><span data-stu-id="21eee-114">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
<span data-ttu-id="21eee-115">Para obtener información detallada sobre los distintos procedimientos que puede realizar mediante el uso de la Skype para el Panel de Control de servidor empresarial, vea [Administrar Skype para Business Server 2015](../../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="21eee-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../../manage/manage.md).</span></span>
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="21eee-116">Para configurar categorías para salones de chat</span><span class="sxs-lookup"><span data-stu-id="21eee-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="21eee-117">En **pertenencia**, en la sección **miembros denegados** , agregue o quite usuarios y otras entidades de seguridad de Active Directory asociados con miembros denegados del salón.</span><span class="sxs-lookup"><span data-stu-id="21eee-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
  
### 

<span data-ttu-id="21eee-118">Para obtener información detallada sobre las características de servidor de Chat persistente y funciones, consulte [Información general de Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="21eee-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="21eee-119">Para obtener información detallada sobre cómo trabajar con las configuraciones de servidor de Chat persistente, consulte [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) en la documentación de implementación y [administración de Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="21eee-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="21eee-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="21eee-120">See also</span></span>

#### 

[<span data-ttu-id="21eee-121">Descripción de la pertenencia de Chat en grupo</span><span class="sxs-lookup"><span data-stu-id="21eee-121">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

