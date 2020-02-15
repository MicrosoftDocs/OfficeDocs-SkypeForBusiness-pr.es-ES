---
title: 'Lync Server 2013: Planeación de la seguridad'
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
ms.openlocfilehash: 3bcc5c5cb36717084f9ec5715feb30b11ced5a3e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="4d480-102">Planeación de la seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d480-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d480-103">_**Última modificación del tema:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="4d480-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="4d480-104">Use esta sección de seguridad para evaluar y administrar los riesgos de seguridad en su implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d480-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="4d480-105">Incluso si la implementación de Lync Server 2013 es modesta, probablemente tenga componentes en la red que tengan su propia documentación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4d480-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="4d480-106">Por lo tanto, es improbable que esta sección abarque todos los aspectos de la seguridad de todos los componentes y áreas relevantes para la implementación.</span><span class="sxs-lookup"><span data-stu-id="4d480-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="4d480-107">Use esta sección como punto de partida para dirigir la seguridad de su implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d480-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="4d480-108">Proporciona instrucciones generales y procedimientos recomendados para evaluar y administrar los riesgos de seguridad más comunes.</span><span class="sxs-lookup"><span data-stu-id="4d480-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="4d480-109">Al final de cada tema, se enumeran los recursos de seguridad y de productos adicionales.</span><span class="sxs-lookup"><span data-stu-id="4d480-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4d480-110">La seguridad es un tema que está en constante evolución.</span><span class="sxs-lookup"><span data-stu-id="4d480-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="4d480-111">A medida que surgen nuevas amenazas y soluciones, los documentos, las soluciones, los métodos y los procedimientos obsoletos deben reemplazarse por material actualizado.</span><span class="sxs-lookup"><span data-stu-id="4d480-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4d480-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4d480-112">In This Section</span></span>

  - [<span data-ttu-id="4d480-113">Características de seguridad clave en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d480-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="4d480-114">Amenazas de seguridad comunes en el entorno informático de hoy día</span><span class="sxs-lookup"><span data-stu-id="4d480-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="4d480-115">Exclusiones de detección de virus para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d480-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="4d480-116">Marco de seguridad para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d480-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="4d480-117">Afrontar las amenazas a su infraestructura básica para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d480-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="4d480-118">Implementación de un puerto y alias no estándar de SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d480-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

