---
title: 'Lync Server 2013: tareas semanales'
TOCTitle: Tareas semanales
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn722432(v=OCS.15)
ms:contentKeyID: 62283297
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tareas semanales en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Las tareas semanales suelen estar relacionadas con la recopilación y análisis de registros e informes.

## Archivar registros de eventos

Si los registros de eventos no están configurados para sobrescribir eventos cuando sea preciso, deben archivarse y eliminarse de manera regular. Esta acción es especialmente importante en el caso de los registros de seguridad, que pueden ser necesarios para investigar posibles infracciones de seguridad.

Su organización deberá definir directivas y procedimientos para el archivado de registros.

## Crear informes

Cree informes de estado para ayudar en la planificación de la capacidad, la revisión de contratos de nivel de servicio y el análisis del rendimiento. Use datos diarios del registro de eventos y el Monitor de sistema para crear informes sobre el uso de discos, memoria y CPU. Use System Center Operations Manager para generar informes de disponibilidad y tiempo de actividad.

Su organización deberá definir directivas y procedimientos para los informes de estado.

## Informes de incidencias

Realice una auditoría semanal de los informes de incidencias de su organización relacionados con Lync Server. Esta auditoría debería incluir lo siguiente:

  - Las principales incidencias generadas, resueltas y pendientes.

  - Soluciones para incidencias sin resolver.

  - Actualización de los informes para incluir las nuevas incidencias.

  - Actualización de un repositorio de documentos para guías sobre resolución de problemas y análisis finales de interrupciones.

Como el sistema de seguimiento de incidencias empleado por su organización es una opción que no depende de Lync Server, no hay disponibles instrucciones o recomendaciones específicas. Consulte la documentación del sistema elegido por la organización.

## Comprobar los registros y el rendimiento de IIS

Realice una revisión semanal de los registros y el rendimiento de Servicios de Internet Information Server (IIS). Para obtener más información sobre cómo supervisar los registros y el rendimiento de ISS, vea [Windows Server 2003 Internet Information Services (IIS): visión general del registro de eventos](http://go.microsoft.com/fwlink/?linkid=36077). La revisión debería incluir lo siguiente:

  - Contadores de caché del servicio Web para supervisar la caché del servicio WWW.

  - Contadores de páginas Active Server (ASP) para supervisar las aplicaciones que se ejecutan como ASP.

Para obtener más información sobre cómo supervisar los registros y el rendimiento de IIS, vea [Windows Server 2003 Internet Information Services (IIS): visión general del registro de eventos](http://go.microsoft.com/fwlink/?linkid=36077).

## Generar informes de base de datos

**Para generar informes de la base de datos SQL**

1.  Abra Lync Server 2013.

2.  En el árbol de consola, expanda el nodo del bosque, expanda **Grupos de servidores Enterprise** y haga clic en el grupo para el que quiere generar un informe de base de datos.

3.  En el panel de detalles, haga clic en la pestaña **Base de datos**.

4.  En la pestaña **Base de datos**, haga lo siguiente:
    
    1.  Para ver el nombre de la base de datos, expanda **Configuración general**, donde se muestra el nombre.
    
    2.  Para recuperar estadísticas actuales de resumen de usuario para el grupo, expanda **Informes de resumen de usuario**, haga clic en **Ir** y vea los resultados.
    
    3.  Para recuperar datos por usuario actuales para un solo usuario del grupo, expanda **Informes por usuario**, escriba el URI del SIP del usuario, haga clic en **Ir** y vea los resultados.

Para recuperar estadísticas actuales de resumen de conferencia del grupo, expanda **Informes de resumen de conferencia**, haga clic en **Ir** y vea los resultados.

## Comprobar si hay actualizaciones de seguridad y Lync Server

Identifique cualquier nuevo Service Pack, revisión o actualización. Si procede, pruébelos en un laboratorio de prueba y use los procedimientos de control de cambios para disponer la implementación en los servidores de producción. Además, Windows Update incluye ahora las actualizaciones de los componentes de Lync Server. Todas las actualizaciones de componentes de Lync Server deben realizarse al mismo tiempo en todos los servidores que ejecutan Lync Server y en los que las actualizaciones son aplicables.

## Ejecutar el Analizador de procedimientos recomendados de Lync Server 2013

El Analizador de procedimientos recomendados de Lync Server 2013 es una herramienta de diagnóstico que recopila información de configuración y determina si esta cumple los procedimientos recomendados por Microsoft. Puede encontrar la documentación para esta herramienta en [Analizador de procedimientos recomendados de Lync Server 2013](lync-server-2013-lync-server-best-practices-analyzer.md) y [Ejecutar el Analizador de procedimientos recomendados](https://technet.microsoft.com/es-es/library/gg398652\(v=ocs.15\)).

La herramienta compara sus datos de configuración de implementación con un conjunto de reglas predefinidas para Lync Server e informa de posible problemas. Por cada problema, la herramienta proporciona la configuración actual en el entorno de Lync Server y la configuración recomendada.

Si dispone del acceso de red adecuado, la herramienta puede examinar el AD DS y los servidores que ejecutan Lync Server 2013 para hacer lo siguiente:

  - Realizar comprobaciones de estado proactivas para verificar que la configuración cumpla las prácticas recomendadas

  - Generar una lista de problemas, como configuraciones poco apropiadas u opciones no admitidas o no recomendadas

  - Valorar el estado general de un sistema

  - Ayudar a resolver problemas específicos

  - Indicarle que descargue actualizaciones disponibles

  - Proporcionar documentación en línea o local sobre los problemas detectados e incluir sugerencias de resolución

  - Generar información de configuración que puede guardarse para su posterior revisión

Asegúrese de que RTCBPA.msi esté instalado en todos los servidores de Lync Server 2013 y genere semanalmente un informe de comprobación de estado. Consulte los resultados y corrija lo que sea necesario.

## Revisar las cifras de contrato de nivel de servicio

Compruebe los datos de rendimiento clave de la semana anterior. Compare el rendimiento con los requisitos del contrato de nivel de servicio. Identifique cualquier tendencia y aquellos elementos que no cumplen sus objetivos.

## Revisar los informes Módulo de administración y Calidad de la experiencia de System Center Operations Manager

Obtenga y revise los informes Módulo de administración y Calidad de la experiencia de Lync Server 2013.

## Generar y ver informes de base de datos para grupos de servidores Enterprise

**Para generar informes de grupos**

1.  Abra Lync Server 2013.

2.  En el árbol de la consola, expanda el nodo del bosque, expanda **Grupos de servidores Enterprise** y después haga clic en el grupo para el que quiere generar un informe de base de datos.

3.  En el panel de detalles, haga clic en la pestaña **Base de datos**.

4.  En la pestaña **Base de datos**, haga lo siguiente:
    
    1.  Para ver el nombre de la base de datos, expanda **Configuración general**, donde se muestra el nombre.
    
    2.  Para recuperar estadísticas actuales de resumen de usuario para el grupo, expanda **Informes de resumen de usuario**, haga clic en **Ir** y vea los resultados.
    
    3.  Para recuperar datos por usuario actuales para un solo usuario del grupo, expanda **Informes por usuario**, escriba el URI del SIP del usuario, haga clic en **Ir** y vea los resultados.

Para recuperar estadísticas actuales de resumen de conferencia del grupo, expanda **Informes de resumen de conferencia**, haga clic en **Ir** y vea los resultados.

Los administradores pueden usar la pestaña **Base de datos** en cada grupo de servidores Enterprise para ver el nombre de la base de datos y obtener y ver informes relativos a la misma.

### Informes y descripciones de bases datos

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
<td><p>Informes de resumen de usuario</p></td>
<td><p>Dbanalyze /v /report:diag [/sqlserver:value]</p>
<p>Esta sección muestra información agregada sobre los usuarios de un grupo, como el número de usuarios habilitados, el número medio de contactos por cada uno y el número de usuarios de características específicas.</p>
<p>Al usar estos informes, la siguiente información puede resultar útil:</p>
<ul>
<li><p>Un usuario habilitado es aquel habilitado en Lync Server 2013 mediante el complemento Usuarios y equipos de Active Directory.</p></li>
<li><p>Un usuario activo es aquel que tiene sesión iniciada o está registrado.</p></li>
<li><p>Los informes de resumen también ofrecen información estadística sobre los contactos. Estas estadísticas solo son válidas para la población de usuarios que ha iniciado sesión al menos una vez y que tiene al menos un contacto. Por tanto, no verá 0 como número mínimo de contactos. Debido a esto, si un usuario carece de contactos (pero está activo por estar registrado), podría ver &lt;vacío&gt; en algunos campos.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Informes por usuario</p></td>
<td><p>Dbanalyze /v /report:disk [/sqlserver:value]</p>
<p>Al contrario que los informes de resumen, que se calculan para una población de usuarios, estos hacen referencia a usuarios específicos.</p></td>
</tr>
<tr class="odd">
<td><p>Informes de resumen de conferencia</p></td>
<td><p>Dbanalyze /v /report:conf [/sqlserver:value]</p>
<p>Esta sección muestra información agregada sobre las estadísticas de resumen de conferencia del grupo, como el número de conferencias activas o el total de participantes.</p></td>
</tr>
<tr class="even">
<td><p>Informes de resumen de usuario</p></td>
<td><p>Dbanalyze /v /report:diag [/sqlserver:value]</p>
<p>Esta sección muestra información agregada sobre los usuarios de un grupo, como el número de usuarios habilitados, el número medio de contactos por cada uno y el número de usuarios de características específicas.</p>
<p>Al usar estos informes, la siguiente información puede resultar útil:</p>
<ul>
<li><p>Un usuario habilitado es aquel habilitado en Lync Server 2013 mediante el complemento Usuarios y equipos de Active Directory.</p></li>
<li><p>Un usuario activo es aquel que tiene sesión iniciada o está registrado.</p></li>
<li><p>Los informes de resumen también ofrecen información estadística sobre los contactos. Estas estadísticas solo son válidas para la población de usuarios que ha iniciado sesión al menos una vez y que tiene al menos un contacto. Por tanto, no verá 0 como número mínimo de contactos. Debido a esto, si un usuario carece de contactos (pero está activo por estar registrado), podría ver &lt;vacío&gt; en algunos campos.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Informes por usuario</p></td>
<td><p>Dbanalyze /v /report:disk [/sqlserver:value]</p>
<p>Al contrario que los informes de resumen, que se calculan para una población de usuarios, estos hacen referencia a usuarios específicos.</p></td>
</tr>
<tr class="even">
<td><p>Informes de resumen de conferencia</p></td>
<td><p>Dbanalyze /v /report:conf [/sqlserver:value]</p>
<p>Esta sección muestra información agregada sobre las estadísticas de resumen de conferencia del grupo, como el número de conferencias activas o el total de participantes.</p></td>
</tr>
</tbody>
</table>


## Ejecutar el Analizador de uso de ancho de banda

El Analizador de uso de ancho de banda es una herramienta que genera informes sobre diferentes vistas de consumo de ancho de banda por parte de los extremos de comunicaciones unificadas en vínculos WAN de la red empresarial. Estos informes pueden usarse para entender mejor el patrón actual de consumo de ancho de banda y para ayudar en la planificación de su capacidad. También itera en la capacidad de ancho de banda asignada a diferentes vínculos.

Esta herramienta hace lo siguiente:

  - Genera informes específicos sobre el uso de audio en la red

  - Mejora la eficacia de planificación de capacidad y la iteración en la capacidad de ancho de banda asignada a diferentes vínculos

El Analizador de uso de ancho de banda puede generar gráficas a partir de informes de uso y capacidad de ancho de banda. Son las siguientes:

  - Todos los vínculos WAN en la red empresarial

  - Filtrados por vínculos WAN elegidos

  - Filtrados por los vínculos WAN que han superado la capacidad de vínculos

  - Filtrados por los vínculos WAN que infrautilizaban el ancho de banda aprovisionado

  - Filtrados por vínculos WAN que estaban alcanzando niveles críticos (un uso de ancho de banda mayor del 90 % de la capacidad del vínculo WAN)

  - Filtrados por el tipo de vínculo WAN: vínculos de sitio de red, vínculos entre regiones y vínculos dentro de un sitio

  - Filtrados por región de red

La documentación para esta herramienta está disponible en [Documentación de las herramientas del kit de recursos de Lync Server 2013](https://technet.microsoft.com/es-es/library/jj945604\(v=ocs.15\)).

## Vea también

#### Otros recursos

[Lista de comprobación de tareas semanales](lync-server-2013-operations-checklists.md)

