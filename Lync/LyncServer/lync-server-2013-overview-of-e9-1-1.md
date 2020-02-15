---
title: 'Lync Server 2013: información general sobre E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6bc8d1f743db31cd248b750a67121c0c6664d07
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="9807e-102">Información general sobre E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9807e-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9807e-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="9807e-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="9807e-104">Microsoft Lync Server 2013 admite llamadas mejoradas 9-1-1 (E9-1-1) desde los clientes de Lync y los dispositivos de Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="9807e-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="9807e-105">Cuando configure Lync Server para E9-1-1, las llamadas de emergencia realizadas desde Lync 2013 o Lync Phone Edition incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos del servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="9807e-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="9807e-106">Las ERL se componen de direcciones civiles (es decir, postales) e información adicional que ayuda a identificar con mayor precisión una ubicación en edificios de oficinas y otras instalaciones con varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="9807e-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="9807e-107">Cuando un usuario realiza una llamada de emergencia, Lync Server enruta el audio de la llamada, junto con la ubicación y la información de devolución de llamada, a través de un servidor de mediación a un proveedor de servicios E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="9807e-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="9807e-108">Desde aquí se facilita la ubicación del autor de la llamada junto con una clave de consulta de servicios de emergencia (ESQK) que permite al PSAP buscar la ERL de esta persona.</span><span class="sxs-lookup"><span data-stu-id="9807e-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="9807e-109">Lync Server admite dos métodos para el enrutamiento de llamadas de emergencia a un proveedor de servicios E9-1-1:</span><span class="sxs-lookup"><span data-stu-id="9807e-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="9807e-110">Una conexión de enlace troncal SIP (Protocolo de inicio de sesión) a un proveedor de servicios E9-1-1 cualificado.</span><span class="sxs-lookup"><span data-stu-id="9807e-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="9807e-111">Una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios E9-1-1 basado en una Red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="9807e-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="9807e-112">Cuando se usa un proveedor de servicios E9-1-1 de tronco SIP, se agrega ERL a la base de datos del servicio de información de ubicación y, a continuación, se validan las ubicaciones con una guía de dirección principal (MSAG) mantenida por el proveedor de servicios E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="9807e-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="9807e-113">Si el proveedor recibe una llamada que no cuenta con información de ubicación o cuya ubicación no se ha validado en la MSAG, redirige la llamada a un Centro de respuesta de llamadas SOS (ECRC) nacional o regional, que dispone de personal especialmente preparado para obtener de forma oral la ubicación del autor de la llamada (si es posible) y redirigir manualmente la llamada al PSAP correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9807e-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="9807e-114">Algunos proveedores de servicios E9-1-1 de enlace troncal SIP también proporcionan a los clientes un número de marcado directo (DID) de RTC para el ECRC, que constituye un medio alternativo de enrutamiento de las llamadas al 9-1-1 si por algún motivo se produce un error en el enlace troncal SIP.</span><span class="sxs-lookup"><span data-stu-id="9807e-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="9807e-115">A diferencia de la multiplexación por división de tiempo (TDM) y los teléfonos de central de conmutación (PBX) basados en IP, que tienen ubicaciones fijas, un punto de conexión de Lync puede ser muy móvil.</span><span class="sxs-lookup"><span data-stu-id="9807e-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="9807e-116">Al implementar la característica E9-1-1, Lync Server ayuda a garantizar que no importa dónde se encuentre el autor de la llamada, a que la llamada de emergencia se puede enrutar a la PSAP que atiende la ubicación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9807e-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="9807e-117">Por ejemplo, si la oficina principal de un usuario está ubicada en Redmond (Washington), pero el usuario realiza una llamada SOS desde el equipo de una sucursal en Wichita (Kansas), el proveedor de servicios E9-1-1 basado en RTC o de enlace troncal SIP redirigirá la llamada al PSAP de Wichita, y no al de Redmond.</span><span class="sxs-lookup"><span data-stu-id="9807e-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="9807e-118">Cuando se usa una puerta de enlace ELIN, también se agrega ERL a la base de datos del servicio de información de ubicación, pero también se incluye un número de ELIN para cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="9807e-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="9807e-119">El número ELIN pasa a ser el número de llamada SOS durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9807e-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="9807e-120">Debe comprobar que el proveedor de RTC carga los ELIN en una base de datos de identificación de ubicación automática (ALI).</span><span class="sxs-lookup"><span data-stu-id="9807e-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9807e-121">Los dispositivos analógicos conectados a Lync no pueden recibir información de ubicación del servicio de información de ubicación o la ubicación de transmisión al proveedor de servicios E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="9807e-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="9807e-122">Si usa la opción del proveedor de servicios E9-1-1 de enlace troncal SIP y tiene que admitir llamadas E9-1-1 desde teléfonos analógicos, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="9807e-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9807e-123"><STRONG></STRONG>&nbsp;Opción&nbsp;tradicional&nbsp;PS-Ali si tiene puertas de enlace RTC locales en cada sitio donde se implementan teléfonos analógicos y cada teléfono analógico tiene un, puede aprovisionar la ubicación del dispositivo analógico directamente con un proveedor de servicios de identificación de ubicación automática (PS-Ali) o conmutador privado.</span><span class="sxs-lookup"><span data-stu-id="9807e-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="9807e-124">En este caso, debe configurar directivas de voz específicas de Lync y asignarlas a los objetos contacto del dispositivo analógico para que las llamadas E9-1-1 que se realizan desde esos teléfonos se redirijan directamente a través de la puerta de enlace local al proveedor de RTC del sitio (en lugar de redirigir la llamada a un enlace troncal SIP del proveedor de servicios E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="9807e-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="9807e-125">Cuando se realiza una llamada SOS, una base de datos de un proveedor de PS-ALI asociado con el enlace troncal de RTC asigna el DID de cada teléfono analógico a una ubicación física, y proporciona esta ubicación al PSAP.</span><span class="sxs-lookup"><span data-stu-id="9807e-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="9807e-126">Estos registros deben actualizarse con el proveedor de servicios de PS-ALI cada vez que los teléfonos se desplazan a ERL diferentes.</span><span class="sxs-lookup"><span data-stu-id="9807e-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="9807e-127"><STRONG></STRONG>&nbsp;Opción&nbsp;del&nbsp;proveedor de servicios E9-1-1 puede registrar el analógico de teléfono analógico y su ERL correspondiente con el proveedor de servicios E9-1-1, si el proveedor de servicios E9-1-1 lo admite.</span><span class="sxs-lookup"><span data-stu-id="9807e-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="9807e-128">Si el proveedor recibe una llamada de Lync Server que no incluye datos PIDF-lo, el proveedor puede ver si hay una coincidencia de base de datos en el número DID de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="9807e-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="9807e-129">Mediante la ERL que se recupera desde su base de datos, el proveedor puede redirigir automáticamente la llamada SOS al PSAP correcto y este recibirá el DID del dispositivo analógico y un registro de ESQK que permite al distribuidor buscar la ubicación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9807e-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="9807e-p108">Si usa la opción de puerta de enlace de ELIN y necesita compatibilidad con las llamadas E9-1-1 desde teléfonos analógicos, puede dar la ubicación del dispositivo analógico directamente con el proveedor de servicios PS-ALI, como se describe en la primera opción mencionada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9807e-p108">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.    </span></span></div>

<span data-ttu-id="9807e-131">Desde el punto de vista de Lync Server, el proceso de E9-1-1 se puede separar en dos fases:</span><span class="sxs-lookup"><span data-stu-id="9807e-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="9807e-132">Fase 1: adquisición de una ubicación</span><span class="sxs-lookup"><span data-stu-id="9807e-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="9807e-133">Fase 2: enrutamiento de la llamada SOS al proveedor de servicios E9-1-1</span><span class="sxs-lookup"><span data-stu-id="9807e-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="9807e-134">En esta sección se describe cómo funcionan estas fases.</span><span class="sxs-lookup"><span data-stu-id="9807e-134">This section describes how these stages work.</span></span>

<span data-ttu-id="9807e-135">Si va a configurar la infraestructura para detectar automáticamente la ubicación del cliente, primero debe decidir qué elementos de red usará para asignar los autores de las llamadas a las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9807e-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="9807e-136">Para obtener más información sobre las opciones posibles, consulte [definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span><span class="sxs-lookup"><span data-stu-id="9807e-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9807e-137">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9807e-137">In This Section</span></span>

  - [<span data-ttu-id="9807e-138">Adquirir una ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9807e-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="9807e-139">Routing E9-1-1 calls by Using a SIP trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9807e-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="9807e-140">Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9807e-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

