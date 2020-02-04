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
ms.openlocfilehash: f7859ea116e4ae63a5777e816c37893f11cf1c39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a>Supervisar el rendimiento de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-15_

El rendimiento de Lync Server 2013 se ve afectado por diversos factores como, por ejemplo, perfiles de usuario, arquitectura del sistema, software, componentes de hardware, puntos de integración de terceros, como puertas de enlace y equipos de telefonía, conectividad y rendimiento de red, Windows Configuración y rendimiento del servicio Active Directory además de la funcionalidad del sistema operativo Windows.

En el centro de un rendimiento de implementaciones de Lync Server 2013, se ha implementado el software y el hardware del servidor. Como ejemplo, un servidor front-end debe tener suficientes recursos de hardware para hacer frente a la carga de usuarios esperada (a corto plazo). Si se requiere un servidor front-end respectivo para proporcionar servicios a usuarios de 10000, un servidor configurado correctamente debe cumplir con los requisitos de carga esperados para garantizar la mejor experiencia posible para el usuario final.

La supervisión del rendimiento del servidor es, por lo tanto, muy importante evaluar si la infraestructura de servidor implementada tiene los recursos de hardware adecuados para los requisitos de carga de pico cotidianos. Supervisar el rendimiento del servidor ayuda a identificar cuellos de botella del sistema que permiten a los administradores aplicar acciones correctivas antes de que se vea afectada la experiencia del usuario final. Los datos de rendimiento deben usarse para planear la capacidad a largo plazo.

A pesar de que la información detallada de todos los objetos y contadores de rendimiento está vinculada a en la [supervisión de Lync Server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), algunos contadores de rendimiento que debe seguir pueden proporcionar a los administradores una vista rápida del rendimiento del sistema:

  - Para realizar un seguimiento del estado general del sistema del servidor front-end, un buen punto de inicio\\es comprobar el procesador% de tiempo de procesador. El valor debería estar siempre por debajo del 80 por ciento.

  - Para realizar un seguimiento del rendimiento de la instancia del software back-end de base de datos de SQL Server utilizada por el grupo de servidores front-end, supervise los siguientes contadores de rendimiento:
    
    LC: ServU-00-DBStore\\ServU – 002-latencia en cola (mseg)
    
    LC: ServU-00-DBStore\\servu-0 04-latencia de SPROC (mseg)
    
    El servidor en buen estado continuo debe mostrar \<los valores de latencia de 100 ms. El mecanismo de límite se activará cuando la latencia alcance 12 segundos, lo que significa que el servidor front-end comienza a limitar las solicitudes al back-end. Esto hace que los clientes comiencen a recibir un mensaje de error demasiado ocupado en el servidor de 503.

  - Para realizar un seguimiento del tiempo de procesamiento en el servidor front-end, supervise el siguiente contador:
    
    LC: SIP-07-administración\\de carga SIP-000-tiempo medio de retención de los mensajes entrantes
    
    Este es otro mecanismo de límite en los servidores front-end, esta vez, comienza cuando el tiempo de procesamiento en el front-end es alto. Si el tiempo de procesamiento promedio es de más de seis segundos, el servidor pasa al modo de limitación y solo permite una transacción pendiente por conexión de cliente.

  - Para realizar un seguimiento de los problemas de memoria en el servidor Back-End SQL, supervise el siguiente contador:
    
    Duración de la página\\del administrador de búfer de SQL Server
    
    Un valor bajo, por debajo de 3600 segundos (junto con las escrituras de latencia alta/s y las páginas de puntos/s) indica la presión de la memoria.

<div>

## <a name="additional-counters-to-view"></a>Contadores adicionales para ver

Hay varios contadores clave que son buenos indicadores de estado general del servidor front-end. Esta no es una lista completa y no está diseñada para identificar la causa de origen. Estos contadores le permitirán realizar una comprobación rápida del estado del servidor. Le recomendamos que verifique estos contadores en cada uno de los servidores del grupo. Es importante comprender cuáles son estos valores de contador cuando el servidor está en buen estado. Se necesita una línea base para comprender qué ha cambiado cuando la experiencia del usuario se ha degradado.

El servidor front-end puede indicar problemas que pueden estar causados por cuellos de botella en otra parte del sistema. Esto significa que es el mejor lugar para empezar al mirar el estado general del sistema.

Dos contadores adicionales para revisar en primer lugar son los siguientes:

LC: ServU-00-DBStore\\ServU-002-latencia en la cola (mseg)

LC: ServU-00-DBStore\\ServU-004-latencia del procedimiento almacenado (mseg)

El contador de latencia de cola representa la hora a la que se dedicó una solicitud de la cola al back-end y la latencia del procedimiento almacenado representa el tiempo que tomará el back-end para procesar la solicitud. Si, por cualquier motivo, el disco, la memoria, la red y el procesador en el back-end están en dificultades, el contador de latencia de cola será alto.

También puede ser alto si hay una elevada latencia de red entre el front-end y el back-end. Entonces, ¿qué es una latencia de cola aceptable?

En 12 segundos, los servidores front-end comienzan a limitar las solicitudes a los servidores back-end. Esto significa que los servidores comienzan a devolver demasiado ocupado: 503 errores a los clientes. Un servidor en buen estado debería tener menos de 100 ms DBStore latencias de cola en estado estable, pero durante las horas en las que el servidor acaba de estar en línea y todos los usuarios inician sesión al mismo tiempo, ese contador puede ser muy alto y es posible que incluso vea varios segundos.

Es posible que tenga una configuración con equilibrio de carga, en la que tiene un grupo implementado con varios servidores front-end y un equilibrador de carga configurado para "número mínimo de conexiones". En este caso, si se reinicia un servidor front-end, todos los usuarios que intenten volver a conectarse apuntarán al servidor reiniciado, porque ese servidor tendrá menos conexiones comparadas con el resto de miembros del grupo. Durante este tiempo, el servidor front-end respectivo se puede sobrecargar mientras que los demás miembros del grupo no lo están.

Le recomendamos que realice el mantenimiento fuera del horario laboral para reducir el efecto de rendimiento porque los usuarios no estarán compitiendo para conectarse al servidor al mismo tiempo.

Si los dos contadores de rendimiento anteriores son altos, el cuello de botella más probable es el servidor SQL back-end. Los siguientes componentes para confirmar son los siguientes:

  - ¿Es demasiado alto la CPU de SQL Server? Por ejemplo, ¿es superior a 80 por ciento?

  - ¿Es alta la latencia de disco?

En un mundo ideal, tiene suficiente memoria RAM para que las bases de datos RTC y RTCDYN estén en la memoria. Entonces, la única razón por la que el servidor tendría acceso al disco es escribir en los archivos de registro y vaciar las bases de datos. Las pruebas han demostrado que 12 GB de RAM son suficientes para implementaciones de usuario de 100.000. Se supone que el tamaño de las bases de datos RTC y RTCDYN es inferior a 12 GB. Si las bases de datos son mayores, es posible que necesite memoria adicional.

Puede determinar si su SQL Server requiere RAM adicional revisando el contador de rendimiento esperanza de vida de la página del administrador de búfer de SQL Server. Un valor inferior a 3.600 indica presión de memoria. También debería ver pocas o ninguna lecturas en la unidad de base de datos si tiene suficiente memoria porque SQL Server solo debe escribir en la base de datos.

Existe un mecanismo de limitación adicional en un servidor front-end de Lync Server 2013 que se inicia si el tiempo de procesamiento del servidor es alto. La limitación de latencia de DBStore solo se habilita si la latencia para SQL Server es alta. Un ejemplo en el que esta limitación está habilitada es si el servidor Front-End está enlazado a la CPU.

Si el tiempo medio de procesamiento **(LC: SIP-07-administración\\de carga SIP-000-el tiempo medio de retención de los mensajes entrantes)** en el servidor es superior a seis segundos, el servidor pasa al modo de limitación y solo ofrece a los usuarios una transacción pendiente por conexión de cliente. Una vez que el tiempo de procesamiento cae a tres segundos, el servidor sale del modo de limitación de peticiones y concede a los usuarios hasta 20 transacciones pendientes por conexión de cliente. Cada vez que el número de transacciones en una conexión específica supera el umbral anterior, la conexión se marca como control de flujo. El resultado es que el servidor no publica ninguna recepción en el mismo, y se incrementa el contador de **conexiones de\\flujo LC: SIP-01-Peers** . Si una conexión permanece en un Estado controlado por flujo durante más de un minuto, el servidor la cerrará. Lo hace de manera inestable. Cuando tiene la oportunidad de comprobar la conexión, determina si se limitó demasiado tiempo y la cerrará si tiene más de un minuto.

Estos son los dos mecanismos de limitación de peticiones y hay un contador de rendimiento que resume lo que está realizando el límite, si lo hay, en el servidor.

**LC: SIP-04-Responses\\sip-053-respuestas 503 locales/seg**

  - El término "local" del contador anterior hace referencia a respuestas generadas de forma local.

  - El código 503 corresponde a servidor no disponible, en el que no debe ver ningún código 503 en un servidor en buen estado. Durante el período en el que un servidor se acaba de conectar, es posible que vea algunos códigos de 503. Cuando todos los usuarios vuelven a iniciar sesión y el servidor vuelve a un estado estable, no debería haber más códigos 503.

**LC: SIP-04-Responses\\sip-074-respuestas 504 locales/seg**

Este contador de rendimiento indica problemas de conectividad con otros servidores y puede indicar errores de conexión o de demoras en la conexión. Si ve 504 errores, se debe comprobar el siguiente contador de rendimiento.

**LC: SIP-01-Peers\\SIP-017-envíos pendientes**

Este contador indica el número de respuestas y solicitudes en cola salientes. Si este contador es alto, lo más probable es que el problema no esté en el servidor local. Ten en cuenta que este contador puede ser alto si hay problemas de latencia de red. También podría indicar problemas con el adaptador de red local, pero es más probable que se deba a un problema en un servidor remoto. Es muy probable que este contador sea alto en un servidor Director cuando el grupo con el que intenta comunicarse está sobrecargado. La clave con este contador es mirar las instancias, no solo el total.

</div>

</div>

<span> </span>

</div>

</div>

</div>

