---
title: 'Lync Server 2013: supervisión del rendimiento de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee7fbb69583a62ac50548bdae11a1a5681398e98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a>Supervisión del rendimiento de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-15_

El rendimiento de Lync Server 2013 se ve afectado por diversos factores, como los perfiles de usuario, la arquitectura del sistema, el software, los componentes de hardware, los puntos de integración de terceros como puertas de enlace y equipos de telefonía, conectividad de red y rendimiento, Windows Configuración y rendimiento del servicio Active Directory además de la funcionalidad del sistema operativo Windows.

En el centro del rendimiento de las implementaciones de Lync Server 2013 es el software y el hardware del servidor en el que se implementa. Por ejemplo, un servidor front-end debe tener suficientes recursos de hardware para hacer frente a la carga de usuarios prevista (a corto plazo). Si se requiere un servidor front-end respectivo para proporcionar servicios a usuarios de 10000, un servidor configurado adecuadamente debe cumplir con los requisitos de carga esperados para poder garantizar la mejor experiencia posible del usuario final.

Por lo tanto, el rendimiento del servidor de supervisión es muy importante para evaluar si la infraestructura de servidor implementada tiene recursos de hardware adecuados para los requisitos de carga máxima cotidianos. El rendimiento del servidor de supervisión ayuda a identificar cuellos de botella del sistema, lo que permite a los administradores aplicar acciones correctivas antes de que la experiencia del usuario final se vea afectada. Los datos de rendimiento deben usarse para la planeación de capacidad a largo plazo.

Mientras que la información detallada de todos los objetos y contadores de rendimiento que deben tenerse en cuenta está vinculada a en la [supervisión de Lync Server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), algunos contadores de rendimiento que debe seguir pueden proporcionar a los administradores una vista rápida del rendimiento del sistema:

  - Para realizar un seguimiento del estado general del sistema del servidor front-end, un buen punto de partida\\es comprobar el procesador% de tiempo de procesador. El valor siempre debe ser inferior 80 por ciento.

  - Para realizar un seguimiento del rendimiento de la instancia de software back-end de base de datos de SQL Server utilizada por el grupo de servidores front-end, supervise los siguientes contadores de rendimiento:
    
    LC: ServU – 00 – DBStore\\ServU – 002 – latencia en cola (MS)
    
    LC: ServU-00 – DBStore\\servu – 0 04 – latencia de SPROC (mseg)
    
    El servidor en buen estado constante debería mostrar \<100 ms de latencia. El mecanismo de limitación se activará cuando la latencia alcance 12 segundos, lo que significa que el servidor front-end empieza a limitar las solicitudes al back-end. Esto hace que los clientes se inicien recibiendo un mensaje de error de servidor de 503 muy ocupado.

  - Para realizar un seguimiento del tiempo de procesamiento en el servidor front-end, supervise el siguiente contador:
    
    LC: SIP-07-Load Management\\SIP-000-tiempo medio de retención de mensajes entrantes
    
    Este es otro mecanismo de limitación en los servidores front-end, esta vez que comienza cuando el tiempo de procesamiento en el front-end es alto. Si el tiempo medio de procesamiento es superior a seis segundos, el servidor entra en el modo de limitación y solo permite una transacción pendiente por conexión de cliente.

  - Para realizar un seguimiento de los problemas de memoria en el servidor Back-End SQL, supervise el siguiente contador:
    
    Esperanza de vida de\\página del administrador de búfer de SQL Server
    
    Un valor bajo, por debajo de 3600 segundos (junto con latencia alta de escrituras/s y páginas de puntos/seg.) indica la presión de la memoria.

<div>

## <a name="additional-counters-to-view"></a>Contadores adicionales para ver

Hay varios contadores clave que son buenos indicadores del estado general del servidor front-end. Esta no es una lista exhaustiva y no está destinada a identificar la causa raíz. Estos contadores le permitirán realizar una comprobación rápida del estado del servidor. Le recomendamos que compruebe estos contadores en cada uno de los servidores del grupo. Es importante comprender cuáles son estos valores de contador cuando el servidor está en buen estado. Se necesita una línea base para comprender lo que ha cambiado cuando la experiencia del usuario se ha degradado.

El servidor front-end puede indicar problemas que pueden deberse a cuellos de botella en otra parte del sistema. Esto significa que es el mejor punto de partida al analizar el estado general del sistema.

Los dos contadores adicionales que deben revisarse primero son los siguientes:

LC: ServU-00-DBStore\\ServU-002-latencia en cola (MS)

LC: ServU-00-DBStore\\ServU-004-latencia de procedimiento almacenado (MS)

El contador de latencia de cola representa el tiempo que una solicitud de la cola dedica al back-end y la latencia del procedimiento almacenado representa el tiempo que tardó el back-end en procesar la solicitud. Si, por algún motivo, el disco, la memoria, la red y el procesador del back-end tienen problemas, el contador de latencia de cola será alto.

También puede ser alto si hay una latencia de red alta entre el front-end y el back-end. ¿Qué es una latencia de cola aceptable?

En 12 segundos, los servidores front-end comienzan a limitar las solicitudes a los servidores back-end. Esto significa que los servidores comienzan a devolver los errores Server Too busy – 503 a los clientes. Un servidor en buen estado debe tener menos de 100 milisegundos de latencias de cola de DBStore en estado estable, pero durante las horas en las que el servidor acaba de estar en línea y los usuarios están todos los inicios de sesión al mismo tiempo, dicho contador puede ser muy alto e incluso puede verse en varios segundos.

Puede tener una configuración de carga equilibrada, en la que tiene un grupo de servidores implementado con varios servidores front-end y un equilibrador de carga configurado para "número mínimo de conexiones". En este caso, si se reinicia un servidor front-end, todos los usuarios que intenten la reconexión recibirán la señal al servidor reiniciado, porque ese servidor tendrá menos conexiones en comparación con los demás miembros del grupo. Durante este tiempo, el servidor front-end respectivo puede estar sobrecargado mientras que los demás miembros del grupo no lo están.

Le recomendamos que realice el mantenimiento fuera del horario de trabajo para reducir el impacto en el rendimiento, ya que los usuarios no estarán compitiendo en la conexión con el servidor al mismo tiempo.

Si los dos contadores de rendimiento anteriores son altos, el cuello de botella más probable es el servidor back-end de SQL. Los siguientes componentes que se deben confirmar son los siguientes:

  - ¿Es demasiado alta la CPU de SQL Server? Por ejemplo, ¿es superior al 80 por ciento?

  - ¿La latencia de disco es alta?

En un mundo ideal, tiene suficiente memoria RAM para tener las bases de datos RTC y RTCDYN en la memoria. A continuación, la única razón por la que el servidor tendría acceso al disco es escribir en los archivos de registro y vaciar a las bases de datos. Las pruebas han demostrado que 12 GB de RAM son suficientes para las implementaciones de 100.000 usuarios. Se supone que el tamaño total de las bases de datos RTC y RTCDYN es inferior a 12 GB. Si las bases de datos son más grandes, puede que necesite más memoria.

Puede determinar si SQL Server requiere RAM adicional mediante la revisión del contador de rendimiento esperanza de vida de la página del administrador de búfer de SQL Server. Un valor inferior a 3.600 indica presión de memoria. También debería ver pocas o ninguna lecturas en la unidad de la base de datos si tiene suficiente memoria porque SQL Server solo debe escribir en la base de datos.

Hay un mecanismo de limitación adicional en un servidor front-end de Lync Server 2013 que se inicia si el tiempo de procesamiento del servidor es alto. La limitación de latencia de DBStore solo está habilitada si la latencia para SQL Server es alta. Un ejemplo en el que esta limitación está habilitada se encuentra en el caso de que el servidor front-end esté enlazado a la CPU.

Si el tiempo medio de procesamiento **(LC: SIP-07-Load\\Management SIP-000-promedio de tiempo de retención de mensajes entrantes)** en el servidor supera los seis segundos, el servidor entrará en el modo de limitación y solo dará a los usuarios una transacción pendiente por conexión de cliente. Una vez que el tiempo de procesamiento cae en tres segundos, el servidor sale del modo de limitación de peticiones y proporciona a los usuarios hasta 20 transacciones pendientes por conexión de cliente. Siempre que el número de transacciones en una conexión específica supera el umbral anterior, la conexión se marca como controlado por flujo. El resultado es que el servidor no envía ningún recepción a él y se incrementa el contador de **conexiones controladas por\\flujo SIP-01-Peers** . Si una conexión permanece en un Estado controlado por flujo durante más de un minuto, el servidor la cierra. Lo hace de forma diferida. Cuando tiene una oportunidad para comprobar la conexión, determina si se ha limitado durante demasiado tiempo y la cierra si tiene más de un minuto.

Estos son los dos mecanismos de limitación de peticiones y hay un contador de rendimiento que resume qué es lo que, en caso de existir, está realizando una limitación del servidor.

**LC: SIP-04-Responses\\sip-053-local 503 respuestas/seg**

  - El término "local" del contador anterior hace referencia a respuestas generadas localmente.

  - El código 503 corresponde al servidor no disponible, en el que no se deben ver los códigos 503 en un servidor en buen estado. Durante el período en el que se acaba de poner en línea un servidor, es posible que vea algunos códigos de 503. Cuando todos los usuarios vuelven a iniciar sesión y el servidor vuelve a un estado estable, no deberían existir códigos 503 adicionales.

**LC: SIP-04-Responses\\sip-074-local 504 respuestas/seg**

Este contador de rendimiento indica problemas de conectividad con otros servidores y puede indicar errores de conexión o de retrasos en la conexión. Si ve 504 errores, se debe comprobar el siguiente contador de rendimiento.

**LC: SIP-01-Peers\\SIP-017-envíos pendientes**

Este contador indica el número de solicitudes y respuestas salientes en cola. Si este contador es alto, lo más probable es que el problema no esté en el servidor local. Tenga en cuenta que este contador puede ser alto si hay problemas de latencia de red. También podría indicar problemas con el adaptador de red local, pero es más probable que se deba a un problema en un servidor remoto. Es muy probable que este contador sea alto en un servidor Director cuando el grupo con el que está intentando comunicarse está sobrecargado. La clave con este contador es mirar las instancias, no solo el total.

</div>

</div>

<span> </span>

</div>

</div>

</div>

