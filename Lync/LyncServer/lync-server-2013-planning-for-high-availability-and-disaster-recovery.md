---
title: 'Lync Server 2013: Planeación de alta disponibilidad y recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 092e59813f76690233a950cd8ce914df47146d37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-31_

Al igual que en Lync Server 2010, el esquema de alta disponibilidad principal para la mayoría de los roles de servidor de Lync Server 2013 se basa en la redundancia de los servidores a través de la agrupación. Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor. Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.

Lync Server 2013 agrega nuevas medidas de recuperación ante desastres para grupos de servidores front-end mediante la introducción de dispersement geográficas de los servidores en dos centros de datos para ofrecer la continuación del servicio en caso de que se desconecte todo un grupo o sitio.

Lync Server 2013 también mejora la alta disponibilidad del servidor back-end, pues admite el reflejo de SQL sincrónico para las bases de datos back-end.

En esta sección se explican estas características principales de alta disponibilidad y recuperación ante desastres, y también se describen los pasos que puede realizar para la alta disponibilidad y la recuperación ante desastres para sus otros roles de servidor.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Grupo front-end para la recuperación ante desastres en Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Recuperación ante desastres del servidor perimetral en Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Planear la resistencia de la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Características de la administración de llamadas para la recuperación ante desastres en Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Configurar servidores de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Resistencia de sitios de metropolitana de Lync Server 2010](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

