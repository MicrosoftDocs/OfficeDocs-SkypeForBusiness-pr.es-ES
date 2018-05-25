---
title: Complemento de chat persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Puede usar la sección de la página de Chat persistente para asociar las direcciones URL a salones de Chat persistente. Estas direcciones URL aparecen en el cliente, en el salón de chat, en el panel de extensibilidad de la conversación. Un administrador necesita agregar complementos a la lista de complementos registrados, y los administradores/creadores del salón de chat necesitan asociar los salones a uno de los complementos registrados para que los clientes puedan ver esta actualización en su cliente.
ms.openlocfilehash: 8d4a74571b2d86295a0f7ffdff986f112380ffd7
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="16aba-105">Complemento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="16aba-105">Persistent Chat Add-in</span></span>
 
<span data-ttu-id="16aba-106">Puede usar **la sección de la página de **Chat persistente** ** para asociar las direcciones URL a salones de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="16aba-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="16aba-107">Estas direcciones URL aparecen en el cliente, en el salón de chat, en el panel de extensibilidad de la conversación.</span><span class="sxs-lookup"><span data-stu-id="16aba-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="16aba-108">Un administrador necesita agregar complementos a la lista de complementos registrados, y los administradores/creadores del salón de chat necesitan asociar los salones a uno de los complementos registrados para que los clientes puedan ver esta actualización en su cliente.</span><span class="sxs-lookup"><span data-stu-id="16aba-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>
  
<span data-ttu-id="16aba-109">Los complementos sirven para ampliar la experiencia en el salón.</span><span class="sxs-lookup"><span data-stu-id="16aba-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="16aba-110">Un complemento típico puede incluir una dirección URL que apunte a una aplicación de Silverlight que intercepta cuando un tablero de cotizaciones se registra en un salón de chat y muestra el historial de cotizaciones en el panel de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="16aba-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="16aba-111">Otros ejemplos serían incrustar una dirección URL de OneNote 2013 en el salón de chat como complemento para incluir contexto compartido, como "Lista de prioridades" o "Tema del día".</span><span class="sxs-lookup"><span data-stu-id="16aba-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
<span data-ttu-id="16aba-112">Para crear complementos para salones de Chat persistente, vea [configurar complementos para salones de Chat persistente en Skype para Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="16aba-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="16aba-113">Si es un administrador de Chat persistente, puede crear complementos mediante el panel de control o los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16aba-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="16aba-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="16aba-114">Tasks that you can perform</span></span>

<span data-ttu-id="16aba-115">En la página **Complemento** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="16aba-115">You can perform the following tasks on the **Add-in** page:</span></span>
  
- [<span data-ttu-id="16aba-116">Configurar complementos para salones de Chat persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="16aba-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)
    
## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="16aba-117">Para configurar complementos para salones de chat</span><span class="sxs-lookup"><span data-stu-id="16aba-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="16aba-118">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="16aba-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
1. <span data-ttu-id="16aba-119">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="16aba-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="16aba-120">Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="16aba-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="16aba-121">Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el panel de control, vea [Open Lync Server Administrative Tools](http://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span><span class="sxs-lookup"><span data-stu-id="16aba-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](http://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>
    
3. <span data-ttu-id="16aba-122">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Complemento**.</span><span class="sxs-lookup"><span data-stu-id="16aba-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="16aba-123">Para implementaciones de varios grupos de servidores de Chat persistente, seleccione el grupo adecuado de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="16aba-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="16aba-124">En la página **Complemento**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="16aba-124">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="16aba-125">En **Seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de Chat persistente que necesita para crear el complemento.</span><span class="sxs-lookup"><span data-stu-id="16aba-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="16aba-126">Los complementos no se pueden mover de un grupo a otro ni compartir entre diferentes grupos.</span><span class="sxs-lookup"><span data-stu-id="16aba-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="16aba-127">Haga lo siguiente en **Complemento nuevo**:</span><span class="sxs-lookup"><span data-stu-id="16aba-127">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="16aba-128">En **Nombre**, especifique un nombre para el nuevo complemento.</span><span class="sxs-lookup"><span data-stu-id="16aba-128">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="16aba-p107">En **URL**, especifique la dirección URL que se va a asociar al complemento. Las direcciones URL se limitan a protocolos http y https.</span><span class="sxs-lookup"><span data-stu-id="16aba-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>
    
7. <span data-ttu-id="16aba-131">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="16aba-131">Click **Commit**.</span></span>
    
### 

<span data-ttu-id="16aba-132">Para obtener información detallada sobre las características de servidor de Chat persistente y funciones, vea [Planear Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Administrar Persistent Chat Server en Skype para Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="16aba-132">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

