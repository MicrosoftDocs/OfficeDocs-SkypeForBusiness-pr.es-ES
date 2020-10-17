---
title: 'Lync Server 2013: Planeación de la seguridad'
description: 'Lync Server 2013: Planeación de la seguridad.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1abc02aa3f42a6b12c66c621b071e0b3ddb545c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549236"
---
# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="5ea0a-103">Planeación de la seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea0a-103">Planning for security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ea0a-104">_**Última modificación del tema:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="5ea0a-104">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="5ea0a-105">Use esta sección de seguridad para evaluar y administrar los riesgos de seguridad en su implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ea0a-105">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="5ea0a-106">Incluso si la implementación de Lync Server 2013 es modesta, probablemente tenga componentes en la red que tengan su propia documentación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5ea0a-106">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="5ea0a-107">Por lo tanto, es improbable que esta sección abarque todos los aspectos de la seguridad de todos los componentes y áreas relevantes para la implementación.</span><span class="sxs-lookup"><span data-stu-id="5ea0a-107">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="5ea0a-108">Use esta sección como punto de partida para dirigir la seguridad de su implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ea0a-108">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="5ea0a-109">Proporciona instrucciones generales y procedimientos recomendados para evaluar y administrar los riesgos de seguridad más comunes.</span><span class="sxs-lookup"><span data-stu-id="5ea0a-109">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="5ea0a-110">Al final de cada tema, se enumeran los recursos de seguridad y de productos adicionales.</span><span class="sxs-lookup"><span data-stu-id="5ea0a-110">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5ea0a-111">La seguridad es un tema que está en constante evolución.</span><span class="sxs-lookup"><span data-stu-id="5ea0a-111">Security is a constantly evolving topic.</span></span> <span data-ttu-id="5ea0a-112">A medida que surgen nuevas amenazas y soluciones, los documentos, las soluciones, los métodos y los procedimientos obsoletos deben reemplazarse por material actualizado.</span><span class="sxs-lookup"><span data-stu-id="5ea0a-112">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5ea0a-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5ea0a-113">In This Section</span></span>

  - [<span data-ttu-id="5ea0a-114">Características de seguridad clave en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea0a-114">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="5ea0a-115">Amenazas de seguridad comunes en el entorno informático de hoy día</span><span class="sxs-lookup"><span data-stu-id="5ea0a-115">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="5ea0a-116">Exclusiones de detección de virus para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea0a-116">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="5ea0a-117">Marco de seguridad para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea0a-117">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="5ea0a-118">Afrontar las amenazas a su infraestructura básica para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea0a-118">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="5ea0a-119">Implementación de un puerto y alias no estándar de SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea0a-119">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

