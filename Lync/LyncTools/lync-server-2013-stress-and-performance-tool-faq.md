---
title: Preguntas más frecuentes de la herramienta stress and performance de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590453f6270ebcd2beebbb26b8035f9e33cc2cd7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Preguntas más frecuentes de la herramienta stress and performance de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

Estas son algunas de las preguntas más frecuentes sobre la herramienta de esfuerzo y rendimiento de Lync Server 2013.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>¿Puedo ejecutar LyncPerfTool. exe en producción?

No se recomienda esto. Esta herramienta afectará al rendimiento del servidor, la seguridad y la experiencia del usuario.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>Estoy registrando en mis usuarios por primera vez. ¿Por qué los servidores se ejecutan con una carga tan alta?

La primera vez que los usuarios inician sesión, hay otras operaciones que se producen. Como resultado, se degradará el rendimiento del servidor back-end de Microsoft SQL Server. Le recomendamos que ejecute una breve prueba que inicie sesión en todos los usuarios y, a continuación, reinicie los clientes antes de medir los resultados. No se admiten más de 12 sesiones de inicio de sesión de usuario simultáneas por segundo, pero esto depende de la configuración de hardware.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Los clientes se están quedando sin memoria. ¿Qué tengo que hacer?

Si los clientes se están quedando sin memoria, debe reducir el número de usuarios por equipo.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>Mis clientes tienen un 100 por ciento de CPU todo el tiempo. ¿Qué tengo que hacer?

Si los clientes están ejecutando una CPU muy alta después de que todos los usuarios hayan iniciado sesión, debe reducir el número de usuarios por equipo. Los picos de CPU elevados son aceptables, pero si se mantiene, es necesario reducir la carga.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>¿Puedo ejecutar la herramienta en el servidor en sí?

No. Este escenario no es compatible y puede producirse un error debido a un error de coincidencia binaria. Además, como el punto es medir el consumo de recursos en el servidor, ejecutar la herramienta hará que las medidas no tengan sentido.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>¿Puedo ejecutar LyncPerfTool. exe en un servidor virtual o en Microsoft Hyper-V Server 2008/2012?

Sí.

</div>

<div>

## <a name="what-does-mpop-mean"></a>¿Qué significa MPOP?

MPOP representa varios puntos de presencia. Se pretende simular el escenario en el que los usuarios inician sesión en Lync 2013 desde varios equipos. Tenga en cuenta que en LyncPerfTool. exe, cada punto de conexión usa el perfil predeterminado (es decir, el perfil no se divide entre los dos puntos de presencia).

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Comencé LyncPerfTool. exe, pero no ocurre nada. ¿Qué sucede?

Compruebe el contador de extremos activos totales en los clientes para ver si los usuarios se conectan. Si los usuarios no se conectan, Compruebe la configuración de Lync Server 2013. Este problema suele producirse porque el nombre del servidor, el prefijo de usuario o la contraseña son incorrectos. Tenga en cuenta que los clientes externos deben especificar el proxy de acceso como el valor TargetServer. Compruebe el puerto en el archivo de configuración.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>¿Cómo puedo saber si algo está ocurriendo?

Los distintos contadores de rendimiento de LyncPerfTool indican si los usuarios están conectando y realizando acciones. Sin embargo, una forma sencilla de comprobar es iniciar sesión en una de las cuentas con Lync 2013 y realizar la acción deseada.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Tengo instaladas las herramientas de planeación de capacidad de Live Communications Server 2007 R2 o Lync Server 2010. ¿Es correcto?

No. Hay problemas de interoperabilidad y debe desinstalar todas las versiones anteriores de este producto.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>¿Las herramientas de estrés y rendimiento configuran la topología del servidor de información de llamadas de CAA?

No. Las herramientas solo crean usuarios, contactos y listas de distribución, y simulan la carga de usuarios.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>¿Cuál es el número máximo de usuarios que admiten las herramientas?

Hemos creado hasta un total de 80.000 usuarios y pruebas ejecutadas que totalizan 30.000 usuarios con estas herramientas. Se recomienda un máximo de 120.000 usuarios, aunque las limitaciones técnicas permiten un valor superior, según el hardware del servidor y el cliente disponibles.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

