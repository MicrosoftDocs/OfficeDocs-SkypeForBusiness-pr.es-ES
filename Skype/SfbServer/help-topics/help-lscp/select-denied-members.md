---
title: Seleccionar miembros denegados
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
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Un administrador de chat persistente puede crear y administrar categorías de salón de chat. Como parte de la creación y administración de categorías de salón de chat, un administrador de chat persistente puede configurar entidades de seguridad (grupos/contenedores/usuarios de Servicios de dominio de Active Directory) que tienen acceso a ser miembros o creadores de los salas de chat de una categoría determinada. Un administrador de chat persistente también puede agregar DeniedMembers a una categoría y se convierten en exclusiones explícitas en la lista de permitidos. DeniedMembers invalida lo que hay en AllowedMembers.
ms.openlocfilehash: c5f942723937fe2da28025fba5da1fc7ee121c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814580"
---
# <a name="select-denied-members"></a><span data-ttu-id="52b05-106">Seleccionar miembros denegados</span><span class="sxs-lookup"><span data-stu-id="52b05-106">Select Denied Members</span></span>

<span data-ttu-id="52b05-107">Un administrador de chat persistente puede crear y administrar categorías de salón de chat.</span><span class="sxs-lookup"><span data-stu-id="52b05-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="52b05-108">Como parte de la creación y administración de categorías de salón de chat, un administrador de chat persistente puede configurar entidades de seguridad (grupos/contenedores/usuarios de Servicios de dominio de Active Directory) que tienen acceso a ser miembros o creadores de los salas de chat de una categoría determinada.</span><span class="sxs-lookup"><span data-stu-id="52b05-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="52b05-109">Un administrador de chat persistente también puede agregar DeniedMembers a una categoría y se convierten en exclusiones explícitas en la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="52b05-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="52b05-110">DeniedMembers invalida lo que hay en AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="52b05-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="52b05-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="52b05-111">Tasks that you can perform</span></span>

<span data-ttu-id="52b05-112">Puede realizar las siguientes tareas en la página **Seleccionar miembros denegados**:</span><span class="sxs-lookup"><span data-stu-id="52b05-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="52b05-113">Configurar categorías</span><span class="sxs-lookup"><span data-stu-id="52b05-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="52b05-114">Nuevas características de servidor de conversaciones en grupo</span><span class="sxs-lookup"><span data-stu-id="52b05-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="52b05-115">Para obtener más información sobre los distintos procedimientos que puede realizar con el Panel de control de Skype Empresarial Server, consulte Administrar Skype Empresarial [Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="52b05-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="52b05-116">Para configurar categorías para salones de chat</span><span class="sxs-lookup"><span data-stu-id="52b05-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="52b05-117">En **Pertenencia**, en la **sección Miembros** denegados, agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con miembros denegados de la sala.</span><span class="sxs-lookup"><span data-stu-id="52b05-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="52b05-118">Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte Información general sobre el servidor [de chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="52b05-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="52b05-119">Para obtener más información sobre cómo trabajar con configuraciones de servidor de chat persistente, consulte [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="52b05-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="52b05-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="52b05-120">See also</span></span>

[<span data-ttu-id="52b05-121">Descripción de la pertenencia al chat persistente</span><span class="sxs-lookup"><span data-stu-id="52b05-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
