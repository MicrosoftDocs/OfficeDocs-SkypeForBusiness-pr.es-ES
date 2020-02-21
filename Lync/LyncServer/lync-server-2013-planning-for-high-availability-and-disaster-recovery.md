---
title: 'Lync Server 2013: Planeación de alta disponibilidad y recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0ce8135481e283275bab507dfbe813a4fd1117b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-31_

Como en Lync Server 2010, el esquema de alta disponibilidad principal para la mayoría de roles de servidor en Lync Server 2013 se basa en la redundancia de servidores a través de la agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor. Esto se aplica a los servidores front-end, los servidores perimetrales, los servidores de mediación y los directores.

Lync Server 2013 agrega nuevas medidas de recuperación ante desastres para grupos de servidores front-end mediante la introducción de dispersión geográficas de sus servidores en dos centros de datos para proporcionar la continuación del servicio en caso de que se produzca un bloqueo o un sitio completo.

Lync Server 2013 también mejora la alta disponibilidad del servidor back-end, ya que admite la creación de reflejos de SQL sincrónicos para las bases de datos back-end.

En esta sección se explican estas principales características de alta disponibilidad y de recuperación ante desastres, y también se describen los pasos que puede realizar para la alta disponibilidad y la recuperación ante desastres para sus otros roles de servidor también.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Recuperación ante desastres del grupo de servidores front-end en Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Recuperación ante desastres del servidor perimetral en Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Planeación de la resistencia de la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Características de administración de llamadas para la recuperación ante desastres en Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Configurar el servidor de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2010 resistencia del sitio metropolitana](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

