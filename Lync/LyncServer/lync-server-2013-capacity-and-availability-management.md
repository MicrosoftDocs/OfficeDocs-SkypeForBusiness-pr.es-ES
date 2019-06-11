---
title: 'Lync Server 2013: administración de capacidad y disponibilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 923dd7a4133da52a68e4d66ee6d5c7c47e7c0421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Administración de la capacidad y disponibilidad de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-18_

El propósito de la administración de capacidad y la administración de la disponibilidad es medir y controlar el rendimiento del sistema. Le recomendamos que implemente procedimientos de administración de capacidad y de disponibilidad para poder medir y controlar el rendimiento del sistema. Debe saber si el sistema está disponible y si puede manejar las exigencias actuales y previstas configurando líneas de base y supervisando el sistema para buscar tendencias.

<div>

## <a name="capacity-management"></a>Administración de capacidad

La administración de la capacidad implica la planeación, el ajuste de tamaño y el control de la capacidad de servicio para ayudar a garantizar que se superan los niveles de rendimiento mínimos especificados en el SLA. Una buena administración de la capacidad ayuda a garantizar que puedes proporcionar servicios de ti a un coste razonable y seguir satisfaciendo los niveles de rendimiento definidos en los SLAs con el cliente. Estos criterios pueden incluir lo siguiente:

  - **Tiempo de respuesta del sistema**   es el tiempo medido que el sistema tarda en realizar acciones típicas. Algunos ejemplos son el tiempo necesario para que la función de servidor de audio y vídeo procese el tráfico de audio o vídeo, el tiempo necesario para que un cliente se cree y se una a una conferencia, o el tiempo que se tarda en actualizar la presencia en todos los clientes de monitor.

  - **Capacidad de almacenamiento**   esta es la capacidad de un sistema de almacenamiento, ya sea una base de datos de contenido, un dispositivo de copia de seguridad o una unidad local. Algunos ejemplos son la cantidad máxima de espacio de almacenamiento que se debe proporcionar por sitio y el tiempo que las copias de seguridad deben almacenarse antes de que se sobrescriban.

Normalmente, la capacidad de ajuste es asegurarse de que haya suficientes recursos físicos disponibles, como el espacio en el disco y el ancho de banda de la red. En la tabla siguiente se enumeran las resoluciones típicas de problemas relacionados con la capacidad.

### <a name="typical-resolutions-for-capacity-related-issues"></a>Resoluciones típicas de problemas relacionados con la capacidad

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
<td><p>Usuarios remotos con un bajo rendimiento de audio y vídeo</p></td>
<td><p>Compruebe si el ancho de banda disponible es adecuado en los vínculos WAN y si QoS está habilitado y configurado correctamente. Consultar los datos de la calidad.</p></td>
</tr>
<tr class="even">
<td><p>La respuesta general del entorno de Lync es lenta.</p></td>
<td><p>Ejecute pruebas para comprobar que los servidores front-end existentes pueden tratar la carga. Introduzca un nuevo servidor de aplicaciones para usuario si es necesario. Compruebe los tiempos de respuesta de la base de datos SQL y corrija las causas de los retrasos (por ejemplo, mejorar la e/s de disco).</p></td>
</tr>
</tbody>
</table>


La solución de problemas más detallada se trata en la guía de redes de Lync Server.

La capacidad se ve afectada por la configuración del sistema y depende de recursos físicos, como el ancho de banda de la red. Por ejemplo, si un entorno de Lync está configurado para realizar una copia de seguridad completa por la noche, debe tener cuidado para garantizar que se minimice el efecto sobre el rendimiento interactivo experimentado por los usuarios finales.

La administración de capacidad es el proceso de mantener la capacidad de un sistema dentro de los niveles aceptables y solucionar los problemas siguientes:

  - ****   El reaccionamiento de los cambios en los requisitos de capacidad debe ajustarse para tener en cuenta los cambios en el sistema o la organización. Por ejemplo, si su entorno decide implementar la telefonía IP empresarial, el número y la ubicación de los servidores de mediación y de las puertas de enlace de red telefónica conmutada (RTC) serán muy importantes. Si va a realizar una Troncalización del Protocolo de inicio de sesión (SIP) o un SIP directo, el diseño general se cambiará significativamente para ofrecer el mejor rendimiento de la telefonía IP empresarial.

  - **Predicción de requisitos**   futuros algunos requisitos de capacidad cambian de forma predecible a lo largo del tiempo. El seguimiento de las tendencias permite planear actualizaciones por adelantado. Por ejemplo, se debe supervisar el ancho de banda disponible entre los distintos sitios de Lync para crear una línea base. Esta línea base le permitirá predecir cuándo tiene que agregar más ancho de banda a estos vínculos, ya que el recuento de usuarios en estos sitios remotos aumenta con el tiempo.

</div>

<div>

## <a name="availability-management"></a>Administración de la disponibilidad

La administración de la disponibilidad es el proceso de garantizar que cualquier servicio de TI sea consistente y rentable para ofrecer el nivel de servicio coherente y confiable requerido por el cliente. La administración de la disponibilidad se ocupa de minimizar la pérdida de servicio y asegurarse de que se realiza la acción adecuada si se pierde el servicio. En un entorno de Lync, puede que le preocupe la preocupación de si el servicio de telefonía IP empresarial está disponible, si los usuarios pueden unirse a conferencias programadas, etc. Un SLA define una frecuencia y una duración de interrupciones aceptables y permite períodos específicos cuando el sistema no está disponible para el mantenimiento planeado.

Si tiene que proporcionar informes a su administración sobre la disponibilidad de los sistemas, o si tiene sanciones financieras o de otro tipos relacionados con los objetivos de disponibilidad que faltan, debe registrar los datos de disponibilidad. Incluso si no tiene requisitos formales, es una buena idea conocer con qué frecuencia se ha producido un error en un sistema en un determinado período de tiempo. Por ejemplo, la disponibilidad del sistema en los últimos 12 meses y el tiempo que se tarda en recuperarse de cada error. Esta información le ayudará a medir y mejorar la efectividad de su equipo para responder a un error del sistema. También puede darle información útil si hay una disputa.

Las medidas relacionadas con la disponibilidad son las siguientes:

  - **Disponibilidad**   generalmente se expresa como el momento en que se puede acceder a un sistema o servicio en comparación con el tiempo que está inactivo. Normalmente se expresa como un porcentaje. (Es posible que vea referencias a "tres nueves" o "cinco nueves". Estas referencias hacen referencia al 99,9 por ciento o al 99,999 por ciento de disponibilidad.)

  - **Confiabilidad**   es una medida del tiempo entre los errores de un sistema y a veces se expresa como el tiempo promedio entre errores (MTBF).

  - **Tiempo de reparación**   es el tiempo que se tarda en recuperar un servicio después de que se produjo un error y se suele expresar como media (es decir, el promedio) de tiempo de reparación (MTTR).

La disponibilidad, la confiabilidad y el tiempo de reparación se relacionan de la siguiente manera:

**Disponibilidad = (MTBF – MTTR)/MTBF**   por ejemplo, si un servidor no funciona dos veces durante un período de seis meses y no está disponible durante un promedio de 20 minutos, la MTBF es de tres meses o 90 días y el MTTR es de 20 minutos. Por lo tanto, Availability = (90 días – 20 minutos)/90 días = 99,985 por ciento.

La administración de la disponibilidad es el proceso de asegurarse de que la disponibilidad se maximice y se mantenga dentro de los parámetros definidos en los SLAs. La administración de la disponibilidad incluye los siguientes procesos:

  - **Supervisión**     del examen Cuándo y por cuánto tiempo los servicios no están disponibles.

  - **Informar**   de las cifras de disponibilidad debe proporcionarse regularmente a los equipos de administración, usuarios y operaciones. Estos informes deben resaltar tendencias e identificar las áreas que hacen bien y las áreas que requieren atención. El informe debe resumir el cumplimiento de los objetivos establecidos en los SLA.

  - **Mejora**   si la disponibilidad no cumple con los objetivos definidos en los SLA o si la tendencia es para reducir la disponibilidad, el proceso de administración de la disponibilidad debe planear los pasos correctos. Esto debe incluir el trabajo con otros equipos responsables de destacar las razones de las interrupciones y planificar las medidas correctivas para evitar una reaparición de las interrupciones.

Las medidas de capacidad y disponibilidad son tareas repetitivas que son ideales para las herramientas automatizadas y scripts como Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que se trata más adelante en este documento.

</div>

<div>

## <a name="see-also"></a>Vea también


[Supervisión de Lync Server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

