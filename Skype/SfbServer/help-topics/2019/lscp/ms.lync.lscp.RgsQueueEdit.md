---
title: Cola de grupos de respuesta Crear nuevos o editar existentes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Las colas de grupo de respuesta mantienen las llamadas a un grupo de respuesta hasta que un agente responde a la llamada.
ms.openlocfilehash: 097c28db7f2ae52d7ab0b362e828c8f05e132481
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808200"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="40075-103">Cola de grupos de respuesta: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="40075-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="40075-104">Las colas de grupo de respuesta mantienen las llamadas a un grupo de respuesta hasta que un agente responde a la llamada.</span><span class="sxs-lookup"><span data-stu-id="40075-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="40075-105">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="40075-105">UI Reference</span></span>

<span data-ttu-id="40075-106">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="40075-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="40075-107">**Nombre** Cada cola debe tener un nombre.</span><span class="sxs-lookup"><span data-stu-id="40075-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="40075-108">Escriba un nombre descriptivo para la cola.</span><span class="sxs-lookup"><span data-stu-id="40075-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="40075-109">**Descripción** Este campo es opcional.</span><span class="sxs-lookup"><span data-stu-id="40075-109">**Description** This field is optional.</span></span> <span data-ttu-id="40075-110">Úselo para proporcionar detalles sobre la cola.</span><span class="sxs-lookup"><span data-stu-id="40075-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="40075-111">**Grupos** Seleccione los grupos de agentes que desea asignar a la cola.</span><span class="sxs-lookup"><span data-stu-id="40075-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="40075-112">Haga clic en **Seleccionar** para agregar grupos de agentes a la lista.</span><span class="sxs-lookup"><span data-stu-id="40075-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="40075-113">Haga clic en **Quitar** para eliminar el grupo de agentes seleccionado de la lista.</span><span class="sxs-lookup"><span data-stu-id="40075-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="40075-114">Las flechas arriba y abajo mueven un grupo de agentes seleccionado hacia arriba y hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="40075-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="40075-115">El orden de los grupos de agentes afecta al orden en que Skype Empresarial Server busca un agente disponible.</span><span class="sxs-lookup"><span data-stu-id="40075-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="40075-116">Es decir, el primer grupo de la lista se busca primero para un agente disponible, seguido del segundo grupo, etc.</span><span class="sxs-lookup"><span data-stu-id="40075-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="40075-117">**Habilitar el tiempo de espera de cola** Active esta casilla para especificar un período máximo de tiempo para que el autor de la llamada espere en espera antes de que un agente responda a la llamada.</span><span class="sxs-lookup"><span data-stu-id="40075-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="40075-118">Si selecciona esta opción, debe especificar también lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="40075-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="40075-119">**Período de tiempo de espera (segundos)** Seleccione o escriba el número máximo de segundos que el autor de la llamada puede esperar antes de que un agente responda a la llamada.</span><span class="sxs-lookup"><span data-stu-id="40075-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="40075-120">**Acción de llamada** Seleccione la acción que se produce cuando se ha desa cabo el tiempo de espera de una llamada. Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="40075-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="40075-121">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="40075-121">**Disconnect**</span></span>

  - <span data-ttu-id="40075-122">**Reenviar al correo de voz** Si selecciona esta opción, en dirección **SIP,** escriba una dirección de correo de voz con el formato sip: <username> @ <domainname> (por ejemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="40075-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="40075-123">**Reenviar al número de teléfono** Si selecciona esta opción, en la dirección **SIP** escriba el número de teléfono con el formato sip: <number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="40075-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="40075-124">**Reenviar a dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="40075-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="40075-125">En **la dirección SIP,** escriba el URI del usuario con el formato sip: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="40075-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="40075-126">**Reenviar a otra cola** Si selecciona esta opción, vaya a la cola que va a recibir las llamadas cuando se haya pasado el tiempo de espera de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="40075-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="40075-127">**Habilitar desbordamiento de cola** Active esta casilla para especificar el número máximo de llamadas que puede contener la cola.</span><span class="sxs-lookup"><span data-stu-id="40075-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="40075-128">Si selecciona esta opción, debe especificar también lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="40075-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="40075-129">**Número máximo de llamadas** Seleccione o escriba el número máximo de llamadas que puede contener la cola.</span><span class="sxs-lookup"><span data-stu-id="40075-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="40075-130">**Reenviar la llamada** Seleccione qué llamada debe realizar una acción cuando se alcance el umbral de desbordamiento de cola.</span><span class="sxs-lookup"><span data-stu-id="40075-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="40075-131">**Acción de llamada** Seleccione la acción que se produce cuando se alcanza el umbral de desbordamiento de cola.</span><span class="sxs-lookup"><span data-stu-id="40075-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="40075-132">Sus opciones son:</span><span class="sxs-lookup"><span data-stu-id="40075-132">Your choices are:</span></span>

  - <span data-ttu-id="40075-133">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="40075-133">**Disconnect**</span></span>

  - <span data-ttu-id="40075-134">**Reenviar al correo de voz** Si selecciona esta opción, en dirección **SIP,** escriba una dirección de correo de voz con el formato sip: <username> @ <domainname> (por ejemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="40075-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="40075-135">**Reenviar al número de teléfono** Si selecciona esta opción, en la dirección **SIP** escriba el número de teléfono con el formato sip: <number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="40075-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="40075-136">**Reenviar a dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="40075-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="40075-137">En **la dirección SIP,** escriba el URI del usuario con el formato sip: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="40075-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="40075-138">**Reenviar a otra cola** Si selecciona esta opción, vaya a la cola que va a recibir llamadas cuando se alcance el umbral de desbordamiento de cola.</span><span class="sxs-lookup"><span data-stu-id="40075-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="40075-139">Para obtener más información sobre las características y capacidades de Grupo de respuesta, consulte [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="40075-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="40075-140">Para obtener detalles sobre cómo trabajar con colas, vea [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="40075-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


