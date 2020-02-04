---
title: 'Lync Server 2013: comprobación de registros de eventos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 862d419d9db5d8465b3507c40fde32acd01bb659
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Comprobar registros de eventos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-06_

Puede usar el [visor de eventos de Windows](http://go.microsoft.com/fwlink/p/?linkid=314067) para ver registros de eventos y obtener información sobre errores de servicio, errores de replicación en AD DS y advertencias sobre recursos del sistema, como memoria virtual y espacio en disco. El visor de eventos se incluye en Windows Server 2008 y 2012.

En la herramienta de registro de 2013 de Lync Server, al finalizar la sesión de depuración, haga clic en **analizar archivos de registro** para ver los archivos de registro con la herramienta de supervisión.

El visor de eventos mantiene registros acerca de aplicaciones, seguridad y eventos del sistema en el equipo. Lync Server 2013 y Windows notifican las advertencias y las condiciones de error a los registros de eventos. Por lo tanto, revise los registros de eventos todos los días.

Use el visor de eventos para:

  - Ver y administrar registros de eventos.

  - Obtenga información sobre los problemas de hardware, software y sistema que se deben resolver.

  - Identifique tendencias que requieran una acción futura.

Un servidor que ejecuta Lync Server en un sistema operativo de servidor Windows registra eventos en cuatro tipos de registros:

  - **Registros de aplicaciones**   el registro de aplicación contiene eventos registrados por aplicaciones o programas. Los desarrolladores determinan los eventos que se deben registrar. Por ejemplo, un programa de base de datos puede grabar un error de archivo en el registro de la aplicación. La mayoría de los eventos relacionados con Lync Server 2013 aparecen en el registro de aplicación.

  - **Registros de seguridad**   el registro de seguridad graba eventos como intentos válidos y no válidos de inicio de sesión, además de eventos relacionados con el uso de recursos, como crear, abrir o eliminar archivos u otros objetos. Por ejemplo, si la auditoría de inicio de sesión está habilitada, los intentos de iniciar sesión en el sistema se grabarán en el registro de seguridad.

  - **Registros del sistema**   el registro del sistema contiene eventos registrados por componentes del sistema de Windows. Por ejemplo, el error de carga de un controlador u otro componente del sistema durante el inicio se graba en el registro del sistema. Los tipos de eventos registrados por los componentes del sistema están predeterminados por el servidor.

  - **Lync Server 2013**   la herramienta de registro graba eventos importantes relacionados con la autenticación, las conexiones y las acciones de usuario. Después de habilitar el registro de diagnóstico, puede ver las entradas del registro en el visor de eventos.

<div>


> [!NOTE]  
> No se recomienda usar la configuración de registro máxima a menos que se le indique que lo haga el servicio de soporte técnico de Microsoft. El registro máximo purga los recursos importantes y puede dar muchos "falsos positivos", es decir, los errores que se registran solo en el registro máximo pero son realmente los esperados y no son causa de preocupación. También le recomendamos que no habilite el registro de diagnóstico de forma permanente. Utilícelo solo para solucionar problemas.



</div>

Dentro de cada registro del visor de eventos, Lync Server 2013 registra eventos informativos, de advertencia y de error. Supervise estos registros estrechamente para realizar un seguimiento de los tipos de transacciones que se realizan en los servidores de Lync Server 2013. Debe archivar periódicamente los registros o usar la conversión automática para evitar quedarse sin espacio. Puesto que los archivos de registro pueden ocupar una cantidad de espacio limitada, aumente el tamaño del registro (por ejemplo, a 50 MB) y configúrelo para que el servidor de Lync Server 2013 pueda continuar escribiendo eventos nuevos.

También puede automatizar la administración de registros de eventos con las siguientes herramientas y tecnologías:

  - System Center Operations Manager supervisa el estado y el uso de los servidores de Lync Server 2013. El paquete de administración de Lync Server 2013 para Operations Manager amplía Operations Manager al proporcionar una supervisión especializada de los servidores que ejecutan Lync Server 2013.

  - El paquete de administración de Lync Server 2013 para los monitores de Operations Manager Standard y Enterprise Edition de Lync Server 2013. Esta versión también incorpora el paquete de administración de la calidad de la experiencia (QoE), que anteriormente era un módulo de administración independiente.

Los tipos supervisados son entradas de registro de eventos, contadores de rendimiento y supervisión estatal de QoE. Esta versión del módulo de administración solo supervisa Lync Server 2013 y 2010, y no se puede usar para supervisar Office Communications Server 2007.

El módulo de administración proporciona las siguientes características:

  - Alertas que indican eventos que afectan al servicio

  - Alertas que indican la configuración y otros problemas de impacto sin servicio

  - Supervisión de estado de los servicios de Lync Server

  - Conocimiento del producto: causa y solución de problemas identificados

Para obtener más información sobre el paquete de administración de Lync Server 2013, consulte [monitorización de Lync server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).

**Event COMB**   la herramienta Event COMB recopila eventos específicos de los registros de eventos de varios equipos a una ubicación centralizada. Le permite denunciar únicamente los identificadores de eventos o los orígenes de eventos que especifique. Para obtener más información acerca de Event COMB, consulte el sitio web de [herramientas de bloqueo y administración de cuentas](http://go.microsoft.com/fwlink/?linkid=35607) .

**Desencadenadores de eventos**   en Windows Server 2012 puede "adjuntar una tarea a este evento" dentro del visor de eventos de Windows, donde un administrador puede ejecutar un programa, enviar un mensaje de correo electrónico o mostrar un mensaje en pantalla. Para obtener más información sobre esta característica, vea el tema sobre Windows Server 2008 R2 [ejecutar una tarea en respuesta a un evento determinado](http://technet.microsoft.com/en-us/library/cc748900.aspx). También puede usar herramientas de línea de comandos, como ' EventTrigger. exe ', para crear y consultar registros de eventos y asociar programas con determinados eventos registrados. Mediante eventtriggers. exe puede crear desencadenadores de eventos que ejecuten programas cuando se produzcan eventos específicos.

<div>

## <a name="see-also"></a>Vea también


[Visor de eventos de Windows](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

