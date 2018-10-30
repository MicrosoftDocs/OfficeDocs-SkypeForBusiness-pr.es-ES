---
title: 'Lync Server 2013: Componentes y topologías para la supervisión'
TOCTitle: Componentes y topologías para la supervisión
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48276569
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes y topologías para la supervisión en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-05_

Dado que los agentes de recopilación de datos unificados se instalan y activan automáticamente en cada servidor front-end, no es necesario configurar un servidor para que actúe como Servidor de supervisión: cada servidor front-end funciona de hecho como Servidor de supervisión. No obstante, deberá instalar y configurar una base de datos para que actúe como almacén de datos back-end para los datos de supervisión. Microsoft Lync Server 2013 puede usar cualquiera de las bases de datos siguientes como almacén back-end para la supervisión:

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Tenga en cuenta que debe usar las ediciones de 64 bits de estas bases de datos y que las versiones de 32 bits de SQL Server no se pueden usar como almacén back-end para la supervisión. Asimismo, Lync Server 2013 no admite las versiones Express Edition de SQL Server 2008 ni de SQL Server 2012. Para más información sobre los requisitos de base de datos para Lync Server 2013, consulte el tema [Compatibilidad con software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md) en la guía de compatibilidad de Lync Server 2013.

Recuerde que SQL Server debe estar instalado y configurado antes de implementar y configurar la supervisión. No obstante, solo tiene que implementar el propio SQL Server, no tiene que instalar las bases de datos de supervisión por adelantado. Estas bases de datos se crearán automáticamente cuando publique la topología de Lync Server.

Al supervisar los datos se puede compartir una instancia de SQL Server con otros tipos de datos. Generalmente, las bases de datos de registro detallado de llamadas (LcsCdr) y de calidad de experiencia (QoEMetrics) comparten la misma instancia de SQL. También es habitual que las dos bases de datos de supervisión se encuentren en la misma instancia de SQL que la base de datos de archivado (LcsLog). El único requisito real con relación a las instancias de SQL Server es que cada una de ellas se limite conforme a lo siguiente:

  - Una instancia de la base de datos back-end de Lync Server 2013. Como norma general, no es aconsejable que la base de datos de supervisión se encuentre en la misma instancia de SQL ni siquiera en el mismo equipo, que la base de datos back-end. Aunque técnicamente es posible, corre el riesgo de que la base de datos de supervisión agote el espacio en disco que necesita la base de datos back-end.

  - Una instancia de la base de datos de registro detallado de llamadas.

  - Una instancia de la base de datos de calidad de experiencia.

  - Una instancia de la base de datos de archivado.

En otras palabras, no puede tener dos instancias de la base de datos LcsCdr en la misma instancia de SQL Server. Si necesita varias instancias de la base de datos LcsCdr, deberá configurar varias instancias de SQL Server.

## Vea también

#### Otros recursos

[Implementación de supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md)

