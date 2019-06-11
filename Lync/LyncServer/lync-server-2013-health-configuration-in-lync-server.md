---
title: 'Lync Server 2013: configuración de estado en Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a719a5e8695dbbd0705aa649d72a32a2bfdc7d38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Configuración de mantenimiento de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Entre los distintos sitios web, los artículos de Microsoft Knowledge base y las herramientas del kit de recursos de Lync Server, los administradores que encuentren problemas al ejecutar Lync Server nunca están lejos de una forma de resolver esos problemas.

Obviamente, no hay ninguna manera de garantizar que nunca se produzcan problemas con Lync Server 2013 porque Lync Server puede verse afectado por muchos factores, como el bloqueo de red y los errores de hardware, que el producto no puede controlar. Al implementar la supervisión de estado, los administradores pueden identificar posibles problemas antes de que se conviertan en problemas reales. Por ejemplo, los administradores pueden usar la supervisión de Lync Server para identificar tendencias y tendencias. Por ejemplo, es posible que un aumento sostenido de la cantidad de conferencias de audio y vídeo sugiera una necesidad de añadir capacidad antes de que el sistema se sobrecargue.

De forma similar, los administradores pueden usar System Center Operations Manager para realizar tareas como emitir alertas en tiempo real cuando se produzcan eventos específicos y ejecutar transacciones sintéticas que prueben proactivamente el sistema. Las transacciones sintéticas se usan en Lync Server para comprobar que los usuarios pueden completar correctamente tareas comunes como iniciar sesión en el sistema, intercambiar mensajes instantáneos o hacer llamadas a un teléfono que se encuentra en la red de telefonía pública conmutada (RTC). Por ejemplo, la ejecución periódica de estas pruebas puede alertarle de posibles problemas con los usuarios que inicien sesión en Lync Server y le dará la oportunidad de corregir el problema antes de que su equipo de soporte se desborde con llamadas de los usuarios que no pueden establecer una conexión. Al usar System Center Operations Manager para ejecutar estas transacciones sintéticas, los administradores pueden supervisar de forma rutinaria su implementación de Lync Server continuamente durante 24 horas al día, sin tener que hacer mucho más allá de responder a las alertas que podrían se va a emitir.

<div>


> [!NOTE]  
> Para Lync Server 2013, el módulo de administración de System Center Operations Manager también puede detectar problemas "externos" que pueden afectar negativamente a Lync Server. Por ejemplo, se puede notificar a los administradores si los servicios de información de Internet (IIS) se desconectan, los recursos del sistema en un equipo de Lync Server caen por debajo de una cantidad determinada o un equipo de Lync Server experimenta un error de hardware.



</div>

La configuración de mantenimiento de Lync Server 2013 se basa en System Center Operations Manager y en el uso de los paquetes de administración de Lync Server. Estos paquetes de administración incluyen varias características y mejoras nuevas, entre las que se incluyen:

  - **Disponibilidad de escenario desde cualquier ubicación.** El paquete de administración de Lync Server 2010 presentó el concepto de supervisión de la disponibilidad del escenario del usuario final con transacciones sintéticas. En Lync Server 2013, estos agentes tienen más transacciones sintéticas y se pueden ejecutar desde una amplia variedad de ubicaciones dentro de la empresa, desde ubicaciones geográficas remotas fuera de la empresa, contra dispositivos de sucursales y con Lync Server 2010 implementaciones para agregar cobertura a implementaciones de borde heredado.

  - **Registros de transacciones sintéticos.** Cuando se produce un error en una transacción sintética, los administradores tienen acceso a los registros HTML para determinar qué ha fallado. Esto incluye comprender qué acción ha fallado, la latencia de cada acción, la línea de comandos que se usa para ejecutar la prueba y el error encontrado.

  - **Mayor cobertura de la confiabilidad de las llamadas.** El paquete de administración de Lync Server 2010 introdujo alertas de confiabilidad para detectar problemas de conectividad graves que afectan a las llamadas de audio de los usuarios finales. Los módulos de administración de Lync Server 2013 agregan cobertura para la mensajería instantánea de punto a punto (mi) y otras características de conferencia básicas para maximizar la cobertura y reducir el ruido.

  - **Supervisión de dependencias.** Los escenarios de Lync Server pueden fallar debido a una variedad de factores externos como IIS desconectado, recursos de memoria y CPU limitados, y problemas de disco. Los nuevos paquetes de administración comprueban varias dependencias críticas para garantizar que los administradores sean conscientes de su impacto.

  - **Informes mejorados.** Un conjunto de informes para ayudar a los administradores a calcular la disponibilidad de escenarios, planear la capacidad y ver qué componentes experimentan la mayoría de los problemas.

Los paquetes de administración también incluyen una variedad de características para ayudar a detectar y diagnosticar proporcionar visibilidad en tiempo real del estado de la implementación de Lync Server. Estas características se muestran en la tabla siguiente.

### <a name="management-pack-features"></a>Características del paquete de administración

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
<td><p>Cmdlets de Windows PowerShell que se pueden ejecutar desde varias ubicaciones para garantizar que los usuarios finales, como el inicio de sesión, la presencia, la mensajería instantánea y las conferencias, estén disponibles para los usuarios finales.</p></td>
</tr>
<tr class="even">
<td><p>Alertas de confiabilidad de llamadas</p></td>
<td><p>Consultas de base de datos para registros de detalles de llamadas (CDR). Estos registros los escriben los servidores front-end para reflejar si los usuarios finales podían conectarse a una llamada o por qué se terminó una llamada. Estas consultas tienen como resultado alertas que indican si una amplia variedad de usuarios finales experimentan problemas de conectividad para las llamadas de par a par o para la funcionalidad de conferencia básica.</p></td>
</tr>
<tr class="odd">
<td><p>Alertas de calidad multimedia</p></td>
<td><p>Consultas de base de datos que tienen los informes de calidad de la experiencia (QoE) publicados por los clientes al final de cada llamada. Estas consultas generan alertas que indican escenarios en los que es probable que los usuarios experimenten una calidad de medios deficiente durante las llamadas y conferencias. Los datos se basan en métricas clave como la latencia y pérdida de paquetes, métricas que se sabe que contribuyen directamente a la calidad de las llamadas.</p></td>
</tr>
<tr class="even">
<td><p>Estado del componente</p></td>
<td><p>Los componentes de servidor individuales generan alertas mediante registros de eventos y contadores de rendimiento. Estas alertas indican condiciones de error que pueden afectar gravemente a uno o más escenarios de usuario final. Estas alertas también pueden indicar diversas condiciones de error, como servicios que no se ejecutan, tarifas elevadas de errores, latencia de mensajes de alta latencia o problemas de conectividad.</p></td>
</tr>
<tr class="odd">
<td><p>Estado de dependencia</p></td>
<td><p>Pueden producirse errores por una variedad de razones externas. Los paquetes de administración ahora supervisan y recopilan datos para algunas de las dependencias externas críticas que pueden indicar problemas graves, como la disponibilidad de IIS, el uso de CPU y de memoria de servidores y procesos, y las métricas de disco.</p></td>
</tr>
</tbody>
</table>


Las alertas emitidas por el sistema se han clasificado en tres categorías generales:

  - **Alertas de alta prioridad.** Estas alertas indican condiciones que provocarán interrupciones de servicio para grupos grandes de usuarios. Por ejemplo, un error de un componente en un solo equipo no es una alerta de alta prioridad porque Lync Server 2013 tiene características de alta disponibilidad integradas. En su lugar, las alertas de alta prioridad representan problemas lo suficientemente graves como para reactivar a los administradores durante la noche. Las interrupciones detectadas por transacciones sintéticas y servicios sin conexión (por ejemplo, audioconferencias/videoconferencias) se califican como alertas de alta prioridad.

  - **Alertas de prioridad media.**. Estas alertas indican condiciones que afectan a un subconjunto de usuarios o indican una degradación de la calidad de las llamadas. Esto incluye problemas como errores de componentes, latencia en el establecimiento de la llamada o disminución de la calidad de audio en la llamada. Las alertas de esta categoría están con estado e indican el estado actual del problema. Por ejemplo, supongamos que los tiempos de establecimiento de llamadas superan el umbral de alerta. Si los tiempos de establecimiento de la llamada vuelven a normal, estas alertas se resolverán automáticamente en System Center Operations Manager. La expectativa de estas alertas es que un administrador las verá en el mismo día laborable.

  - **Otras alertas.** Son alertas de componentes que pueden afectar a un usuario específico o a un subconjunto de usuarios. Por ejemplo, es posible que el servicio de libreta de direcciones no pueda analizar la entrada de Active Directory de un usuario dado. La expectativa de estas alertas es que los administradores las recibirán cuando tengan tiempo disponible.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configuración de Lync Server 2013 para que funcione con System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Usar el registro avanzado para transacciones sintéticas en Lync Server 2013](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Uso de Microsoft SQL Server 2008 R2 como base de datos de System Center Operations Manager para Lync Server 2013](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

