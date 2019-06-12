---
title: 'Lync Server 2013: tareas semanales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3128780c456c3f38f306d31f258ce903eb50a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a>Tareas semanales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-08-17_

Las tareas semanales generalmente están relacionadas con la recopilación y el análisis de registros e informes.

<div>

## <a name="archive-event-logs"></a>Archivar registros de eventos

Si los registros de eventos no están configurados para sobrescribir eventos según sea necesario, se deben archivar y eliminar regularmente. Esta acción es especialmente importante para los registros de seguridad, que pueden ser necesarios al investigar intentos de violación de la seguridad.

Su organización tendrá que definir directivas y procedimientos para el archivado de registro.

</div>

<div>

## <a name="create-reports"></a>Crear informes

Crear informes de estado para ayudar con el planeamiento de la capacidad, las revisiones de SLA y el análisis de rendimiento. Use datos diarios del registro de eventos y el monitor del sistema para crear informes sobre el uso del disco, la memoria y la CPU. Use System Center Operations Manager para generar informes de disponibilidad y de tiempo.

Su organización tendrá que definir directivas y procedimientos para los informes de estado.

</div>

<div>

## <a name="incident-reports"></a>Informes de incidentes

Realice una auditoría semanal de los informes de incidentes de la organización relacionados con Lync Server. Esta auditoría debe incluir lo siguiente:

  - Los principales incidentes generados, resueltos y pendientes.

  - Soluciones para incidentes sin resolver.

  - Actualizar informes para incluir nuevos vales de problemas.

  - Actualización de un repositorio de documentos para las guías de solución de problemas y los análisis de las interrupciones.

Puesto que el sistema de seguimiento de incidentes de su organización es una elección independiente de Lync Server, hay instrucciones específicas o punteros que no están disponibles. Consulte la documentación del sistema que eligió su organización.

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>Comprobar los registros y el rendimiento de IIS

Realizar una revisión semanal de los registros y el rendimiento de servicios de información de Internet (IIS). Para obtener más información sobre cómo supervisar los registros y el rendimiento de IIS, vea [información general del registro de eventos de Windows Server 2003 servicios de Internet Information Server (IIS)](http://go.microsoft.com/fwlink/?linkid=36077). La revisión debe incluir lo siguiente:

  - Contadores de caché del servicio web para supervisar la caché del servicio WWW.

  - Contadores de páginas Active Server (ASP) para supervisar las aplicaciones que se ejecutan como ASP.

</div>

<div>

## <a name="generate-database-reports"></a>Generar informes de base de datos

**Para generar informes en la base de datos SQL**

1.  Abra Lync Server 2013.

2.  En el árbol de consola, expanda el nodo bosque, expanda **grupos empresariales**y, a continuación, haga clic en el grupo para el que desea generar un informe de base de datos.

3.  En el panel de detalles, haga clic en la pestaña **base de datos** .

4.  En la pestaña **base de datos** , haga lo siguiente:
    
    1.  Para ver el nombre de la base de datos, expanda **Configuración general**y vea el nombre de la base de datos.
    
    2.  Para recuperar las estadísticas de Resumen de usuario actuales de la agrupación, expanda **informes de Resumen de usuario**, haga clic en **ir**y vea los resultados.
    
    3.  Para recuperar los datos actuales por usuario para un único usuario del grupo, expanda **informes por usuario**, escriba el URI del SIP del usuario, haga clic en **ir**y vea los resultados.

Para recuperar las estadísticas de Resumen de conferencia actuales de la agrupación, expanda **informes de Resumen de conferencia**, haga clic en **ir**y vea los resultados.

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>Comprobar la seguridad y las actualizaciones de Lync Server

Identifique los nuevos Service Packs, revisiones o actualizaciones. Si es necesario, Pruébelos en un laboratorio de pruebas y use los procedimientos de control de cambios para organizar la implementación en los servidores de producción. Además, las actualizaciones de componentes de Lync Server ahora están disponibles como parte de Windows Update. Todas las actualizaciones de componentes de Lync Server deben actualizarse al mismo tiempo en todos los servidores que ejecuten Lync Server para los que sean aplicables las actualizaciones.

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>Ejecutar el analizador de procedimientos recomendados de Lync Server 2013

La herramienta Best Practices Analyzer de Lync Server 2013 es una herramienta de diagnóstico que recopila información de configuración y determina si la configuración se establece de acuerdo con las prácticas recomendadas de Microsoft. La documentación de esta herramienta está en el [analizador de procedimientos recomendados de Lync Server 2013](lync-server-2013-lync-server-best-practices-analyzer.md).

La herramienta compara los datos de configuración de la implementación con un conjunto de reglas predefinidas para Lync Server e informa de posibles problemas. Para cada problema notificado, la herramienta proporciona la configuración actual en el entorno de Lync Server y la configuración recomendada.

Con el acceso de red correcto, la herramienta puede examinar su AD DS y los servidores que ejecutan Lync Server 2013 para hacer lo siguiente:

  - Realizar comprobaciones de estado de forma proactiva, comprobando que la configuración se establece de acuerdo con las mejores prácticas recomendadas

  - Generar una lista de problemas, como valores de configuración subóptimos o opciones no compatibles o no recomendadas

  - Juzgar el estado general de un sistema

  - Ayudar a solucionar problemas específicos

  - Le pedirá que descargue las actualizaciones si están disponibles

  - Proporcionar documentación en línea y local sobre problemas notificados e incluir sugerencias para la solución de problemas

  - Generar información de configuración que se puede capturar para una revisión posterior

Asegúrese de que RTCBPA. msi esté instalado en todos los servidores de Lync Server 2013 y genere un informe de comprobación de Estado semanal. Anote los resultados y corríjalos, si es necesario.

</div>

<div>

## <a name="review-sla-performance-figures"></a>Revisar las cifras de rendimiento de SLA

Compruebe los datos clave de rendimiento de la semana anterior. Revise el rendimiento según los requisitos del SLA. Identifique tendencias y elementos que no hayan cumplido sus objetivos.

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>Revisar el paquete de administración de System Center Operations Manager y los informes de calidad de experiencia

Obtener y revisar el paquete de administración de Lync Server 2013 y los informes de calidad de la experiencia.

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>Generar y ver informes de base de datos para grupos de empresa

**Para generar informes de grupo**

1.  Abra Lync Server 2013.

2.  En el árbol de consola, expanda el nodo bosque, expanda **grupos empresariales**y, a continuación, haga clic en el grupo para el que desea generar un informe de base de datos.

3.  En el panel de detalles, haga clic en la pestaña **base de datos** .

4.  En la pestaña **base de datos** , haga lo siguiente:
    
    1.  Para ver el nombre de la base de datos, expanda **Configuración general**y vea el nombre de la base de datos.
    
    2.  Para recuperar las estadísticas de Resumen de usuario actuales de la agrupación, expanda **informes de Resumen de usuario**, haga clic en **ir**y vea los resultados.
    
    3.  Para recuperar los datos actuales por usuario para un único usuario del grupo, expanda **informes por usuario**, escriba el URI del SIP del usuario, haga clic en **ir**y vea los resultados.

Para recuperar las estadísticas de Resumen de conferencia actuales de la agrupación, expanda **informes de Resumen de conferencia**, haga clic en **ir**y vea los resultados.

Para cada grupo de servidores Enterprise, los administradores pueden usar la pestaña **base** de datos para ver el nombre de la base de datos y recuperar y ver informes de la base de datos.

### <a name="database-reports-and-descriptions"></a>Informes y descripciones de bases de datos

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sección</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Informes de Resumen de usuario</p></td>
<td><p>Dbanalyze/v/Report: diag [/SQLServer: value]</p>
<p>En esta sección se muestra información de agregado acerca de los usuarios de un grupo, como el número de usuarios habilitados, el número promedio de contactos por usuario y el número de usuarios para características específicas.</p>
<p>Al usar estos informes, la siguiente información puede resultar útil:</p>
<ul>
<li><p>Un usuario habilitado es un usuario que está habilitado para Lync Server 2013 mediante el complemento usuarios y equipos de Active Directory.</p></li>
<li><p>Un usuario activo es un usuario que ha iniciado sesión o está registrado.</p></li>
<li><p>Los informes de resumen también ofrecen un conjunto de información estadística sobre los contactos. Estas estadísticas solo son válidas para la población de usuarios que han iniciado sesión al menos una vez y que tienen al menos un contacto. Por lo tanto, generalmente no verás un número mínimo de contactos de 0. Debido a este comportamiento, si un usuario no tiene contactos (pero está activo, en el caso de que el usuario haya registrado), es &lt;posible&gt; que vea: vacío para algunos campos de estadísticas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Informes por usuario</p></td>
<td><p>Dbanalyze/v/Report: Disk [/SQLServer: value]</p>
<p>A diferencia de los informes de Resumen, que se calculan sobre un llenado de usuario, se trata de informes sobre un usuario específico.</p></td>
</tr>
<tr class="odd">
<td><p>Informes de Resumen de conferencia</p></td>
<td><p>Dbanalyze/v/Report: conf [/SQLServer: valor]</p>
<p>En esta sección se muestra información adicional sobre las estadísticas de Resumen de la Conferencia para el grupo, como el número de conferencias activas y el número total de participantes.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>Ejecución del analizador de uso de ancho de banda

Bandwidth Utilization Analyzer es una herramienta que genera informes sobre diferentes vistas de consumo de ancho de banda por los puntos de conexión de comunicaciones unificadas en vínculos WAN de la red empresarial. Estos informes se pueden usar para comprender el patrón de consumo de ancho de banda actual y para ayudar con la planificación de capacidad de ancho de banda. Además, también itera en la capacidad de ancho de banda asignada a diferentes vínculos.

Esta herramienta hace lo siguiente:

  - Genera informes específicos para el uso de audio a través de la red.

  - Mejora la eficacia de planificación de capacidad y la iteración en la capacidad de ancho de banda asignada a diferentes vínculos

El analizador de uso de ancho de banda puede generar trazados gráficos de capacidad de ancho de banda e informes de uso. Son los siguientes:

  - Todos los vínculos WAN en la red empresarial

  - Filtrado por los vínculos de WAN seleccionados elegidos

  - Filtrados por los vínculos WAN que han superado la capacidad de vínculos

  - Filtrado por vínculos WAN que estaban usando el ancho de banda aprovisionado

  - Filtrar por vínculos WAN que alcanzaran niveles críticos (un uso de ancho de banda superior al 90 por ciento de la capacidad de ancho de banda del vínculo WAN)

  - Filtrado por tipo de vínculo WAN: vínculos de sitios de red, vínculos interregional y vínculos dentro de un sitio

  - Filtrados por región de red

La documentación de esta herramienta está disponible en la [documentación de las herramientas del kit de recursos de Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=623245).

</div>

<div>

## <a name="see-also"></a>Vea también


[Lista de comprobación semanal de tareas](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

