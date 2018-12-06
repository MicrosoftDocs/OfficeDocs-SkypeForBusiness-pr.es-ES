---
title: 'Lync Server 2013: Enlace troncal SIP'
TOCTitle: Enlace troncal SIP
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48275790
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enlace troncal SIP en Lync Server 2013

 

_**Última modificación del tema:** 2012-08-13_

El Protocolo de inicio de sesión (SIP) se usa para iniciar y administrar sesiones de comunicaciones de voz sobre IP (VoIP) del servicio telefónico básico y para otros servicios de comunicación en tiempo real, como la mensajería instantánea, las conferencias, la detección de presencia y los elementos multimedia. Esta sección ofrece información sobre la planeación para implementar *troncos SIP* , un tipo de conexión SIP que se extiende más allá del límite de su red local.

## ¿Qué es el enlace troncal SIP?

Un tronco SIP es una conexión IP que establece un vínculo de comunicaciones SIP entre su organización y un proveedor de servicios de telefonía de Internet (ITSP) más allá de su firewall. En general, los troncos SIP se usan para conectar el sitio central de una organización a un ITSP. En ciertos casos, se puede usar también el enlace troncal SIP para conectar una sucursal a un ITSP.

## Troncos SIP y conexiones SIP directas

El término *tronco* deriva de la tecnología de circuitos conmutados. Se refiere a una línea física dedicada que conecta el equipo de conmutación telefónica. Como sus predecesores, los troncos de multiplexación por división de tiempo (TDM), los troncos SIP son conexiones entre dos redes SIP independientes, la de Lync Server 2013 Enterprise y el ITSP. A diferencia de los troncos de circuitos conmutados, los enlaces troncales SIP son conexiones virtuales que se pueden establecer sobre cualquiera de los tipos de conexión de enlaces troncales SIP compatibles. Para ver información detallada acerca de los tipos de conexión compatibles, vea [¿Cómo puedo implementar el enlace troncal SIP en Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Por otra parte, las conexiones SIP directas son conexiones SIP que no cruzan los límites de la red local (es decir, que se conectan a central de conmutación (PBX) o a una red telefónica conmutada (RTC) dentro de su red local). Para ver más detalles acerca de cómo usar las conexiones SIP directas con Lync Server 2013, consulte [Conexiones SIP directas en Lync Server 2013](lync-server-2013-direct-sip-connections.md).

## En esta sección

  - [Información general sobre los enlaces troncales SIP en Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [¿Cómo puedo implementar el enlace troncal SIP en Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Componentes y topologías para el enlace troncal SIP en Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Enlace troncal SIP de sitios de sucursal en Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Lista de comprobaciones para la implementación del enlace troncal SIP para Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

