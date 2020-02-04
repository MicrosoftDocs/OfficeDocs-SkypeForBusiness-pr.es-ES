---
title: 'Lync Server 2013: control de admisión de llamadas en una red MPLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ff730e64b7c7a63e277e73fa082f6d9d4e1ca3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a>Control de admisión de llamadas en una red MPLS con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

En una red de conmutación de etiquetas multiprotocolo (MPLS), todos los sitios se conectan a través de una malla completa. Es decir, todos los sitios se conectan directamente a la red troncal del proveedor de servicios de Internet MPLS y se proporciona ancho de banda a todos los sitios para que lo usen a través de un vínculo WAN a la nube MPLS. No existe ningún concentrador de red ni ningún sitio central que controle el enrutamiento IP. En la siguiente figura se muestra una red sencilla basada en la tecnología MPLS.

**Red MPLS de ejemplo**

![Control de admisión de llamadas (CAC) con MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "Control de admisión de llamadas (CAC) con MPLS")

Para implementar el servicio de control de admisión de llamadas (CAC) en una red MPLS necesitas crear una región de red que represente la nube MPLS y un sitio de red que represente cada uno de los sitios satélite MPLS. En la siguiente figura se muestra cómo tendrán que configurarse la región de red y los sitios de red para representar la red MPLS de ejemplo de la figura anterior. Los límites de ancho de banda generales y los límites de sesión de ancho de banda se basan en la capacidad del vínculo WAN desde el sitio de red hasta la región de red que representa la nube MPLS.

**Región de red y sitios de red para una red MPLS**

![Diagrama de control de admisión de llamadas (CAC) con MPLS](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Diagrama de control de admisión de llamadas (CAC) con MPLS")

</div>

<span> </span>

</div>

</div>

</div>

