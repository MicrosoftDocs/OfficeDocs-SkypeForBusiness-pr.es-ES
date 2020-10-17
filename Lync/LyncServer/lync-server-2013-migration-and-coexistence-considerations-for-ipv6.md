---
title: 'Lync Server 2013: consideraciones sobre la coexistencia y la migración para IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f091b12b12913af107991c86b87d1d738bf88bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513617"
---
# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Consideraciones sobre la coexistencia y la migración para IPv6 en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-14_

La versión 6 de IP (IPv6) no es compatible con Lync Server 2010 u Office Communications Server. Por motivos de prueba piloto, puede probar Lync Server 2010 y la coexistencia de pila dual de Lync Server 2013. Se recomienda que todos los grupos de servidores de un sitio central determinado se actualicen a Lync Server 2013 antes de habilitar IPv6 (red de doble pila) para cualquiera de los grupos. Si necesita configurar un grupo solo para IPv6, se recomienda configurar un grupo de servidores solo IPv6 en su entorno de prueba.

Se admiten los siguientes escenarios durante la migración y coexistencia:

  - Lync Server 2013, Lync Server 2010 y grupos de servidores de Office Communications Server 2007 R2 en modo IPv4, coexistencia con Lync Server 2013 en modo de pila dual.

  - Grupo de servidores de Lync Server 2013 en modo de solo IPv6, si el grupo de solo IPv6 está en silos.

</div>

<span> </span>

</div>

</div>

</div>

