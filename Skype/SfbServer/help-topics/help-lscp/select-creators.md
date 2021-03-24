---
title: Seleccionar creadores
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
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: Crear y administrar salas de chat persistente es mucho más fácil con el uso correcto de categorías. Un administrador de chat persistente puede definir AllowedMembers y Creators para cada categoría y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat creados en la categoría. Los administradores de chat persistente crean y administran categorías mediante el Panel de control de Skype Empresarial Server o Windows PowerShell cmdlets.
ms.openlocfilehash: 7d98ff058251b8bd14eb37a0ae5ba633f5a99c48
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107956"
---
# <a name="select-creators"></a><span data-ttu-id="96e7a-105">Seleccionar creadores</span><span class="sxs-lookup"><span data-stu-id="96e7a-105">Select Creators</span></span>

<span data-ttu-id="96e7a-106">Crear y administrar salas de chat persistente es mucho más fácil con el uso correcto de categorías.</span><span class="sxs-lookup"><span data-stu-id="96e7a-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="96e7a-107">Un administrador de chat persistente puede definir **AllowedMembers** y Creators para cada categoría y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat **creados** en la categoría.</span><span class="sxs-lookup"><span data-stu-id="96e7a-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="96e7a-108">Los administradores de chat persistente crean y administran categorías mediante el Panel de control de Skype Empresarial Server o Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="96e7a-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="96e7a-109">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="96e7a-109">Tasks that you can perform</span></span>

<span data-ttu-id="96e7a-110">Puede realizar las siguientes tareas en la página **Seleccionar creadores**:</span><span class="sxs-lookup"><span data-stu-id="96e7a-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="96e7a-111">Configurar categorías</span><span class="sxs-lookup"><span data-stu-id="96e7a-111">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="96e7a-112">Nuevas características de servidor de conversaciones en grupo</span><span class="sxs-lookup"><span data-stu-id="96e7a-112">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="96e7a-113">Para obtener información detallada sobre los diferentes procedimientos que puede realizar mediante el Panel de control de Skype Empresarial Server, vea [Manage Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="96e7a-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="96e7a-114">Para configurar categorías para salones de chat</span><span class="sxs-lookup"><span data-stu-id="96e7a-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="96e7a-115">En **Pertenencia**, en la **sección Creadores,** agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con creadores para la categoría.</span><span class="sxs-lookup"><span data-stu-id="96e7a-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="96e7a-116">Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de salones de chat.</span><span class="sxs-lookup"><span data-stu-id="96e7a-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="96e7a-117">Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="96e7a-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="96e7a-118">Para obtener más información sobre cómo trabajar con configuraciones de servidor de chat persistente, consulte [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) en la documentación sobre implementación y [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="96e7a-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="96e7a-119">Ver también</span><span class="sxs-lookup"><span data-stu-id="96e7a-119">See also</span></span>

[<span data-ttu-id="96e7a-120">Descripción de la pertenencia a chat persistente</span><span class="sxs-lookup"><span data-stu-id="96e7a-120">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)

[<span data-ttu-id="96e7a-121">Uso de categorías para administrar el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="96e7a-121">Using Categories to Administer Persistent Chat Server</span></span>](/previous-versions/office/lync-server-2013/using-categories-to-administer-persistent-chat-server)

[<span data-ttu-id="96e7a-122">Mover un salón de chat de una categoría a otra</span><span class="sxs-lookup"><span data-stu-id="96e7a-122">Moving a Chat Room from One Category to Another</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-moving-a-chat-room-from-one-category-to-another)

[<span data-ttu-id="96e7a-123">Creación o edición de un salón nuevo</span><span class="sxs-lookup"><span data-stu-id="96e7a-123">Creating or Editing a New Room</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-editing-a-new-room)