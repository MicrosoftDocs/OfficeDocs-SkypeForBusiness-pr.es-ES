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

# <a name="cdr-table-details-in-lync-server-2013"></a>Detalles de la tabla de CDR en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

En los siguientes temas se detallan las columnas de cada una de las tablas de esquema de base de datos de los registros detallados de llamadas (CDR).

<div>

## <a name="in-this-section"></a>En esta sección

  - [Tabla de aplicaciones en Lync Server 2013](lync-server-2013-application-table.md)

  - [Tabla CallPriorities en Lync Server 2013](lync-server-2013-callpriorities-table.md)

  - [Tabla CallType en Lync Server 2013](lync-server-2013-calltype-table.md)

  - [Tabla ClientVersions en Lync Server 2013](lync-server-2013-clientversions-table.md)

  - [Tabla ConferenceJoinTimeThresholds en Lync Server 2013](lync-server-2013-conferencejointimethresholds-table.md)

  - [Tabla ConferenceMessageCount en Lync Server 2013](lync-server-2013-conferencemessagecount-table.md)

  - [Tabla conferencias en Lync Server 2013](lync-server-2013-conferences-table.md)

  - [Tabla ConferenceSessionDetails en Lync Server 2013](lync-server-2013-conferencesessiondetails-table.md)

  - [Tabla ConferenceUris en Lync Server 2013](lync-server-2013-conferenceuris-table.md)

  - [Tabla ContentTypes en Lync Server 2013](lync-server-2013-contenttypes-table.md)

  - [Tabla DeRegisterType en Lync Server 2013](lync-server-2013-deregistertype-table.md)

  - [Tabla Devices en Lync Server 2013](lync-server-2013-devices-table.md)

  - [Tabla de cuadros de diálogo en Lync Server 2013](lync-server-2013-dialogs-table.md)

  - [Tabla EdgeServers en Lync Server 2013](lync-server-2013-edgeservers-table.md)

  - [Tabla categoría en Lync Server 2013](lync-server-2013-errorcategory-table.md)

  - [Tabla ErrorDef en Lync Server 2013](lync-server-2013-errordef-table.md)

  - [Tabla ErrorReport en Lync Server 2013](lync-server-2013-errorreport-table.md)

  - [Tabla FileTransfers en Lync Server 2013](lync-server-2013-filetransfers-table.md)

  - [Tabla FocusJoinsAndLeaves en Lync Server 2013](lync-server-2013-focusjoinsandleaves-table.md)

  - [Tabla front-end en Lync Server 2013](lync-server-2013-frontend-table.md)

  - [Tabla gateways en Lync Server 2013](lync-server-2013-gateways-table.md)

  - [Tabla HardwareVersions en Lync Server 2013](lync-server-2013-hardwareversions-table.md)

  - [Tabla IMReportSummary en Lync Server 2013](lync-server-2013-imreportsummary-table.md)

  - [Tabla Locations in Lync Server 2013](lync-server-2013-locations-table.md)

  - [Tabla Manufacturers en Lync Server 2013](lync-server-2013-manufacturers-table.md)

  - [Tabla McuJoinsAndLeaves en Lync Server 2013](lync-server-2013-mcujoinsandleaves-table.md)

  - [Tabla MCU en Lync Server 2013](lync-server-2013-mcus-table.md)

  - [Tabla de medios en Lync Server 2013](lync-server-2013-media-table.md)

  - [Tabla de MediaL en Lync Server 2013](lync-server-2013-medialist-table.md)

  - [Tabla MediationServers en Lync Server 2013](lync-server-2013-mediationservers-table.md)

  - [Tabla MSMQProcessing en Lync Server 2013](lync-server-2013-msmqprocessing-table.md)

  - [Tabla teléfonos en Lync Server 2013](lync-server-2013-phones-table.md)

  - [Tabla pools en Lync Server 2013](lync-server-2013-pools-table.md)

  - [Tabla ProgressReport en Lync Server 2013](lync-server-2013-progressreport-table.md)

  - [Tabla PurgeSettings en Lync Server 2013](lync-server-2013-purgesettings-table.md)

  - [Tabla de registro en Lync Server 2013](lync-server-2013-registration-table.md)

  - [Tabla roles en Lync Server 2013](lync-server-2013-roles-table.md)

  - [Tabla Servers en Lync Server 2013](lync-server-2013-servers-table.md)

  - [Tabla SessionDetails en Lync Server 2013](lync-server-2013-sessiondetails-table.md)

  - [Tabla SIPResponseMetaData en Lync Server 2013](lync-server-2013-sipresponsemetadata-table.md)

  - [Tabla de sindicación en Lync Server 2013](lync-server-2013-syndicators-table.md)

  - [Tabla SyndicatorsTenantMap en Lync Server 2013](lync-server-2013-syndicatorstenantmap-table.md)

  - [Tabla de tareas en Lync Server 2013](lync-server-2013-task-table.md)

  - [Tabla Tenants en Lync Server 2013](lync-server-2013-tenants-table.md)

  - [Tabla UriTypes en Lync Server 2013](lync-server-2013-uritypes-table.md)

  - [Tabla users en Lync Server 2013](lync-server-2013-users-table.md)

  - [Tabla UserAgentDef en Lync Server 2013](lync-server-2013-useragentdef-table.md)

  - [Tabla UserStatistics en Lync Server 2013](lync-server-2013-userstatistics-table.md)

  - [Tabla VoipDetails en Lync Server 2013](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

