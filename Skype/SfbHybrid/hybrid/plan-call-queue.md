---
title: Planeación de una cola de llamadas en la nube
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
description: Información general sobre el uso de un operador automático de la nube con Skype empresarial Server 2019.
ms.openlocfilehash: d14aeab9857f2a54e6622fb368193a2e270e0f49
ms.sourcegitcommit: 477aac9e14fced139ee7dd827942ce35b9769b63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "43510799"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="163d2-103">Planear colas de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="163d2-103">Plan Cloud call queues</span></span>

<span data-ttu-id="163d2-104">La cola de llamadas en la nube es un servicio que acepta llamadas de clientes, reproduce un mensaje de saludo y, a continuación, coloca estas llamadas en una cola de espera mientras busca una lista preconfigurada de agentes para responder a estas llamadas.</span><span class="sxs-lookup"><span data-stu-id="163d2-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="163d2-105">Puede definir el conjunto de agentes en listas de distribución o grupos de seguridad habilitados para correo.</span><span class="sxs-lookup"><span data-stu-id="163d2-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="163d2-106">Su organización puede tener una o varias colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="163d2-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="163d2-107">Las colas de llamadas se suelen usar en combinación con los operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="163d2-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="163d2-108">Además, las colas de llamadas en la nube pueden proporcionar:</span><span class="sxs-lookup"><span data-stu-id="163d2-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="163d2-109">Música mientras los autores de llamadas esperan en espera</span><span class="sxs-lookup"><span data-stu-id="163d2-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="163d2-110">Configuración personalizada para el tamaño máximo de la cola de llamadas, el tiempo de espera y las opciones de administración de llamadas</span><span class="sxs-lookup"><span data-stu-id="163d2-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="163d2-111">Cada cola de llamadas tiene asignada una **cuenta de recursos** (consulte [configurar cuentas de recursos](configure-onprem-ra.md)) en el sistema de Skype empresarial Server 2019, que se vinculará directamente a una cola de llamadas en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="163d2-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="163d2-112">Consulte [crear una cola de llamadas en la nube](/MicrosoftTeams/create-a-phone-system-call-queue) para obtener más información sobre qué son las colas de llamadas y qué opciones y características existen para las colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="163d2-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="163d2-113">Puede asignar varios números de teléfono a una cola de llamadas, pero deben ser números de servicio de Microsoft, números de enrutamiento directos o números híbridos.</span><span class="sxs-lookup"><span data-stu-id="163d2-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="163d2-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="163d2-114">Requirements</span></span>

<span data-ttu-id="163d2-115">En los siguientes requisitos se da por sentado que ya ha implementado Skype empresarial Server 2019 en una topología compatible.</span><span class="sxs-lookup"><span data-stu-id="163d2-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="163d2-116">Sus requisitos dependen de su escenario:</span><span class="sxs-lookup"><span data-stu-id="163d2-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="163d2-117">Para una nueva configuración de colas de llamadas en la nube, siga los pasos descritos en [Configure Resource accounts](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="163d2-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="163d2-118">Tendrá que crear cuentas de recursos en línea o en Skype empresarial Server 2019, y es posible que también deba asociar un número de teléfono con la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="163d2-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="163d2-119">Además de los requisitos anteriores, deben configurarse los siguientes requisitos para conectarse al servicio cola de llamadas en la nube de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="163d2-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="163d2-120">Conectividad híbrida.</span><span class="sxs-lookup"><span data-stu-id="163d2-120">Hybrid connectivity.</span></span> <span data-ttu-id="163d2-121">Si ya ha implementado Skype empresarial Server y desea habilitar las colas de llamadas en la nube para los usuarios locales, debe asegurarse de que tiene una conectividad híbrida configurada entre su entorno local y el entorno en línea.</span><span class="sxs-lookup"><span data-stu-id="163d2-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="163d2-122">A veces, se denomina configuración de dominio dividido.</span><span class="sxs-lookup"><span data-stu-id="163d2-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="163d2-123">Para obtener más información, consulte [planear la conectividad híbrida entre Skype empresarial Server y office 365](plan-hybrid-connectivity.md) y [configurar la conectividad híbrida entre Skype empresarial server y Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="163d2-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="163d2-124">Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia de usuario virtual de sistema telefónico de sistema gratuito.</span><span class="sxs-lookup"><span data-stu-id="163d2-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="163d2-125">Esto proporciona funciones del sistema telefónico a números de teléfono en el nivel de la organización y le permite crear funciones de cola de llamadas y operador automático.</span><span class="sxs-lookup"><span data-stu-id="163d2-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="163d2-126">Cree una [cuenta de recursos](configure-onprem-ra.md) local para cada cola de llamadas y asigne una licencia y un número de teléfono si es necesario.</span><span class="sxs-lookup"><span data-stu-id="163d2-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="163d2-127">Recursos de planeación adicionales</span><span class="sxs-lookup"><span data-stu-id="163d2-127">Additional planning resources</span></span>

<span data-ttu-id="163d2-128">En el tutorial titulado [Small Business example-set up an operador automático](/microsoftteams/tutorial-org-aa) se recorre el proceso de recopilar información sobre las necesidades de los usuarios, planear una estructura de operadores automáticos y usuarios (y, posiblemente, colas de llamadas), escribir los mensajes del menú e implementar el plan en el centro de administración en línea.</span><span class="sxs-lookup"><span data-stu-id="163d2-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="163d2-129">Revise el tutorial y use los ejercicios en los que se crea el plan.</span><span class="sxs-lookup"><span data-stu-id="163d2-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="163d2-130">Cuando tenga una estructura sólida que satisfaga sus necesidades y un script que guíe a los clientes con eficacia, continúe con la [configuración de las cuentas de recursos](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="163d2-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="163d2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="163d2-131">See Also</span></span>

[<span data-ttu-id="163d2-132">Configurar cuentas de recursos</span><span class="sxs-lookup"><span data-stu-id="163d2-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="163d2-133">Habilitar la grabación de mensajes personalizados con la interfaz de usuario de teléfono</span><span class="sxs-lookup"><span data-stu-id="163d2-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="163d2-134">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="163d2-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="163d2-135">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="163d2-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

<span data-ttu-id="163d2-136">[Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) (Planeamiento de la conectividad híbrida entre Skype Empresarial Server y Office 365)</span><span class="sxs-lookup"><span data-stu-id="163d2-136">[Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md)</span></span>

[<span data-ttu-id="163d2-137">Configuración de la conectividad híbrida entre Skype Empresarial Server y Office 365</span><span class="sxs-lookup"><span data-stu-id="163d2-137">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="163d2-138">Administrar cuentas de recursos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="163d2-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
