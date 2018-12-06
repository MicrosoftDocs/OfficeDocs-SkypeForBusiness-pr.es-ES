---
title: "Grupo de director escalado: Equilibrio de carga DNS y equilibrs. carga de hardware"
TOCTitle: Grupo de director escalado - Equilibrio de carga DNS y equilibradores de carga de hardware
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48276249
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grupo de director escalado - Equilibrio de carga DNS y equilibradores de carga de hardware en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-22_

Un Grupo de directores escalado, en el cual hay más de un Director implementado para manejar capacidad adicional y brindar mayor disponibilidad, requiere un equilibrio de carga para distribuir la comunicación entre el cliente y el servidor hacia todos los miembros del grupo. Un Director aloja servicios web con las mismas características que un Grupo de servidores front-end. Para proporcionar el equilibrio de carga, puede usar el equilibrio de carga de hardware o equilibrio de carga del sistema de nombres de dominio (DNS) y equilibrio de carga de hardware. El equilibrio de carga de hardware se requiere para los servicios web y el equilibrio de carga de DNS independiente no proporciona las capacidades requeridas para los servicios web.

En los siguientes temas se describen las condiciones de planificación para la implementación de un Grupo de directores mediante un equilibrio de carga de DNS junto con el equilibrio de carga de hardware. Si planea usar el equilibrio de carga de hardware, pero no planea usar el equilibrio de carga de DNS para el Grupo de directores, consulte el tema [Grupo de servidores de director escalado - Equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) que describe los requisitos de planificación para esa topología.

![Grupo de director escalado](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Grupo de director escalado")

## En esta sección

  - [Resumen de certificado - Carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Resumen de puerto - Carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Resumen de DNS - Carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

