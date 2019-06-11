---
title: Preguntas más frecuentes sobre la herramienta de estrés y rendimiento de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffcfbca3a2cf58e4e7b87619bb78dabbe42b16bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Preguntas más frecuentes sobre la herramienta de estrés y rendimiento de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

Estas son algunas de las preguntas más frecuentes sobre la herramienta Lync Server 2013 stress and performance.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>¿Puedo ejecutar LyncPerfTool. exe en producción?

No lo recomendamos. Esta herramienta afectará al rendimiento del servidor, la seguridad y la experiencia del usuario.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>Estoy iniciando sesión por primera vez en mis usuarios. ¿Por qué los servidores se ejecutan con una carga elevada?

La primera vez que los usuarios inician sesión, hay otras operaciones que se producen. Como resultado, se degradará el rendimiento en el servidor de back-end de Microsoft SQL Server. Le recomendamos que ejecute una prueba breve que inicie sesión en todos los usuarios y que, después, reinicie los clientes antes de medir los resultados. No se admiten más de 12 sesiones de usuario simultáneas de inicio de sesión por segundo, pero esto depende de la configuración del hardware.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Los clientes se están quedando sin memoria. ¿Qué debo hacer?

Si los clientes se están quedando sin memoria, tendrá que reducir el número de usuarios por equipo.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>Mis clientes están en el 100 por ciento de la CPU todo el tiempo. ¿Qué debo hacer?

Si los clientes ejecutan una CPU muy alta después de que todos los usuarios hayan iniciado sesión, tendrá que reducir el número de usuarios por equipo. Los picos de CPU altos son aceptables, pero si se mantiene, es necesario reducir la carga.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>¿Puedo ejecutar la herramienta en el servidor en sí?

No. Este escenario no es compatible y puede dar error debido a que los binarios no coinciden. Además, como el punto es medir el consumo de recursos en el servidor, ejecutar la herramienta hará que las medidas no tengan sentido.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>¿Puedo ejecutar LyncPerfTool. exe en un servidor virtual o en Microsoft Hyper-V Server 2008/2012?

Sí.

</div>

<div>

## <a name="what-does-mpop-mean"></a>¿Qué significa MPOP?

MPOP representa varios puntos de presencia. Está pensado para simular el escenario en el que los usuarios inician sesión en Lync 2013 desde varios equipos. Tenga en cuenta que en LyncPerfTool. exe, cada extremo usa el perfil predeterminado (es decir, el perfil no se divide entre los dos puntos de presencia).

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Comencé LyncPerfTool. exe, pero no sucede nada. ¿Qué pasa?

Compruebe el contador de extremos activos totales de los clientes para ver si los usuarios se conectan. Si los usuarios no se conectan, Compruebe la configuración de la 2013 de Lync Server. Este problema suele ocurrir porque el nombre del servidor, el prefijo de usuario o la contraseña son incorrectos. Tenga en cuenta que los clientes externos deberían especificar el proxy de acceso como el valor de TargetServer. Compruebe el puerto en el archivo de configuración.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>¿Cómo puedo saber si algo está sucediendo?

Los diversos contadores de rendimiento de LyncPerfTool indican si los usuarios están conectados o no, y realizan acciones. Sin embargo, una forma sencilla de comprobar es iniciar sesión en una de las cuentas con Lync 2013 y realizar la acción que desee.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Tengo instaladas las herramientas de planeación de capacidad de Live Communications Server 2007 R2 o Lync Server 2010. ¿Es correcto?

No. Hay problemas de interoperabilidad y debe desinstalar todas las versiones anteriores de este producto.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>¿Configuran las herramientas de estrés y rendimiento la topología de servidor de información de llamadas de CAA?

No. Las herramientas solo crean usuarios, contactos y listas de distribución, y simulan la carga de usuarios.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>¿Cuál es el número máximo de usuarios que admiten las herramientas?

Hemos creado hasta un total de 80.000 usuarios y pruebas ejecutadas que suman a 30.000 usuarios, usando estas herramientas. Sugerimos un máximo de 120.000 usuarios, aunque las limitaciones técnicas permiten un valor superior, según el hardware del cliente y del servidor que esté disponible.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

