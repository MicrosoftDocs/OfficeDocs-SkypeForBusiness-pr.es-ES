---
title: 'Lync Server 2013: definir una puerta de enlace en el generador de topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18f257648ba24930eaab0d314e34178ffd67a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="63aa6-102">Definir una puerta de enlace en el generador de topología de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63aa6-102">Define a gateway in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63aa6-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="63aa6-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="63aa6-104">Siga estos pasos para usar el generador de topología para definir un *interlocutor* con el que pueda asociar un servidor de mediación para proporcionar conectividad a la red de telefonía pública conmutada (RTC) para los usuarios habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="63aa6-104">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="63aa6-105">Un interlocutor al servidor de mediación puede ser una puerta de enlace PSTN, IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP) al que se conecta mediante la configuración de un tronco de SIP.</span><span class="sxs-lookup"><span data-stu-id="63aa6-105">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63aa6-106">En este tema se supone que ha configurado al menos un grupo de servidores front-end interno o un servidor Standard Edition en al menos un sitio central con un servidor de mediación colocada o independiente, como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="63aa6-106">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="63aa6-107">En este tema también se presupone que ha verificado que su infraestructura cumple con los requisitos previos descritos en <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">requisitos de software para telefonía IP empresarial en Lync server 2013</A> y los <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">requisitos previos de seguridad y configuración de telefonía IP empresarial en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="63aa6-107">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="63aa6-108">Para definir un interlocutor para el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="63aa6-108">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="63aa6-109">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="63aa6-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="63aa6-110">En Lync Server 2013, nombre del sitio, componentes compartidos, haga clic con el botón derecho en el nodo **puertas de enlace RTC** y, a continuación, haga clic en **nueva puerta de enlace RTC**.</span><span class="sxs-lookup"><span data-stu-id="63aa6-110">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="63aa6-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="63aa6-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="63aa6-112">En **Definir nueva puerta de enlace IP/RTC**, escriba el nombre de dominio completo (FQDN) o la dirección IP del par y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="63aa6-112">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="63aa6-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="63aa6-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63aa6-114">Si especifica la seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del interlocutor del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="63aa6-114">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="63aa6-115">Defina el modo de escucha (IPv4 o IPv6) de la dirección IP de la nueva puerta de enlace RTC y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="63aa6-115">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="63aa6-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="63aa6-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="63aa6-117">Defina un *tronco raíz* para la nueva puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="63aa6-117">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="63aa6-118">Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace que se identifica de forma única por la tupla.</span><span class="sxs-lookup"><span data-stu-id="63aa6-118">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="63aa6-119">{Media Server FQDN, Puerto de escucha del servidor de mediación (TLS o TCP): IP de puerta de enlace y FQDN, Puerto de escucha de la puerta de enlace}</span><span class="sxs-lookup"><span data-stu-id="63aa6-119">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="63aa6-120">Al definir una puerta de enlace RTC en el generador de topología, debe definir un tronco raíz para agregar correctamente la puerta de enlace RTC a su topología.</span><span class="sxs-lookup"><span data-stu-id="63aa6-120">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="63aa6-121">El tronco raíz no puede quitarse hasta que se quite la puerta de enlace RTC asociada.</span><span class="sxs-lookup"><span data-stu-id="63aa6-121">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="63aa6-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="63aa6-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="63aa6-123">En **Puerto de escucha para la puerta de enlace IP/RTC**, escriba el puerto de escucha que usará la puerta de enlace, PBX o SBC para los mensajes SIP del servidor de mediación que se asociará con el tronco raíz de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="63aa6-123">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="63aa6-124">(De forma predeterminada, los puertos son 5066 para Protocolo de transmisión de control [TCP] y 5067 para la Seguridad de la capa de transporte [TLS] en una puerta de enlace RTC, PBX o SBC.</span><span class="sxs-lookup"><span data-stu-id="63aa6-124">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="63aa6-125">En un equipo de sucursales con la supervivencia en un sitio de sucursal, los puertos predeterminados son 5081 para TCP y 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="63aa6-125">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="63aa6-126">En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el par y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="63aa6-126">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63aa6-127">Por razones de seguridad, le recomendamos encarecidamente que implemente un interlocutor en el servidor de mediación que pueda usar TLS.</span><span class="sxs-lookup"><span data-stu-id="63aa6-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="63aa6-128">En **servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociarlo con el tronco raíz de esta puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="63aa6-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="63aa6-129">En **Puerto de servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación usará para los mensajes SIP de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="63aa6-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63aa6-130">Con varias compatibilidades troncales en Lync Server 2013, se pueden definir varios puertos de señalización SIP en el servidor de mediación para que se usen en la comunicación con varias puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="63aa6-130">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="63aa6-131">Al definir un tronco, el <STRONG>Puerto de servidor de mediación asociado</STRONG> debe estar dentro del intervalo de los puertos de escucha para el protocolo respectivo permitido por el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="63aa6-131">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="63aa6-132">Este intervalo de puertos se define en Lync Server 2013 y en los grupos de mediación.</span><span class="sxs-lookup"><span data-stu-id="63aa6-132">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="63aa6-133">Haga clic con el botón derecho en el grupo de servidores de mediación de interés y seleccione <STRONG>Editar propiedades</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="63aa6-133">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="63aa6-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span><span class="sxs-lookup"><span data-stu-id="63aa6-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="63aa6-135">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="63aa6-135">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63aa6-136">Antes de completar este paso, asegúrese de que el interlocutor que ha definido está ejecutándose y esté usando el FQDN o la dirección IP que especificó.</span><span class="sxs-lookup"><span data-stu-id="63aa6-136">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="63aa6-137">A continuación, para agregar el elemento del mismo nivel a la topología, siga los procedimientos que se describen en [publicar la topología de Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="63aa6-137">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="63aa6-138">Debe publicar su topología cada vez que use el generador de topologías para crear o modificar su topología, de modo que los datos se puedan usar para instalar los archivos de los servidores que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="63aa6-138">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="63aa6-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="63aa6-139">See Also</span></span>


[<span data-ttu-id="63aa6-140">Modificar un tronco en el generador de topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63aa6-140">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

