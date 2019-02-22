---
title: Plan para apariencia de línea compartida en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Leer este tema para obtener información sobre cómo planear la apariencia de línea Shared (SLA) en Skype para Business Server 2015, de noviembre de 2015 actualización acumulativa.
ms.openlocfilehash: b65d637426b0a8533089b21021bce566373ca9f1
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "23884511"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="078a1-103">Plan para apariencia de línea compartida en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="078a1-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="078a1-104">Leer este tema para obtener información sobre cómo planear la apariencia de línea Shared (SLA) en Skype para Business Server 2015, de noviembre de 2015 actualización acumulativa.</span><span class="sxs-lookup"><span data-stu-id="078a1-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="078a1-105">Apariencia de línea compartida es una característica de Skype para la empresa para el tratamiento de varias llamadas en un número específico de llamar a un número compartido.</span><span class="sxs-lookup"><span data-stu-id="078a1-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="078a1-106">SLA puede configurar cualquier enterprise voice habilitado Skype para usuarios de empresa como un número compartido con varias líneas para responder a varias llamadas.</span><span class="sxs-lookup"><span data-stu-id="078a1-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="078a1-107">En realidad, las llamadas no se reciben en el número compartido, sino que se desvían a usuarios que actúan como delegados para el número compartido.</span><span class="sxs-lookup"><span data-stu-id="078a1-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="078a1-108">Cualquiera de estos delegados puede responder a la llamada mientras el resto de los delegados recibe una notificación en su teléfono sobre el usuario que respondió a la llamada y la línea que está ocupada como resultado.</span><span class="sxs-lookup"><span data-stu-id="078a1-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="078a1-109">El número de líneas y los delegados se pueden configurar para un número compartido en SLA.</span><span class="sxs-lookup"><span data-stu-id="078a1-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="078a1-110">Además, también se pueden configurar otras opciones avanzadas para un número compartido, como BusyOption (que se produce cuando todas las líneas están ocupadas) y MissedCallOption (si ninguno de los delegados responde a una llamada).</span><span class="sxs-lookup"><span data-stu-id="078a1-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="078a1-111">SLA sólo se admite en los siguientes dispositivos de teléfono (no se admite para Skype para clientes empresariales en equipos, teléfonos móviles o en otros dispositivos):</span><span class="sxs-lookup"><span data-stu-id="078a1-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="078a1-112">Polycom VVX300 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="078a1-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="078a1-113">Polycom VVX400 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="078a1-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="078a1-114">Polycom VVX500 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="078a1-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="078a1-115">Polycom VVX600 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="078a1-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="078a1-116">SLA es una característica nueva de Skype para Business Server, de noviembre de 2015 actualización acumulativa.</span><span class="sxs-lookup"><span data-stu-id="078a1-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="078a1-117">Para obtener información sobre la implementación de SLA, vea [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="078a1-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="078a1-118">Lista de características</span><span class="sxs-lookup"><span data-stu-id="078a1-118">Feature List</span></span>

<span data-ttu-id="078a1-119">Configurar un grupo de SLA permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="078a1-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="078a1-p102">Todos los delegados del grupo pueden responder a llamadas entrantes al mismo número compartido. Las llamadas pueden estar basadas en RTC o en SIP.</span><span class="sxs-lookup"><span data-stu-id="078a1-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="078a1-122">Los delegados pueden responder llamadas y ponerlas en espera.</span><span class="sxs-lookup"><span data-stu-id="078a1-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="078a1-123">Los delegados pueden transferir llamadas a un número fuera del grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="078a1-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="078a1-124">Los delegados pueden ver cuántas llamadas están actualmente en el número compartido, así como ver el estado de esas llamadas.</span><span class="sxs-lookup"><span data-stu-id="078a1-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="078a1-p103">Puede configurar un número máximo de llamadas simultáneas para el número compartido. Además, puede configurar cómo quiere administrar las llamadas adicionales cuando se alcanza el número máximo. Las llamadas que superen el límite se pueden rechazar con una señal de línea ocupada, desviar a un número alternativo o desviarlas al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="078a1-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="078a1-p104">Puede configurar cómo quiere administrar las llamadas perdidas (llamadas que no se responden después de un tiempo específico). Si habilita el correo de voz para la identidad de grupo, las llamadas perdidas se desvían automáticamente al correo de voz. Si no tiene habilitado el correo de voz para la identidad de grupo (número compartido), puede elegir que las llamadas perdidas se rechacen con una señal de línea ocupada, se desvíen a un número alternativo o se desconecten.</span><span class="sxs-lookup"><span data-stu-id="078a1-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

