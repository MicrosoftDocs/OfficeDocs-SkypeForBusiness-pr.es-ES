---
title: Definir una puerta de enlace en el generador de Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumen: Obtenga información sobre cómo definir una puerta de enlace RTC en el generador de Skype para Business Server.'
ms.openlocfilehash: 036c6805ab2c4821ee1bb0544b75553ab40c7100
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876323"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="80166-103">Definir una puerta de enlace en el generador de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="80166-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="80166-104">**Resumen:** Obtenga información sobre cómo definir una puerta de enlace RTC en el generador de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="80166-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="80166-105">Siga estos pasos para usar el generador de topología para definir a un par con el que se puede asociar un servidor de mediación para proporcionar conectividad a la red telefónica conmutada (RTC) para los usuarios habilitados para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="80166-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="80166-106">Un elemento del mismo nivel para el servidor de mediación puede ser una puerta de enlace de RTC, un sistema IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicio de telefonía de Internet (ITSP) al que se conecta mediante la configuración de un tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="80166-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="80166-107">Para definir un par para el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="80166-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="80166-108">Inicie el generador: Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="80166-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="80166-109">En Skype para Business Server, el nombre del sitio, componentes compartidos, haga clic en el nodo de **Puertas de enlace RTC** y, a continuación, haga clic en **Nueva puerta de enlace de RTC**.</span><span class="sxs-lookup"><span data-stu-id="80166-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="80166-110">En **Definir nueva puerta de enlace IP/RTC**, escriba el nombre de dominio completo (FQDN) o la dirección IP del par y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="80166-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80166-111">Si especifica seguridad de capa de transporte (TLS) como el tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del par del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="80166-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="80166-112">Defina el modo de escucha (IPv4 o IPv6) de la dirección IP de la nueva puerta de enlace RTC y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="80166-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="80166-113">Defina un tronco raíz para la nueva puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="80166-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="80166-114">Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace de identificación única efectuada mediante tupla.</span><span class="sxs-lookup"><span data-stu-id="80166-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="80166-115">{FQDN de servidor de mediación, puerto de escucha de servidor de mediación (TLS o TCP): puerta de enlace IP y FQDN, puerto de escucha de puerta de enlace}</span><span class="sxs-lookup"><span data-stu-id="80166-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="80166-116">Al definir una puerta de enlace RTC en el generador, debe definir un tronco raíz para agregar correctamente la puerta de enlace de RTC a la topología.</span><span class="sxs-lookup"><span data-stu-id="80166-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="80166-117">El tronco raíz no puede quitarse hasta que se quite la puerta de enlace RTC asociada.</span><span class="sxs-lookup"><span data-stu-id="80166-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="80166-118">En **Puerto de escucha para puerta de enlace IP/RTC**, escriba el puerto de escucha que va a usar la puerta de enlace, PBX o SBC para los mensajes SIP desde el servidor de mediación que se asociará con el tronco raíz de la puerta de enlace de RTC.</span><span class="sxs-lookup"><span data-stu-id="80166-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="80166-119">(De forma predeterminada, los puertos son 5066 para Protocolo de transmisión de control [TCP] y 5067 para la Seguridad de la capa de transporte [TLS] en una puerta de enlace RTC, PBX o SBC.</span><span class="sxs-lookup"><span data-stu-id="80166-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="80166-120">En una aplicación de sucursal con funciones de supervivencia en un sitio de sucursal, los puertos predeterminados son 5081 para TCP y 5082 para TLS).</span><span class="sxs-lookup"><span data-stu-id="80166-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="80166-121">En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el par y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="80166-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80166-122">Por motivos de seguridad, recomendamos encarecidamente que implemente a un punto para el servidor de mediación que pueda usar TLS.</span><span class="sxs-lookup"><span data-stu-id="80166-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="80166-123">En **Servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociar con el tronco raíz de esta puerta de enlace de RTC.</span><span class="sxs-lookup"><span data-stu-id="80166-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="80166-124">En **puerto de servidor de mediación asociado**, escriba el puerto de escucha que se va a usar el servidor de mediación para mensajes SIP desde la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="80166-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80166-125">Compatible con varios tronco en Skype para Business Server, puede definir varios puertos en el servidor de mediación para la comunicación con varias puertas de enlace de RTC de señalización de SIP.</span><span class="sxs-lookup"><span data-stu-id="80166-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="80166-126">Al definir un tronco, el **puerto del servidor de mediación asociado** debe estar dentro del intervalo de puertos de escucha para el protocolo respectivo permitida por el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="80166-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="80166-127">Este intervalo de puertos se define en Skype para Business Server y los grupos de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="80166-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="80166-128">Haga clic en el grupo de servidores de mediación de interés y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="80166-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="80166-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="80166-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="80166-130">Asegúrese de que el par definido está en ejecución y usa el FQDN o la dirección IP que ha especificado.</span><span class="sxs-lookup"><span data-stu-id="80166-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="80166-131">A continuación, haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="80166-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="80166-132">Haga clic con el botón derecho en el nodo **Skype Empresarial Server** y, luego, haga clic en **Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="80166-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

