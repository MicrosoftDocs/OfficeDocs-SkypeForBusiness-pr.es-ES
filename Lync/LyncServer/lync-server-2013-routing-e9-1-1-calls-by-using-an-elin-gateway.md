---
title: 'Lync Server 2013: Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97c921a0b31438103ba74dcc64925e5b2069a8e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="38332-102">Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38332-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38332-103">_**Última modificación del tema:** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="38332-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="38332-104">Algunos asociados del Programa de interoperabilidad abierto de comunicaciones unificadas proporcionan puertas de enlace de número de identificación de ubicación de emergencia (ELIN), que constituyen una alternativa a las conexiones troncales SIP con un proveedor de servicio E9-1-1 cualificado.</span><span class="sxs-lookup"><span data-stu-id="38332-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="38332-105">Las puertas de enlace ELIN admiten la conectividad ISDN o de contabilización de mensajes automática y centralizada (CAMA) con servicios E9-1-1 basados en la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="38332-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="38332-106">Para obtener más información sobre los partners que proporcionan puertas de enlace de ELIN y vínculos [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)a la documentación, consulte.</span><span class="sxs-lookup"><span data-stu-id="38332-106">For details about partners who provide ELIN gateways and links to their documentation, see [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="38332-107">Al igual que las conexiones troncales SIP con los proveedores de servicios E9-1-1, las puertas de enlace ELIN también ofrecen los medios necesarios para enrutar una llamada de emergencia al punto de respuesta de seguridad pública (PSAP) más adecuado para el autor de la llamada, pero estas puertas de enlace usan un número ELIN para identificar la ubicación.</span><span class="sxs-lookup"><span data-stu-id="38332-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="38332-108">Defina ELINs para cada ubicación de respuesta de emergencia (ERL) de su organización (para obtener más información, vea [administrar ubicaciones de puertas de enlace de Elin en Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span><span class="sxs-lookup"><span data-stu-id="38332-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="38332-109">Cuando use una puerta de enlace de ELIN para llamadas de emergencia, use la misma infraestructura de Lync Server E9-1-1 que usaría para una conexión de protocolo troncal de SIP.</span><span class="sxs-lookup"><span data-stu-id="38332-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="38332-110">Es decir, la base de datos del servicio de información de ubicación proporciona la ubicación al cliente de Lync Server y la Directiva de ubicación la habilita y define el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="38332-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="38332-111">Sin embargo, con una puerta de enlace de ELIN necesita agregar la ELINs a la base de datos de servicios de información de ubicación y hacer que el operador PSTN la cargue en la base de datos de identificación de ubicación automática (ALI).</span><span class="sxs-lookup"><span data-stu-id="38332-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="38332-112">Cuando un cliente de Lync obtiene su ubicación desde el servicio de información de ubicación, la ubicación incluye la ELIN.</span><span class="sxs-lookup"><span data-stu-id="38332-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="38332-113">Durante una llamada de emergencia, ELIN se incluye con la ubicación que se envía a la puerta de enlace de ELIN.</span><span class="sxs-lookup"><span data-stu-id="38332-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="38332-114">La puerta de enlace de ELIN identifica la llamada como llamada de emergencia e intercambia el número de la persona que llama con el ELIN.</span><span class="sxs-lookup"><span data-stu-id="38332-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="38332-115">A continuación, la puerta de enlace de ELIN enruta la llamada a la RTC con el ELIN como el número de llamada.</span><span class="sxs-lookup"><span data-stu-id="38332-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="38332-116">El proveedor E9-1-1 de RTC busca la ELIN en la base de datos de ALI, que es una base de datos complementaria para la base de datos de la guía de dirección maestra (MSAG).</span><span class="sxs-lookup"><span data-stu-id="38332-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="38332-117">La RTC envía entonces la llamada a la PSAP más adecuada en función de la búsqueda de ALI, y el PSAP envía los primeros respondedores a la ubicación de la persona que llama basándose en la búsqueda de ALI.</span><span class="sxs-lookup"><span data-stu-id="38332-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="38332-118">El número de llamada se almacena en caché en la puerta de enlace de ELIN durante un período de tiempo predefinido para las devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="38332-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="38332-119">Durante una devolución de llamada, el PSAP llega a la puerta de enlace de ELIN, que intercambia el ELIN para el número de marcado interno directo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="38332-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="38332-120">Las puertas de enlace de ELIN solo admiten llamadas de emergencia desde la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="38332-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="38332-121">No admiten llamadas de emergencia hechas desde fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="38332-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="38332-122">Para obtener detalles sobre el uso de una conexión de troncal de SIP para llamadas de emergencia, consulte <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls Using an SIP trunk in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="38332-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="38332-123">En el siguiente diagrama se muestra cómo se enruta una llamada de emergencia de Lync Server a la PSAP al usar una puerta de enlace de ELIN.</span><span class="sxs-lookup"><span data-stu-id="38332-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="38332-124">**Enrutamiento de llamadas E9-1-1 con una puerta de enlace ELIN**</span><span class="sxs-lookup"><span data-stu-id="38332-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="38332-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="38332-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="38332-126">Una invitación SIP que contiene la ubicación, el número de devolución de llamada de la persona que llama y la dirección URL de notificación (opcional) y el número de devolución de llamada de la Conferencia se enrutan a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38332-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="38332-127">Lync Server coincide con el número de emergencia y, después, enruta la llamada (según el valor de **uso de RTC** definido en la política de ubicación correspondiente) a un servidor de mediación y desde allí a una puerta de enlace de Elin.</span><span class="sxs-lookup"><span data-stu-id="38332-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="38332-128">La puerta de enlace ELIN enruta la llamada a través de un tronco ISDN o CAMA a la RTC.</span><span class="sxs-lookup"><span data-stu-id="38332-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="38332-p106">La RTC identifica la llamada como una llamada de emergencia y la enruta a un enrutador selectivo de E9-1-1 de la red, que busca el número del autor de la llamada en la base de datos ALI para obtener la ubicación geográfica. Tras ello, el enrutador selectivo de E9-1-1 envía la llamada al PSAP más adecuado en función de la información de ubicación que haya suministrado la base de datos ALI. </span><span class="sxs-lookup"><span data-stu-id="38332-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="38332-132">Si ha configurado la Directiva de ubicación para las notificaciones, uno o varios de los responsables de seguridad de la organización reciben un mensaje instantáneo especial de notificación de emergencia de Lync.</span><span class="sxs-lookup"><span data-stu-id="38332-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="38332-133">Este mensaje siempre se muestra en la pantalla de los equipos de los responsables de seguridad y proporciona información sobre el nombre, el número de teléfono, la hora y la ubicación de la persona que realiza la llamada, lo que permite al personal de seguridad responder con rapidez a la persona que realiza la llamada de emergencia por medio de un mensaje instantáneo o de voz.</span><span class="sxs-lookup"><span data-stu-id="38332-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="38332-p108">En caso de que la llamada se interrumpa antes de tiempo, el PSAP usa el ELIN para ponerse en contacto directamente con el autor de la llamada. La puerta de enlace ELIN intercambia el ELIN por el DID del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="38332-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

