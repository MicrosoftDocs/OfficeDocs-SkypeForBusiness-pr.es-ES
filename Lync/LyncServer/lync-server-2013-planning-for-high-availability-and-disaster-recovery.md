---
title: "Lync Server 2013: Planificación de alta disponibilidad y recuperación ante desastres"
TOCTitle: Planeación de alta disponibilidad y recuperación ante desastres
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48274534
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013

 

_**Última modificación del tema:** 2013-10-31_

Al igual que en Lync Server 2010, el principal esquema de alta disponibilidad para la mayoría de los roles en Lync Server 2013 se basa en la redundancia de servidores a través de la agrupación de servidores. Si falla un servidor que esté ejecutando un determinado rol, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga. Esto se aplica a servidores front-end, servidores perimetrales, servidores de mediación y directores.

Lync Server 2013 agrega nuevas medidas de recuperación de desastres para grupos de servidores front-end introduciendo la dispersión geográfica de sus servidores en dos centros de datos para proporcionar continuación de servicio en caso de que caigan un sitio o grupo de servidores completo.

Lync Server 2013 también mejora la alta disponibilidad para el servidor back-end admitiendo la creación de reflejo de SQL sincrónico para sus bases de datos back-end.

Esta sección explica estas características principales de alta disponibilidad y recuperación ante desastres, y trata además qué pasos puede tomar para alta disponibilidad y recuperación ante desastres también para sus otros servidores.

## En esta sección

  - [Grupo front-end para la recuperación ante desastres en Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Recuperación ante desastres del servidor perimetral en Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Planear la resistencia de la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Características de la administración de llamadas para la recuperación ante desastres en Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Configurar servidores de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Resistencia de sitios de metropolitana de Lync Server 2010](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

