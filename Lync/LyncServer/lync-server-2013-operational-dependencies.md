---
title: 'Lync Server 2013: dependencias operativas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2403fde7387c1ef5af7d402ad9bc859aa95fe6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Dependencias operativas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-05-15_

La arquitectura de referencia que se describe en este documento le ayudará a asegurarse de que tiene una implementación de Lync Server 2013 que no solo escala a los requisitos de la organización, sino que está diseñada según los procedimientos recomendados de Microsoft. Asegúrese de que la implementación de Lync Server 2013 es un servicio dinámico y, al igual que cualquier otro servicio de la empresa, sigue necesitando supervisión y administración proactiva para mantener un alto nivel de disponibilidad de servicio y calidad de servicio para la empresa.

Como Lync Server 2013 se convierte en profundidad en las actividades cotidianas de la organización, es importante que el servicio se administre con una administración de niveles de servicio precisa y tangible. La arquitectura del sistema Lync puede llegar a ser compleja y muy integrada y para mantener una administración eficaz del nivel de servicio y establecer SLAs para Lync Server 2013 se convierte en crítica para comprender las dependencias del sistema en otras plataformas y servidores. Igualmente importante es tener en cuenta qué servicios empresariales, como las aplicaciones integradas de voz y de comunicaciones unificadas, se convierten en independientes en Lync.

Lync Server 2013 debe establecerse teniendo en cuentan todas las dependencias mencionadas. El mapa de servicio le permitirá formular un SLA entre Lync y su servicio dependiente y proporcionar un punto de partida para la negociación del SLA.

En la siguiente tabla se enumeran los servicios de dependencia típicos para una infraestructura de Lync. Cada una de estas tecnologías debe tener su propia supervisión proactiva.

### <a name="typical-dependency-services"></a>Servicios de dependencia típicos

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Servicio de dependencia</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sistemas operativos</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Hardware de servidor</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Active Directory</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infraestructura de clave pública</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servicio de nombres de dominio</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Servicios de bases de datos</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servicios de almacenamiento</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Administración del sistema: supervisión y distribución</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servicios de seguridad: antivirus</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infraestructura de red: Internet</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Infraestructura de red: interna (LAN/WAN)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infraestructura de telefonía: IP-PBX y puertas de enlace</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servicios en la nube</p></td>
<td></td>
</tr>
</tbody>
</table>


Se supone que la organización es una tarea muy madura para ejercitar las funciones básicas de administración de nivel de servicio, como la administración de cambios, incidentes y versiones, como se indica en el MOF. La solución de Lync debe ser adoptada por estas funciones y estar sujeta a los mismos procesos de administración operativos.

A partir de la información obtenida anteriormente, ahora tenemos un conocimiento más profundo de lo que puede afectar al servicio Lync en la empresa. Para ayudar a garantizar la calidad y disponibilidad del servicio de Lync Server 2013, las siguientes herramientas de supervisión deben acompañar a la implementación de la arquitectura de referencia:

### <a name="monitoring-tools"></a>Herramientas de supervisión

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Descripción</th>
<th>Sitio aplicable</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor de supervisión de Lync Server 2013</p></td>
<td><p>Implemente al menos un rol de servidor de supervisión de Lync Server 2013 por sitio central y configure la calidad de la experiencia (QoE) Reporting Pack.</p>
<p>Consulte la documentación de implementación de Lync Server 2013 para obtener más información:</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Implementación de la supervisión en Lync Server 2013</a></p></td>
<td><p>Sitios centrales</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Tethering cada grupo a su instancia más cercana del rol del servidor de supervisión.</p></td>
<td><p>Sitios centrales</p>
<p>Sitios de sucursal</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012 con el módulo de administración de Microsoft Lync Server 2013 (MP) importado.</p>
<p>El módulo de administración que implementa la instrumentación tradicional basada en el registro de eventos y el contador de rendimiento se usa, así como la habilitación de la instrumentación reciente disponible en Lync Server 2013.</p></td>
<td><p>Sitios centrales</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Asegúrese de que la detección central para la detección de roles y componentes que deben supervisarse se completen automáticamente en función de un script de detección central que lea el documento de topología publicado en la base de datos de administración central.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p>
<p>Sitio perimetral</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Implementar agentes del centro de Operations Manager 2007 en todos los servidores implementados que ejecutan Lync Server.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p>
<p>Sitio perimetral</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Asegúrese de que las alertas con prioridad están configuradas para la notificación:</p>
<p>Alertas de prioridad alta</p>
<p>Alertas de prioridad media</p>
<p>Otras alertas.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p>
<p>Sitio perimetral</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Configure la supervisión de puertos para la implementación.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p>
<p>Sitio perimetral</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Configurar la supervisión de direcciones URL para la implementación</p></td>
<td><p>Sitio central</p></td>
</tr>
<tr class="odd">
<td><p>Integración de Lync y System Center Operations Manager</p></td>
<td><p>Implementar la confiabilidad de las llamadas y la calidad de los medios MonitoringCall la fiabilidad y la supervisión de la calidad de los medios use el equipo servidor de supervisión como nodo de monitor para supervisar la confiabilidad de las llamadas y la calidad de los medios de Lync Server. Estas dos características consultan las bases de datos del servidor de supervisión para realizar el análisis.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Garantizar que los umbrales de advertencia de calidad de medios se configuran correctamente. En la tabla siguiente se indican los resultados de opinión media de red máxima por códec. En producción, estos resultados deben supervisarse durante un período de tiempo determinado y los umbrales aceptables deben establecerse en función de los resultados de las puntuaciones NMOS específicas de la organización.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p></td>
</tr>
<tr class="odd">
<td><p>Monitor de transacción sintética de Lync Server 2013</p></td>
<td><p>Implemente un servidor de Lync dedicado para que sea un monitor de transacciones sintéticas.</p>
<p>Las transacciones sintéticas son cmdlets de Windows PowerShell de Lync Server 2013 que se desencadenan automáticamente por el módulo de administración en un intervalo predefinido. Se ejecutan en un nodo de monitor de transacciones sintéticas que es un servidor designado por el administrador responsable de la detección y la ejecución de STs para cada grupo de servidores.</p>
<p>No se recomienda usar un servidor de Microsoft Lync Server 2013 existente como nodo de monitor de transacciones sintéticas. Esto se debe a los requisitos de uso intensivo de CPU y memoria para ejecutar STs. Use un nuevo equipo servidor (o un servidor virtual) para el nodo Monitor de transacciones sintéticas.</p></td>
<td><p>Sitio central</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Implementación del nodo de monitor de transacciones sintéticas.</p>
<p>Consulte el documento MonitoringCS_withSCOM. docx de la documentación de conexión de UCTAP.</p></td>
<td><p>Sitio central</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>Puntuaciones máximas de MOS de red por códec

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Escenario</th>
<th>Códec</th>
<th>NMOS máx</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas de UC a UC</p></td>
<td><p>WB RTAudio</p></td>
<td><p>4.10</p></td>
</tr>
<tr class="even">
<td><p>Llamadas de UC a UC</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Llamada de conferencia</p></td>
<td><p>Siren</p></td>
<td><p>3,72</p></td>
</tr>
<tr class="even">
<td><p>Llamada de UC-RTC</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Llamada de UC-RTC</p></td>
<td><p>G-711</p></td>
<td><p>3,61</p></td>
</tr>
</tbody>
</table>


Más allá de las anteriores actividades de supervisión proactivas, las tareas de mantenimiento deben ejecutarse para sitios centrales, perimetrales y de sucursal en una periodicidad diaria, semanal y mensual, tal como se define en la guía de operaciones de Lync RA.

</div>

<span> </span>

</div>

</div>

</div>

