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
ms.openlocfilehash: 9fc8bf615de02a4c9eefcd204c832c5c8691eb7e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821960"
---
# <a name="select-creators"></a><span data-ttu-id="7a692-105">Seleccionar creadores</span><span class="sxs-lookup"><span data-stu-id="7a692-105">Select Creators</span></span>

<span data-ttu-id="7a692-106">Crear y administrar salas de chat persistente es mucho más fácil con el uso correcto de categorías.</span><span class="sxs-lookup"><span data-stu-id="7a692-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="7a692-107">Un administrador de chat persistente puede definir **AllowedMembers** y Creators para cada categoría y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat **creados** en la categoría.</span><span class="sxs-lookup"><span data-stu-id="7a692-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="7a692-108">Los administradores de chat persistente crean y administran categorías mediante el Panel de control de Skype Empresarial Server o Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7a692-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="7a692-109">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="7a692-109">Tasks that you can perform</span></span>

<span data-ttu-id="7a692-110">Puede realizar las siguientes tareas en la página **Seleccionar creadores**:</span><span class="sxs-lookup"><span data-stu-id="7a692-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="7a692-111">Configurar categorías</span><span class="sxs-lookup"><span data-stu-id="7a692-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="7a692-112">Nuevas características de servidor de conversaciones en grupo</span><span class="sxs-lookup"><span data-stu-id="7a692-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="7a692-113">Para obtener más información sobre los distintos procedimientos que puede realizar con el Panel de control de Skype Empresarial Server, consulte Administrar Skype Empresarial [Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="7a692-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="7a692-114">Para configurar categorías para salones de chat</span><span class="sxs-lookup"><span data-stu-id="7a692-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="7a692-115">En **Pertenencia**, en la **sección** Creadores, agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con los creadores de la categoría.</span><span class="sxs-lookup"><span data-stu-id="7a692-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="7a692-116">Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de salones de chat.</span><span class="sxs-lookup"><span data-stu-id="7a692-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="7a692-117">Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte Información general sobre el servidor [de chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="7a692-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="7a692-118">Para obtener más información sobre cómo trabajar con configuraciones de servidor de chat persistente, consulte [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="7a692-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a692-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a692-119">See also</span></span>

[<span data-ttu-id="7a692-120">Descripción de la pertenencia al chat persistente</span><span class="sxs-lookup"><span data-stu-id="7a692-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="7a692-121">Uso de categorías para administrar el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="7a692-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="7a692-122">Mover un salón de chat de una categoría a otra</span><span class="sxs-lookup"><span data-stu-id="7a692-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="7a692-123">Creación o edición de un salón nuevo</span><span class="sxs-lookup"><span data-stu-id="7a692-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
