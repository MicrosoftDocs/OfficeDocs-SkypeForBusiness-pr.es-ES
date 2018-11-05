---
title: 'Lync Server 2013: Control de admisión de llamadas en una red MPLS'
TOCTitle: Control de admisión de llamadas en una red MPLS
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48274406
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Control de admisión de llamadas en una red MPLS con Lync Server 2013

 

_**Última modificación del tema:** 2012-09-22_

En una red de conmutación de etiquetas multiprotocolo (MPLS), todos los sitios se conectan mediante una malla completa. Es decir, todos los sitios se conectan directamente a la red troncal del proveedor del servicio de internet MPLS, y se proporciona ancho de banda a todos los sitios para que lo usen a través de un vínculo WAN a la nube MPLS. No existe ningún concentrador de red ni ningún sitio central que controle el enrutamiento IP. En la siguiente figura se muestra una red sencilla basada en la tecnología MPLS.

**Red MPLS de ejemplo**

![Control de admisión de llamadas (CAC) con MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "Control de admisión de llamadas (CAC) con MPLS")

Para implementar el control admisión de llamadas (CAC) en una red MPLS, debe crear una región de red que represente la nube MPLS y un sitio de red que represente cada uno de los sitios satélite MPLS. En la siguiente figura se muestra cómo deberán configurarse la región de red y los sitios de red para representar la red MPLS de ejemplo de la figura anterior. Los límites de ancho de banda generales y los límites de sesión de ancho de banda se basan en la capacidad del vínculo WAN desde el sitio de red hasta la región de red que representa la nube MPLS.

**Región de red y sitios de red para una red MPLS**

![Diagrama de control de admisión de llamadas (CAC) con MPLS](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Diagrama de control de admisión de llamadas (CAC) con MPLS")

