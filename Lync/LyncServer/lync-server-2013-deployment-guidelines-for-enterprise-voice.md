---
title: 'Lync Server 2013: directrices de implementación para telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc2aee745a362e58003c62f483dda6c63ab244f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="3fcfa-102">Instrucciones de implementación para telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fcfa-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fcfa-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3fcfa-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="3fcfa-104">En este tema se describen los requisitos previos y otras instrucciones que se deben tener en cuenta al planear la implementación de Lync Server 2013 y la carga de trabajo de la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="3fcfa-105">Requisitos previos de implementación</span><span class="sxs-lookup"><span data-stu-id="3fcfa-105">Deployment Prerequisites</span></span>

<span data-ttu-id="3fcfa-106">Para obtener una experiencia óptima al implementar la telefonía IP empresarial, asegúrese de que la infraestructura de ti, la red y los sistemas cumplen los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="3fcfa-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="3fcfa-107">Lync Server 2013 Standard Edition o Enterprise Edition está instalado y en funcionamiento en la red.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="3fcfa-108">Todos los servidores perimetrales se implementan y funcionan en la red perimetral, incluidos los servidores perimetrales con el servicio perimetral de acceso, el servicio perimetral a/V, el servicio perimetral de conferencia web y un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="3fcfa-109">Se han creado uno o más usuarios y están habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="3fcfa-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) o el último Service Pack o Microsoft Exchange Server 2010 está instalado.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="3fcfa-111">Uno de ellos es necesario para integrar la mensajería unificada (MU) de Exchange con Lync Server y proporcionar notificaciones enriquecidas e información de registro de llamadas a los extremos de cliente.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="3fcfa-112">Un número de teléfono principal único se ha designado, normalizado y copiado al atributo **msRTCSIP-line** para cada usuario que se va a habilitar para la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3fcfa-113">Lync Server admite números E. 164 y números de marcado hacia adentro (DID) no directo.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="3fcfa-114">Los números no DID pueden representarse con el formato <STRONG> &lt;E.&gt;164; ext&lt;=&gt; Extension</STRONG> o como una cadena de dígitos, con el requisito de que la extensión privada sea única en toda la empresa.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="3fcfa-115">Por ejemplo, el número privado 1001 se puede representar como <STRONG>+1425550100;ext=1001</STRONG> o como <STRONG>1001</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="3fcfa-116">Cuando se representa como <STRONG>1001</STRONG>, se espera que este número privado sea único en toda la empresa.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="3fcfa-117">Los administradores que implementen la telefonía IP empresarial deben ser miembros del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="3fcfa-118">Como mínimo, Office Communicator 2007 se ha implementado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="3fcfa-119">Para usar las características nuevas de esta versión, se ha implementado Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="3fcfa-120">Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="3fcfa-121">Cada equipo donde se instale el servidor de mediación deberá:</span><span class="sxs-lookup"><span data-stu-id="3fcfa-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="3fcfa-122">Un servidor miembro de un dominio y preparado para los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="3fcfa-123">Para los procedimientos de preparación de los servicios de dominio de Active Directory, consulte preparación de los [servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="3fcfa-124">Ejecutar uno de los sistemas operativos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3fcfa-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="3fcfa-125">La edición de 64 bits del sistema operativo Windows Server 2008 Standard</span><span class="sxs-lookup"><span data-stu-id="3fcfa-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="3fcfa-126">La edición de 64 bits del sistema operativo Windows Server 2008 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3fcfa-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="3fcfa-p105">Si la conexión a la red telefónica conmutada (RTC) o central de conmutación (PBX) se realiza por medio de una conexión de multiplexación por división de tiempo (TDM), una o más puertas de enlace RTC deben estar disponibles para la implementación. (Si la conexión se realiza por medio de un tronco SIP, no se necesita ninguna puerta de enlace RTC.)</span><span class="sxs-lookup"><span data-stu-id="3fcfa-p105">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment. (If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="3fcfa-129">Interrupciones de alimentación, de la red o del servicio telefónico</span><span class="sxs-lookup"><span data-stu-id="3fcfa-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="3fcfa-130">Si se produce una interrupción, una interrupción u otra degradación de los servicios de alimentación, red o teléfono en su ubicación, es posible que la voz, la mensajería instantánea, la presencia y otras características de Lync Server y cualquier dispositivo conectado a Lync Server no funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="3fcfa-131">Enterprise Voice depende de la disponibilidad del servidor y de la operabilidad del cliente VoIP y del hardware</span><span class="sxs-lookup"><span data-stu-id="3fcfa-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="3fcfa-132">Las comunicaciones de voz con Lync Server dependen de la disponibilidad del software de servidor y del correcto funcionamiento de los clientes de voz o de los dispositivos telefónicos de hardware que se conectan al software del servidor.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="3fcfa-133">Métodos de acceso alternativos a los servicios de emergencia</span><span class="sxs-lookup"><span data-stu-id="3fcfa-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="3fcfa-134">Para las ubicaciones en las que se instala un cliente de voz (por ejemplo, un equipo con cliente de Lync o un dispositivo de Lync Phone Edition), se recomienda mantener una opción de copia de seguridad para que los usuarios llamen a los servicios de emergencia (por ejemplo, 911 o 999) en caso de un error de alimentación , la degradación de la conectividad de red, la interrupción del servicio telefónico u otros problemas que puedan impedir el funcionamiento de los dispositivos Lync Server, Lync o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="3fcfa-135">Esas opciones alternativas pueden ser un teléfono conectado a una línea de la red telefónica conmutada estándar o un teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="3fcfa-136">Llamadas de emergencia y sistemas telefónicos de varias líneas</span><span class="sxs-lookup"><span data-stu-id="3fcfa-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="3fcfa-137">El uso de un sistema telefónico multilínea (MLTS) puede estar sujeto a U. el estado o leyes federales o las leyes de otros países o regiones que requieren la MLTS para proporcionar al número de teléfono, la extensión o la ubicación física de un autor de la llamada a los servicios de emergencia aplicables cuando una persona que llama se coloca en los servicios de emergencia (por ejemplo, cuando se marca un número de acceso de emergencia como 911 o 999).</span><span class="sxs-lookup"><span data-stu-id="3fcfa-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="3fcfa-138">En esta versión, Lync Server se puede configurar para proporcionar una ubicación física de un autor de llamada a un proveedor de servicios de emergencia, tal como se describe en [Planning for Emergency Services (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="3fcfa-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="3fcfa-139">El cumplimiento de la ley MLTS es la única responsabilidad del comprador de los dispositivos Lync Server, cliente de Lync y Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

