---
title: Grupos de respuesta creación nuevos o edición grupo de agentes existentes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: Los grupos de agentes definen quién puede responder las llamadas a un grupo de respuesta (conocido como agentes) y la configuración que se aplica a todos los agentes del grupo.
ms.openlocfilehash: 044fd86109b7c413d414b174a5f9527e8c535d42
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215209"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="2b9a5-103">Grupos de respuesta: Crear nuevo o editar existente</span><span class="sxs-lookup"><span data-stu-id="2b9a5-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="2b9a5-104">Los grupos de agentes definen quién puede responder las llamadas a un grupo de respuesta (conocido como agentes) y la configuración que se aplica a todos los agentes del grupo.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2b9a5-105">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="2b9a5-105">UI Reference</span></span>

<span data-ttu-id="2b9a5-106">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2b9a5-107">**Nombre** Cada grupo de agentes requiere un nombre único.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="2b9a5-108">Use un nombre descriptivo que identifica la función del grupo.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="2b9a5-109">Por ejemplo, Help Desk.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-109">For example, Help Desk.</span></span>

- <span data-ttu-id="2b9a5-110">**Descripción** Este campo es opcional.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-110">**Description** This field is optional.</span></span> <span data-ttu-id="2b9a5-111">Úselo para proporcionar detalles sobre el grupo.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="2b9a5-112">**Directiva de participación** Especifique el modo en que los agentes inician sesión en el grupo de respuesta:</span><span class="sxs-lookup"><span data-stu-id="2b9a5-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="2b9a5-p103">Seleccione **Informal** para especificar que los agentes en el grupo no necesitan iniciar ni cerrar sesión en el grupo. Los agentes informales se conectan de forma automática cuando inician sesión. El valor predeterminado es **Informal**.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-p103">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in. The default is **Informal**.</span></span>

  - <span data-ttu-id="2b9a5-115">Seleccione **Formal** para especificar que los agentes en el grupo deben iniciar sesión y cerrar. Cuando se selecciona esta opción, los agentes, haga clic en un elemento de menú en el cliente para abrir un explorador y mostrar una consola de página web para iniciar y cerrar sesión.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="2b9a5-116">**Tiempo de alerta (segundos)** Especifique el número de segundos que hay que llamar a un agente antes de ofrecer la llamada al siguiente agente disponible.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="2b9a5-117">El valor tiene que ser de al menos 10 segundos e inferior a 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="2b9a5-118">El valor predeterminado es 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="2b9a5-119">**Método de enrutamiento** Seleccione el método para determinar el orden en que los agentes reciben llamadas:</span><span class="sxs-lookup"><span data-stu-id="2b9a5-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="2b9a5-120">Seleccione **Máxima inactividad** para ofrecer una llamada nueva primero al agente que haya estado más tiempo inactivo (el que más tiempo ha estado **Disponible** o **Inactivo**).</span><span class="sxs-lookup"><span data-stu-id="2b9a5-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="2b9a5-p105">Seleccione **En paralelo** para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo. La llamada se envía al primer agente que la acepte.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="2b9a5-123">Seleccione **Round robin** para ofrecer una llamada nueva a un agente cada vez.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="2b9a5-124">Seleccione **En serie** para ofrecer siempre una llamada nueva a los agentes en el orden en que aparecen en la lista **Agentes**.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="2b9a5-125">Seleccione el **operador** para ofrecer una nueva llamada a todos los agentes que han iniciado sesión y la aplicación de grupo de respuesta al mismo tiempo, independientemente de su presencia actual.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="2b9a5-126">Automáticos y los usuarios de cliente que se configuran como agentes pueden ver todas las llamadas que están en espera y pueden responder a las llamadas en espera en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="2b9a5-127">La llamada se envía al primer agente que la acepta y el resto de operadores y usuarios dejará de verla.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="2b9a5-128">**Agentes** Seleccione los usuarios que van a ser agentes para el grupo de respuesta en una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="2b9a5-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="2b9a5-129">Seleccione **utilizar una lista de distribución de correo electrónico existente** para usar una lista de distribución de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="2b9a5-130">Escriba el correo electrónico de la lista de distribución en **Dirección de la lista de distribución**.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b9a5-p108">Solo puede seleccionar una lista de distribución por grupo de agentes. Si la lista de distribución incluye listas de distribución anidadas, estas no se incluirán en el grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b9a5-133">El orden en que los agentes se muestran en la lista de distribución afecta al orden en que los agentes reciben llamadas para round robin y el enrutamiento en serie.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b9a5-134">Miembros ocultos o las listas ocultas pueden quedar visibles para los administradores de grupo de respuesta o los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="2b9a5-135">Para obtener información detallada, vea [crear o modificar un grupo de agentes en Skype para la empresa](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span><span class="sxs-lookup"><span data-stu-id="2b9a5-135">For details, see [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="2b9a5-p110">Seleccione **Definir un grupo de agentes personalizado** para seleccionar los usuarios que quiere asignar como agentes del grupo de respuesta. Haga clic en **Seleccionar** para agregar un agente a la lista y en **Quitar** para eliminar un agente seleccionado de la lista.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="2b9a5-p111">Las flechas arriba y abajo mueven un agente seleccionado hacia arriba y hacia abajo en la lista de agentes. El orden de los agentes afecta al orden en que los agentes reciben llamadas para round robin y el enrutamiento en serie.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="2b9a5-141">Para obtener información detallada sobre las características de grupo de respuesta y funciones, consulte [Plan para la aplicación de grupo de respuesta en Skype para Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="2b9a5-142">Para más información sobre cómo trabajar con grupos de agentes, mire [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="2b9a5-142">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


