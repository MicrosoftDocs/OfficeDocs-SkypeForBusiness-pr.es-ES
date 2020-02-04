---
title: Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63c1ce638e6bc9509c8faf46b39989b366f610a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="2e2da-102">Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL) de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e2da-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e2da-103">_**Última modificación del tema:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="2e2da-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="2e2da-104">Una aplicación de servidor de Microsoft SIP Processing language (MSPL) es una aplicación de solo secuencias de comandos que usa un lenguaje de scripting en lugar de la API 2010 de Microsoft Lync.</span><span class="sxs-lookup"><span data-stu-id="2e2da-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="2e2da-105">MSPL proporciona un control más granular sobre el filtrado y los comportamientos de proxy, además de una facilidad para enviar mensajes específicos a aplicaciones SIP basadas en transacciones.</span><span class="sxs-lookup"><span data-stu-id="2e2da-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="2e2da-106">MSPL se usa específicamente para filtrar y enrutar mensajes SIP.</span><span class="sxs-lookup"><span data-stu-id="2e2da-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="2e2da-107">Las aplicaciones MSPL se ejecutan en el mismo proceso que el módulo UserServices, mientras que un programa basado en la API de Lync 2010 se ejecuta en un proceso independiente.</span><span class="sxs-lookup"><span data-stu-id="2e2da-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="2e2da-108">Puede usar la página de **aplicación de servidor** del grupo **topología** del panel de control de Lync Server para ver una lista de aplicaciones de servidor MSPL que se ejecutan en servidores front-end en su entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e2da-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="2e2da-109">La lista muestra las secuencias de comandos disponibles para cada grupo, así como si están habilitadas o críticas.</span><span class="sxs-lookup"><span data-stu-id="2e2da-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="2e2da-110">Las secuencias de comandos se ejecutan en el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="2e2da-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="2e2da-111">Estas secuencias de comandos incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2e2da-111">These scripts include the following:</span></span>

  - <span data-ttu-id="2e2da-112">ClientVersionFilter proporciona al administrador una manera de especificar la versión de los clientes compatibles con un grupo.</span><span class="sxs-lookup"><span data-stu-id="2e2da-112">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool.</span></span> <span data-ttu-id="2e2da-113">El filtro de versión del cliente comprueba la versión del cliente y puede impedir que el cliente inicie sesión o presente al usuario con un mensaje que indica que está usando un cliente que no es compatible.</span><span class="sxs-lookup"><span data-stu-id="2e2da-113">The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported.</span></span> <span data-ttu-id="2e2da-114">El filtro de versión del cliente también se puede configurar para mostrar un mensaje al usuario que contiene la dirección URL de la última versión descargable del cliente.</span><span class="sxs-lookup"><span data-stu-id="2e2da-114">The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="2e2da-115">TranslationService traduce un número que un usuario marca a un número E. 164 según las reglas de normalización definidas por el administrador.</span><span class="sxs-lookup"><span data-stu-id="2e2da-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="2e2da-116">Para obtener más información, vea [reglas de traducción en Lync Server 2013](lync-server-2013-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="2e2da-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="2e2da-117">IncomingFederation exige la validación de la Federación de nivel de inquilino para los mensajes entre inquilinos y los mensajes entrantes de implementaciones externas.</span><span class="sxs-lookup"><span data-stu-id="2e2da-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="2e2da-118">UserServices es el componente de las conferencias, la presencia y el registrador SIP de un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="2e2da-118">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server.</span></span> <span data-ttu-id="2e2da-119">Ofrece características de conferencia, presencia y mensajería instantánea estrechamente integradas que se basan en la parte superior del proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="2e2da-119">It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="2e2da-120">InterClusterRouting es responsable de dirigir las llamadas al grupo de registrador principal de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="2e2da-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="2e2da-121">Para obtener más información, consulte [componentes de VoIP del servidor front-end para Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span><span class="sxs-lookup"><span data-stu-id="2e2da-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="2e2da-122">IIMFilter (filtro inteligente de mensajes instantáneos) bloquea los mensajes que contienen direcciones URL en las que se puede hacer clic o que intentan iniciar transferencias de archivos.</span><span class="sxs-lookup"><span data-stu-id="2e2da-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="2e2da-123">IIMFilter también comprueba la versión del cliente en nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="2e2da-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="2e2da-124">IIMFilter afecta a las transferencias de archivos que se inician mediante Lync Server o Communicator.</span><span class="sxs-lookup"><span data-stu-id="2e2da-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="2e2da-125">De forma predeterminada, los vínculos seleccionables se desactivan agregando un carácter de subrayado antes del primer carácter del vínculo.</span><span class="sxs-lookup"><span data-stu-id="2e2da-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="2e2da-126">Un administrador puede cambiar este comportamiento para que el vínculo esté bloqueado, en cuyo caso los mensajes que contengan direcciones URL en las que se puede hacer clic o que intenten iniciar una transferencia de archivos están bloqueados por el servidor para que no llegue a sus destinos previstos.</span><span class="sxs-lookup"><span data-stu-id="2e2da-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="2e2da-127">IIMFilter se instala en todos los servidores que ejecutan Lync Server, excepto los servidores proxy y los servidores de archivado.</span><span class="sxs-lookup"><span data-stu-id="2e2da-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="2e2da-128">UserPinService se usa para comprobar los números de identificación personal (PIN) para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="2e2da-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="2e2da-129">DefaultRouting es la aplicación de enrutamiento predeterminada para servidores que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2e2da-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="2e2da-130">Está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2e2da-130">It is enabled by default.</span></span> <span data-ttu-id="2e2da-131">La aplicación de enrutamiento se instala en todos los servidores Standard Edition y Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="2e2da-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="2e2da-132">ExumRouting enruta las llamadas a la mensajería unificada de Exchange Server (UM).</span><span class="sxs-lookup"><span data-stu-id="2e2da-132">ExumRouting routes calls to Exchange Server Unified Messaging (UM).</span></span> <span data-ttu-id="2e2da-133">ExumRouting determina el servidor de mensajería unificada de Exchange adecuado para enrutar la llamada a cuando haya un nuevo mensaje de correo de voz para depositar.</span><span class="sxs-lookup"><span data-stu-id="2e2da-133">ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit.</span></span> <span data-ttu-id="2e2da-134">ExumRouting también controla otros aspectos de la integración de mensajería unificada de Exchange, incluido el enrutamiento al operador automático y al acceso de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="2e2da-134">ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="2e2da-135">OutboundRouting determina la puerta de enlace que dirige una llamada a un número de teléfono según el número marcado y la autorización de marcado del usuario.</span><span class="sxs-lookup"><span data-stu-id="2e2da-135">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization.</span></span> <span data-ttu-id="2e2da-136">OutboundRouting también controla el redireccionamiento de llamadas si una puerta de enlace no puede procesar una llamada.</span><span class="sxs-lookup"><span data-stu-id="2e2da-136">OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="2e2da-137">QoEAgent recibe informes de datos de la calidad de la experiencia (QoE) a partir de puntos de conexión a través de solicitudes de servicio SIP y envía los datos a la cola de destino en el servidor de supervisión o a consumidores de terceros mediante HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="2e2da-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="2e2da-138">Para obtener más información, consulte [implementación de la supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="2e2da-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="2e2da-139">OutgoingFederation exige la validación de la Federación en el nivel de inquilino para los mensajes dirigidos a una implementación externa de destino.</span><span class="sxs-lookup"><span data-stu-id="2e2da-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="2e2da-140">AcpRoutinglos servidores proxy INVITAn a las solicitudes dirigidas al proveedor de servicios de audioconferencia a la puerta de enlace del proveedor de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="2e2da-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="2e2da-141">Entre los scripts que se ejecutan en servidores perimetrales se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2e2da-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="2e2da-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="2e2da-142">IIMFilter</span></span>

  - <span data-ttu-id="2e2da-143">OptionsHandler responde a las solicitudes de opciones entrantes con **200 aceptar** si la solicitud se destina al servidor actual.</span><span class="sxs-lookup"><span data-stu-id="2e2da-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="2e2da-144">Se usa para la validación de topología.</span><span class="sxs-lookup"><span data-stu-id="2e2da-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2e2da-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e2da-145">See Also</span></span>


[<span data-ttu-id="2e2da-146">Habilitar o deshabilitar una aplicación de servidor de Microsoft SIP Processing language (MSPL) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e2da-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="2e2da-147">Marcar una aplicación de Microsoft SIP Processing language (MSPL) como crítica o incrítica en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e2da-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

