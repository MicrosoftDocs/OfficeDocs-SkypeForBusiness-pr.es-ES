---
title: Definir una puerta de enlace en el generador de topologías de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumen: Aprenda a definir una puerta de enlace RTC en el generador de topologías de Skype empresarial Server.'
ms.openlocfilehash: 41f5f37d7da23848c8a19d11347183d0c0697532
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767733"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="e3453-103">Definir una puerta de enlace en el generador de topologías de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e3453-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="e3453-104">**Resumen:** Obtenga información sobre cómo definir una puerta de enlace RTC en el generador de topologías de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e3453-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="e3453-105">Siga estos pasos para usar el generador de topología para definir un interlocutor con el que pueda asociar un servidor de mediación para proporcionar conectividad a la red de telefonía pública conmutada (RTC) para los usuarios habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="e3453-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="e3453-106">Un interlocutor al servidor de mediación puede ser una puerta de enlace PSTN, IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP) al que se conecta mediante la configuración de un tronco de SIP.</span><span class="sxs-lookup"><span data-stu-id="e3453-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="e3453-107">Para definir un par para el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="e3453-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="e3453-108">Iniciar generador de topología: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="e3453-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="e3453-109">En Skype empresarial Server, el nombre de su sitio, componentes compartidos, haga clic con el botón derecho en el nodo **puertas de enlace RTC** y, a continuación, haga clic en **nueva puerta de enlace RTC**.</span><span class="sxs-lookup"><span data-stu-id="e3453-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="e3453-110">En **Definir nueva puerta de enlace IP/RTC**, escriba el nombre de dominio completo (FQDN) o la dirección IP del par y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e3453-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3453-111">Si especifica la seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del interlocutor del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="e3453-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="e3453-112">Defina el modo de escucha (IPv4 o IPv6) de la dirección IP de la nueva puerta de enlace RTC y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e3453-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="e3453-113">Defina un tronco raíz para la nueva puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="e3453-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="e3453-114">Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace que se identifica de forma única por la tupla.</span><span class="sxs-lookup"><span data-stu-id="e3453-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="e3453-115">{Media Server FQDN, Puerto de escucha del servidor de mediación (TLS o TCP): IP de puerta de enlace y FQDN, Puerto de escucha de la puerta de enlace}</span><span class="sxs-lookup"><span data-stu-id="e3453-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="e3453-116">Al definir una puerta de enlace RTC en el generador de topología, debe definir un tronco raíz para agregar correctamente la puerta de enlace RTC a su topología.</span><span class="sxs-lookup"><span data-stu-id="e3453-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="e3453-117">El tronco raíz no puede quitarse hasta que se quite la puerta de enlace RTC asociada.</span><span class="sxs-lookup"><span data-stu-id="e3453-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="e3453-118">En **Puerto de escucha para la puerta de enlace IP/RTC**, escriba el puerto de escucha que usará la puerta de enlace, PBX o SBC para los mensajes SIP del servidor de mediación que se asociará con el tronco raíz de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="e3453-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="e3453-119">(De forma predeterminada, los puertos son 5066 para Protocolo de transmisión de control [TCP] y 5067 para la Seguridad de la capa de transporte [TLS] en una puerta de enlace RTC, PBX o SBC.</span><span class="sxs-lookup"><span data-stu-id="e3453-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="e3453-120">En un equipo de sucursales con la supervivencia en un sitio de sucursal, los puertos predeterminados son 5081 para TCP y 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="e3453-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="e3453-121">En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el par y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e3453-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3453-122">Por razones de seguridad, le recomendamos encarecidamente que implemente un interlocutor en el servidor de mediación que pueda usar TLS.</span><span class="sxs-lookup"><span data-stu-id="e3453-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="e3453-123">En **servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociarlo con el tronco raíz de esta puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="e3453-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="e3453-124">En **Puerto de servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación usará para los mensajes SIP de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="e3453-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3453-125">Con la compatibilidad de varios troncales en Skype empresarial Server, puede definir varios puertos de señalización SIP en el servidor de mediación para la comunicación con varias puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="e3453-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="e3453-126">Al definir un tronco, el **Puerto de servidor de mediación asociado** debe estar dentro del intervalo de los puertos de escucha para el protocolo respectivo permitido por el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="e3453-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="e3453-127">Este intervalo de puertos se define en Skype empresarial Server y en los grupos de mediación.</span><span class="sxs-lookup"><span data-stu-id="e3453-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="e3453-128">Haga clic con el botón derecho en el grupo de servidores de mediación de interés y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e3453-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="e3453-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="e3453-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="e3453-130">Asegúrese de que el par definido está en ejecución y usa el FQDN o la dirección IP que ha especificado.</span><span class="sxs-lookup"><span data-stu-id="e3453-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="e3453-131">A continuación, haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="e3453-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="e3453-132">Haga clic con el botón derecho en el nodo **Skype Empresarial Server** y, luego, haga clic en **Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="e3453-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

