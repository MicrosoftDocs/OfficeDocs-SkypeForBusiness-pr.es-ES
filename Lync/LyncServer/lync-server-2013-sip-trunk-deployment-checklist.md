---
title: 'Lync Server 2013: Lista de comprobaciones para la implementación del enlace troncal SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7854693702f1583ccaeb2ae6d54a1c7cb9bbcbcd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="f8b7c-102">Lista de comprobaciones para la implementación del enlace troncal SIP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8b7c-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8b7c-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f8b7c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f8b7c-104">Antes de que puedas implementar un tronco de SIP, tú y tu proveedor de servicios deben intercambiar información básica sobre los puntos de conexión de tu troncal de SIP.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="f8b7c-105">Obtenga la siguiente información para cada puerta de enlace de ITSP a la que se conectará:</span><span class="sxs-lookup"><span data-stu-id="f8b7c-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="f8b7c-106">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="f8b7c-106">IP address</span></span>

  - <span data-ttu-id="f8b7c-107">Nombre de dominio completo (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f8b7c-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8b7c-108">Es posible que el proveedor de servicios le pida que se conecte a más de una puerta de enlace de ITSP.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="f8b7c-109">En ese caso, debe configurar una conexión entre cada una de las puertas de enlace de ITSP y cada servidor de mediación de su grupo.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="f8b7c-110">La información que asignes a tu proveedor de servicios depende de tu tipo de conexión troncal de SIP:</span><span class="sxs-lookup"><span data-stu-id="f8b7c-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="f8b7c-111">En el caso de las conexiones de red privada o de cambio multiprotocolo (MPLS), asigne a la ITSP la dirección IP de enrutamiento pública del enrutador en la red perimetral (también conocida como DMZ, zona desmilitarizada y subred filtrada).</span><span class="sxs-lookup"><span data-stu-id="f8b7c-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="f8b7c-112">Compruebe que la puerta de enlace o el controlador de borde de sesión (SBC) en el ITSP puede comunicarse con esta dirección.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="f8b7c-113">Además, da al ITSP el FQDN de tu servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="f8b7c-114">En el caso de las conexiones de red privada virtual (VPN), asigne a la ITSP la dirección IP de su servidor VPN.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="f8b7c-115">Consideraciones de certificados</span><span class="sxs-lookup"><span data-stu-id="f8b7c-115">Certificate Considerations</span></span>

<span data-ttu-id="f8b7c-116">Para determinar si necesita un certificado para la Troncalización SIP, consulte a su ITSP acerca de la compatibilidad con el protocolo:</span><span class="sxs-lookup"><span data-stu-id="f8b7c-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="f8b7c-117">Si su ITSP es compatible con el protocolo de control de transmisión (TCP), no necesita un certificado.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="f8b7c-118">Si su ITSP es compatible con la seguridad de la capa de transporte (TLS), ITSP debe proporcionarle un certificado.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8b7c-119">SIP funciona junto con el protocolo de transporte en tiempo real (RTP) o el protocolo de transporte seguro en tiempo real (SRTP), los protocolos que administran los datos de voz reales en las llamadas de voz a través del Protocolo de Internet (VoIP).</span><span class="sxs-lookup"><span data-stu-id="f8b7c-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="f8b7c-120">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="f8b7c-120">Deployment Process</span></span>

<span data-ttu-id="f8b7c-121">Para implementar el lado servidor de Lync de la conexión de troncal de SIP, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f8b7c-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="f8b7c-122">Con el generador de topologías de Lync Server, cree y configure la topología de dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="f8b7c-123">Para obtener más información, vea [definir y configurar una topología en el generador de topología para Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="f8b7c-124">Use el panel de control de Lync Server para configurar el enrutamiento de voz para el nuevo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="f8b7c-125">Para obtener más información, vea [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="f8b7c-126">Pruebe la conectividad mediante el cmdlet **Test-CsPstnOutboundCall** .</span><span class="sxs-lookup"><span data-stu-id="f8b7c-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="f8b7c-127">Para obtener más información, vea la documentación del shell de administración de Lync Server o la ayuda del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

