---
title: Cola de grupos de respuesta crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Las colas de grupos de respuesta contienen llamadas a un grupo de respuesta hasta que un agente responde a la llamada.
ms.openlocfilehash: 3eba4fbba662ecc1497b5c8d0aac14ce5083c1ea
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286351"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="0fa6e-103">Cola de grupos de respuesta: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="0fa6e-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="0fa6e-104">Las colas de grupos de respuesta contienen llamadas a un grupo de respuesta hasta que un agente responde a la llamada.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0fa6e-105">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="0fa6e-105">UI Reference</span></span>

<span data-ttu-id="0fa6e-106">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="0fa6e-107">**Nombre** Cada cola debe tener un nombre.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="0fa6e-108">Escriba un nombre descriptivo para la cola.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="0fa6e-109">**Descripción** Este campo es opcional.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-109">**Description** This field is optional.</span></span> <span data-ttu-id="0fa6e-110">Úselo para proporcionar detalles sobre la cola.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="0fa6e-111">**Grupos** Seleccione los grupos de agentes que desea asignar a la cola.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="0fa6e-112">Haga clic en **Seleccionar** para agregar grupos de agentes a la lista.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="0fa6e-113">Haga clic en **Quitar** para eliminar el grupo de agentes seleccionado de la lista.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="0fa6e-114">Las flechas arriba y abajo mueven un grupo de agentes seleccionado hacia arriba y hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="0fa6e-115">El orden de los grupos de agentes afecta al orden en el que Skype empresarial Server busca un agente disponible.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="0fa6e-116">Es decir, el primer grupo de la lista se busca primero en un agente disponible, seguido del segundo grupo y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="0fa6e-117">**Habilitar el tiempo de espera de la cola** Seleccione esta casilla para especificar un período máximo de tiempo para que la persona que llama espere en espera antes de que un agente responda a la llamada.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="0fa6e-118">Si selecciona esta opción, tendrá que especificar también lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0fa6e-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="0fa6e-119">**Período de tiempo de espera (segundos)** Selecciona o escribe el número máximo de segundos que una persona que llama puede esperar antes de que un agente responda a la llamada.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="0fa6e-120">**Acción llamar** Seleccione la acción que se produce cuando se agota el tiempo de espera de una llamada. Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="0fa6e-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="0fa6e-121">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="0fa6e-121">**Disconnect**</span></span>

  - <span data-ttu-id="0fa6e-122">**Reenviar al correo de voz** Si selecciona esta opción, en **dirección SIP**, escriba una dirección de correo de voz en el formato SIP<username> @ <domainname> : (por ejemplo, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0fa6e-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="0fa6e-123">**Desviar al número de teléfono** Si selecciona esta opción, en **dirección SIP** , escriba el número de teléfono con el formato SIP<number> @ <domainname> : (por ejemplo, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0fa6e-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="0fa6e-124">**Desviar a dirección SIP** Seleccione esta opción para desviar la llamada a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="0fa6e-125">En **dirección SIP**, escriba el URI para el usuario con el formato SIP:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="0fa6e-126">**Reenviar a otra cola** Si selecciona esta opción, vaya a la cola que recibirá las llamadas cuando se agote el tiempo de espera de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="0fa6e-127">**Habilitar desbordamiento de cola** Seleccione esta casilla para especificar un número máximo de llamadas que la cola puede contener.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="0fa6e-128">Si selecciona esta opción, tendrá que especificar también lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0fa6e-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="0fa6e-129">**Número máximo de llamadas** Seleccione o escriba el número máximo de llamadas que puede contener la cola.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="0fa6e-130">**Desviar la llamada** Seleccione la llamada que debe tomarse cuando se cumpla el umbral de desbordamiento de la cola.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="0fa6e-131">**Acción llamar** Seleccione la acción que se produce cuando se alcanza el umbral de desbordamiento de la cola.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="0fa6e-132">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="0fa6e-132">Your choices are:</span></span>

  - <span data-ttu-id="0fa6e-133">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="0fa6e-133">**Disconnect**</span></span>

  - <span data-ttu-id="0fa6e-134">**Reenviar al correo de voz** Si selecciona esta opción, en **dirección SIP**, escriba una dirección de correo de voz en el formato SIP<username> @ <domainname> : (por ejemplo, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0fa6e-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="0fa6e-135">**Desviar al número de teléfono** Si selecciona esta opción, en **dirección SIP** , escriba el número de teléfono con el formato SIP<number> @ <domainname> : (por ejemplo, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0fa6e-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="0fa6e-136">**Desviar a dirección SIP** Seleccione esta opción para desviar la llamada a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="0fa6e-137">En **dirección SIP**, escriba el URI para el usuario con el formato SIP:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="0fa6e-138">**Reenviar a otra cola** Si selecciona esta opción, vaya a la cola que va a recibir llamadas cuando se cumpla el umbral de desbordamiento de la cola.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="0fa6e-139">Para obtener más información sobre las funciones y características de los grupos de respuesta, consulte [planear la aplicación de grupo de respuesta en Skype empresarial Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="0fa6e-140">Para más información sobre cómo trabajar con colas, mire [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="0fa6e-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


