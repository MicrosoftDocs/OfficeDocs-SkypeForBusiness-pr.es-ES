---
title: 'Lync Server 2013: implementación de servidores de mediación y definición de homólogos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e9ca9fa29d2646a38a9cbf94d79ba9766b21d62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="92854-102">Implementación de servidores de mediación y definición de pares en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92854-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92854-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="92854-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="92854-104">Los grupos de servidores front-end disponen de la carga de trabajo de Enterprise Voice, la Conferencia de acceso telefónico local y las aplicaciones avanzadas de telefonía IP (aplicación de grupo de respuesta, aplicación de estacionamiento de llamadas, control de admisión de llamadas (CAC), etc.).</span><span class="sxs-lookup"><span data-stu-id="92854-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="92854-105">Con Lync Server 2013, la funcionalidad del servidor de mediación está integrada en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="92854-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="92854-106">Un servidor de mediación independiente independiente ya no es necesario.</span><span class="sxs-lookup"><span data-stu-id="92854-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="92854-107">Los grupos de servidores front-end se pueden comunicar directamente con puertas de enlace compatibles (una puerta de enlace de red telefónica conmutada (RTC) o una IP-PBX), lo que elimina la necesidad de que un servidor de mediación sirva como intermediario.</span><span class="sxs-lookup"><span data-stu-id="92854-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="92854-108">La única excepción es si configura un tronco SIP para conectarse a un controlador de borde de sesión para un proveedor de servicios de telefonía por Internet.</span><span class="sxs-lookup"><span data-stu-id="92854-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="92854-109">Para conectar su infraestructura de telefonía IP empresarial a su proveedor de tronco SIP, se debe implementar un servidor de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="92854-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="92854-110">La conexión entre Lync Server (el componente del servidor de mediación en un grupo de servidores front-end o un servidor de mediación independiente) y una puerta de enlace se define como una asociación lógica llamada *tronco*.</span><span class="sxs-lookup"><span data-stu-id="92854-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="92854-111">En los temas de esta sección se describe cómo definir un tronco y cómo implementar un servidor de mediación independiente, si se conecta a un tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="92854-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="92854-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="92854-112">In This Section</span></span>

  - [<span data-ttu-id="92854-113">Definir un servidor de mediación en el generador de topologías de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92854-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="92854-114">Definir una puerta de enlace en el generador de topologías de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92854-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="92854-115">Instalar los archivos del servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92854-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="92854-116">Definir troncos adicionales en el generador de topologías de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92854-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="92854-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="92854-117">Related Sections</span></span>

[<span data-ttu-id="92854-118">Configurar las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92854-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

