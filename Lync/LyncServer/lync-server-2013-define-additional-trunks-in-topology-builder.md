---
title: 'Lync Server 2013: definir troncos adicionales en el generador de topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c55e8073bd1ad1bb2db69096e4e58aa2b148e775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="46952-102">Definir más troncos en el generador de topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46952-102">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46952-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="46952-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="46952-104">Siga estos pasos para usar el generador de topología para definir un enlace adicional al que pueda asociar un *interlocutor* con un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="46952-104">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="46952-105">Un interlocutor proporciona a los usuarios habilitados para telefonía IP empresarial con conectividad a la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="46952-105">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="46952-106">Un par puede ser una puerta de enlace RTC, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="46952-106">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="46952-107">El tronco define esta conexión entre el servidor de mediación y el interlocutor.</span><span class="sxs-lookup"><span data-stu-id="46952-107">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="46952-108">Se pueden definir varios troncos por servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="46952-108">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="46952-109">Se puede asociar un servidor de mediación con varios elementos del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="46952-109">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="46952-110">Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace identificada de forma única por la tupla:</span><span class="sxs-lookup"><span data-stu-id="46952-110">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="46952-111">{Media Server FQDN, Puerto de escucha del servidor de mediación (TLS o TCP): IP de puerta de enlace y FQDN, Puerto de escucha de la puerta de enlace}</span><span class="sxs-lookup"><span data-stu-id="46952-111">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46952-112">En este tema se supone que tiene configurado una puerta de enlace PSTN y un tronco raíz con al menos un servidor o grupo de mediación de proviene o independiente, tal y como se describe en <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir una puerta de enlace en el generador de topología de Lync Server 2013</A> , en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="46952-112">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="46952-113">En este tema se supone que ha configurado al menos un grupo de servidores front-end o un servidor Standard Edition en un sitio central como mínimo, como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="46952-113">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="46952-114">Para definir un troncal adicional entre un servidor de mediación y un interlocutor de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="46952-114">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="46952-115">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="46952-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="46952-116">En Lync Server 2013, nombre del sitio, **componentes compartidos**, haga clic con el botón derecho en el nodo **troncos** y, después, haga clic en **nuevo tronco**.</span><span class="sxs-lookup"><span data-stu-id="46952-116">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="46952-117">![Pantalla de estructura de archivos del generador de topología de Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Pantalla de estructura de archivos del generador de topología de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="46952-117">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="46952-118">En **Definir nuevo tronco**, escriba un nombre descriptivo para identificar con exclusividad el tronco.</span><span class="sxs-lookup"><span data-stu-id="46952-118">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="46952-119">Dos troncos no pueden tener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="46952-119">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46952-120">Si especifica la seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del interlocutor del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="46952-120">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="46952-121">En **Puerta de enlace PSTN asociada**, seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.</span><span class="sxs-lookup"><span data-stu-id="46952-121">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="46952-122">![Configuración de propiedades para puerta de enlace RTC peer para troncal](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Configuración de propiedades para puerta de enlace RTC peer para troncal")</span><span class="sxs-lookup"><span data-stu-id="46952-122">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="46952-123">En **Puerto en escucha para la puerta de enlace RTC**, escriba el puerto de escucha que el interlocutor (puerta de enlace PSTN, IP-PBX o SBC) recibirá los mensajes SIP del servidor de mediación que se va a asociar con este tronco.</span><span class="sxs-lookup"><span data-stu-id="46952-123">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="46952-124">Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="46952-124">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="46952-125">Los puertos predeterminados de los equipos de las sucursales supervivientes son 5081 para TCP y 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="46952-125">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="46952-126">En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el punto.</span><span class="sxs-lookup"><span data-stu-id="46952-126">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46952-127">Por razones de seguridad, le recomendamos encarecidamente que implemente un interlocutor en el servidor de mediación que pueda usar TLS.</span><span class="sxs-lookup"><span data-stu-id="46952-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="46952-128">En **servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociarlo con el tronco raíz de este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="46952-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="46952-129">En **Puerto de servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación recibirá los mensajes SIP del interlocutor.</span><span class="sxs-lookup"><span data-stu-id="46952-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46952-130">Con varias compatibilidades troncales en Lync Server 2013, no se pueden configurar dos troncos con diferentes nombres de tronco con el mismo <STRONG>Puerto de servidor de mediación asociado</STRONG> y <STRONG>Puerto de escucha para la puerta de enlace IP/PSTN</STRONG></span><span class="sxs-lookup"><span data-stu-id="46952-130">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46952-131">Con varias compatibilidades troncales en Lync Server 2013, se pueden definir varios puertos de señalización SIP en el servidor de mediación para la comunicación con varios elementos del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="46952-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="46952-132">Al definir un tronco, el número de <STRONG>Puerto de servidor de mediación asociado</STRONG> debe estar dentro del intervalo de los puertos de escucha para el protocolo respectivo permitido por el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="46952-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="46952-133">Este intervalo de puertos se define en Lync Server 2013 y en grupos de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="46952-133">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="46952-134">Haga clic con el botón derecho en el grupo de servidores de mediación y seleccione <STRONG>Editar propiedades</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="46952-134">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="46952-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span><span class="sxs-lookup"><span data-stu-id="46952-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="46952-136">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46952-136">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46952-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="46952-137">See Also</span></span>


[<span data-ttu-id="46952-138">Modificar un tronco en el generador de topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46952-138">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

