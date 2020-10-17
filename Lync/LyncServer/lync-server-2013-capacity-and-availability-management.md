---
title: 'Lync Server 2013: administración de la capacidad y la disponibilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efef66bcac833bb67c67dc453c25f3e0f6d51ba1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512857"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Administración de la capacidad y la disponibilidad en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-18_

El propósito de la administración de la capacidad y la administración de la disponibilidad es medir y controlar el rendimiento del sistema. Le recomendamos que implemente procedimientos de administración de la capacidad y la disponibilidad para que pueda medir y controlar el rendimiento del sistema. Tiene que saber si el sistema está disponible y si puede controlar las demandas actuales y previstas estableciendo líneas de base y supervisando el sistema para buscar tendencias.

<div>

## <a name="capacity-management"></a>Administración de la capacidad

La administración de la capacidad implica la planeación, el ajuste de tamaño y el control de la capacidad del servicio para ayudar a garantizar que se superen los niveles de rendimiento mínimos especificados en el SLA. Una buena administración de la capacidad contribuye a garantizar que puede proporcionar servicios de ti a un coste razonable y seguir cumpliendo los niveles de rendimiento definidos en los SLAs con el cliente. Estos criterios pueden incluir lo siguiente:

  - Tiempo de respuesta **del sistema**     Se trata del tiempo medido que el sistema lleva a cabo acciones típicas. Algunos ejemplos son el tiempo necesario para que el rol de servidor de audio y vídeo procese el tráfico de audio y vídeo, el tiempo necesario para que un cliente cree y se una a una conferencia, o el tiempo que se tarda en actualizar la presencia en todos los clientes de monitor.

  - **Capacidad**     de almacenamiento Esta es la capacidad de un sistema de almacenamiento, ya sea una base de datos de contenido, un dispositivo de copia de seguridad o una unidad local. Algunos ejemplos son la cantidad máxima de espacio de almacenamiento que se debe proporcionar por sitio y el tiempo que se almacenan las copias de seguridad antes de que se sobrescriban.

El ajuste de la capacidad suele ser un caso para asegurarse de que haya suficientes recursos físicos disponibles, como espacio en disco y ancho de banda de la red. En la siguiente tabla se enumeran las soluciones típicas para problemas relacionados con la capacidad.

### <a name="typical-resolutions-for-capacity-related-issues"></a>Soluciones típicas para problemas relacionados con la capacidad

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Problema</th>
<th>Posible resolución</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuarios remotos con un rendimiento deficiente de audio y vídeo</p></td>
<td><p>Compruebe si el ancho de banda adecuado está disponible en los vínculos WAN y si QoS está habilitado y configurado correctamente. Compruebe los datos de QoE.</p></td>
</tr>
<tr class="even">
<td><p>La respuesta general del entorno de Lync es lenta.</p></td>
<td><p>Ejecute las pruebas para comprobar que los servidores front-end existentes pueden tratar la carga. Introduzca un nuevo servidor front-end si es necesario. Compruebe los tiempos de respuesta de la base de datos SQL y corrija las causas de los retrasos (por ejemplo, mejorar e/s de disco).</p></td>
</tr>
</tbody>
</table>


La solución de problemas con más detalle se describe en la guía de redes de Lync Server.

La capacidad se ve afectada por la configuración del sistema y depende de los recursos físicos, como el ancho de banda de la red. Por ejemplo, si un entorno de Lync está configurado para realizar una copia de seguridad completa por la noche, debe tener cuidado para garantizar que se minimice el efecto en el rendimiento interactivo que experimentan los usuarios finales.

La administración de la capacidad es el proceso de mantener la capacidad de un sistema dentro de los niveles aceptables y resuelve los problemas siguientes:

  - **Reaccionar ante los cambios en los requisitos**     Los requisitos de capacidad deben ajustarse para tener en cuenta los cambios en el sistema o la organización. Por ejemplo, si su entorno decide implementar la telefonía IP empresarial, la cantidad y la ubicación de los servidores de mediación y las puertas de enlace de la red telefónica conmutada (RTC) serán muy importantes. Si va a realizar un enlace troncal del Protocolo de inicio de sesión (SIP) o un SIP directo, el diseño general se cambiará significativamente para proporcionar el mejor rendimiento de la telefonía IP empresarial.

  - **Predecir los requisitos futuros**     Algunos requisitos de capacidad cambian de forma predecible a lo largo del tiempo. Al realizar un seguimiento de las tendencias, puede planear actualizaciones por adelantado. Por ejemplo, el ancho de banda disponible entre varios sitios de Lync debe supervisarse para crear una línea base. Esta línea base le permitirá predecir cuándo tiene que agregar más ancho de banda a estos vínculos, ya que el recuento de usuarios en estos sitios remotos aumenta con el tiempo.

</div>

<div>

## <a name="availability-management"></a>Administración de la disponibilidad

La administración de la disponibilidad es el proceso de garantizar que cualquier servicio de ti ofrezca de forma coherente y rentable el nivel de servicio coherente y fiable que requiera el cliente. La administración de la disponibilidad se ocupa de minimizar la pérdida de servicio y asegurarse de que se realiza la acción apropiada si se pierde el servicio. En un entorno de Lync, puede que le preocupe saber si el servicio de telefonía IP empresarial está disponible, si los usuarios pueden unirse a conferencias programadas, etc. Un SLA define una frecuencia aceptable y la duración de las interrupciones, y permite períodos determinados cuando el sistema no está disponible para el mantenimiento planeado.

Si tiene que proporcionar informes a su administración sobre la disponibilidad de los sistemas o si tiene alguna penalización financiera u otras penalizaciones asociadas con los objetivos de disponibilidad que faltan, debe registrar los datos de disponibilidad. Incluso si no tiene dichos requisitos formales, es una buena idea saber con qué frecuencia se produce un error en un sistema durante un período de tiempo determinado. Por ejemplo, la disponibilidad del sistema en los últimos 12 meses y el tiempo que tardó en recuperarse de cada error. Esta información le ayudará a medir y mejorar la efectividad del equipo para responder a un error del sistema. También puede darle información útil si hay una disputa.

Las medidas relacionadas con la disponibilidad son las siguientes:

  - **Disponibilidad**     Normalmente, esto se expresa como la hora a la que se puede tener acceso a un sistema o servicio en comparación con el momento en que está inactivo. Normalmente se expresa como un porcentaje. (Es posible que vea referencias a "tres nueves" o "cinco nueves". Estos hacen referencia a la disponibilidad de 99,9 por ciento o el 99,999 por ciento.)

  - **Confiabilidad**     Se trata de una medida del tiempo entre errores de un sistema y a veces se expresa como media (o media) tiempo entre errores (MTBF).

  - **Tiempo de reparación**     Este es el tiempo que se tarda en recuperar un servicio después de que se haya producido un error y que a menudo se expresa como media (que significa promedio) de tiempo de reparación (MTTR).

La disponibilidad, la confiabilidad y el tiempo de reparación se relacionan de la siguiente manera:

**Disponibilidad = (MTBF – MTTR)/MTBF**     Por ejemplo, si se produce un error en un servidor dos veces durante un período de seis meses y no está disponible durante un promedio de 20 minutos, la MTBF es de tres meses o 90 días y el MTTR es de 20 minutos. Por lo tanto, Availability = (90 días – 20 minutos)/90 días = 99,985 por ciento.

La administración de la disponibilidad es el proceso de garantizar que la disponibilidad se maximice y se mantenga dentro de los parámetros definidos en los SLA. La administración de la disponibilidad incluye los siguientes procesos:

  - **Supervisión**     Examinar Cuándo y durante cuánto tiempo los servicios no están disponibles.

  - **Informes**     Las cifras de disponibilidad deben proporcionarse con regularidad a los equipos de administración, usuarios y operaciones. Estos informes deben resaltar tendencias e identificar las áreas que están haciendo bien y las que requieren atención. El informe debe resumir el cumplimiento de los objetivos establecidos en los SLA.

  - **Mejora**     Si la disponibilidad no cumple con los objetivos definidos en los SLAs o donde la tendencia es a reducir la disponibilidad, el proceso de administración de la disponibilidad debe planear los pasos necesarios para los remedios. Esto debe incluir trabajar con otros equipos responsables para resaltar los motivos de las interrupciones y planear las acciones correctivas para evitar una reaparición de las interrupciones.

Las medidas de capacidad y disponibilidad son tareas repetitivas que resultan adecuadas para las herramientas automatizadas y scripts como Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que se describen más adelante en este documento.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Supervisión de Lync Server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

