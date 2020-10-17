---
title: 'Lync Server 2013: componentes VoIP del servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62261a4d4651e38941f5068b58636b82d0151965
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500707"
---
# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="9e6f2-102">Componentes VoIP del servidor front-end para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e6f2-102">Front End Server VoIP components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e6f2-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9e6f2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9e6f2-104">Los componentes de VoIP ubicados en los servidores front-end son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9e6f2-104">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="9e6f2-105">Servicio de conversión</span><span class="sxs-lookup"><span data-stu-id="9e6f2-105">Translation Service</span></span>

  - <span data-ttu-id="9e6f2-106">Componente de enrutamiento de entrada</span><span class="sxs-lookup"><span data-stu-id="9e6f2-106">Inbound Routing component</span></span>

  - <span data-ttu-id="9e6f2-107">Componente de enrutamiento de salida</span><span class="sxs-lookup"><span data-stu-id="9e6f2-107">Outbound Routing component</span></span>

  - <span data-ttu-id="9e6f2-108">Componente de enrutamiento de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="9e6f2-108">Exchange UM Routing component</span></span>

  - <span data-ttu-id="9e6f2-109">Componente de enrutamiento entre clústeres</span><span class="sxs-lookup"><span data-stu-id="9e6f2-109">Intercluster Routing component</span></span>

  - [<span data-ttu-id="9e6f2-110">Componente de servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e6f2-110">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="9e6f2-111">Servicio de conversión</span><span class="sxs-lookup"><span data-stu-id="9e6f2-111">Translation Service</span></span>

<span data-ttu-id="9e6f2-p101">El servicio de conversión es el componente de servidor que se encarga de convertir un número marcado al formato E.164 u otro formato, de acuerdo con las reglas de normalización definidas por el administrador. El Servicio de conversión puede convertir a formatos distintos de E.164 si la organización utiliza un sistema de numeración privado o una puerta de enlace o PBX que no admite E.164.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="9e6f2-114">Componente de enrutamiento de entrada</span><span class="sxs-lookup"><span data-stu-id="9e6f2-114">Inbound Routing Component</span></span>

<span data-ttu-id="9e6f2-115">El componente de enrutamiento de entrada se encarga de las llamadas entrantes, en gran medida de acuerdo con las preferencias especificadas por los usuarios en los clientes de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-115">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="9e6f2-116">También facilita las llamadas delegadas y las llamadas simultáneas, si el usuario las configura.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-116">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="9e6f2-117">Por ejemplo, los usuarios especifican si las llamadas sin contestar se transfieren o simplemente se registran para su notificación.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-117">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="9e6f2-118">Si el desvío de llamadas está habilitado, los usuarios pueden especificar si las llamadas no respondidas deben reenviarse a otro número o a un servidor de mensajería unificada de Exchange que se haya configurado para proporcionar el contestador automático.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-118">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="9e6f2-119">El componente de enrutamiento de entrada está instalado de forma predeterminada en todos los servidores front-end y de servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-119">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="9e6f2-120">Componente de enrutamiento de salida</span><span class="sxs-lookup"><span data-stu-id="9e6f2-120">Outbound Routing Component</span></span>

<span data-ttu-id="9e6f2-121">El componente de enrutamiento de salida redirige las llamadas a destinos PBX o RTC.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-121">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="9e6f2-122">Aplica reglas de autorización de llamadas, que se definen en la directiva de voz del usuario, a los autores de las llamadas y determina la puerta de enlace RTC óptima para enrutar cada llamada.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-122">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="9e6f2-123">El componente de enrutamiento de salida está instalado de forma predeterminada en todos los servidores front-end y de servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-123">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="9e6f2-124">La lógica de enrutamiento utilizada por el componente de enrutamiento de salida la configuran en gran medida administradores de red o de telefonía de acuerdo con los requisitos de sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-124">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="9e6f2-125">Componente de enrutamiento de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="9e6f2-125">Exchange UM Routing Component</span></span>

<span data-ttu-id="9e6f2-126">El componente de enrutamiento de mensajería unificada de Exchange administra el enrutamiento entre Lync Server y los servidores que ejecutan la mensajería unificada (MU) de Exchange para integrar Lync Server con las características de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-126">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="9e6f2-127">El componente de enrutamiento de mensajería unificada de Exchange también controla el reenrutamiento del correo de voz por la RTC si los servidores de mensajería unificada de Exchange no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-127">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="9e6f2-128">Si tiene usuarios de Enterprise Voice en sitios de sucursal que no tienen un vínculo WAN resistente a un sitio central, la aplicación de sucursal con funciones de supervivencia que se implementa en el sitio de sucursal proporciona supervivencia de correo de voz para usuarios de sucursal durante una interrupción de la WAN.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-128">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="9e6f2-129">Cuando el vínculo WAN no está disponible, la aplicación de sucursal con funciones de supervivencia hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e6f2-129">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="9e6f2-130">vuelve a enrutar las llamadas por la RTC al servidor de mensajería unificada de Exchange del sitio central</span><span class="sxs-lookup"><span data-stu-id="9e6f2-130">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="9e6f2-131">proporciona al usuario la posibilidad de recuperar mensajes de correo de voz por la RTC</span><span class="sxs-lookup"><span data-stu-id="9e6f2-131">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="9e6f2-132">pone en cola las notificaciones de llamada perdida y luego las carga en el servidor de mensajería unificada de Exchange cuando el vínculo WAN se restaura.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-132">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="9e6f2-133">Para habilitar el redireccionamiento del correo de voz, se recomienda que el administrador de Exchange configure el operador automático de mensajería unificada (AA) de Exchange para que sólo acepte mensajes.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-133">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="9e6f2-134">Para obtener más información sobre estas características, consulte [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y [Planning for Enterprise Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-134">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="9e6f2-135">Componente de enrutamiento entre clústeres</span><span class="sxs-lookup"><span data-stu-id="9e6f2-135">Intercluster Routing Component</span></span>

<span data-ttu-id="9e6f2-p105">El componente de enrutamiento entre clústeres es el responsable del enrutamiento de llamadas al grupo principal del registrador de los destinatarios de las llamadas. Si este no está disponible, el componente enruta la llamada al grupo de reserva del registrador de los destinatarios de las llamadas. Si no se puede tener acceso a los grupos principal y de reserva del registrador de los destinatarios de las llamadas por la red IP, el componente de enrutamiento entre clústeres desvía la llamada por la RTC al número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-p105">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool. If that is unavailable, the component routes the call to the callee’s backup Registrar pool. If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="9e6f2-139">Otros componentes de servidor front-end necesarios para VoIP</span><span class="sxs-lookup"><span data-stu-id="9e6f2-139">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="9e6f2-140">Entre otros componentes que residen en el servidor front-end o el director que proporciona compatibilidad esencial para VoIP, pero que no son componentes de VoIP, se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9e6f2-140">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="9e6f2-141">**Servicios de usuario.**</span><span class="sxs-lookup"><span data-stu-id="9e6f2-141">**User Services.**</span></span> <span data-ttu-id="9e6f2-142">Realiza una búsqueda inversa de número en el número de teléfono de destino de cada llamada entrante y asocia ese número al URI de SIP del usuario de destino.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-142">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="9e6f2-143">Con esta información, el componente de enrutamiento de entrada distribuye la llamada a los extremos de SIP registrados del usuario.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-143">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="9e6f2-144">Servicios de usuario es un componente principal de todos los directores y servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-144">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="9e6f2-145">**Replicador de usuarios.**</span><span class="sxs-lookup"><span data-stu-id="9e6f2-145">**User Replicator.**</span></span> <span data-ttu-id="9e6f2-146">Extrae números de teléfono de usuario de servicios de dominio de Active Directory y los escribe en las tablas de la base de datos RTC, donde están disponibles para los servicios de usuario y el servidor de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-146">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="9e6f2-147">El replicador de usuarios es un componente principal en todos los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-147">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="9e6f2-148">**Servidor de libreta de direcciones.**</span><span class="sxs-lookup"><span data-stu-id="9e6f2-148">**Address Book Server.**</span></span> <span data-ttu-id="9e6f2-149">Proporciona información de la lista global de direcciones de servicios de dominio de Active Directory a clientes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-149">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="9e6f2-150">También recupera información de contactos y usuarios de la base de datos RTC, escribe la información en los archivos de la libreta de direcciones y, a continuación, almacena los archivos en una carpeta compartida en la que los clientes de Lync los descargan.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-150">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="9e6f2-151">El servidor de la libreta de direcciones escribe la información en la base de datos de RTCAb, que usa el servicio de consulta Web de la libreta de direcciones para responder a las consultas de búsqueda de los usuarios desde Microsoft Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-151">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="9e6f2-152">Opcionalmente, normaliza los números de teléfono de los usuarios de la empresa que se escriben en la base de datos RTC con el fin de aprovisionar contactos de usuarios en Lync.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-152">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="9e6f2-153">El servicio de libreta de direcciones está instalado de forma predeterminada en todos los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-153">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="9e6f2-154">El servicio de consulta Web de la libreta de direcciones se instala de forma predeterminada con los servicios web en cada uno de los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-154">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

