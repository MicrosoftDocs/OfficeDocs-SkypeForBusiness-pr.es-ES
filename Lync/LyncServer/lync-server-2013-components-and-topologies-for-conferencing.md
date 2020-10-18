---
title: Componentes y topologías de Lync Server 2013 para conferencias
description: Componentes y topologías de Lync Server 2013 para conferencias.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 719fe81d0f634b1eab1e79c2e7e665e89b0a791a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576866"
---
# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="40829-103">Componentes y topologías para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40829-103">Components and topologies for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40829-104">_**Última modificación del tema:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="40829-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="40829-105">Al seleccionar Conferencia en el generador de topologías, las conferencias se implementan como parte del servidor front-end o del servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="40829-105">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="40829-106">Las conferencias de acceso telefónico y el uso compartido de PowerPoint requieren componentes y configuraciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="40829-106">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="40829-107">En las secciones siguientes se describen los componentes y las topologías admitidos para las conferencias web, las conferencias A/V y las conferencias de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="40829-107">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="40829-108">Componentes admitidos</span><span class="sxs-lookup"><span data-stu-id="40829-108">Supported Components</span></span>

<span data-ttu-id="40829-109">Los únicos componentes de conferencia web y conferencia A/V requieren son los servidores front-end de la organización o los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="40829-109">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="40829-110">Para obtener una lista de requisitos de hardware y software para los servidores front-end y los servidores Standard Edition, consulte [hardware admitido para Lync server 2013](lync-server-2013-supported-hardware.md) y [compatibilidad con la infraestructura y el software de servidor en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="40829-110">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="40829-111">Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar el uso compartido y la representación de presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="40829-111">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="40829-112">Para más información sobre la instalación y la configuración del servidor de Office Web Apps, vea [Configuring Integration with Office Web Apps Server and Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="40829-112">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="40829-113">Además de los requisitos de conferencia web y conferencia A/V, las conferencias de acceso telefónico local usan los siguientes componentes de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="40829-113">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="40829-114">**Servicio**     de aplicación El servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas (UC).</span><span class="sxs-lookup"><span data-stu-id="40829-114">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="40829-115">Las conferencias de acceso telefónico local usan dos aplicaciones de comunicaciones unificadas que requieren el servicio de aplicación: operador de conferencia y anuncio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="40829-115">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="40829-116">El servicio de aplicación se instala y se activa de forma predeterminada en todos los servidores front-end de un grupo de servidores front-end, y en todos los servidores Standard Edition, al implementar una carga de trabajo de conferencia y seleccionar la opción de conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="40829-116">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="40829-117">Aplicación de operador de **Conferencia**     La aplicación de operador de conferencia es una aplicación de comunicaciones unificadas que acepta llamadas de red telefónica conmutada (RTC), reproduce preguntas y une las llamadas a una conferencia a/V.</span><span class="sxs-lookup"><span data-stu-id="40829-117">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="40829-118">La aplicación operador de conferencia se instala y activa de forma predeterminada al implementar una carga de trabajo de conferencia y seleccionar la opción de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="40829-118">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="40829-119">Aplicación de anuncio de **Conferencia**     La aplicación de anuncio de conferencia es una aplicación de comunicaciones unificadas que reproduce tonos y mensajes a los participantes de RTC en determinadas acciones, como cuando un participante se une a una conferencia o la abandona, los participantes se silencian o se desactivan, por ejemplo, alguien entra en la sala de espera o la Conferencia está bloqueada o desbloqueada.</span><span class="sxs-lookup"><span data-stu-id="40829-119">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="40829-120">La aplicación de anuncio de conferencia también admite comandos de tono de marcado de frecuencia múltiple (DTMF) del teclado del teléfono.</span><span class="sxs-lookup"><span data-stu-id="40829-120">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="40829-121">La aplicación de anuncio de conferencia se instala y activa automáticamente de forma predeterminada al implementar una carga de trabajo de conferencia y seleccionar la opción de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="40829-121">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="40829-122">**Página de configuración de conferencia de acceso telefónico local**     La página de configuración de la Conferencia de acceso telefónico local muestra los números de acceso telefónico de conferencia con los idiomas disponibles, la información de conferencia asignada (es decir, para las reuniones que no necesitan programarse) y los controles de DTMF en conferencia, y admite la administración del número de identificación personal (PIN) y la información de conferencia asignada.</span><span class="sxs-lookup"><span data-stu-id="40829-122">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="40829-123">La página de configuración de la Conferencia de acceso telefónico local se instala automáticamente como parte de los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="40829-123">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="40829-124">**Lync server 2013, servidor de mediación y puerta de enlace RTC**     La Conferencia de acceso telefónico local requiere un servidor de mediación para convertir la señalización (y los medios, en algunas configuraciones) entre Lync Server 2013 y la puerta de enlace RTC y una puerta de enlace RTC para convertir la señalización y los medios entre el servidor de mediación y la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="40829-124">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="40829-125">Para las conferencias de acceso telefónico local, debe implementar al menos un servidor de mediación y, al menos, uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="40829-125">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="40829-126">Una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="40829-126">PSTN gateway</span></span>
    
      - <span data-ttu-id="40829-127">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="40829-127">IP-PBX</span></span>
    
      - <span data-ttu-id="40829-128">Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta mediante la configuración de un tronco SIP</span><span class="sxs-lookup"><span data-stu-id="40829-128">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="40829-129">Si también está implementando la telefonía IP empresarial, el servidor de mediación y las puertas de enlace RTC forman parte de la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="40829-129">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="40829-130">Si no está implementando Enterprise Voice, debe implementar al menos un servidor de mediación y al menos una puerta de enlace RTC, IP-PBX o SBC para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="40829-130">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="40829-131">**Almacén**     de archivos El almacén de archivos se usa para los archivos de audio de nombre grabado.</span><span class="sxs-lookup"><span data-stu-id="40829-131">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="40829-132">El almacenamiento de archivos es un componente estándar de toda implementación Enterprise Edition o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="40829-132">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="40829-133">**Almacén**     de usuario El almacén de usuario se usa para almacenar los PIN del usuario Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40829-133">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="40829-134">Los PIN tienen asignado un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="40829-134">PINs are hashed.</span></span> <span data-ttu-id="40829-135">El almacenamiento de usuarios es un componente estándar de toda implementación Enterprise Edition o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="40829-135">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="40829-136">Panel de control de **Lync Server**     Algunas opciones de configuración de acceso telefónico se pueden configurar mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40829-136">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="40829-137">Shell de administración de **Lync Server**     Todas las opciones de configuración de acceso telefónico local se pueden configurar con los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40829-137">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="40829-138">Los cmdlets del shell de administración de Lync Server están disponibles para implementar, configurar, ejecutar, supervisar y solucionar problemas de aplicación del operador de conferencia y de la aplicación de anuncio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="40829-138">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="40829-139">Para obtener más información acerca de los cmdlets específicos, consulte Lync Server Management Shell Documentation.</span><span class="sxs-lookup"><span data-stu-id="40829-139">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="40829-140">Topologías admitidas</span><span class="sxs-lookup"><span data-stu-id="40829-140">Supported Topologies</span></span>

<span data-ttu-id="40829-141">En Lync Server 2013, el servidor que ejecuta los servicios de conferencia siempre se combina con los servidores front-end o los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="40829-141">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="40829-142">Durante la implementación inicial, el generador de topologías le ofrece la opción de incluir conferencias en la topología.</span><span class="sxs-lookup"><span data-stu-id="40829-142">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="40829-143">También puede utilizar el Generador de topologías para agregar conferencia a una implementación existente.</span><span class="sxs-lookup"><span data-stu-id="40829-143">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="40829-144">Para obtener más información, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="40829-144">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="40829-145">Topologías de conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="40829-145">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="40829-146">Puede implementar la característica de conferencia de acceso telefónico local en las configuraciones y topologías siguientes:</span><span class="sxs-lookup"><span data-stu-id="40829-146">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="40829-147">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="40829-147">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="40829-148">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="40829-148">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="40829-149">Con o sin telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="40829-149">With or without Enterprise Voice</span></span>

<span data-ttu-id="40829-150">Puede implementar aplicaciones de servicio de aplicación, operador de conferencia y anuncio de conferencia en un sitio central, pero no en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="40829-150">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40829-151">Si implementa la Conferencia de acceso telefónico local, debe implementarla en todos los grupos de servidores en los que implemente Lync Server 2013 conferencias.</span><span class="sxs-lookup"><span data-stu-id="40829-151">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="40829-152">No es necesario asignar números de acceso en cada grupo de servidores, pero debe implementar la característica de conferencia de acceso telefónico local en cada grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="40829-152">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="40829-153">Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso de un grupo de servidores para unirse a una conferencia de 2013 de Lync Server en un grupo de servidores diferente.</span><span class="sxs-lookup"><span data-stu-id="40829-153">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="40829-154">Topologías admitidas para Lync Server 2013 y Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="40829-154">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="40829-155">Lync Server 2013 proporciona las siguientes formas de configurar Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="40829-155">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="40829-156">Dependiendo de sus necesidades, puede:</span><span class="sxs-lookup"><span data-stu-id="40829-156">Depending on your needs you can:</span></span>

  - <span data-ttu-id="40829-157">**Instale Lync Server 2013 y Office Web Apps Server local detrás del firewall de su organización y en la misma zona de red.**</span><span class="sxs-lookup"><span data-stu-id="40829-157">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="40829-158">Con esta topología, el acceso externo a Office Web Apps Server se proporcionará a través del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="40829-158">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="40829-159">Tanto Lync Server 2013 como Office Web Apps Server (o una granja de servidores de Office Web Apps Server) están instalados de forma local y detrás del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="40829-159">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="40829-160">Lo ideal sería instalar Office Web Apps Server en la misma zona de red que Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40829-160">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="40829-161">Los clientes externos de Lync pueden conectarse a Lync Server 2013 y a Office Web Apps Server mediante un servidor de proxy inverso, que es un servidor que recibe solicitudes de Internet y las reenvía a la red interna.</span><span class="sxs-lookup"><span data-stu-id="40829-161">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="40829-162">(Los clientes internos no necesitan usar el servidor de proxy inverso porque se pueden conectar directamente a Office Web Apps Server). Esta topología funciona mejor si desea usar una granja de Office Web Apps Server dedicada que solo se usa en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40829-162">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="40829-163">**Uso de Office Web Apps Server implementado externamente**</span><span class="sxs-lookup"><span data-stu-id="40829-163">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="40829-164">En esta topología, Lync Server 2013 se implementa localmente y usa un servidor de Office Web Apps que se implementa fuera de la zona de red de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40829-164">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="40829-165">Esto puede ocurrir cuando Office Web Apps Server se comparte entre varias aplicaciones de la Corporación y se implementa en una red que requiere Lync Server para usar la interfaz externa de Office Web Apps Server y viceversa.</span><span class="sxs-lookup"><span data-stu-id="40829-165">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="40829-166">No es necesario instalar un servidor proxy inverso; en su lugar, todas las solicitudes del servidor de Office Web Apps a Lync Server 2013 se enrutan a través del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="40829-166">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="40829-167">Tanto el cliente de Lync interno como el externo se conectan a Office Web Apps Server mediante la dirección URL externa.</span><span class="sxs-lookup"><span data-stu-id="40829-167">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="40829-168">Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción el **servidor de Office Web Apps se implementa en una red externa (es decir, perimetral/Internet)** en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="40829-168">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="40829-169">Para obtener más información [, consulte Configuración de la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="40829-169">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="40829-170">Sea cual sea la topología seleccionada, es fundamental que estén abiertos los puertos de firewall correctos.</span><span class="sxs-lookup"><span data-stu-id="40829-170">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="40829-171">Debe asegurarse de que los firewalls, los nombres DNS, las direcciones IP y los puertos no estén bloqueados por los firewalls de Office Web Apps Server, el equilibrador de carga o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40829-171">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40829-172">Otra opción para ofrecer acceso externo a Office Web Apps Server es implementar el servidor en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="40829-172">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="40829-173">Si decide hacerlo, tenga en cuenta que el programa de instalación de Office Web Apps Server requiere que el equipo servidor pertenezca a su dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="40829-173">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="40829-174">A menos que la Directiva de red permita que los equipos de la red perimetral sean miembros de dominio de Active Directory, se recomienda no instalar Office Web Apps Server en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="40829-174">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="40829-175">En su lugar, debe instalar Office Web Apps Server en la red interna y proporcionar a los usuarios externos el acceso a través del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="40829-175">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

