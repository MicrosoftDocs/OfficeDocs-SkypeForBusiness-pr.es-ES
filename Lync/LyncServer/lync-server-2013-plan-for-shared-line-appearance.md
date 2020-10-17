---
title: 'Lync Server 2013: planear la apariencia de línea compartida'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a79c053098d1fbd3ba364a12b18fb335a0687e46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519837"
---
# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="54a9b-102">Planeación de la apariencia de línea compartida en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54a9b-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54a9b-103">_**Última modificación del tema:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="54a9b-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="54a9b-104">Lea este tema para obtener información sobre cómo planear la apariencia de línea compartida (SLA) en Lync Server 2013, actualización acumulativa abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="54a9b-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="54a9b-105">La apariencia de línea compartida es una característica de Lync Server 2013, actualización acumulativa de abril de 2016 para administrar varias llamadas en un número específico denominado número compartido.</span><span class="sxs-lookup"><span data-stu-id="54a9b-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="54a9b-106">SLA puede configurar cualquier usuario de Lync habilitado para Enterprise Voice como un número compartido con varias líneas para responder a varias llamadas.</span><span class="sxs-lookup"><span data-stu-id="54a9b-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="54a9b-107">En realidad, las llamadas no se reciben en el número compartido, sino que se reenvían a los usuarios que actúan como delegados para el número compartido.</span><span class="sxs-lookup"><span data-stu-id="54a9b-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="54a9b-108">Cualquiera de los delegados puede recoger la llamada mientras el resto de los delegados reciben una notificación en su teléfono sobre quién ha seleccionado la llamada y qué línea se ha vuelto ocupada como resultado.</span><span class="sxs-lookup"><span data-stu-id="54a9b-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="54a9b-109">Tanto el número de líneas como los delegados se pueden configurar para un número compartido en SLA.</span><span class="sxs-lookup"><span data-stu-id="54a9b-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="54a9b-110">Además, las opciones avanzadas, como BusyOption (lo que sucede en una situación en la que todas las líneas están ocupadas) y MissedCallOption (el caso en que ninguno de los delegados selecciona una llamada), también se pueden configurar para un número compartido.</span><span class="sxs-lookup"><span data-stu-id="54a9b-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="54a9b-111">SLA solo se admite en los siguientes dispositivos telefónicos (no es compatible con los clientes de Lync en equipos, teléfonos móviles u otros dispositivos):</span><span class="sxs-lookup"><span data-stu-id="54a9b-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="54a9b-112">Polycom VVX300 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="54a9b-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="54a9b-113">Polycom VVX400 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="54a9b-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="54a9b-114">Polycom VVX500 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="54a9b-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="54a9b-115">Polycom VVX600 con actualización de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="54a9b-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="54a9b-116">SLA es una nueva característica de Lync Server 2013, actualización acumulativa de abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="54a9b-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="54a9b-117">Para obtener información sobre la implementación de SLA, consulte [deploy Shared line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="54a9b-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="54a9b-118">Lista de características</span><span class="sxs-lookup"><span data-stu-id="54a9b-118">Feature List</span></span>

<span data-ttu-id="54a9b-119">La configuración de un grupo de SLA permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="54a9b-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="54a9b-120">Todos los delegados del grupo pueden responder a las llamadas entrantes al mismo número compartido.</span><span class="sxs-lookup"><span data-stu-id="54a9b-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="54a9b-121">Las llamadas pueden estar basadas en RTC o en SIP.</span><span class="sxs-lookup"><span data-stu-id="54a9b-121">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="54a9b-122">Los delegados pueden contener y seleccionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="54a9b-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="54a9b-123">Los delegados pueden transferir llamadas a un número fuera del grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="54a9b-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="54a9b-124">Los delegados pueden ver cuántas llamadas hay actualmente en el número compartido y ver el estado de cada una de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="54a9b-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="54a9b-125">Puede configurar un número máximo de llamadas simultáneas para el número compartido.</span><span class="sxs-lookup"><span data-stu-id="54a9b-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="54a9b-126">También puede establecer cómo desea que se traten las llamadas adicionales después de que se alcance este máximo.</span><span class="sxs-lookup"><span data-stu-id="54a9b-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="54a9b-127">Las llamadas excesivas pueden rechazarse con una señal de ocupado, desviarse a un número alternativo o reenviarse a un correo de voz.</span><span class="sxs-lookup"><span data-stu-id="54a9b-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="54a9b-128">Puede configurar el modo en que desea que se controlen las llamadas perdidas (llamadas que no se seleccionan después de un período de tiempo determinado).</span><span class="sxs-lookup"><span data-stu-id="54a9b-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="54a9b-129">Si habilita el correo de voz para la identidad de grupo, las llamadas perdidas pasarán automáticamente a correo de voz.</span><span class="sxs-lookup"><span data-stu-id="54a9b-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="54a9b-130">Si no tiene habilitado el correo de voz para la identidad de grupo (número compartido), puede elegir que las llamadas perdidas se rechacen con una señal de ocupado, se reenvíen a un número alternativo o se desconecten.</span><span class="sxs-lookup"><span data-stu-id="54a9b-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

