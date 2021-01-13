---
title: Planear la apariencia de línea compartida en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Lea este tema para obtener información sobre cómo planear la apariencia de línea compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015.
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813350"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="95b53-103">Planear la apariencia de línea compartida en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="95b53-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="95b53-104">Lea este tema para obtener información sobre cómo planear la apariencia de línea compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015.</span><span class="sxs-lookup"><span data-stu-id="95b53-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="95b53-105">La apariencia de línea compartida es una característica de Skype Empresarial para controlar varias llamadas en un número específico denominado número compartido.</span><span class="sxs-lookup"><span data-stu-id="95b53-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="95b53-106">Sla can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span><span class="sxs-lookup"><span data-stu-id="95b53-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="95b53-107">En realidad, las llamadas no se reciben en el número compartido, sino que se reenvían a los usuarios que actúan como delegados del número compartido.</span><span class="sxs-lookup"><span data-stu-id="95b53-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="95b53-108">Cualquiera de los delegados puede recibir la llamada mientras que el resto de los delegados recibe una notificación en su teléfono sobre quién ha recibido la llamada y qué línea está ocupada como resultado.</span><span class="sxs-lookup"><span data-stu-id="95b53-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="95b53-109">Tanto el número de líneas como los delegados se pueden configurar para un número compartido en SLA.</span><span class="sxs-lookup"><span data-stu-id="95b53-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="95b53-110">Además, las opciones avanzadas, como BusyOption (lo que sucede en una situación en la que todas las líneas están ocupadas) y MissedCallOption (el caso en el que ninguno de los delegados selecciona una llamada), también se pueden configurar para un número compartido.</span><span class="sxs-lookup"><span data-stu-id="95b53-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="95b53-111">Sla is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span><span class="sxs-lookup"><span data-stu-id="95b53-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="95b53-112">Polycom VVX300 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="95b53-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="95b53-113">Polycom VVX400 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="95b53-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="95b53-114">Polycom VVX500 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="95b53-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="95b53-115">Polycom VVX600 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="95b53-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="95b53-116">SLA es una nueva característica de Skype Empresarial Server, actualización acumulativa de noviembre de 2015.</span><span class="sxs-lookup"><span data-stu-id="95b53-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="95b53-117">Para obtener información acerca de la implementación de SLA, vea [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="95b53-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="95b53-118">Lista de características</span><span class="sxs-lookup"><span data-stu-id="95b53-118">Feature List</span></span>

<span data-ttu-id="95b53-119">La configuración de un grupo de SLA permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95b53-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="95b53-120">Todos los delegados del grupo pueden responder llamadas entrantes al mismo número compartido.</span><span class="sxs-lookup"><span data-stu-id="95b53-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="95b53-121">Las llamadas pueden estar basadas en RTC o en SIP.</span><span class="sxs-lookup"><span data-stu-id="95b53-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="95b53-122">Los delegados pueden retener y recoger llamadas.</span><span class="sxs-lookup"><span data-stu-id="95b53-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="95b53-123">Los delegados pueden transferir llamadas a un número fuera del grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="95b53-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="95b53-124">Los delegados pueden ver cuántas llamadas hay actualmente en el número compartido y ver el estado de cada una de esas llamadas.</span><span class="sxs-lookup"><span data-stu-id="95b53-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="95b53-125">Puede configurar un número máximo de llamadas simultáneas para el número compartido.</span><span class="sxs-lookup"><span data-stu-id="95b53-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="95b53-126">También puede establecer cómo desea que se controle otras llamadas después de alcanzar este máximo.</span><span class="sxs-lookup"><span data-stu-id="95b53-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="95b53-127">El exceso de llamadas puede rechazarse con una señal de disponibilidad, reenviarse a un número alternativo o reenviarse al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="95b53-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="95b53-128">Puede configurar cómo desea que se controle las llamadas perdidas (las llamadas no se seleccionan después de un tiempo determinado).</span><span class="sxs-lookup"><span data-stu-id="95b53-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="95b53-129">Si habilita el correo de voz para la identidad del grupo, las llamadas perdidas se enviarán automáticamente al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="95b53-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="95b53-130">Si no tiene habilitado el correo de voz para la identidad del grupo (número compartido), puede elegir que las llamadas perdidas se rechacen con una señal de disponibilidad, se reenvían a un número alternativo o se desconecten.</span><span class="sxs-lookup"><span data-stu-id="95b53-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

