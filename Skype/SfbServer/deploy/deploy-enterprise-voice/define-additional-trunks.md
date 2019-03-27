---
title: Definición de troncos adicionales en el generador de Skype para Business Server
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumen: Obtenga información sobre cómo definir un tronco adicional entre un servidor de mediación y una puerta de enlace, del mismo nivel en el generador de Skype para Business Server.'
ms.openlocfilehash: 874d32053f4c3d91f16818bd34dc11806de8692c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881963"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="4ce96-103">Definición de troncos adicionales en el generador de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="4ce96-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="4ce96-104">**Resumen:** Obtenga información sobre cómo definir un tronco adicional entre un servidor de mediación y una puerta de enlace, del mismo nivel en el generador de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="4ce96-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="4ce96-105">Siga estos pasos para definir un tronco adicional a la que se puede asociar a un par con un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="4ce96-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="4ce96-106">Un par proporciona a los usuarios habilitados para Enterprise Voice con conectividad a la red telefónica pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="4ce96-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="4ce96-107">Un par puede ser una puerta de enlace RTC, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="4ce96-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="4ce96-108">Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="4ce96-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ce96-109">En este tema se da por supuesto que tienen el programa de instalación de una puerta de enlace RTC y tronco raíz con al menos un independientes o combinados servidor de mediación o grupo de servidores tal como se describe en [definir una puerta de enlace en el generador de Skype para Business Server](define-a-gateway.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="4ce96-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="4ce96-110">Para definir un tronco adicional entre un servidor de mediación y un par de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="4ce96-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="4ce96-111">Inicie el generador: Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="4ce96-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="4ce96-112">En Skype para Business Server, el nombre del sitio, **Componentes compartidos**, haga clic en el nodo **troncos** y, a continuación, haga clic en **Nuevo tronco**.</span><span class="sxs-lookup"><span data-stu-id="4ce96-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="4ce96-113">En **Definir nuevo tronco**, escriba un nombre descriptivo para identificar con exclusividad el tronco.</span><span class="sxs-lookup"><span data-stu-id="4ce96-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="4ce96-114">Dos troncos no pueden tener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="4ce96-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="4ce96-115">Si especifica seguridad de capa de transporte (TLS) como el tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del par del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="4ce96-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="4ce96-116">En **Puerta de enlace PSTN asociada**, seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.</span><span class="sxs-lookup"><span data-stu-id="4ce96-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="4ce96-117">En **Puerto de escucha para puerta de enlace RTC**, escriba el puerto de escucha que el par (puerta de enlace RTC, IP-PBX o SBC) recibirá mensajes SIP desde el servidor de mediación es que se asociará con este tronco.</span><span class="sxs-lookup"><span data-stu-id="4ce96-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="4ce96-118">Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="4ce96-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="4ce96-119">Los puertos de la aplicación de sucursal con funciones de supervivencia predeterminados son 5081 para TCP y 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="4ce96-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="4ce96-120">En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el punto.</span><span class="sxs-lookup"><span data-stu-id="4ce96-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ce96-121">Por motivos de seguridad, recomendamos encarecidamente que implemente a un punto para el servidor de mediación que pueda usar TLS.</span><span class="sxs-lookup"><span data-stu-id="4ce96-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="4ce96-122">En el **Servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociar con el tronco raíz de este punto</span><span class="sxs-lookup"><span data-stu-id="4ce96-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="4ce96-123">En **puerto de servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación recibirá mensajes SIP desde el mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="4ce96-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ce96-124">Compatible con varios tronco en Skype para Business Server, no se puede configurar dos troncos con nombres de tronco diferentes con el mismo **puerto del servidor de mediación asociado** y el **Puerto de escucha para puerta de enlace IP/RTC**</span><span class="sxs-lookup"><span data-stu-id="4ce96-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="4ce96-125">Compatible con varios tronco en Skype para Business Server, se puede definir varios SIP señalización puertos en el servidor de mediación para la comunicación con varios elementos del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="4ce96-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="4ce96-126">Al definir un tronco, debe ser el número de **puerto del servidor de mediación asociado** dentro del intervalo de puertos de escucha para el protocolo respectivo permitida por el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="4ce96-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="4ce96-127">Este intervalo de puertos se define en Skype para grupos de Business Server y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="4ce96-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="4ce96-128">Haga clic en el grupo de servidores de mediación correspondiente y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4ce96-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="4ce96-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="4ce96-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="4ce96-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce96-130">Click **OK**.</span></span> 
    

