---
title: Acceso a datos de supervisión en Lync Server 2013
TOCTitle: Acceso a datos de supervisión en Lync Server 2013
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49889358
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Acceso a datos de supervisión en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-05_

Los datos de supervisión se almacenan en dos bases de datos de SQL Server: LcsCdr para obtener los datos de registro de detalles y QoEMetrics para los datos de Calidad de la experiencia. No hay nada especial en estas dos bases de datos; esto significa que los datos almacenados en estas bases de datos pueden accederse con cualquiera de las herramientas que usa generalmente para acceder y analizar los datos de SQL Server.

Una herramienta que debe considerar para acceder y analizar los datos de supervisión son los Lync Serverinformes de supervisión. Los Informes de supervisión son un conjunto de informes estándar que son publicados por el servicio de informes del servidor de Microsoft SQL. Estos informes, a los que se puede acceder con un explorador web, proporcionan información de uso, diagnóstico de llamadas y calidad de medios, basada en la información del registro detallado de llamadas (CDR) y la calidad de la experiencia (QoE) almacenada en las bases de datos de CDR y QoE. Los informes de supervisión incluyen el Lync Server 2013 y pueden instalarse desde el Lync Server Asistente de implementación después de instalar Lync Server y de configurar la supervisión.

Como se observó, los Informes de supervisión requieren el uso del servicio de informes del servidor SQL. El servicio de informes del servidor SQL puede instalarse simultáneamente con el Servidor SQL o puede instalarse en cualquier momento después de haber instalado el Servidor SQL.

Para obtener más información, vea el tema [Instalación de informes de supervisión de Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) en la guía de implementación de Lync Server 2013.

