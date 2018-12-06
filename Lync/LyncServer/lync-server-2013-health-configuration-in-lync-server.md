---
title: Configuración del estado en Lync Server 2013
TOCTitle: Configuración del estado en Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48276558
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración del estado en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Gracias a varios sitios web, los artículos de Microsoft Knowledge Base y las herramientas del kit de recursos de Lync Server, los administradores que tengan problemas durante la ejecución de Lync Server podrán solucionarlos sin dificultad.

Obviamente, no hay manera de garantizar que nunca tendrá problemas con Lync Server 2013 porque Lync Server puede resultar afectado por elementos diversos, como caídas de la red y errores de hardware que quedan fuera del control del producto. Al implementar la supervisión de estado, los administradores pueden identificar problemas posibles antes de que se conviertan en problemas reales. Por ejemplo, pueden usar la supervisión de Lync Server para identificar tendencias, como un aumento continuado del número de conferencias de audio o vídeo podría sugerir que es necesario agregar capacidad al sistema antes de que se sobrecargue.

Igualmente, los administradores pueden usar System Center Operations Manager para, por ejemplo, emitir alertas en tiempo real cuando se produzcan determinados eventos, y para ejecutar transacciones sintéticas que prueben el sistema proactivamente. Las transacciones sintéticas se usan en Lync Server para comprobar que los usuarios pueden completar correctamente tareas comunes, como el inicio de sesión en el sistema, el intercambio de mensajes instantáneos o la realización de llamadas a un teléfono ubicado en la Red telefónica conmutada (RTC). Por ejemplo, si estas pruebas se ejecutan periódicamente pueden alertarle de posibles problemas de inicio de sesión de los usuarios con Lync Server y darle la oportunidad de corregir el problema antes de que el equipo de soporte técnico se vea desbordado por las llamadas de los usuarios que no pueden establecer la conexión. Si usa System Center Operations Manager para ejecutar estas transacciones sintéticas, los administradores podrán supervisar rutinariamente la implementación de Lync Server de forma continuada durante 24 horas al día, sin necesidad de hacer mucho más además de responder a las alertas que puedan emitirse.


> [!NOTE]
> Para Lync Server 2013, el módulo de administración de System Center Operations Manager también puede detectar problemas "externos" que pueden afectar negativamente a Lync Server. Por ejemplo, los administradores pueden recibir una notificación si Servicios de Internet Information Server (IIS) se desconecta, los recursos del sistema de un equipo de Lync Server son inferiores a una cantidad determinada, o si un equipo de Lync Server experimenta un error de hardware.



La configuración de estado de Lync Server 2013 se conforma con System Center Operations Manager y el uso de los módulos de administración de Lync Server. Estos módulos de administración incluyen varias características y mejoras nuevas, como:

  - **Disponibilidad de escenario desde cualquier ubicación.** El módulo de administración de Lync Server 2010 introdujo el concepto de la supervisión de la disponibilidad de escenario del usuario final con transacciones sintéticas. En Lync Server 2013, estos agentes tienen más transacciones sintéticas y pueden ejecutarse desde varias ubicaciones en el interior de una empresa, desde ubicaciones geográficas remotas externas a la empresa, en aplicaciones de sucursales o en implementaciones de Lync Server 2010 para agregar cobertura a las implementaciones de servidores perimetrales heredadas.

  - **Registros de transacciones sintéticas.** Cuando se producen errores en una transacción sintética, los administradores tienen acceso a los registros de HTML para determinar dónde se ha producido el error. Esto incluye comprender qué acción ha generado errores, la latencia de cada acción, la línea de comandos que se ha usado para ejecutar la prueba y el error que se ha detectado.

  - **Mayor cobertura de confiabilidad de llamadas.** El módulo de administración de Lync Server 2010 introdujo la alerta de confiabilidad de llamadas para detectar los problemas de conectividad graves que afectan a las llamadas de audio de los usuarios finales. Los módulos de administración de Lync Server 2013 aumentan la cobertura para la mensajería instantánea (MI) punto a punto y para otras características de conferencia básicas, para maximizar la cobertura al tiempo que se reduce el ruido.

  - **Supervisión de dependencia.** Los escenarios de Lync Server pueden generar errores debido a diversos factores, como la desconexión de IIS, CPU y recursos de memoria limitados, y problemas de disco. Los nuevos módulos de administración comprueban varias dependencias fundamentales para que los administradores sean conscientes de su impacto.

  - **Generación de informes mejorada.** Un conjunto de informes para ayudar a los administradores a calcular la disponibilidad de escenarios, planear la capacidad y averiguar qué componentes experimentan la mayoría de los problemas.

Los módulos de administración también incluyen diversas características para proporcionar más visibilidad en tiempo real del estado de la implementación de Lync Server. Estas características se enumeran en la tabla siguiente.

### Características del módulo de administración

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Característica</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transacciones sintéticas</p></td>
<td><p>Cmdlets de Windows PowerShell que se pueden ejecutar desde diversas ubicaciones para que el usuario final pueda disponer fácilmente de escenarios como el inicio de sesión, la presencia, la MI y las conferencias.</p></td>
</tr>
<tr class="even">
<td><p>Alertas de confiabilidad de llamadas</p></td>
<td><p>Consultas de base de datos de los registros detallados de llamadas (CDR). Estos registros se generan desde Servidores front-end y muestran si los usuarios finales pudieron conectarse a una llamada o por qué se interrumpió una llamada. Estas consultas producen alertas cuando un amplio rango de usuarios finales sufre problemas de conectividad con las llamadas punto a punto o con la funcionalidad de conferencia básica.</p></td>
</tr>
<tr class="odd">
<td><p>Alertas de calidad de medios</p></td>
<td><p>Consultas de base de datos que examinan los informes de calidad de la experiencia (QoE) que publican los clientes al finalizar cada llamada. Estas consultas producen alertas que resaltan los escenarios en los que los usuarios pueden experimentar una mala calidad de los medios durante las llamadas o conferencias. Los datos se crean a partir de métricas clave, como la pérdida y latencia de paquete, que se sabe que inciden directamente en la calidad de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>Estado de los componentes</p></td>
<td><p>Los distintos componentes de servidor pueden producir alertas a través de los registros de eventos y los contadores de rendimiento. Estas alertas indican las condiciones de error que pueden incidir gravemente en uno o varios escenarios de usuario. Estas alertas también pueden indicar otras condiciones de error, como servicios que no se ejecutan, latencia de mensajes o porcentajes de errores elevados, o problemas de conectividad.</p></td>
</tr>
<tr class="odd">
<td><p>Estado de dependencia</p></td>
<td><p>Los errores pueden producirse por diferentes motivos externos. Ahora, los módulos de administración pueden supervisar y recopilar datos de algunas dependencias externas importantes que podrían indicar problemas graves, como la disponibilidad de IIS, el uso de la memoria y la CPU de los servidores y los procesos, y métricas de disco.</p></td>
</tr>
</tbody>
</table>


Las alertas que emite el sistema se han clasificado en tres categorías generales:

  - **Alertas de alta prioridad.** Estas alertas indican condiciones que ocasionarán interrupciones en el servicio para grandes grupos de usuarios. Por ejemplo, un error de componente en una sola máquina no es un alerta de alta prioridad porque Lync Server 2013 cuenta con características de alta disponibilidad integradas. Las alertas de alta prioridad indican problemas suficientemente graves "para que los administradores se levanten de noche". Las interrupciones que detectan las transacciones sintéticas y los servicios sin conexión (por ejemplo, las conferencias de audio y vídeo) se consideran alertas de alta prioridad.

  - **Alertas de prioridad media.**. Estas alertas indican condiciones que afectan a un subconjunto de usuarios o indican una disminución de la calidad de la llamada. Esto incluye problemas como errores de componentes, latencia en el establecimiento de llamadas o una disminución de la calidad de audio en las llamadas. Las alertas de esta categoría son alertas con estado e indican el estado actual del problema. Por ejemplo, supongamos que el tiempo de establecimiento de llamada supera el umbral de alerta. Cuando el tiempo de establecimiento de llamada vuelva a ser normal, estas alertas se resolverán automáticamente en System Center Operations Manager. Se espera que los administradores examinen estas alertas el mismo día laboral en que se producen.

  - **Otras alertas.** Son alertas de componentes que podrían afectar a un usuario o a un subconjunto de usuarios determinado. Por ejemplo, cuando el Servicio de libreta de direcciones no analiza la entrada de Active Directory de un usuario determinado. Se espera que los administradores se ocupen de estas alertas cuando tengan tiempo para ello.

## En esta sección

  - [Configuración de Lync Server para funcionar con el administrador de System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Uso de registro enriquecido para transacciones sintéticas](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Uso de Microsoft SQL Server 2008 R2 como base de datos de System Center Operations Manager](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

