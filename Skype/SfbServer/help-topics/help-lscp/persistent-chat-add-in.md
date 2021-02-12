---
title: Complemento de chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Puede usar la sección Complemento de la página chat persistente para asociar direcciones URL con los salón de chat persistente. Estas direcciones URL aparecen en el cliente en el salón de chat en el panel de extensibilidad de la conversación. Un administrador debe agregar complementos a la lista de complementos registrados, y los administradores/creadores de salas de chat deben asociar los salas con uno de los complementos registrados para que los usuarios puedan ver esta actualización en su cliente.
ms.openlocfilehash: 306cd54864400362a869db34d79f1fe6241d81ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803780"
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="4e0f9-105">Complemento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="4e0f9-105">Persistent Chat Add-in</span></span>

<span data-ttu-id="4e0f9-106">Puede usar la sección **Complemento de** la página **chat** persistente para asociar direcciones URL con los salón de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="4e0f9-107">Estas direcciones URL aparecen en el cliente en el salón de chat en el panel de extensibilidad de la conversación.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="4e0f9-108">Un administrador debe agregar complementos a la lista de complementos registrados, y los administradores/creadores de salas de chat deben asociar los salas con uno de los complementos registrados para que los usuarios puedan ver esta actualización en su cliente.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="4e0f9-109">Los complementos se usan para ampliar la experiencia en el salón.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="4e0f9-110">Un complemento típico puede incluir una dirección URL que apunta a una aplicación de Silverlight que intercepta cuando se publica un ticker de bolsa en un salón de chat y muestra el historial de acciones en el panel de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="4e0f9-111">Otros ejemplos incluyen la incrustación de una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir determinado contexto compartido, como "Prioridades" o "Tema del día".</span><span class="sxs-lookup"><span data-stu-id="4e0f9-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="4e0f9-112">Para crear complementos para los salón de chat persistente, consulte Configurar complementos para los salas de chat persistente en [Skype Empresarial Server 2015.](../../manage/persistent-chat/configure-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="4e0f9-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="4e0f9-113">Si es un administrador de chat persistente, puede crear complementos mediante el panel de control o los cmdlets Windows PowerShell usuario.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="4e0f9-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="4e0f9-114">Tasks that you can perform</span></span>

<span data-ttu-id="4e0f9-115">Puede realizar las siguientes tareas en la página **Complemento**:</span><span class="sxs-lookup"><span data-stu-id="4e0f9-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="4e0f9-116">Configurar complementos para los salas de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4e0f9-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="4e0f9-117">Para configurar complementos para salones de chat</span><span class="sxs-lookup"><span data-stu-id="4e0f9-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="4e0f9-118">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="4e0f9-119">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="4e0f9-120">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="4e0f9-121">Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control, consulte [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span><span class="sxs-lookup"><span data-stu-id="4e0f9-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="4e0f9-122">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Complemento**.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="4e0f9-123">Para varias implementaciones de grupos de servidores de chat persistente, seleccione el grupo adecuado en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="4e0f9-124">En la página **Complemento**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="4e0f9-125">En **Seleccionar un servicio,** seleccione el servicio correspondiente al grupo de servidores de chat persistente donde necesita crear el complemento.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="4e0f9-126">Los complementos no se pueden mover de un grupo a otro ni compartir entre grupos distintos.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="4e0f9-127">En **Nuevo complemento**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e0f9-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="4e0f9-128">En **Nombre**, especifique un nombre para el nuevo complemento.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="4e0f9-p107">En **Dirección URL**, especifique la dirección URL que se va a asociar con el complemento. Las direcciones URL están limitadas a los protocolos http y https.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="4e0f9-131">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4e0f9-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e0f9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e0f9-132">See also</span></span>

<span data-ttu-id="4e0f9-133">Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="4e0f9-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>


