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
description: Un administrador de chat persistente puede crear y administrar categorías de salón de chat. Como parte de la creación y administración de categorías de salón de chat, un administrador de chat persistente puede configurar entidades de seguridad (grupos/contenedores/usuarios de servicios de dominio de Active Directory) que tienen acceso a ser miembros o creadores de salas de chat de una categoría determinada. Un administrador de chat persistente también puede agregar DeniedMembers a una categoría y estas se convierten en exclusiones explícitas en la lista permitida. DeniedMembers invalida lo que hay en AllowedMembers.
ms.openlocfilehash: 5a31716c2fae15c6216ed050b543673479415a76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107966"
---
# <a name="select-denied-members"></a><span data-ttu-id="394d5-106">Seleccionar miembros denegados</span><span class="sxs-lookup"><span data-stu-id="394d5-106">Select Denied Members</span></span>

<span data-ttu-id="394d5-107">Un administrador de chat persistente puede crear y administrar categorías de salón de chat.</span><span class="sxs-lookup"><span data-stu-id="394d5-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="394d5-108">Como parte de la creación y administración de categorías de salón de chat, un administrador de chat persistente puede configurar entidades de seguridad (grupos/contenedores/usuarios de servicios de dominio de Active Directory) que tienen acceso a ser miembros o creadores de salas de chat de una categoría determinada.</span><span class="sxs-lookup"><span data-stu-id="394d5-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="394d5-109">Un administrador de chat persistente también puede agregar DeniedMembers a una categoría y estas se convierten en exclusiones explícitas en la lista permitida.</span><span class="sxs-lookup"><span data-stu-id="394d5-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="394d5-110">DeniedMembers invalida lo que hay en AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="394d5-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="394d5-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="394d5-111">Tasks that you can perform</span></span>

<span data-ttu-id="394d5-112">Puede realizar las siguientes tareas en la página **Seleccionar miembros denegados**:</span><span class="sxs-lookup"><span data-stu-id="394d5-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="394d5-113">Configurar categorías</span><span class="sxs-lookup"><span data-stu-id="394d5-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="394d5-114">Nuevas características de servidor de conversaciones en grupo</span><span class="sxs-lookup"><span data-stu-id="394d5-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="394d5-115">Para obtener información detallada sobre los diferentes procedimientos que puede realizar mediante el Panel de control de Skype Empresarial Server, vea [Manage Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="394d5-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="394d5-116">Para configurar categorías para salones de chat</span><span class="sxs-lookup"><span data-stu-id="394d5-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="394d5-117">En **Pertenencia**, en la sección **Miembros** denegados, agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con miembros que se denieguen de la sala.</span><span class="sxs-lookup"><span data-stu-id="394d5-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="394d5-118">Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="394d5-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="394d5-119">Para obtener más información sobre cómo trabajar con configuraciones de servidor de chat persistente, consulte [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) en la documentación sobre implementación y [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="394d5-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="394d5-120">Ver también</span><span class="sxs-lookup"><span data-stu-id="394d5-120">See also</span></span>

[<span data-ttu-id="394d5-121">Descripción de la pertenencia a chat persistente</span><span class="sxs-lookup"><span data-stu-id="394d5-121">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)