---
title: Grupos de respuesta Crear nuevo o editar grupo de agentes existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: Los grupos de agentes definen quién puede responder las llamadas a un grupo de respuesta (conocido como agentes) y la configuración que se aplica a todos los agentes del grupo.
ms.openlocfilehash: 944cd48745a2524ccfcd795d9edc60e806859301
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118969"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="df664-103">Grupos de respuesta: Crear nuevos o editar los grupos de agentes existentes</span><span class="sxs-lookup"><span data-stu-id="df664-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="df664-104">Los grupos de agentes definen quién puede responder las llamadas a un grupo de respuesta (conocido como agentes) y la configuración que se aplica a todos los agentes del grupo.</span><span class="sxs-lookup"><span data-stu-id="df664-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="df664-105">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="df664-105">UI Reference</span></span>

<span data-ttu-id="df664-106">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="df664-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="df664-107">**Nombre** Cada grupo de agentes requiere un nombre único.</span><span class="sxs-lookup"><span data-stu-id="df664-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="df664-108">Use un nombre descriptivo que identifique la función del grupo.</span><span class="sxs-lookup"><span data-stu-id="df664-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="df664-109">Por ejemplo, Servicio de asistencia.</span><span class="sxs-lookup"><span data-stu-id="df664-109">For example, Help Desk.</span></span>

- <span data-ttu-id="df664-110">**Descripción** Este campo es opcional.</span><span class="sxs-lookup"><span data-stu-id="df664-110">**Description** This field is optional.</span></span> <span data-ttu-id="df664-111">Úselo para proporcionar detalles sobre el grupo.</span><span class="sxs-lookup"><span data-stu-id="df664-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="df664-112">**Directiva de participación** Especifique la forma en que los agentes deben iniciar sesión en el grupo de respuesta:</span><span class="sxs-lookup"><span data-stu-id="df664-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="df664-113">Seleccione **Informal** para especificar que los agentes del grupo no necesitan iniciar y cerrar sesión. Los agentes informales inician sesión automáticamente cuando inician sesión.</span><span class="sxs-lookup"><span data-stu-id="df664-113">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in.</span></span> <span data-ttu-id="df664-114">El valor predeterminado es **Informal**.</span><span class="sxs-lookup"><span data-stu-id="df664-114">The default is **Informal**.</span></span>

  - <span data-ttu-id="df664-115">Seleccione **Formal** para especificar que los agentes del grupo deben iniciar y cerrar sesión. Al seleccionar esta opción, los agentes hacen clic en un elemento de menú del cliente para abrir un explorador y mostrar una consola de página web para iniciar y salir.</span><span class="sxs-lookup"><span data-stu-id="df664-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="df664-116">**Hora de alerta (segundos)** Especifique el número de segundos para llamar a un agente antes de ofrecer la llamada al siguiente agente disponible.</span><span class="sxs-lookup"><span data-stu-id="df664-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="df664-117">El valor debe ser de al menos 10 segundos e inferior a 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="df664-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="df664-118">El valor predeterminado es 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="df664-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="df664-119">**Método de enrutamiento** Seleccione el método para determinar el orden en que los agentes reciben llamadas:</span><span class="sxs-lookup"><span data-stu-id="df664-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="df664-120">Seleccione **Máxima inactividad** para ofrecer una llamada nueva primero al agente que ha estado más tiempo inactivo (el que más tiempo ha estado **Disponible** o **Inactivo**).</span><span class="sxs-lookup"><span data-stu-id="df664-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="df664-p105">Seleccione **Enrutamiento paralelo** para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo. La llamada se envía al primer agente que la acepte.</span><span class="sxs-lookup"><span data-stu-id="df664-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="df664-123">Seleccione **Round robin** para ofrecer una llamada nueva a un agente cada vez.</span><span class="sxs-lookup"><span data-stu-id="df664-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="df664-124">Seleccione **Enrutamiento en serie** para ofrecer siempre una llamada nueva a los agentes en el orden en que aparecen en la lista **Agentes**.</span><span class="sxs-lookup"><span data-stu-id="df664-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="df664-125">Seleccione **Operador** para ofrecer una nueva llamada a todos los agentes que han iniciado sesión y a la aplicación grupo de respuesta al mismo tiempo, independientemente de su presencia actual.</span><span class="sxs-lookup"><span data-stu-id="df664-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="df664-126">Los operadores y usuarios cliente configurados como agentes pueden ver todas las llamadas que están en espera y pueden responder llamadas en espera en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="df664-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="df664-127">La llamada se envía al primer agente que la acepta y los demás operadores y usuarios ya no ven la llamada.</span><span class="sxs-lookup"><span data-stu-id="df664-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="df664-128">**Agentes** Seleccione los usuarios que deben ser agentes para el grupo de respuesta de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="df664-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="df664-129">Seleccione **Usar una lista de distribución de correo electrónico existente** para usar una lista de distribución de Exchange.</span><span class="sxs-lookup"><span data-stu-id="df664-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="df664-130">Escriba la dirección de correo electrónico de la lista de distribución en **Dirección de la lista de distribución**.</span><span class="sxs-lookup"><span data-stu-id="df664-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df664-p108">Solo puede seleccionar una lista de distribución por grupo de agentes. Si la lista de distribución incluye listas de distribución anidadas, estas no se incluirán en el grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="df664-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df664-133">El orden en que los agentes se muestran en la lista de distribución afecta al orden en que los agentes reciben llamadas para round robin y el enrutamiento en serie.</span><span class="sxs-lookup"><span data-stu-id="df664-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df664-134">Las pertenencias ocultas o listas ocultas pueden ser visibles para los administradores o usuarios del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="df664-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="df664-135">Para obtener más información, [vea Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span><span class="sxs-lookup"><span data-stu-id="df664-135">For details, see [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="df664-p110">Seleccione **Definir un grupo de agentes personalizado** para seleccionar los usuarios que desee asignar como agentes para el grupo de respuesta. Haga clic en **Seleccionar** para agregar un agente a la lista. Haga clic en **Quitar** para eliminar un agente seleccionado de la lista.</span><span class="sxs-lookup"><span data-stu-id="df664-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="df664-p111">Las flechas arriba y abajo mueven un agente seleccionado hacia arriba y hacia abajo en la lista de agentes. El orden de los agentes afecta al orden en que los agentes reciben llamadas para round robin y el enrutamiento en serie.</span><span class="sxs-lookup"><span data-stu-id="df664-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="df664-141">Para obtener más información sobre las características y capacidades del grupo de respuesta, vea [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="df664-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="df664-142">Para obtener detalles sobre cómo trabajar con grupos de agentes, vea [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="df664-142">For details about working with agent groups, see [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) in the Operations documentation.</span></span>