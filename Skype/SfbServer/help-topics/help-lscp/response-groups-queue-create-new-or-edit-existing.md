---
title: Cola de grupos de respuesta cree nuevos o edite los existentes
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Las colas de respuesta grupo contienen llamadas a un grupo de respuesta hasta que un agente responde a la llamada.
ms.openlocfilehash: f5223aaca700c10a25631131db69a55de1362ddc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="2db5d-103">Cola de grupos de respuesta: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="2db5d-103">Response Groups Queue: Create New or Edit Existing</span></span>
 
<span data-ttu-id="2db5d-104">Las colas de respuesta grupo contienen llamadas a un grupo de respuesta hasta que un agente responde a la llamada.</span><span class="sxs-lookup"><span data-stu-id="2db5d-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="2db5d-105">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="2db5d-105">UI Reference</span></span>

<span data-ttu-id="2db5d-106">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="2db5d-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="2db5d-107">**Nombre** Cada una de ellas debe tener un nombre.</span><span class="sxs-lookup"><span data-stu-id="2db5d-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="2db5d-108">Escriba un nombre descriptivo para la cola.</span><span class="sxs-lookup"><span data-stu-id="2db5d-108">Type a descriptive name for the queue.</span></span>
    
- <span data-ttu-id="2db5d-109">**Descripción** Este campo es opcional.</span><span class="sxs-lookup"><span data-stu-id="2db5d-109">**Description** This field is optional.</span></span> <span data-ttu-id="2db5d-110">Úselo para proporcionar detalles sobre la cola.</span><span class="sxs-lookup"><span data-stu-id="2db5d-110">Use it to provide additional details about the queue.</span></span>
    
- <span data-ttu-id="2db5d-111">**Grupos** Seleccione los grupos de agentes que desea asignar a la cola.</span><span class="sxs-lookup"><span data-stu-id="2db5d-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="2db5d-112">Haga clic en **Seleccionar** para agregar grupos de agentes a la lista.</span><span class="sxs-lookup"><span data-stu-id="2db5d-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="2db5d-113">Haga clic en **Quitar** para eliminar el grupo de agentes seleccionado de la lista.</span><span class="sxs-lookup"><span data-stu-id="2db5d-113">Click **Remove** to delete the selected agent group from the list.</span></span>
    
    <span data-ttu-id="2db5d-114">Las flechas arriba y abajo mover un grupo de agentes seleccionados hacia arriba y hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="2db5d-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="2db5d-115">El orden de los grupos de agentes afecta al orden en el que Skype para Business Server busca un agente disponible.</span><span class="sxs-lookup"><span data-stu-id="2db5d-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="2db5d-116">Es decir, el primer grupo de la lista se busca primero un agente disponible, seguido por el segundo grupo y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="2db5d-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>
    
- <span data-ttu-id="2db5d-117">**Activar el tiempo de espera de cola** Active esta casilla de verificación para especificar un período máximo de tiempo para que un llamador esperar en espera antes de que un agente responde a la llamada.</span><span class="sxs-lookup"><span data-stu-id="2db5d-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="2db5d-118">Si selecciona esta opción, tendrá que especificar también lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2db5d-118">If you select this option, you also need to specify the following:</span></span>
    
  - <span data-ttu-id="2db5d-119">**Tiempo de espera (segundos)** Seleccione o escriba el número máximo de segundos que un llamador puede esperar antes de que un agente responde a la llamada.</span><span class="sxs-lookup"><span data-stu-id="2db5d-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>
    
  - <span data-ttu-id="2db5d-120">**Llamar a la acción** Seleccione la acción que se produce cuando se agota el tiempo de espera de una llamada. Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="2db5d-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>
    
  - <span data-ttu-id="2db5d-121">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="2db5d-121">**Disconnect**</span></span>
    
  - <span data-ttu-id="2db5d-122">**Reenviar a correo de voz** Si selecciona esta opción, en la **dirección SIP**, escriba una dirección de correo de voz en el formato sip:<username> @ <domainname> (por ejemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2db5d-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>
    
  - <span data-ttu-id="2db5d-123">**Reenviar a número de teléfono** Si selecciona esta opción, en la **dirección SIP** escriba el número de teléfono en el formato sip:<number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2db5d-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>
    
  - <span data-ttu-id="2db5d-124">**Reenviar a la dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="2db5d-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="2db5d-125">En la **dirección SIP**, escriba el identificador URI para el usuario en el formato sip:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="2db5d-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>
    
  - <span data-ttu-id="2db5d-126">**Reenviar a otra cola** Si selecciona esta opción, vaya a la cola para recibir llamadas cuando el tiempo de espera de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2db5d-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>
    
- <span data-ttu-id="2db5d-127">**Habilitar el desbordamiento de la cola** Active esta casilla de verificación para especificar un número máximo de llamadas que puede contener la cola.</span><span class="sxs-lookup"><span data-stu-id="2db5d-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="2db5d-128">Si selecciona esta opción, tendrá que especificar también lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2db5d-128">If you select this option, you also need to specify the following:</span></span>
    
  - <span data-ttu-id="2db5d-129">**Número máximo de llamadas** Seleccione o escriba el número máximo de llamadas que puede contener la cola.</span><span class="sxs-lookup"><span data-stu-id="2db5d-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>
    
  - <span data-ttu-id="2db5d-130">**Reenviar la llamada** Seleccione qué llamada es tomar medidas cuando se alcanza el umbral de desbordamiento de la cola.</span><span class="sxs-lookup"><span data-stu-id="2db5d-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>
    
  - <span data-ttu-id="2db5d-131">**Llamar a la acción** Seleccione la acción que se produce cuando se alcanza el umbral de desbordamiento de la cola.</span><span class="sxs-lookup"><span data-stu-id="2db5d-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="2db5d-132">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="2db5d-132">Your choices are:</span></span>
    
  - <span data-ttu-id="2db5d-133">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="2db5d-133">**Disconnect**</span></span>
    
  - <span data-ttu-id="2db5d-134">**Reenviar a correo de voz** Si selecciona esta opción, en la **dirección SIP**, escriba una dirección de correo de voz en el formato sip:<username> @ <domainname> (por ejemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2db5d-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>
    
  - <span data-ttu-id="2db5d-135">**Reenviar a número de teléfono** Si selecciona esta opción, en la **dirección SIP** escriba el número de teléfono en el formato sip:<number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2db5d-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>
    
  - <span data-ttu-id="2db5d-136">**Reenviar a la dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="2db5d-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="2db5d-137">En la **dirección SIP**, escriba el identificador URI para el usuario en el formato sip:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="2db5d-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>
    
  - <span data-ttu-id="2db5d-138">**Reenviar a otra cola** Si selecciona esta opción, vaya a la cola a la que va a recibir llamadas, cuando se alcanza el umbral de desbordamiento de la cola.</span><span class="sxs-lookup"><span data-stu-id="2db5d-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>
    
<span data-ttu-id="2db5d-139">Para obtener más información acerca de capacidades y características de los grupos de respuesta, vea [Planear la aplicación de grupo de respuesta en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación de planeamiento.</span><span class="sxs-lookup"><span data-stu-id="2db5d-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="2db5d-140">Para obtener más información acerca de cómo trabajar con colas, consulte [Administrar colas de grupo de respuesta](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="2db5d-140">For details about working with queues, see [Managing Response Group Queues](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>
  

