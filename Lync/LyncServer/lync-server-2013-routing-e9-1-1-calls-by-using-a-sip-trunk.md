---
title: 'Lync Server 2013: enrutamiento de llamadas E9-1-1 mediante un enlace troncal SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f45bd91eade0de6f290fd87e52effb25c669999a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="fef4e-102">Routing E9-1-1 calls by Using a SIP trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef4e-102">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fef4e-103">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="fef4e-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="fef4e-104">El uso de troncos SIP para establecer una conexión con un proveedor de servicios E9-1-1 es una de las formas de implementar servicios E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="fef4e-104">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="fef4e-105">Para obtener información detallada sobre el uso de una puerta de enlace de ELIN para conectarse a un proveedor de servicios E9-1-1 basado en una red telefónica conmutada (RTC), consulte [Routing E9-1-1 calls by Using a Elin Gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="fef4e-105">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="fef4e-106">El siguiente diagrama muestra cómo se enruta una llamada de emergencia desde Lync Server al punto de respuesta de seguridad pública (PSAP) cuando se usa un tronco SIP y un proveedor de servicios E9-1-1 cualificado.</span><span class="sxs-lookup"><span data-stu-id="fef4e-106">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="fef4e-107">**Enrutamiento de llamadas E9-1-1 mediante troncos SIP**</span><span class="sxs-lookup"><span data-stu-id="fef4e-107">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="fef4e-108">![Enrutamiento de llamadas de emergencia de Lync Server a PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Enrutamiento de llamadas de emergencia de Lync Server a PSAP")</span><span class="sxs-lookup"><span data-stu-id="fef4e-108">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="fef4e-109">Cuando se realiza una llamada de emergencia desde un cliente compatible de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="fef4e-109">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="fef4e-110">Un SIP INVITE que contiene la ubicación, el número de devolución de llamada del autor de la llamada y la dirección URL de notificación (opcional) y el número de devolución de llamada de conferencia se redirige a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fef4e-110">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="fef4e-111">Lync Server coincide con el número de emergencia y enruta la llamada (en función del valor de **uso de RTC** que se define en la Directiva de ubicación correspondiente) a un servidor de mediación y, desde allí, a través de un tronco SIP al proveedor de servicios E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="fef4e-111">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="fef4e-p102">El proveedor de servicios E9-1-1 enruta la llamada de emergencia al PSAP adecuado según la ubicación proporcionada con la llamada. Cuando el cliente incluye una ubicación de respuesta de emergencia (ERL) validada en la llamada de emergencia, el proveedor dirige automáticamente la llamada al punto PSAP adecuado. Si el usuario especificó la ubicación manualmente, el centro de respuestas a llamadas de emergencia (ECRC) verifica verbalmente en primer lugar la exactitud de la ubicación con la persona que llama antes de enrutar la llamada de emergencia al PSAP.</span><span class="sxs-lookup"><span data-stu-id="fef4e-p102">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call. When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP. If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="fef4e-115">Si ha configurado la Directiva de ubicación para las notificaciones, se enviará a uno o más de los responsables de seguridad de la organización un mensaje instantáneo especial de notificación de emergencia de Lync.</span><span class="sxs-lookup"><span data-stu-id="fef4e-115">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="fef4e-116">Este mensaje siempre aparece en la pantalla de los responsables de seguridad y contiene el nombre, número de teléfono, hora y ubicación del autor de la llamada para que el personal de seguridad pueda ponerse en contacto con él rápidamente mediante un mensaje instantáneo o de voz.</span><span class="sxs-lookup"><span data-stu-id="fef4e-116">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="fef4e-117">Si ha configurado la directiva de ubicación para las conferencias y el proveedor de servicios E9-1-1 lo admite, el departamento de seguridad se unirá a la llamada en conferencia con audio unidireccional o bidireccional.</span><span class="sxs-lookup"><span data-stu-id="fef4e-117">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="fef4e-118">Si la llamada se interrumpe de forma prematura, el PSAP usa el número de devolución de llamada para contactar directamente con la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="fef4e-118">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

