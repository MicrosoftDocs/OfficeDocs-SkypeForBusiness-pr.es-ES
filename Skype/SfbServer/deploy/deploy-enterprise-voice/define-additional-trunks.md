---
title: Definir más troncos en el generador de topología en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumen: Aprenda a definir un troncal adicional entre un servidor de mediación y una puerta de enlace del mismo nivel en el generador de topología de Skype empresarial Server.'
ms.openlocfilehash: de6cfd45c9e5f8440fcbcf6b6098a82edda752f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303315"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="cda67-103">Definir más troncos en el generador de topología en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cda67-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="cda67-104">**Resumen:** Aprenda a definir un troncal adicional entre un servidor de mediación y una puerta de enlace del mismo nivel en el generador de topología de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cda67-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="cda67-105">Siga estos pasos para definir un enlace adicional al que pueda asociar un interlocutor con un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="cda67-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="cda67-106">Un interlocutor proporciona a los usuarios habilitados para telefonía IP empresarial con conectividad a la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="cda67-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="cda67-107">Un par puede ser una puerta de enlace RTC, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="cda67-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="cda67-108">Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="cda67-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cda67-109">En este tema se supone que tiene configurado una puerta de enlace RTC y un tronco de raíz con al menos un servidor o grupo de mediación colocado o independiente, según se describe en [definir una puerta de enlace en el generador de topologías de Skype empresarial Server](define-a-gateway.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="cda67-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="cda67-110">Para definir un troncal adicional entre un servidor de mediación y un interlocutor de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="cda67-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="cda67-111">Iniciar generador de topología: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="cda67-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="cda67-112">En Skype empresarial Server, el nombre de su sitio, **componentes**compartidos, haga clic con el botón secundario en el nodo **troncos** y luego haga clic en **nuevo tronco**.</span><span class="sxs-lookup"><span data-stu-id="cda67-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="cda67-113">En **Definir nuevo tronco**, escriba un nombre descriptivo para identificar con exclusividad el tronco.</span><span class="sxs-lookup"><span data-stu-id="cda67-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="cda67-114">Dos troncos no pueden tener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="cda67-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="cda67-115">Si especifica la seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del interlocutor del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="cda67-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="cda67-116">En **Puerta de enlace PSTN asociada**, seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.</span><span class="sxs-lookup"><span data-stu-id="cda67-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="cda67-117">En **Puerto en escucha para la puerta de enlace RTC**, escriba el puerto de escucha que el interlocutor (puerta de enlace PSTN, IP-PBX o SBC) recibirá los mensajes SIP del servidor de mediación que se va a asociar con este tronco.</span><span class="sxs-lookup"><span data-stu-id="cda67-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="cda67-118">Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="cda67-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="cda67-119">Los puertos predeterminados de los equipos de las sucursales supervivientes son 5081 para TCP y 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="cda67-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="cda67-120">En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el punto.</span><span class="sxs-lookup"><span data-stu-id="cda67-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cda67-121">Por razones de seguridad, le recomendamos encarecidamente que implemente un interlocutor en el servidor de mediación que pueda usar TLS.</span><span class="sxs-lookup"><span data-stu-id="cda67-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="cda67-122">En **servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociarlo con el tronco raíz de este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="cda67-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="cda67-123">En **Puerto de servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación recibirá los mensajes SIP del interlocutor.</span><span class="sxs-lookup"><span data-stu-id="cda67-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cda67-124">Con la compatibilidad de varios troncales en Skype empresarial Server, no se pueden configurar dos troncos con diferentes nombres de tronco con el mismo **Puerto de servidor de mediación asociado** y **Puerto de escucha para la puerta de enlace IP/PSTN**</span><span class="sxs-lookup"><span data-stu-id="cda67-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="cda67-125">Con varias compatibilidades troncales en Skype empresarial Server, se pueden definir varios puertos de señalización SIP en el servidor de mediación para la comunicación con varios elementos del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="cda67-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="cda67-126">Al definir un tronco, el número de **Puerto de servidor de mediación asociado** debe estar dentro del intervalo de los puertos de escucha para el protocolo respectivo permitido por el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="cda67-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="cda67-127">Este intervalo de puertos se define en Skype empresarial Server y en los grupos de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="cda67-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="cda67-128">Haga clic con el botón derecho en el grupo de servidores de mediación y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cda67-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="cda67-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="cda67-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="cda67-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cda67-130">Click **OK**.</span></span> 
    

