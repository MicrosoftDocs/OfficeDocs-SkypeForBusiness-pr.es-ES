---
title: 'Lync Server 2013: Componentes y topologías para la supervisión'
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
ms.openlocfilehash: 76e857d0c80793f61b8e60686cc9455d27bb9f95
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Componentes y topologías para la supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

Debido a que los agentes de recopilación de datos unificados se instalan y activan automáticamente en cada servidor front-end, no es necesario configurar un servidor para que actúe como servidor de supervisión; cada servidor front-end funciona como servidor de supervisión. Sin embargo, necesitará instalar y configurar una base de datos para que actúe como almacén de datos del back-end para los datos de supervisión. Microsoft Lync Server 2013 puede usar cualquiera de las siguientes bases de datos como almacén back-end para la supervisión:

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Tenga en cuenta que debe usar las ediciones de 64 bits de estas bases de datos; las versiones de 32 bits de SQL Server no se pueden usar como almacén de back-end para la supervisión. Del mismo modo, Lync Server 2013 no es compatible con las ediciones Express de SQL Server 2008 o SQL Server 2012. Para obtener más información sobre los requisitos de base de datos de Lync Server 2013 consulte el tema [compatibilidad de software de base de datos en Lync server 2013](lync-server-2013-database-software-support.md) en la guía de compatibilidad de lync Server 2013.

Recuerde que es preciso que SQL Server esté instalado y configurado antes de implementar y configurar la supervisión. Sin embargo, solo necesita implementar SQL Server en sí; no es necesario configurar las bases de datos de supervisión con antelación. En su lugar, estas bases de datos se crearán automáticamente cuando publique la topología de Lync Server.

Al supervisar los datos se puede compartir una instancia de SQL Server con otros tipos de datos. Generalmente, las bases de datos del registro detallado de llamadas (LcsCdr) y de la calidad de la experiencia (QoEMetrics) comparten la misma instancia de SQL. También es habitual que las dos bases de datos de supervisión se encuentren en la misma instancia de SQL que la base de datos de archivado (LcsLog). El único requisito real con relación a las instancias de SQL Server es que cada una de ellas se limite conforme a lo siguiente:

  - Una instancia de la base de datos back-end de Lync Server 2013. Como norma general, no recomendamos que la base de datos de supervisión se encuentre en la misma instancia de SQL, ni siquiera en el mismo equipo, que la base de datos back-end. Aunque técnicamente es posible, corre el riesgo de que la base de datos de supervisión agote el espacio en disco que necesita la base de datos back-end.

  - Una instancia de la base de datos del registro detallado de llamadas.

  - Una instancia de la base de datos de la calidad de la experiencia.

  - Una instancia de la base de datos de archivado.

En otras palabras, no puede tener dos instancias de la base de datos LcsCdr en la misma instancia de SQL Server. Si necesita varias instancias de la base de datos LcsCdr, tendrá que configurar varias instancias de SQL Server.

<div>

## <a name="see-also"></a>Vea también


[Implementación de la supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

