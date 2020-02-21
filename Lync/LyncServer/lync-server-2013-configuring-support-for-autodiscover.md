---
title: 'Lync Server 2013: configuración de la compatibilidad con detección automática'
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
ms.openlocfilehash: 1bbb9007562dfecdc4f38b6cf8ac3f1579094ed6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="f82a3-102">Configuración de la compatibilidad con detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f82a3-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f82a3-103">_**Última modificación del tema:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="f82a3-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="f82a3-104">El **servicio Detección automática** de servicios Web de Lync Server apareció por primera vez en la actualización acumulativa de lync Server 2010: noviembre de 2011.</span><span class="sxs-lookup"><span data-stu-id="f82a3-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="f82a3-105">Esta actualización viene acompañada de la versión inicial de clientes móviles de Lync.</span><span class="sxs-lookup"><span data-stu-id="f82a3-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="f82a3-106">El servicio Detección automática expuso los servicios de movilidad, conocido como el servicio MCX.</span><span class="sxs-lookup"><span data-stu-id="f82a3-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="f82a3-107">El servicio Detección automática actúa como una única ubicación para que todos los clientes soliciten información sobre los servicios y las características que están disponibles y cómo ponerse en contacto con los servicios, ya sea mediante un nombre de dominio completo o una referencia de localizador de recursos uniforme Web.</span><span class="sxs-lookup"><span data-stu-id="f82a3-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="f82a3-108">La detección automática expone una serie de características y cada cliente realizará solicitudes basadas en las características que el cliente puede usar.</span><span class="sxs-lookup"><span data-stu-id="f82a3-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="f82a3-109">Por ejemplo, un cliente de Lync 2013 de escritorio usará autodiscvoer para determinar los servicios web externos, pero no usará los servicios de movilidad (MCX).</span><span class="sxs-lookup"><span data-stu-id="f82a3-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="f82a3-110">Para definir y habilitar correctamente a los clientes para que usen las características disponibles, se deben definir los escenarios que permiten a un cliente buscar y usar entradas de detección automática de manera eficaz.</span><span class="sxs-lookup"><span data-stu-id="f82a3-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="f82a3-111">Para usar autodoscover, su implementación requiere que un proxy inverso publique los servicios Web de Lync Server, que los registros DNS están configurados para resolver consultas DNS para el servicio Detección automática de Lync Server y los servicios Web de Lync Server, y que los servicios de certificados están configurados correctamente para su escenario específico.</span><span class="sxs-lookup"><span data-stu-id="f82a3-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f82a3-112">Para obtener información técnica sobre los elementos que se encuentran dentro de la solicitud o respuesta de detección automática, consulte <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f82a3-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f82a3-113">La siguiente información y tablas definen, por escenario, qué configuraciones debe implementar (si las hay) para proporcionar el uso eficaz y completo del servicio de detección automática.</span><span class="sxs-lookup"><span data-stu-id="f82a3-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="f82a3-114">La información de los siguientes temas es específica de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f82a3-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f82a3-115">Si está buscando instrucciones sobre cómo planear la movilidad para Lync Server 2010, consulte [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113).</span><span class="sxs-lookup"><span data-stu-id="f82a3-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="f82a3-116">Para implementar Mobility para Lync Server 2010, consulte[https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="f82a3-116">To deploy Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f82a3-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f82a3-117">In This Section</span></span>

  - [<span data-ttu-id="f82a3-118">Configuración de DNS para la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f82a3-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="f82a3-119">Configuración de certificados para la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f82a3-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="f82a3-120">Configuración de un proxy inverso para detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f82a3-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="f82a3-121">Configuración de detección automática en Lync Server 2013 para implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="f82a3-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

