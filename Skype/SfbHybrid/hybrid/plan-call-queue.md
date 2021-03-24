---
title: Planear una cola de llamadas en la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Información general sobre cómo usar un operador automático en la nube con Skype Empresarial Server 2019.
ms.openlocfilehash: 62731691f4e56c923d2dd8fa6057f244776ec65b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110496"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="d96ac-103">Plan de colas de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="d96ac-103">Plan Cloud call queues</span></span>

<span data-ttu-id="d96ac-104">La cola de llamadas en la nube es un servicio que acepta llamadas de clientes, reproduce un mensaje de saludo y, a continuación, coloca estas llamadas en una cola de espera mientras se busca en una lista predefinida de agentes para responder a estas llamadas.</span><span class="sxs-lookup"><span data-stu-id="d96ac-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="d96ac-105">Puede definir el conjunto de agentes en listas de distribución habilitadas para correo o grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d96ac-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="d96ac-106">Su organización puede tener una o varias colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d96ac-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="d96ac-107">Las colas de llamadas se usan normalmente en combinación con operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="d96ac-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="d96ac-108">Además, las colas de llamadas en la nube pueden proporcionar:</span><span class="sxs-lookup"><span data-stu-id="d96ac-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="d96ac-109">Música mientras los autores de llamadas están esperando en espera</span><span class="sxs-lookup"><span data-stu-id="d96ac-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="d96ac-110">Configuración personalizada para las opciones de tamaño máximo, tiempo de espera y control de llamadas de la cola de llamadas</span><span class="sxs-lookup"><span data-stu-id="d96ac-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="d96ac-111">A cada cola de llamadas se le asigna una cuenta de recursos **(vea** [Configurar](configure-onprem-ra.md)cuentas de recursos) en el sistema de Skype Empresarial Server 2019 que se vinculará directamente a una cola de llamadas en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d96ac-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d96ac-112">Consulte [Crear una cola de llamadas en](/MicrosoftTeams/create-a-phone-system-call-queue) la nube para obtener más información sobre qué son las colas de llamadas y qué opciones y características existen para las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d96ac-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="d96ac-113">Puede asignar varios números de teléfono a una cola de llamadas, pero deben ser números de servicio de Microsoft, números de enrutamiento directo o números híbridos.</span><span class="sxs-lookup"><span data-stu-id="d96ac-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="d96ac-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d96ac-114">Requirements</span></span>

<span data-ttu-id="d96ac-115">Los siguientes requisitos suponen que ya tiene Skype Empresarial Server 2019 implementado en una topología compatible.</span><span class="sxs-lookup"><span data-stu-id="d96ac-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="d96ac-116">Los requisitos dependen del escenario:</span><span class="sxs-lookup"><span data-stu-id="d96ac-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="d96ac-117">Para una nueva configuración de colas de llamadas en la nube, siga los pasos descritos en [Configurar cuentas de recursos](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="d96ac-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="d96ac-118">Deberá crear cuentas de recursos en línea o en Skype Empresarial Server 2019, y es posible que también necesite asociar un número de teléfono con la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d96ac-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="d96ac-119">Además de los requisitos anteriores, los siguientes requisitos deben configurarse para conectarse al servicio de cola de llamadas de Microsoft Cloud:</span><span class="sxs-lookup"><span data-stu-id="d96ac-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="d96ac-120">Conectividad híbrida.</span><span class="sxs-lookup"><span data-stu-id="d96ac-120">Hybrid connectivity.</span></span> <span data-ttu-id="d96ac-121">Si ya ha implementado Skype Empresarial Server y desea habilitar las colas de llamadas en la nube para los usuarios locales, debe asegurarse de que tiene la conectividad híbrida configurada entre los entornos locales y en línea.</span><span class="sxs-lookup"><span data-stu-id="d96ac-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="d96ac-122">A veces se denomina configuración de dominio dividido.</span><span class="sxs-lookup"><span data-stu-id="d96ac-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="d96ac-123">Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 u Office 365](plan-hybrid-connectivity.md) y [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 u Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="d96ac-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="d96ac-124">Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia de usuario virtual del sistema telefónico sin costo.</span><span class="sxs-lookup"><span data-stu-id="d96ac-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="d96ac-125">Esto proporciona funcionalidades del sistema telefónico a los números de teléfono en el nivel de la organización y le permite crear funciones de operador automático y cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d96ac-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="d96ac-126">Cree una cuenta de recurso local [para](configure-onprem-ra.md) cada cola de llamadas y asigne una licencia y un número de teléfono si es necesario.</span><span class="sxs-lookup"><span data-stu-id="d96ac-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

<span data-ttu-id="d96ac-127">Cuando tenga una estructura sólida que satisfaga sus necesidades y un script que guía a los clientes de forma eficiente, vaya a  [Configurar cuentas de recursos](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="d96ac-127">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d96ac-128">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d96ac-128">See Also</span></span>

[<span data-ttu-id="d96ac-129">Configurar cuentas de recursos</span><span class="sxs-lookup"><span data-stu-id="d96ac-129">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="d96ac-130">Habilitar la grabación de mensajes personalizados con la interfaz de usuario de teléfono</span><span class="sxs-lookup"><span data-stu-id="d96ac-130">Enable custom prompt recording using the telephone user interface</span></span>](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="d96ac-131">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="d96ac-131">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="d96ac-132">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="d96ac-132">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="d96ac-133">Planear la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="d96ac-133">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="d96ac-134">Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="d96ac-134">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="d96ac-135">Administrar cuentas de recursos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d96ac-135">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)