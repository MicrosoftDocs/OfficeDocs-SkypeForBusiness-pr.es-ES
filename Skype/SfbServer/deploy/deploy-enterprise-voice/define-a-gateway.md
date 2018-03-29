---
title: Definir una puerta de enlace en el Generador de topologías en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumen: Conozca cómo definir una puerta de enlace PSTN en el generador de topología en Skype para Business Server 2015.'
ms.openlocfilehash: 7fa7f95fd04cf491dad32b0ab6cc050c5ebb0b0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="2c2c7-103">Definir una puerta de enlace en el Generador de topologías en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="2c2c7-103">Define a gateway in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2c2c7-104">**Resumen:** Aprenda a definir una puerta de enlace PSTN en el generador de topología en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2c2c7-105">Siga estos pasos para utilizar el generador de topología para definir un elemento del mismo nivel con el que se puede asociar un servidor de mediación para proporcionar conectividad a la red telefónica pública conmutada (PSTN) para los usuarios habilitados para Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="2c2c7-106">Un interlocutor para el servidor de mediación puede ser una puerta de enlace PSTN, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicio de telefonía de Internet (ITSP) al que se conecta mediante la configuración de un troncal SIP.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="2c2c7-107">Para definir un par para el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="2c2c7-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="2c2c7-108">Iniciar el generador de topología: Haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="2c2c7-109">En Skype para Business Server, el nombre del sitio, los componentes compartidos, haga clic en el nodo de **Puertas de enlace PSTN** y, a continuación, haga clic en **Nueva puerta de enlace PSTN**.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="2c2c7-110">En **Definir nueva puerta de enlace IP/RTC**, escriba el nombre de dominio completo (FQDN) o la dirección IP del par y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2c2c7-111">Si especifica Transport Layer Security (TLS) como el tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del interlocutor del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="2c2c7-112">Defina el modo de escucha (IPv4 o IPv6) de la dirección IP de la nueva puerta de enlace RTC y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="2c2c7-113">Definir un tronco de raíz para la puerta de enlace PSTN.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="2c2c7-114">Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace que se identifica por la tupla.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="2c2c7-115">{FQDN del servidor de mediación, puerto de escucha de servidor de mediación (TLS o TCP): puerta de enlace IP y FQDN, puerto de escucha de puerta de enlace}</span><span class="sxs-lookup"><span data-stu-id="2c2c7-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="2c2c7-116">Al definir una puerta de enlace PSTN en el generador de topología, debe definir un tronco raíz para agregar correctamente la puerta de enlace PSTN a la topología.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="2c2c7-117">El tronco raíz no puede quitarse hasta que se quite la puerta de enlace RTC asociada.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="2c2c7-118">En **Puerto de escucha para la puerta de enlace IP/PSTN**, escriba el puerto de escucha que se va a utilizar la puerta de enlace, PBX o SBC para mensajes SIP desde el servidor de mediación se asociará con el tronco de raíz de la puerta de enlace PSTN.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="2c2c7-119">(De forma predeterminada, los puertos son 5066 para Protocolo de transmisión de control [TCP] y 5067 para la Seguridad de la capa de transporte [TLS] en una puerta de enlace RTC, PBX o SBC.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="2c2c7-120">En un dispositivo de sucursal que sobreviven en un sitio de sucursal, los puertos predeterminados son 5081 para TCP y 5082 para TLS).</span><span class="sxs-lookup"><span data-stu-id="2c2c7-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="2c2c7-121">En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el par y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2c2c7-122">Por razones de seguridad, se recomienda encarecidamente que implementa a un interlocutor en el servidor de mediación que pueden usar TLS.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="2c2c7-123">En **Servidor de mediación asociado**, seleccione el grupo de servidor de mediación para asociar con el tronco de raíz de esta puerta de enlace PSTN.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="2c2c7-124">En **puerto de servidor de mediación asociada**, escriba el puerto de escucha que se va a utilizar el servidor de mediación para los mensajes desde la puerta de enlace SIP.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2c2c7-125">Compatible con varios tronco en Skype para Business Server, puede definir varios puertos en el servidor de mediación para la comunicación con varias puertas de enlace de RTC de señalización de SIP.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="2c2c7-126">Al definir un tronco, debe ser el **puerto del servidor de mediación asociado** dentro del intervalo de puertos de escucha del protocolo respectivos permitidos por el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="2c2c7-127">Este intervalo de puerto se define en Skype para Business Server y grupos de mediación.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="2c2c7-128">Haga clic en el grupo de servidor de mediación de interés y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="2c2c7-129">Especifique el intervalo de puertos en el campo **Puertos de escucha**.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="2c2c7-p105">Asegúrese de que el par definido está en ejecución y usa el FQDN o la dirección IP que ha especificado. A continuación, haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="2c2c7-p105">Be sure that the peer you defined is running and using the FQDN or IP address that you specified. Then click **Finish**.</span></span>
    
11. <span data-ttu-id="2c2c7-132">Haga clic con el botón derecho en el nodo **Skype Empresarial Server** y, luego, haga clic en **Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="2c2c7-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

