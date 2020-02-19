---
title: 'Lync Server 2013: detalles de la tabla de CDR'
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
ms.openlocfilehash: dcb8d75948f1b85257f0182d571ea2fe08f3a0d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="6c2e9-102">Detalles de la tabla de CDR en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c2e9-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6c2e9-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6c2e9-104">En los siguientes temas se detallan las columnas de cada una de las tablas de esquema de base de datos de los registros detallados de llamadas (CDR).</span><span class="sxs-lookup"><span data-stu-id="6c2e9-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6c2e9-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6c2e9-105">In This Section</span></span>

  - [<span data-ttu-id="6c2e9-106">Tabla de aplicaciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="6c2e9-107">Tabla CallPriorities en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="6c2e9-108">Tabla CallType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="6c2e9-109">Tabla ClientVersions en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="6c2e9-110">Tabla ConferenceJoinTimeThresholds en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="6c2e9-111">Tabla ConferenceMessageCount en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="6c2e9-112">Tabla conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="6c2e9-113">Tabla ConferenceSessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="6c2e9-114">Tabla ConferenceUris en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="6c2e9-115">Tabla ContentTypes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="6c2e9-116">Tabla DeRegisterType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="6c2e9-117">Tabla Devices en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="6c2e9-118">Tabla de cuadros de diálogo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="6c2e9-119">Tabla EdgeServers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="6c2e9-120">Tabla categoría en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="6c2e9-121">Tabla ErrorDef en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="6c2e9-122">Tabla ErrorReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="6c2e9-123">Tabla FileTransfers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="6c2e9-124">Tabla FocusJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="6c2e9-125">Tabla front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="6c2e9-126">Tabla gateways en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="6c2e9-127">Tabla HardwareVersions en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="6c2e9-128">Tabla IMReportSummary en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="6c2e9-129">Tabla Locations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="6c2e9-130">Tabla Manufacturers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="6c2e9-131">Tabla McuJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="6c2e9-132">Tabla MCU en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="6c2e9-133">Tabla de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="6c2e9-134">Tabla de MediaL en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="6c2e9-135">Tabla MediationServers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="6c2e9-136">Tabla MSMQProcessing en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="6c2e9-137">Tabla teléfonos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="6c2e9-138">Tabla pools en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="6c2e9-139">Tabla ProgressReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="6c2e9-140">Tabla PurgeSettings en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="6c2e9-141">Tabla de registro en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="6c2e9-142">Tabla roles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="6c2e9-143">Tabla Servers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="6c2e9-144">Tabla SessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="6c2e9-145">Tabla SIPResponseMetaData en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="6c2e9-146">Tabla de sindicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="6c2e9-147">Tabla SyndicatorsTenantMap en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="6c2e9-148">Tabla de tareas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="6c2e9-149">Tabla Tenants en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="6c2e9-150">Tabla UriTypes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="6c2e9-151">Tabla users en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="6c2e9-152">Tabla UserAgentDef en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="6c2e9-153">Tabla UserStatistics en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="6c2e9-154">Tabla VoipDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2e9-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

