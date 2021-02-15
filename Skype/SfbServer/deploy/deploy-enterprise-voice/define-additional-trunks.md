---
title: Definir troncos adicionales en topology Builder en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumen: obtenga información sobre cómo definir un tronco adicional entre un servidor de mediación y una puerta de enlace del mismo nivel en topology Builder en Skype Empresarial Server.'
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837000"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="910ad-103">Definir troncos adicionales en topology Builder en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="910ad-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="910ad-104">**Resumen:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="910ad-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="910ad-105">Siga estos pasos para definir un tronco adicional al que puede asociar un sistema del mismo nivel con un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="910ad-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="910ad-106">Un sistema del mismo nivel proporciona usuarios habilitados para Telefonía IP empresarial con conectividad a la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="910ad-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="910ad-107">Un punto puede ser una puerta de enlace PSTN, un IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="910ad-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="910ad-108">Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="910ad-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="910ad-109">En este tema se presupone que ha configurado una puerta de enlace RTC y un tronco raíz con al menos un servidor o grupo de servidores de mediación local o independiente, tal como se describe en Definir una puerta de enlace en [topology Builder en Skype Empresarial Server](define-a-gateway.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="910ad-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="910ad-110">Para definir un tronco adicional entre un servidor de mediación y una puerta de enlace del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="910ad-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="910ad-111">Inicie el Generador de topologías: Haga clic en Inicio **,** Todos los **programas,** Skype Empresarial **Server 2015** y, a continuación, haga clic en Skype Empresarial **Server 2015Topology Builder.**</span><span class="sxs-lookup"><span data-stu-id="910ad-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="910ad-112">En Skype Empresarial Server, su nombre de sitio, **Componentes** **compartidos,** haga clic con el botón secundario en el nodo Troncos y, a continuación, haga clic **en Nuevo tronco.**</span><span class="sxs-lookup"><span data-stu-id="910ad-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="910ad-113">En **Definir nuevo tronco**, escriba un nombre descriptivo para identificar con exclusividad el tronco.</span><span class="sxs-lookup"><span data-stu-id="910ad-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="910ad-114">Dos troncos no pueden tener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="910ad-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="910ad-115">Si especifica Seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del mismo nivel del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="910ad-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="910ad-116">En **Puerta de enlace PSTN asociada**, seleccione la puerta de enlace de mismo nivel PSTN para asociarla a este tronco.</span><span class="sxs-lookup"><span data-stu-id="910ad-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="910ad-117">En Puerto de escucha para la puerta de enlace RTC, escriba el puerto de escucha que el interlocutor (puerta de enlace RTC, IP-PBX o SBC) recibirá mensajes SIP del servidor de mediación que se asociará a este tronco.</span><span class="sxs-lookup"><span data-stu-id="910ad-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="910ad-118">Los puertos de mismo nivel habituales son 5066 para el protocolo de control de transmisiones (TCP) y 5067 para la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="910ad-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="910ad-119">Los puertos predeterminados de aplicación de sucursal con funciones de supervivencia son 5081 para TCP y 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="910ad-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="910ad-120">En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el punto.</span><span class="sxs-lookup"><span data-stu-id="910ad-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="910ad-121">Por motivos de seguridad, se recomienda encarecidamente implementar un sistema del mismo nivel en el servidor de mediación que pueda usar TLS.</span><span class="sxs-lookup"><span data-stu-id="910ad-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="910ad-122">En **Servidor de mediación asociado,** seleccione el grupo de servidores de mediación que desea asociar con el tronco raíz de este sistema del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="910ad-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="910ad-123">En **el puerto del servidor de mediación** asociado, escriba el puerto de escucha en el que el servidor de mediación recibirá mensajes SIP del sistema del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="910ad-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="910ad-124">Con la compatibilidad con varios troncos en Skype Empresarial Server, dos  troncos con nombres de tronco diferentes no se pueden configurar con el mismo puerto de servidor de mediación asociado y puerto de escucha para la puerta de enlace **IP/RTC**</span><span class="sxs-lookup"><span data-stu-id="910ad-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="910ad-125">Con la compatibilidad con varios troncos en Skype Empresarial Server, se pueden definir varios puertos de señalización SIP en el servidor de mediación para la comunicación con varios sistemas del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="910ad-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="910ad-126">Al definir un  tronco, el número de puerto del servidor de mediación asociado debe estar dentro del intervalo de puertos de escucha para el protocolo respectivo permitido por el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="910ad-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="910ad-127">Este intervalo de puertos se define en los grupos de servidores de mediación y Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="910ad-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="910ad-128">Haga clic con el botón secundario en el grupo de servidores de mediación correspondiente y seleccione **Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="910ad-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="910ad-129">Especifique el intervalo de puertos en el campo **Puertos de escucha**.</span><span class="sxs-lookup"><span data-stu-id="910ad-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="910ad-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="910ad-130">Click **OK**.</span></span> 
    

