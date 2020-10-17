---
title: 'Lync Server 2013: detalles de la tabla de CDR'
description: 'Lync Server 2013: detalles de la tabla de CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331a3dfd4ffccac2ac4a442eeb9ad9171defb41c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544396"
---
# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="27b0e-103">Detalles de la tabla de CDR en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-103">CDR table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27b0e-104">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="27b0e-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="27b0e-105">En los siguientes temas se detallan las columnas de cada una de las tablas de esquema de base de datos de los registros detallados de llamadas (CDR).</span><span class="sxs-lookup"><span data-stu-id="27b0e-105">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="27b0e-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="27b0e-106">In This Section</span></span>

  - [<span data-ttu-id="27b0e-107">Tabla de aplicaciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-107">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="27b0e-108">Tabla CallPriorities en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-108">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="27b0e-109">Tabla CallType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-109">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="27b0e-110">Tabla ClientVersions en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-110">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="27b0e-111">Tabla ConferenceJoinTimeThresholds en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-111">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="27b0e-112">Tabla ConferenceMessageCount en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-112">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="27b0e-113">Tabla conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-113">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="27b0e-114">Tabla ConferenceSessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-114">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="27b0e-115">Tabla ConferenceUris en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-115">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="27b0e-116">Tabla ContentTypes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-116">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="27b0e-117">Tabla DeRegisterType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-117">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="27b0e-118">Tabla Devices en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-118">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="27b0e-119">Tabla de cuadros de diálogo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-119">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="27b0e-120">Tabla EdgeServers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-120">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="27b0e-121">Tabla categoría en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-121">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="27b0e-122">Tabla ErrorDef en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-122">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="27b0e-123">Tabla ErrorReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-123">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="27b0e-124">Tabla FileTransfers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-124">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="27b0e-125">Tabla FocusJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-125">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="27b0e-126">Tabla front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-126">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="27b0e-127">Tabla gateways en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-127">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="27b0e-128">Tabla HardwareVersions en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-128">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="27b0e-129">Tabla IMReportSummary en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-129">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="27b0e-130">Tabla Locations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-130">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="27b0e-131">Tabla Manufacturers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-131">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="27b0e-132">Tabla McuJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-132">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="27b0e-133">Tabla MCU en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-133">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="27b0e-134">Tabla de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-134">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="27b0e-135">Tabla de MediaL en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-135">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="27b0e-136">Tabla MediationServers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-136">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="27b0e-137">Tabla MSMQProcessing en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-137">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="27b0e-138">Tabla teléfonos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-138">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="27b0e-139">Tabla pools en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-139">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="27b0e-140">Tabla ProgressReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-140">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="27b0e-141">Tabla PurgeSettings en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-141">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="27b0e-142">Tabla de registro en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-142">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="27b0e-143">Tabla roles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-143">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="27b0e-144">Tabla Servers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-144">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="27b0e-145">Tabla SessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-145">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="27b0e-146">Tabla SIPResponseMetaData en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-146">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="27b0e-147">Tabla de sindicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-147">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="27b0e-148">Tabla SyndicatorsTenantMap en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-148">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="27b0e-149">Tabla de tareas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-149">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="27b0e-150">Tabla Tenants en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-150">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="27b0e-151">Tabla UriTypes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-151">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="27b0e-152">Tabla users en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-152">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="27b0e-153">Tabla UserAgentDef en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-153">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="27b0e-154">Tabla UserStatistics en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-154">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="27b0e-155">Tabla VoipDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b0e-155">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

