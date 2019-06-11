---
title: 'Lync Server 2013: Componentes y topologías para la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0c848b3c404bc9bce3b54d6ed52157d1b9da679
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="8526f-102">Componentes y topologías para la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8526f-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8526f-103">_**Última modificación del tema:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="8526f-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="8526f-104">Debido a que los agentes de recopilación de datos unificados se instalan y activan automáticamente en cada servidor front-end, no es necesario configurar un servidor para que actúe como servidor de supervisión; cada servidor front-end funciona como servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="8526f-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="8526f-105">Sin embargo, necesitará instalar y configurar una base de datos para que actúe como almacén de datos del back-end para los datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="8526f-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="8526f-106">Microsoft Lync Server 2013 puede usar cualquiera de las siguientes bases de datos como almacén back-end para la supervisión:</span><span class="sxs-lookup"><span data-stu-id="8526f-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="8526f-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="8526f-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="8526f-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="8526f-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="8526f-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="8526f-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="8526f-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="8526f-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="8526f-111">Tenga en cuenta que debe usar las ediciones de 64 bits de estas bases de datos; las versiones de 32 bits de SQL Server no se pueden usar como almacén de back-end para la supervisión.</span><span class="sxs-lookup"><span data-stu-id="8526f-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="8526f-112">Del mismo modo, Lync Server 2013 no es compatible con las ediciones Express de SQL Server 2008 o SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="8526f-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="8526f-113">Para obtener más información sobre los requisitos de base de datos de Lync Server 2013 consulte el tema [compatibilidad de software de base de datos en Lync server 2013](lync-server-2013-database-software-support.md) en la guía de compatibilidad de lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8526f-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="8526f-114">Recuerde que es preciso que SQL Server esté instalado y configurado antes de implementar y configurar la supervisión.</span><span class="sxs-lookup"><span data-stu-id="8526f-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="8526f-115">Sin embargo, solo necesita implementar SQL Server en sí; no es necesario configurar las bases de datos de supervisión con antelación.</span><span class="sxs-lookup"><span data-stu-id="8526f-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="8526f-116">En su lugar, estas bases de datos se crearán automáticamente cuando publique la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8526f-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="8526f-p104">Al supervisar los datos se puede compartir una instancia de SQL Server con otros tipos de datos. Generalmente, las bases de datos del registro detallado de llamadas (LcsCdr) y de la calidad de la experiencia (QoEMetrics) comparten la misma instancia de SQL. También es habitual que las dos bases de datos de supervisión se encuentren en la misma instancia de SQL que la base de datos de archivado (LcsLog). El único requisito real con relación a las instancias de SQL Server es que cada una de ellas se limite conforme a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8526f-p104">Monitoring data can share a SQL Server instance with other types of data. Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog). About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="8526f-120">Una instancia de la base de datos back-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8526f-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="8526f-121">Como norma general, no recomendamos que la base de datos de supervisión se encuentre en la misma instancia de SQL, ni siquiera en el mismo equipo, que la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="8526f-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="8526f-122">Aunque técnicamente es posible, corre el riesgo de que la base de datos de supervisión agote el espacio en disco que necesita la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="8526f-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="8526f-123">Una instancia de la base de datos del registro detallado de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8526f-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="8526f-124">Una instancia de la base de datos de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="8526f-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="8526f-125">Una instancia de la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="8526f-125">One instance of the archiving database.</span></span>

<span data-ttu-id="8526f-126">En otras palabras, no puede tener dos instancias de la base de datos LcsCdr en la misma instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8526f-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="8526f-127">Si necesita varias instancias de la base de datos LcsCdr, tendrá que configurar varias instancias de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8526f-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8526f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8526f-128">See Also</span></span>


[<span data-ttu-id="8526f-129">Implementación de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8526f-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

