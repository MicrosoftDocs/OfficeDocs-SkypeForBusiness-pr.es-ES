---
title: 'Lync Server 2013: configuración de la compatibilidad con la detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 779929d270fa4ae2f8eec59a954c2273ff61b44f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="1ed70-102">Configuración de la compatibilidad con la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed70-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ed70-103">_**Última modificación del tema:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="1ed70-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="1ed70-104">El **servicio de detección automática** de servicios Web de Lync Server apareció en primer lugar en la actualización acumulativa de lync Server 2010:2011 de noviembre.</span><span class="sxs-lookup"><span data-stu-id="1ed70-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="1ed70-105">Esta actualización viene acompañada de la versión inicial de clientes móviles de Lync.</span><span class="sxs-lookup"><span data-stu-id="1ed70-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="1ed70-106">El servicio de detección automática expuso los servicios de movilidad, conocido como el servicio MCX.</span><span class="sxs-lookup"><span data-stu-id="1ed70-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="1ed70-107">El servicio de detección automática actúa como una única ubicación para que todos los clientes soliciten información sobre los servicios y las características disponibles, y cómo comunicarse con ellos, ya sea mediante un nombre de dominio completo o una referencia de localizador de recursos uniforme Web.</span><span class="sxs-lookup"><span data-stu-id="1ed70-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="1ed70-108">Detección automática expone una serie de características y cada cliente realiza solicitudes basadas en las características que el cliente puede usar.</span><span class="sxs-lookup"><span data-stu-id="1ed70-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="1ed70-109">Por ejemplo, un cliente de Lync 2013 de escritorio usará autodiscvoer para determinar los servicios web externos, pero no usará los servicios de movilidad (MCX).</span><span class="sxs-lookup"><span data-stu-id="1ed70-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="1ed70-110">Para definir correctamente y habilitar a los clientes para que usen las características disponibles, se deben definir los escenarios que permiten a un cliente buscar y usar entradas de detección automática de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="1ed70-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="1ed70-111">Para usar autodoscover, su implementación requiere que un proxy inverso publique los servicios Web de Lync Server, que los registros DNS están configurados para resolver consultas DNS para el servicio Detección automática de Lync Server y los servicios Web de Lync Server, y que los servicios de Certificate Server están correctamente configurados para tu escenario específico.</span><span class="sxs-lookup"><span data-stu-id="1ed70-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1ed70-112">Para obtener información técnica sobre lo que hacen los elementos dentro de la solicitud o respuesta de detección automática, consulte <A href="lync-server-2013-understanding-autodiscover.md">Descripción de la detección automática en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1ed70-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1ed70-113">La siguiente información y tablas definen, por ejemplo, qué configuraciones (si las hay) necesita implementar para proporcionar el uso efectivo y completo del servicio de detección automática.</span><span class="sxs-lookup"><span data-stu-id="1ed70-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="1ed70-114">La información de los temas siguientes es específica de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ed70-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="1ed70-115">Si está buscando información sobre cómo planear la movilidad para Lync Server 2010, consulte [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span><span class="sxs-lookup"><span data-stu-id="1ed70-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="1ed70-116">Para implementar la movilidad de Lync Server 2010, consulte[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="1ed70-116">To deploy Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1ed70-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1ed70-117">In This Section</span></span>

  - [<span data-ttu-id="1ed70-118">Configuración de DNS para la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed70-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="1ed70-119">Configuración de certificados para la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed70-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="1ed70-120">Configuración de un proxy inverso para detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed70-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="1ed70-121">Configuración de la detección automática en Lync Server 2013 para implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="1ed70-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

