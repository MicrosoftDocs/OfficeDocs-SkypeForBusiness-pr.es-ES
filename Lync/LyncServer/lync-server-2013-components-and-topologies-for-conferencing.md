---
title: 'Lync Server 2013: Componentes y topologías para conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5caf5ba33e863e08bf4f728d2bf11394f37f20b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="fe9b6-102">Componentes y topologías para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe9b6-102">Components and topologies for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe9b6-103">_**Última modificación del tema:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="fe9b6-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="fe9b6-104">Al seleccionar conferencias en el generador de topologías, las conferencias se implementan como parte del servidor front-end o del servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="fe9b6-105">Las conferencias de acceso telefónico local y el uso compartido de PowerPoint requieren configuración y componentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="fe9b6-106">En las siguientes secciones se describen los componentes y las topologías compatibles para conferencias web, conferencias A/V y conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="fe9b6-107">Componentes admitidos</span><span class="sxs-lookup"><span data-stu-id="fe9b6-107">Supported Components</span></span>

<span data-ttu-id="fe9b6-108">Los únicos componentes que las conferencias web y las conferencias A/V requieren son los servidores front-end de la organización o los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="fe9b6-109">Para obtener una lista de los requisitos de hardware y software para los servidores front-end y los servidores Standard Edition, consulte [hardware admitido para Lync server 2013](lync-server-2013-supported-hardware.md) y [compatibilidad con el software de servidor y la infraestructura en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="fe9b6-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="fe9b6-110">Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar el uso compartido y el procesamiento de presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="fe9b6-111">Para obtener más información sobre cómo instalar y configurar el servidor de Office Web Apps, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="fe9b6-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="fe9b6-112">Además de los requisitos para las conferencias web y A/V, las conferencias de acceso telefónico local usan los siguientes componentes de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="fe9b6-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="fe9b6-113">\*\*\*\*   El servicio de aplicación de servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas (UC).</span><span class="sxs-lookup"><span data-stu-id="fe9b6-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="fe9b6-114">Las conferencias de acceso telefónico local usan dos aplicaciones de comunicaciones unificadas que requieren servicio de aplicación: operador de conferencia y anuncio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="fe9b6-115">El servicio de aplicación se instala y activa de forma predeterminada en todos los servidores front-end de un grupo de servidores front-end y en todos los servidores Standard Edition cuando se implementa una carga de trabajo de conferencia y se selecciona la opción de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="fe9b6-116">\*\*\*\*   El Asistente para conferencias de conferencia del operador de conferencia es una aplicación de comunicaciones unificadas que acepta llamadas de red telefónica conmutada (RTC), reproduce preguntas y une las llamadas a una conferencia a/V.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="fe9b6-117">El operador de conferencias se instala y activa de forma predeterminada al implementar una carga de trabajo de conferencia y seleccionar la opción de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="fe9b6-118">**Anuncio de conferencia**   la aplicación de anuncios de conferencias es una aplicación de comunicaciones unificadas que reproduce tonos y se solicita a los participantes de la RTC en determinadas acciones, como cuando se unen a los participantes o salen de una conferencia. los participantes se silencian o se silencian, alguien entra en la sala de conferencias o la Conferencia está bloqueada o desbloqueada.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="fe9b6-119">La aplicación de anuncio de conferencia también es compatible con los comandos multifrecuencia de tono dual (DTMF) del teclado del teléfono.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="fe9b6-120">El anuncio de conferencia se instala automáticamente y se activa de forma predeterminada al implementar una carga de trabajo de conferencia y seleccionar la opción de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="fe9b6-121">**Página configuración de conferencia de acceso telefónico**   local la página Configuración de conferencia de acceso telefónico local muestra los números de acceso telefónico local de la Conferencia con los idiomas disponibles, la información de conferencia asignada (es decir, las reuniones que no es necesario programar) y controles de DTMF en conferencia y admite la administración del número de identificación personal (PIN) e información de conferencia asignada.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="fe9b6-122">La página de Configuración de conferencia de acceso telefónico local se instala automáticamente como parte de los servicios web.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="fe9b6-123">**Lync Server 2013, servidor de mediación y**   Conferencia de acceso telefónico local de la puerta de enlace RTC requiere un servidor de mediación para traducir la señalización (y los medios, en algunas configuraciones) entre Lync Server 2013 y la puerta de enlace RTC, y una puerta de enlace RTC para traducir señalización y medios entre el servidor de mediación y la puerta de enlace PSTN.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="fe9b6-124">Para las conferencias de acceso telefónico local, debe implementar al menos un servidor de mediación y al menos uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="fe9b6-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="fe9b6-125">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="fe9b6-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="fe9b6-126">Un sistema IP-PBX</span><span class="sxs-lookup"><span data-stu-id="fe9b6-126">IP-PBX</span></span>
    
      - <span data-ttu-id="fe9b6-127">Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta por medio de la configuración de un tronco SIP</span><span class="sxs-lookup"><span data-stu-id="fe9b6-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe9b6-128">Si también va a implementar la telefonía IP empresarial, el servidor de mediación y las puertas de enlace RTC forman parte de la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="fe9b6-129">Si no está implementando la telefonía IP empresarial, debe implementar al menos un servidor de mediación y, como mínimo, una puerta de enlace PSTN, IP-PBX o SBC para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="fe9b6-130">\*\*\*\*   El almacén de archivos del almacén de archivos se usa para archivos de audio de nombres grabados.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="fe9b6-131">El almacenamiento de archivos es un componente estándar de toda implementación Enterprise Edition o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="fe9b6-132">\*\*\*\* Almacén de usuario del almacén de usuario se usa para almacenar los pin de 2013 de Lync Server.   </span><span class="sxs-lookup"><span data-stu-id="fe9b6-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="fe9b6-133">Los PIN tienen asignado un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-133">PINs are hashed.</span></span> <span data-ttu-id="fe9b6-134">El almacenamiento de usuarios es un componente estándar de toda implementación Enterprise Edition o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="fe9b6-135">**Panel de control de Lync Server**   es posible configurar la configuración de acceso telefónico mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="fe9b6-136">**Shell de administración de Lync Server**   toda la configuración de acceso telefónico local se puede establecer mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="fe9b6-137">Los cmdlets del shell de administración de Lync Server están disponibles para implementar, configurar, ejecutar, supervisar y solucionar problemas de aplicaciones del operador de conferencias y de la aplicación de anuncios de conferencias.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="fe9b6-138">Para obtener más información sobre cmdlets específicos, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="fe9b6-139">Topologías admitidas</span><span class="sxs-lookup"><span data-stu-id="fe9b6-139">Supported Topologies</span></span>

<span data-ttu-id="fe9b6-140">En Lync Server 2013, el servidor que ejecuta servicios de conferencia siempre se encuentra en los servidores front-end o servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="fe9b6-141">Durante la implementación inicial, Topology Builder le ofrece la opción de incluir conferencias en su topología.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="fe9b6-142">También puede utilizar el generador de topologías para agregar conferencias a una implementación existente.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="fe9b6-143">Para obtener más información, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="fe9b6-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="fe9b6-144">Toplogies de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="fe9b6-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="fe9b6-145">Puede implementar conferencias de acceso telefónico local en las siguientes topologías y configuraciones:</span><span class="sxs-lookup"><span data-stu-id="fe9b6-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="fe9b6-146">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="fe9b6-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="fe9b6-147">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="fe9b6-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="fe9b6-148">Con o sin telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="fe9b6-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="fe9b6-149">Puede implementar la aplicación servicio de aplicaciones, operador de conferencia y anuncio de conferencia en un sitio central, pero no en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe9b6-150">Si implementa una conferencia de acceso telefónico local, debe implementarla en todos los grupos donde implementará la Conferencia de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="fe9b6-151">No es necesario asignar números de acceso en cada grupo de servidores, pero tiene que implementar la característica de conferencia de acceso telefónico local en cada grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="fe9b6-152">Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso desde un grupo para unirse a una conferencia de 2013 de Lync Server en un grupo diferente.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="fe9b6-153">Topologías compatibles con Lync Server 2013 y Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="fe9b6-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="fe9b6-154">Lync Server 2013 proporciona las siguientes formas de configurar el servidor de Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="fe9b6-155">Dependiendo de sus necesidades, puede:</span><span class="sxs-lookup"><span data-stu-id="fe9b6-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="fe9b6-156">**Instale Lync Server 2013 y Office Web Apps Server local detrás del firewall de su organización y en la misma zona de red.**</span><span class="sxs-lookup"><span data-stu-id="fe9b6-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="fe9b6-157">Con esta topología, el acceso externo a Office Web Apps Server se proporcionará a través del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="fe9b6-158">Tanto Lync Server 2013 como Office Web Apps Server (o una granja de Office Web Apps Server) están instalados de forma local y detrás del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="fe9b6-159">Idealmente, debe instalar Office Web Apps Server en la misma zona de red que Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="fe9b6-160">Los clientes externos de Lync pueden conectarse a Lync Server 2013 y a Office Web Apps Server mediante un servidor proxy inverso, que es un servidor que recibe solicitudes de Internet y las reenvía a la red interna.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="fe9b6-161">(Los clientes internos no necesitan usar el servidor proxy inverso porque pueden conectarse directamente a Office Web Apps Server). Esta topología funciona mejor si desea usar una granja de servidores de Office Web Apps dedicada que solo se usa en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="fe9b6-162">**Usar un servidor de Office Web Apps implementado externamente**</span><span class="sxs-lookup"><span data-stu-id="fe9b6-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="fe9b6-163">En esta topología, Lync Server 2013 se implementa de forma local y usa un servidor de Office Web Apps que se implementa fuera de la zona de red de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="fe9b6-164">Esto puede ocurrir cuando Office Web Apps Server se comparte en varias aplicaciones de la Corporación y se implementa en una red que necesita Lync Server para usar la interfaz externa de Office Web Apps Server y viceversa.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="fe9b6-165">No es necesario instalar un servidor proxy inverso; en su lugar, todas las solicitudes de Office Web Apps Server a Lync Server 2013 se enrutan a través del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="fe9b6-166">Los clientes de Lync internos y externos se conectan a Office Web Apps Server mediante la dirección URL externa.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="fe9b6-167">Si el servidor de Office Web Apps se implementa fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)** en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="fe9b6-168">Para obtener más información [, vea configuración de la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="fe9b6-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="fe9b6-169">Sea cual sea la topología seleccionada, es fundamental que estén abiertos los puertos de firewall correctos.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="fe9b6-170">Debe asegurarse de que los firewalls, las direcciones IP y los puertos no estén bloqueados por firewalls en el servidor de Office Web Apps, el equilibrador de carga o el servidor de Lync.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe9b6-171">Otra opción para proporcionar acceso externo a Office Web Apps Server es implementar el servidor en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="fe9b6-172">Si decide hacerlo, tenga en cuenta que la configuración de Office Web Apps Server requiere que el equipo servidor sea miembro de su dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="fe9b6-173">A menos que su Directiva de red permita que los equipos de la red perimetral sean miembros de dominio de Active Directory, se recomienda que no instale Office Web Apps Server en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="fe9b6-174">En su lugar, debe instalar Office Web Apps Server en la red interna y proporcionar acceso a usuarios externos a través del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

