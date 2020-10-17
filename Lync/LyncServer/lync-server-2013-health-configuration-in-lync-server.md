---
title: 'Lync Server 2013: configuración de mantenimiento en Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0164a9e3003c130bc7b14a4312397a4559843c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528247"
---
# <a name="health-configuration-in-lync-server-2013"></a>Configuración de mantenimiento en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Entre los diversos sitios web, los artículos de Microsoft Knowledge base y las herramientas del kit de recursos de Lync Server, los administradores que se enfrentan a problemas al ejecutar Lync Server nunca están lejos de una forma de resolver estos problemas.

Obviamente, no hay forma de garantizar que nunca se produzcan problemas con Lync Server 2013 porque Lync Server se puede ver afectado por muchas cosas, como los bloqueos de red y los errores de hardware, que el producto en sí no puede controlar. Mediante la implementación de la supervisión de estado, los administradores pueden identificar posibles problemas antes de que se conviertan en problemas reales. Por ejemplo, los administradores pueden usar la supervisión de Lync Server para identificar tendencias y Tendencies. Por ejemplo, un aumento constante en el número de conferencias de audio y vídeo puede sugerir una necesidad de agregar capacidad antes de que el sistema se sobrecargue.

De manera similar, los administradores pueden usar System Center Operations Manager para realizar tareas como emitir alertas en tiempo real cuando se produzcan eventos específicos y ejecutar transacciones sintéticas que prueben proactivamente el sistema. Las transacciones sintéticas se usan en Lync Server para comprobar que los usuarios puedan completar correctamente tareas comunes como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono ubicado en la red telefónica conmutada (RTC). Por ejemplo, la ejecución periódica de estas pruebas puede alertarle de posibles problemas con los usuarios que inician sesión en Lync Server y le da la oportunidad de corregir el problema antes de que su equipo de soporte se inunde con llamadas de los usuarios que no pueden establecer una conexión. Mediante el uso de System Center Operations Manager para ejecutar estas transacciones sintéticas, los administradores pueden supervisar de forma rutinaria su implementación de Lync Server continuamente durante 24 horas al día, sin tener que hacer nada más allá de responder a las alertas que se puedan emitir.

<div>


> [!NOTE]  
> Para Lync Server 2013, el módulo de administración de System Center Operations Manager también puede detectar problemas "externos" que pueden afectar negativamente a Lync Server. Por ejemplo, se puede notificar a los administradores si Internet Information Services (IIS) se desconecta, los recursos del sistema en un equipo de Lync Server están por debajo de una cantidad determinada o un equipo de Lync Server experimenta un error de hardware.



</div>

La configuración de mantenimiento de Lync Server 2013 se basa en System Center Operations Manager y el uso de los paquetes de administración de Lync Server. Estos módulos de administración incluyen varias características y mejoras nuevas, como:

  - **Disponibilidad de escenario desde cualquier ubicación.** El módulo de administración de Lync Server 2010 incorporó el concepto de supervisión de disponibilidad de escenario de usuario final con transacciones sintéticas. En Lync Server 2013, estos agentes tienen más transacciones sintéticas y se pueden ejecutar desde una amplia variedad de ubicaciones dentro de la empresa, desde ubicaciones geográficas remotas fuera de la empresa, a los dispositivos de sucursales y a las implementaciones de Lync Server 2010 para agregar cobertura a las implementaciones perimetrales heredadas.

  - **Registros de transacciones sintéticas.** Cuando se producen errores en una transacción sintética, los administradores tienen acceso a los registros de HTML para determinar dónde se ha producido el error. Esto incluye comprender qué acción ha generado errores, la latencia de cada acción, la línea de comandos que se ha usado para ejecutar la prueba y el error que se ha detectado.

  - **Mayor cobertura de confiabilidad de llamadas.** El módulo de administración de Lync Server 2010 ha creado alertas de confiabilidad de llamadas para detectar problemas de conectividad graves que afectan a las llamadas de audio de los usuarios finales. Los paquetes de administración de Lync Server 2013 agregan cobertura para la mensajería instantánea de punto a punto (mi) y otras características de conferencia básicas para maximizar la cobertura mientras se reduce el ruido.

  - **Supervisión de dependencia.** Los escenarios de Lync Server pueden fallar debido a varios factores externos, como IIS sin conexión, recursos de memoria y CPU limitados, y problemas de disco. Los nuevos módulos de administración comprueban varias dependencias fundamentales para que los administradores sean conscientes de su impacto.

  - **Generación de informes mejorada.** Un conjunto de informes para ayudar a los administradores a calcular la disponibilidad de escenarios, planear la capacidad y averiguar qué componentes experimentan la mayoría de los problemas.

Los paquetes de administración también incluyen una variedad de características para ayudar a detectar y diagnosticar proporcionar visibilidad en tiempo real de la implementación de Lync Server. Estas características se enumeran en la tabla siguiente.

### <a name="management-pack-features"></a>Características del módulo de administración

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
<td><p>Cmdlets de Windows PowerShell que se pueden ejecutar desde varias ubicaciones para garantizar que los usuarios finales, como el inicio de sesión, la presencia, la mensajería instantánea y la Conferencia, estén disponibles de forma fácil para los usuarios finales.</p></td>
</tr>
<tr class="even">
<td><p>Alertas de confiabilidad de llamadas</p></td>
<td><p>Consultas de base de datos de los registros detallados de llamadas (CDR). Estos registros los escriben los servidores front-end para reflejar si los usuarios finales podían conectarse a una llamada o por qué se terminó una llamada. Estas consultas producen alertas cuando un amplio rango de usuarios finales sufre problemas de conectividad con las llamadas punto a punto o con la funcionalidad de conferencia básica.</p></td>
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

  - **Alertas de alta prioridad.** Estas alertas indican condiciones que ocasionarán interrupciones en el servicio para grandes grupos de usuarios. Por ejemplo, un error de componente en un solo equipo no es una alerta de prioridad alta porque Lync Server 2013 tiene características integradas de alta disponibilidad. Las alertas de alta prioridad indican problemas suficientemente graves "para que los administradores se levanten de noche". Las interrupciones que detectan las transacciones sintéticas y los servicios sin conexión (por ejemplo, las conferencias de audio y vídeo) se consideran alertas de alta prioridad.

  - **Alertas de prioridad media.**. Estas alertas indican condiciones que afectan a un subconjunto de usuarios o indican una disminución de la calidad de la llamada. Esto incluye problemas como errores de componentes, latencia en el establecimiento de llamadas o una disminución de la calidad de audio en las llamadas. Las alertas de esta categoría son alertas con estado e indican el estado actual del problema. Por ejemplo, supongamos que el tiempo de establecimiento de llamada supera el umbral de alerta. Si las horas de establecimiento de llamadas vuelven a su normalidad, estas alertas se resolverán automáticamente en System Center Operations Manager. Se espera que los administradores examinen estas alertas el mismo día laboral en que se producen.

  - **Otras alertas.** Son alertas de componentes que podrían afectar a un usuario o a un subconjunto de usuarios determinado. Por ejemplo, cuando el Servicio de libreta de direcciones no analiza la entrada de Active Directory de un usuario determinado. Se espera que los administradores se ocupen de estas alertas cuando tengan tiempo para ello.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configuración de Lync Server 2013 para trabajar con System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Uso del registro enriquecido para transacciones sintéticas en Lync Server 2013](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Uso de Microsoft SQL Server 2008 R2 como base de datos de System Center Operations Manager para Lync Server 2013](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

