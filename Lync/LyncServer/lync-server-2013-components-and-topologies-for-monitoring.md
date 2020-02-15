---
title: 'Lync Server 2013: componentes y topologías para la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 065cab8b4db7ecbc764ab8a8c6168c88fe1afd50
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="d90e5-102">Componentes y topologías para la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d90e5-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d90e5-103">_**Última modificación del tema:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="d90e5-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="d90e5-104">Como los agentes unificados de recopilación de datos se instalan y activan automáticamente en cada servidor front-end, no es necesario configurar un servidor para que actúe como servidor de supervisión; cada servidor front-end ya funciona como un servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="d90e5-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="d90e5-105">Sin embargo, tendrá que instalar y configurar una base de datos para que actúe como almacén de datos back-end para los datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="d90e5-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="d90e5-106">Microsoft Lync Server 2013 puede usar cualquiera de las siguientes bases de datos como almacén back-end para la supervisión:</span><span class="sxs-lookup"><span data-stu-id="d90e5-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="d90e5-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="d90e5-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="d90e5-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d90e5-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="d90e5-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="d90e5-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="d90e5-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d90e5-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="d90e5-111">Tenga en cuenta que debe usar las ediciones de 64 bits de estas bases de datos; las versiones de 32 bits de SQL Server no se pueden usar como almacén back-end para la supervisión.</span><span class="sxs-lookup"><span data-stu-id="d90e5-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="d90e5-112">De forma similar, Lync Server 2013 no es compatible con las ediciones Express de SQL Server 2008 o SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="d90e5-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="d90e5-113">Para obtener más información sobre los requisitos de bases de datos para Lync Server 2013, vea el tema [compatibilidad de software de base de datos en Lync server 2013](lync-server-2013-database-software-support.md) en la guía de compatibilidad de lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d90e5-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="d90e5-114">Tenga en cuenta que SQL Server debe estar instalado y configurado antes de implementar y configurar la supervisión.</span><span class="sxs-lookup"><span data-stu-id="d90e5-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="d90e5-115">Sin embargo, solo tiene que implementar el propio SQL Server; no es necesario que configure las bases de datos de supervisión con antelación.</span><span class="sxs-lookup"><span data-stu-id="d90e5-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="d90e5-116">En su lugar, las bases de datos se crearán automáticamente cuando publique la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d90e5-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="d90e5-117">Los datos de supervisión pueden compartir una instancia de SQL Server con otros tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="d90e5-117">Monitoring data can share a SQL Server instance with other types of data.</span></span> <span data-ttu-id="d90e5-118">Normalmente, la base de datos de registro detallado de llamadas (LcsCdr) y la base de datos de calidad de la experiencia (QoEMetrics) comparten la misma instancia de SQL; también es común para las dos bases de datos de supervisión estar en la misma instancia de SQL que la base de datos de archivado (LcsLog).</span><span class="sxs-lookup"><span data-stu-id="d90e5-118">Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog).</span></span> <span data-ttu-id="d90e5-119">Sobre el único requisito real de las instancias de SQL Server es que cualquier instancia de SQL Server se limita a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d90e5-119">About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="d90e5-120">Una instancia de la base de datos back-end 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d90e5-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="d90e5-121">(Como regla general, no se recomienda que la base de datos de supervisión se colocará en la misma instancia de SQL, o incluso en el mismo equipo, que la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="d90e5-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="d90e5-122">Si bien técnicamente es posible, se corre el riesgo de que la base de datos de supervisión use espacio en disco necesario para la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="d90e5-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="d90e5-123">Una instancia de la base de datos de registro detallado de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d90e5-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="d90e5-124">Una instancia de la base de datos de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="d90e5-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="d90e5-125">Una instancia de la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="d90e5-125">One instance of the archiving database.</span></span>

<span data-ttu-id="d90e5-126">En otras palabras, no puede tener dos instancias de la base de datos de LcsCdr en la misma instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d90e5-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="d90e5-127">Si necesita varias instancias de la base de datos LcsCdr, tendrá que configurar varias instancias de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d90e5-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d90e5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="d90e5-128">See Also</span></span>


[<span data-ttu-id="d90e5-129">Implementación de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d90e5-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

