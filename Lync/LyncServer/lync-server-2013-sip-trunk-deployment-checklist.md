---
title: 'Lync Server 2013: lista de comprobación para la implementación del tronco SIP'
description: 'Lync Server 2013: lista de comprobación de implementación de tronco de SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbab9647a7146b2478317ab6c020969506f9c0ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559046"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="98a83-103">Lista de comprobación para la implementación del tronco SIP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98a83-103">SIP trunk deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98a83-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="98a83-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="98a83-105">Para poder implementar un tronco SIP, primero debe intercambiar alguna información de conexión básica con su proveedor de servicios relacionada con sus respectivos extremos de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="98a83-105">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="98a83-106">Obtenga la información siguiente de cada una de las puertas de enlace del proveedor de servicios de telefonía por Internet a las que se vaya a conectar:</span><span class="sxs-lookup"><span data-stu-id="98a83-106">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="98a83-107">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="98a83-107">IP address</span></span>

  - <span data-ttu-id="98a83-108">Nombre de dominio completo (FQDN)</span><span class="sxs-lookup"><span data-stu-id="98a83-108">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98a83-109">Es posible que el proveedor de servicios le pida que se conecte a más de una puerta de enlace del proveedor de servicios de telefonía por Internet.</span><span class="sxs-lookup"><span data-stu-id="98a83-109">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="98a83-110">En ese caso, debe configurar una conexión entre cada puerta de enlace de ITSP y cada uno de los servidores de mediación del grupo.</span><span class="sxs-lookup"><span data-stu-id="98a83-110">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="98a83-111">La información que facilita al proveedor de servicios depende del tipo de conexión del tronco SIP:</span><span class="sxs-lookup"><span data-stu-id="98a83-111">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="98a83-112">En el caso de conexiones de red privadas o de conmutación multiprotocolo mediante etiquetas (MPLS, Multiprotocol Label Switching) facilite al proveedor de servicios de telefonía por Internet la dirección IP enrutable públicamente del enrutador de su red perimetral (también conocida como extranet o subred filtrada).</span><span class="sxs-lookup"><span data-stu-id="98a83-112">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="98a83-113">Compruebe que la puerta de enlace o el controlador de borde de sesión (SBC) del proveedor de servicios de telefonía por Internet pueda obtener acceso a esta dirección.</span><span class="sxs-lookup"><span data-stu-id="98a83-113">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="98a83-114">Proporcione también al ITSP el FQDN del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="98a83-114">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="98a83-115">Para conexiones de red privada virtual (VPN), facilítele también la dirección IP del servidor VPN.</span><span class="sxs-lookup"><span data-stu-id="98a83-115">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="98a83-116">Consideraciones de certificados</span><span class="sxs-lookup"><span data-stu-id="98a83-116">Certificate Considerations</span></span>

<span data-ttu-id="98a83-117">Para determinar si necesita un certificado para el enlace troncal SIP, infórmese con su proveedor de servicios de telefonía por Internet acerca de la compatibilidad con protocolos:</span><span class="sxs-lookup"><span data-stu-id="98a83-117">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="98a83-118">Si solo admite el protocolo de control de transmisión (TCP), no necesita ningún certificado.</span><span class="sxs-lookup"><span data-stu-id="98a83-118">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="98a83-119">Si admite el protocolo de seguridad de la capa de transporte (TLS), el proveedor de servicios de telefonía por Internet deberá proporcionarle un certificado.</span><span class="sxs-lookup"><span data-stu-id="98a83-119">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98a83-120">El protocolo SIP trabaja junto con el protocolo de transporte en tiempo real (RTP) o el protocolo de transporte seguro en tiempo real (SRTP), que son los encargados de administrar los datos de voz reales en las llamadas del protocolo de Voz sobre Protocolo de Internet (VoIP).</span><span class="sxs-lookup"><span data-stu-id="98a83-120">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="98a83-121">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="98a83-121">Deployment Process</span></span>

<span data-ttu-id="98a83-122">Para implementar el lado de Lync Server de la conexión de tronco SIP, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="98a83-122">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="98a83-123">Mediante el generador de topologías de Lync Server, cree y configure la topología de dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="98a83-123">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="98a83-124">Para obtener información detallada, consulte [definir y configurar una topología en Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="98a83-124">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="98a83-125">Mediante el panel de control de Lync Server, configure el enrutamiento de voz para el nuevo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="98a83-125">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="98a83-126">Para obtener más información, consulte [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="98a83-126">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="98a83-127">Pruebe la conectividad con el cmdlet **Test-CsPstnOutboundCall**.</span><span class="sxs-lookup"><span data-stu-id="98a83-127">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="98a83-128">Para obtener más información, consulte la documentación o la ayuda del shell de administración de Lync Server para el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98a83-128">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

