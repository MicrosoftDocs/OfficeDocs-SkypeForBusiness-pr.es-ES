---
title: 'Lync Server 2013: dependencias operativas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d54ef9959f48c085ad4f5f28f182b86442ebec8c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Dependencias operativas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-05-15_

La arquitectura de referencia que se describe en este documento le ayudará a asegurarse de que tiene una implementación de Lync Server 2013 que no solo escala a los requisitos de la organización, sino que está diseñado según las prácticas recomendadas de Microsoft. Asegúrese de que la implementación de Lync Server 2013 es un servicio dinámico y, al igual que cualquier otro servicio de la empresa, aún requiere supervisión y administración proactiva para mantener un alto nivel de disponibilidad de servicio y calidad de servicio para la empresa.

Puesto que Lync Server 2013 se hace profundamente ingranulario en las empresas cotidianas de la organización, es importante que el servicio se administre mediante una administración de nivel de servicio precisa y tangible. La arquitectura del sistema de Lync puede ser compleja y muy integrada, y para mantener la administración del nivel de servicio eficaz y establecer SLAs para Lync Server 2013 es fundamental comprender las dependencias del sistema en otras plataformas y servidores. Igualmente importante es anotar qué servicios empresariales, como las aplicaciones integradas de voz y comunicaciones, se convierten en dependientes en Lync.

Lync Server 2013 debe establecerse con todas las dependencias mencionadas. El mapa de servicio le permitirá formular un SLA entre Lync y su servicio dependiente y proporcionar un lugar de inicio para la negociación de SLA.

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
<td><p>Infraestructura de red-Internet</p></td>
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


Se supone que la organización se ha consolidado en el ejercicio de las funciones básicas de administración del nivel de servicio, como la administración de cambios, incidentes y versiones, según lo prescribe el MOF. Las soluciones de Lync deben ser adoptadas por estas funciones y están sujetas a los mismos procesos de administración operativos.

Partiendo de la información obtenida anteriormente, ahora tenemos una mayor comprensión de lo que puede afectar al servicio Lync en la empresa. Para garantizar la calidad y disponibilidad del servicio de Lync Server 2013, las siguientes herramientas de supervisión deben acompañar a la implementación de arquitectura de referencia:

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
<td><p>Implemente al menos un rol de servidor de supervisión de Lync Server 2013 por sitio central y configure la calidad de la experiencia (QoE).</p>
<p>Para obtener más información, consulte la documentación de implementación de Lync Server 2013:</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Implementación de la supervisión en Lync Server 2013</a></p></td>
<td><p>Sitios centrales</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Tethering cada grupo a su instancia más cercana de la función de servidor de supervisión.</p></td>
<td><p>Sitios centrales</p>
<p>Sitios de sucursales</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012 con el módulo de administración de Microsoft Lync Server 2013 (MP) importado.</p>
<p>El módulo de administración implementa la instrumentación tradicional basada en el registro de eventos y en el contador de rendimiento, así como la habilitación de la instrumentación recién disponible en Lync Server 2013.</p></td>
<td><p>Sitios centrales</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Asegúrese de que el descubrimiento central para descubrir los roles y componentes que es necesario supervisar se completa automáticamente según un script de detección central que lee el documento de topología publicado en la base de datos de administración central.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p>
<p>Sitio perimetral</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Implemente agentes de System Center Operations Manager 2007 en todos los servidores implementados que ejecuten Lync Server.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p>
<p>Sitio perimetral</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Asegúrese de que las alertas prioritarias están configuradas para notificaciones:</p>
<p>Alertas de prioridad alta</p>
<p>Alertas de prioridad media</p>
<p>Otras alertas.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p>
<p>Sitio perimetral</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Configure la supervisión de puertos para su implementación.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p>
<p>Sitio perimetral</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Configurar la supervisión de URL para la implementación</p></td>
<td><p>Sitio central</p></td>
</tr>
<tr class="odd">
<td><p>Integración de Lync y System Center Operations Manager</p></td>
<td><p>Implementar la confiabilidad de las llamadas y la calidad de los medios MonitoringCall la fiabilidad y la supervisión de la calidad de los medios use el equipo servidor de supervisión como nodo de monitor para supervisar la confiabilidad de las llamadas y la calidad de los medios de Lync Server. Estas dos características consultan las bases de datos del servidor de supervisión para realizar análisis.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Garantizar que los umbrales de advertencia de calidad de medios se hayan configurado correctamente. En la tabla siguiente se indican los resultados de opinión medios máximos de la red por códec. En la producción, estas puntuaciones deben vigilarse durante un período establecido y los umbrales aceptables se deben establecer en función de las puntuaciones de NMOS específicas de la organización.</p></td>
<td><p>Sitio central</p>
<p>Sitio de sucursal</p></td>
</tr>
<tr class="odd">
<td><p>Monitor de transacción sintética de Lync Server 2013</p></td>
<td><p>Implementar un servidor de Lync dedicado para que sea un monitor de transacciones sintéticos.</p>
<p>Las transacciones sintéticas son cmdlets de Lync Server 2013 de Windows PowerShell que el módulo de administración desencadena automáticamente en un intervalo predefinido. Se ejecutan en un nodo de monitor de transacciones sintéticos, que es un servidor designado por el administrador responsable de detectar y ejecutar STs para cada grupo.</p>
<p>No se recomienda usar un servidor de Microsoft Lync Server 2013 existente como nodo de supervisor de transacciones sintéticos. Esto se debe a los requisitos de uso intensivo de CPU y memoria para ejecutar STs. Use un nuevo equipo servidor (o un servidor virtual) para el nodo Monitor de transacciones sintéticos.</p></td>
<td><p>Sitio central</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Implementación del nodo de monitor de transacciones sintéticas.</p>
<p>Consulte el documento MonitoringCS_withSCOM. docx de la documentación de UCTAP Connect.</p></td>
<td><p>Sitio central</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>Puntuaciones de OP de red máxima por códec

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
<td><p>UC-llamadas UC</p></td>
<td><p>RTAudio WB</p></td>
<td><p>4,10</p></td>
</tr>
<tr class="even">
<td><p>UC-llamadas UC</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Llamada de conferencia</p></td>
<td><p>Siren</p></td>
<td><p>3,72</p></td>
</tr>
<tr class="even">
<td><p>UC-llamada RTC</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>UC-llamada RTC</p></td>
<td><p>G-711</p></td>
<td><p>3,61</p></td>
</tr>
</tbody>
</table>


Antes y después de las actividades de supervisión proactivas anteriores, las tareas de mantenimiento deben ejecutarse para sitios centrales, perimetrales y de sucursales en una periodicidad diaria, semanal y mensual, según se define en la guía de operaciones de Lync RA.

</div>

<span> </span>

</div>

</div>

</div>

