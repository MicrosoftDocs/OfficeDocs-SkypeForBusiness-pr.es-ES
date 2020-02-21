---
title: 'Lync Server 2013: crear registros DNS para servidores de proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79c583f5c25ea58f0d1a2ea32246db8eec8f7740
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Crear registros DNS para servidores de proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-29_

Cree registros A de DNS externos que apunten a la interfaz externa pública de Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, el servidor de Forefront Threat Management Gateway 2010 Server o el enrutamiento de solicitud de Internet Information Server, tal como se describe en [configure DNS for Edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md). Necesita registros DNS para los FQDN de servicio Web externo para cada grupo de servidores, Director (o grupo de directores) y cada dirección URL sencilla.

Para conseguir los registros DNS mínimos para la resolución de cliente en el proxy inverso, deben crearse los siguientes registros:

  - Registros de host (A) que definen los servicios web externos publicados para directores y grupos de directores (por ejemplo, **webdirext.contoso.com**)

  - Registros de host (A) que definen los servicios web externos publicados para servicios web externos hospedados en los grupos de servidores front-end y roles de servidor Standard Edition (por ejemplo, **webext.contoso.com**)

  - Registro(s) del host (A) para las direcciones URL sencillas; por ejemplo, **dialin.contoso.com** y**meet.contoso.com**)

  - Registro host (A) para el registro externo de detección de Lync y también proporciona un puntero a detección automática para todas las aplicaciones Web, incluidos Lync Web App, Scheduler y Mobility (por ejemplo, **lyncdiscover.contoso.com**)

  - Registros de host (A) para la dirección URL de Office Web Apps Server (por ejemplo, **officewebapp01.contoso.com**)

Para obtener más información, consulte [Resumen DNS-proxy inverso en Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

</div>

<span> </span>

</div>

</div>

</div>

