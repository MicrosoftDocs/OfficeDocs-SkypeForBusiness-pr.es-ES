---
title: 'Lync Server 2013: lista de comprobación para la implementación del tronco SIP'
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
ms.openlocfilehash: 09c9916be9b32eb4a1fb0a5981cc6769bafc3420
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519707"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="94b5a-102">Lista de comprobación para la implementación del tronco SIP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94b5a-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94b5a-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="94b5a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="94b5a-104">Para poder implementar un tronco SIP, primero debe intercambiar alguna información de conexión básica con su proveedor de servicios relacionada con sus respectivos extremos de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="94b5a-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="94b5a-105">Obtenga la información siguiente de cada una de las puertas de enlace del proveedor de servicios de telefonía por Internet a las que se vaya a conectar:</span><span class="sxs-lookup"><span data-stu-id="94b5a-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="94b5a-106">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="94b5a-106">IP address</span></span>

  - <span data-ttu-id="94b5a-107">Nombre de dominio completo (FQDN)</span><span class="sxs-lookup"><span data-stu-id="94b5a-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94b5a-108">Es posible que el proveedor de servicios le pida que se conecte a más de una puerta de enlace del proveedor de servicios de telefonía por Internet.</span><span class="sxs-lookup"><span data-stu-id="94b5a-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="94b5a-109">En ese caso, debe configurar una conexión entre cada puerta de enlace de ITSP y cada uno de los servidores de mediación del grupo.</span><span class="sxs-lookup"><span data-stu-id="94b5a-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="94b5a-110">La información que facilita al proveedor de servicios depende del tipo de conexión del tronco SIP:</span><span class="sxs-lookup"><span data-stu-id="94b5a-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="94b5a-111">En el caso de conexiones de red privadas o de conmutación multiprotocolo mediante etiquetas (MPLS, Multiprotocol Label Switching) facilite al proveedor de servicios de telefonía por Internet la dirección IP enrutable públicamente del enrutador de su red perimetral (también conocida como extranet o subred filtrada).</span><span class="sxs-lookup"><span data-stu-id="94b5a-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="94b5a-112">Compruebe que la puerta de enlace o el controlador de borde de sesión (SBC) del proveedor de servicios de telefonía por Internet pueda obtener acceso a esta dirección.</span><span class="sxs-lookup"><span data-stu-id="94b5a-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="94b5a-113">Proporcione también al ITSP el FQDN del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="94b5a-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="94b5a-114">Para conexiones de red privada virtual (VPN), facilítele también la dirección IP del servidor VPN.</span><span class="sxs-lookup"><span data-stu-id="94b5a-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="94b5a-115">Consideraciones de certificados</span><span class="sxs-lookup"><span data-stu-id="94b5a-115">Certificate Considerations</span></span>

<span data-ttu-id="94b5a-116">Para determinar si necesita un certificado para el enlace troncal SIP, infórmese con su proveedor de servicios de telefonía por Internet acerca de la compatibilidad con protocolos:</span><span class="sxs-lookup"><span data-stu-id="94b5a-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="94b5a-117">Si solo admite el protocolo de control de transmisión (TCP), no necesita ningún certificado.</span><span class="sxs-lookup"><span data-stu-id="94b5a-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="94b5a-118">Si admite el protocolo de seguridad de la capa de transporte (TLS), el proveedor de servicios de telefonía por Internet deberá proporcionarle un certificado.</span><span class="sxs-lookup"><span data-stu-id="94b5a-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94b5a-119">El protocolo SIP trabaja junto con el protocolo de transporte en tiempo real (RTP) o el protocolo de transporte seguro en tiempo real (SRTP), que son los encargados de administrar los datos de voz reales en las llamadas del protocolo de Voz sobre Protocolo de Internet (VoIP).</span><span class="sxs-lookup"><span data-stu-id="94b5a-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="94b5a-120">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="94b5a-120">Deployment Process</span></span>

<span data-ttu-id="94b5a-121">Para implementar el lado de Lync Server de la conexión de tronco SIP, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="94b5a-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="94b5a-122">Mediante el generador de topologías de Lync Server, cree y configure la topología de dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="94b5a-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="94b5a-123">Para obtener información detallada, consulte [definir y configurar una topología en Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="94b5a-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="94b5a-124">Mediante el panel de control de Lync Server, configure el enrutamiento de voz para el nuevo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="94b5a-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="94b5a-125">Para obtener más información, consulte [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="94b5a-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="94b5a-126">Pruebe la conectividad con el cmdlet **Test-CsPstnOutboundCall**.</span><span class="sxs-lookup"><span data-stu-id="94b5a-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="94b5a-127">Para obtener más información, consulte la documentación o la ayuda del shell de administración de Lync Server para el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94b5a-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

