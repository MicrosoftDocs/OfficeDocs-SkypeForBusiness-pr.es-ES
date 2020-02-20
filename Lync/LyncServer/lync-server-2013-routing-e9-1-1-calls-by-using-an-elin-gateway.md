---
title: 'Lync Server 2013: enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN'
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
ms.openlocfilehash: 93e2e3bf94175f2f0ec3f4f7528cc969fe19529c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="f8727-102">Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8727-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8727-103">_**Última modificación del tema:** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="f8727-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="f8727-104">Algunos asociados del Programa de interoperabilidad abierto de comunicaciones unificadas proporcionan puertas de enlace de número de identificación de ubicación de emergencia (ELIN), que constituyen una alternativa a las conexiones troncales SIP con un proveedor de servicio E9-1-1 cualificado.</span><span class="sxs-lookup"><span data-stu-id="f8727-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="f8727-105">Las puertas de enlace ELIN admiten la conectividad ISDN o de contabilización de mensajes automática y centralizada (CAMA) con servicios E9-1-1 basados en la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="f8727-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="f8727-106">Para más información sobre los socios que proporcionan ELIN puertas de enlace y vínculos a la [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425)documentación, consulte.</span><span class="sxs-lookup"><span data-stu-id="f8727-106">For details about partners who provide ELIN gateways and links to their documentation, see [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="f8727-107">Al igual que las conexiones de enlace troncal SIP a los proveedores de servicios E9-1-1, las puertas de enlace de ELIN también proporcionan los medios para enrutar una llamada de emergencia al punto de respuesta de seguridad pública más apropiado del autor de la llamada (PSAP), pero estas puertas de enlace utilizan un ELIN como identificador de ubicación.</span><span class="sxs-lookup"><span data-stu-id="f8727-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="f8727-108">Defina Elin para cada ubicación de respuesta de emergencia (ERL) de la organización (para obtener más información, consulte [administrar ubicaciones para puertas de enlace de Elin en Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span><span class="sxs-lookup"><span data-stu-id="f8727-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="f8727-109">Cuando se usa una puerta de enlace de ELIN para las llamadas de emergencia, se usa la misma infraestructura de Lync Server E9-1-1 que se usaría para una conexión de enlace troncal SIP.</span><span class="sxs-lookup"><span data-stu-id="f8727-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="f8727-110">Es decir, la base de datos del servicio de información de ubicación proporciona la ubicación al cliente de Lync Server y la Directiva de ubicación habilita la característica y define el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="f8727-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="f8727-111">Sin embargo, con una puerta de enlace ELIN, debe agregar el Elin a la base de datos del servicio de información de ubicación y hacer que el operador de RTC los cargue a la base de datos de identificación de ubicación automática (ALI).</span><span class="sxs-lookup"><span data-stu-id="f8727-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="f8727-112">Cuando un cliente de Lync obtiene su ubicación del servicio de información de ubicación, la ubicación incluye ELIN.</span><span class="sxs-lookup"><span data-stu-id="f8727-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="f8727-113">Durante las llamadas de emergencia, el ELIN se incluye con la información de ubicación que se envía a la puerta de enlace ELIN.</span><span class="sxs-lookup"><span data-stu-id="f8727-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="f8727-114">Esta puerta de enlace identifica la llamada como llamada de emergencia y cambia el número de la persona que llama por el ELIN.</span><span class="sxs-lookup"><span data-stu-id="f8727-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="f8727-115">A continuación, la puerta de enlace ELIN enruta la llamada al RTC con el ELIN como número llamante.</span><span class="sxs-lookup"><span data-stu-id="f8727-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="f8727-116">El proveedor de servicios E9-1-1 de RTC busca el ELIN en la base de datos ALI, que actúa como una base de datos adicional a la base de datos de guía de direcciones principal (MSAG).</span><span class="sxs-lookup"><span data-stu-id="f8727-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="f8727-117">Acto seguido el operador de RTC envía la llamada al PSAP más adecuado en función de la búsqueda realizada en la base de datos ALI y el PSAP envía el personal de emergencia disponible a la ubicación de la persona que realiza según los resultados de la búsqueda ALI.</span><span class="sxs-lookup"><span data-stu-id="f8727-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="f8727-118">El número de llamada se almacena en la memoria caché de la puerta de enlace ELIN durante un tiempo predeterminado para las devoluciones de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f8727-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="f8727-119">Durante la devolución de llamada, el PSAP contacta con la puerta de enlace ELIN que, a su vez, cambia el ELIN por el número de llamada directa a la extensión (DID) de la persona que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="f8727-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="f8727-120">Las puertas de enlace ELIN solo admiten las llamadas de emergencia desde la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="f8727-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="f8727-121">No admiten las llamadas de emergencia realizadas fuera de su red.</span><span class="sxs-lookup"><span data-stu-id="f8727-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8727-122">Para obtener más información sobre el uso de una conexión de enlace troncal SIP para llamadas de emergencia, consulte <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by Using a SIP trunk in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f8727-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f8727-123">El siguiente diagrama muestra cómo se enruta una llamada de emergencia desde Lync Server a la PSAP cuando se usa una puerta de enlace ELIN.</span><span class="sxs-lookup"><span data-stu-id="f8727-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="f8727-124">**Enrutamiento de llamadas E9-1-1 con una puerta de enlace ELIN**</span><span class="sxs-lookup"><span data-stu-id="f8727-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="f8727-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="f8727-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="f8727-126">Un SIP INVITE que contiene la ubicación, el número de devolución de llamada del autor de la llamada y la dirección URL de notificación (opcional) y el número de devolución de llamada de conferencia se enruta a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8727-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="f8727-127">Lync Server coincide con el número de emergencia y, a continuación, enruta la llamada (en función del valor **uso de RTC** definido en la Directiva de ubicación correspondiente) a un servidor de mediación y desde ahí a una puerta de enlace Elin.</span><span class="sxs-lookup"><span data-stu-id="f8727-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="f8727-128">La puerta de enlace ELIN enruta la llamada a través de un tronco ISDN o CAMA a la RTC.</span><span class="sxs-lookup"><span data-stu-id="f8727-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="f8727-p106">La RTC identifica la llamada como una llamada de emergencia y la enruta a un enrutador selectivo de E9-1-1 de la red, que busca el número del autor de la llamada en la base de datos ALI para obtener la ubicación geográfica. Tras ello, el enrutador selectivo de E9-1-1 envía la llamada al PSAP más adecuado en función de la información de ubicación que haya suministrado la base de datos ALI.</span><span class="sxs-lookup"><span data-stu-id="f8727-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="f8727-132">Si ha configurado la Directiva de ubicación para las notificaciones, se enviará a uno o más de los responsables de seguridad de la organización un mensaje instantáneo especial de notificación de emergencia de Lync.</span><span class="sxs-lookup"><span data-stu-id="f8727-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="f8727-133">Este mensaje siempre aparece en la pantalla de los responsables de seguridad y contiene el nombre, número de teléfono, hora y ubicación del autor de la llamada para que el personal de seguridad pueda ponerse en contacto con él rápidamente mediante un mensaje instantáneo o de voz.</span><span class="sxs-lookup"><span data-stu-id="f8727-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="f8727-p108">En caso de que la llamada se interrumpa antes de tiempo, el PSAP usa el ELIN para ponerse en contacto directamente con el autor de la llamada. La puerta de enlace ELIN intercambia el ELIN por el DID del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f8727-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

