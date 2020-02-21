---
title: 'Lync Server 2013: contratos de nivel de servicio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f902a946d272ce3a16db5f032b74ec031c7e3a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="ef165-102">Acuerdos de nivel de servicio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef165-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef165-103">_**Última modificación del tema:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="ef165-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="ef165-104">El SLA es un documento que define los servicios que el cliente espera de usted.</span><span class="sxs-lookup"><span data-stu-id="ef165-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="ef165-105">La complejidad y el contenido de este documento dependen en gran medida de si los clientes son internos (dentro del entorno) o externos.</span><span class="sxs-lookup"><span data-stu-id="ef165-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="ef165-106">Clientes externos</span><span class="sxs-lookup"><span data-stu-id="ef165-106">External Customers</span></span>

<span data-ttu-id="ef165-107">Si su cliente es externo, el acuerdo de nivel de servicio puede formar parte de un contrato legal con incentivos financieros y sanciones por rendimiento dentro o fuera de los niveles de servicio definidos.</span><span class="sxs-lookup"><span data-stu-id="ef165-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="ef165-108">La definición de estos niveles de servicio debe formar parte de la negociación general de contratos.</span><span class="sxs-lookup"><span data-stu-id="ef165-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="ef165-109">Como con todos los contratos, es importante que ambas partes comprendan las expectativas.</span><span class="sxs-lookup"><span data-stu-id="ef165-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="ef165-110">El SLA define estas expectativas.</span><span class="sxs-lookup"><span data-stu-id="ef165-110">The SLA defines these expectations.</span></span> <span data-ttu-id="ef165-111">El contenido del documento debería cambiar con poca frecuencia y solo debido a las negociaciones con el cliente.</span><span class="sxs-lookup"><span data-stu-id="ef165-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="ef165-112">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="ef165-112">Internal Customers</span></span>

<span data-ttu-id="ef165-113">Si su cliente es interno, es posible que desee definir los servicios que se esperarán de los equipos de operaciones y de los sistemas de ti.</span><span class="sxs-lookup"><span data-stu-id="ef165-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="ef165-114">El SLA puede ser creado por el personal de operaciones y pensado como un conjunto de objetivos para la disponibilidad de los servicios de ti dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="ef165-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="ef165-115">O bien, los niveles de rendimiento se pueden establecer mediante la administración y se usan como pruebas de referencia al evaluar el rendimiento del personal.</span><span class="sxs-lookup"><span data-stu-id="ef165-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="ef165-116">Criterios típicos</span><span class="sxs-lookup"><span data-stu-id="ef165-116">Typical Criteria</span></span>

<span data-ttu-id="ef165-117">Los SLAs incluyen secciones que definen los criterios de niveles mínimos de disponibilidad, soporte técnico y capacidad.</span><span class="sxs-lookup"><span data-stu-id="ef165-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="ef165-118">**La disponibilidad**   define las horas y los sistemas operativos en los que estarán disponibles los sitios y otros servicios de Lync.</span><span class="sxs-lookup"><span data-stu-id="ef165-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="ef165-119">Debe definirse cualquier mantenimiento rutinario que afecte a la disponibilidad del servicio.</span><span class="sxs-lookup"><span data-stu-id="ef165-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="ef165-120">Definir los factores externos que afectan al servicio, por ejemplo, la pérdida de conectividad a Internet.</span><span class="sxs-lookup"><span data-stu-id="ef165-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="ef165-121">**Soporte técnico**   defina las horas en las que estará disponible el soporte para un sistema.</span><span class="sxs-lookup"><span data-stu-id="ef165-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="ef165-122">Especifique los métodos para que los clientes se pongan en contacto con el personal de soporte técnico, la manera en que se agrupan los incidentes y el tiempo de respuesta y para resolver el incidente.</span><span class="sxs-lookup"><span data-stu-id="ef165-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="ef165-123">Definir la frecuencia y el contenido de los comentarios para el cliente.</span><span class="sxs-lookup"><span data-stu-id="ef165-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="ef165-124">**La capacidad**   define el tamaño máximo habilitado de los sitios de Lync y los pasos que se deben tomar si se supera el límite.</span><span class="sxs-lookup"><span data-stu-id="ef165-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="ef165-125">Definir el tiempo máximo habilitado para realizar tareas estándar, como el tiempo para recuperar un documento de una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="ef165-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="ef165-126">Definir el número máximo de usuarios por grupo de Lync y aceptar un proceso para aumentar la capacidad si se agregan más usuarios.</span><span class="sxs-lookup"><span data-stu-id="ef165-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

