---
title: 'Lync Server 2013: componentes y topologías para la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d93920040ff18d623748b375849f5639a831772a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Componentes y topologías para la supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

Como los agentes unificados de recopilación de datos se instalan y activan automáticamente en cada servidor front-end, no es necesario configurar un servidor para que actúe como servidor de supervisión; cada servidor front-end ya funciona como un servidor de supervisión. Sin embargo, tendrá que instalar y configurar una base de datos para que actúe como almacén de datos back-end para los datos de supervisión. Microsoft Lync Server 2013 puede usar cualquiera de las siguientes bases de datos como almacén back-end para la supervisión:

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Tenga en cuenta que debe usar las ediciones de 64 bits de estas bases de datos; las versiones de 32 bits de SQL Server no se pueden usar como almacén back-end para la supervisión. De forma similar, Lync Server 2013 no es compatible con las ediciones Express de SQL Server 2008 o SQL Server 2012. Para obtener más información sobre los requisitos de bases de datos para Lync Server 2013, vea el tema [compatibilidad de software de base de datos en Lync server 2013](lync-server-2013-database-software-support.md) en la guía de compatibilidad de lync Server 2013.

Tenga en cuenta que SQL Server debe estar instalado y configurado antes de implementar y configurar la supervisión. Sin embargo, solo tiene que implementar el propio SQL Server; no es necesario que configure las bases de datos de supervisión con antelación. En su lugar, las bases de datos se crearán automáticamente cuando publique la topología de Lync Server.

Los datos de supervisión pueden compartir una instancia de SQL Server con otros tipos de datos. Normalmente, la base de datos de registro detallado de llamadas (LcsCdr) y la base de datos de calidad de la experiencia (QoEMetrics) comparten la misma instancia de SQL; también es común para las dos bases de datos de supervisión estar en la misma instancia de SQL que la base de datos de archivado (LcsLog). Sobre el único requisito real de las instancias de SQL Server es que cualquier instancia de SQL Server se limita a lo siguiente:

  - Una instancia de la base de datos back-end 2013 de Lync Server. (Como regla general, no se recomienda que la base de datos de supervisión se colocará en la misma instancia de SQL, o incluso en el mismo equipo, que la base de datos back-end. Si bien técnicamente es posible, se corre el riesgo de que la base de datos de supervisión use espacio en disco necesario para la base de datos back-end.

  - Una instancia de la base de datos de registro detallado de llamadas.

  - Una instancia de la base de datos de calidad de la experiencia.

  - Una instancia de la base de datos de archivado.

En otras palabras, no puede tener dos instancias de la base de datos de LcsCdr en la misma instancia de SQL Server. Si necesita varias instancias de la base de datos LcsCdr, tendrá que configurar varias instancias de SQL Server.

<div>

## <a name="see-also"></a>Vea también


[Implementación de la supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

