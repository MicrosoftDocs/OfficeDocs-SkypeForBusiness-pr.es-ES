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
ms.openlocfilehash: 41c49839b01b531c1cd4c9a5eb4cff5fb6a155f4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Comprobación de registros de eventos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-06_

Puede usar el [visor de eventos de Windows](https://go.microsoft.com/fwlink/p/?linkid=314067) para ver los registros de eventos y obtener información sobre errores de servicio, errores de replicación en AD DS y advertencias sobre los recursos del sistema, como la memoria virtual y el espacio en disco. El visor de eventos se incluye con Windows Server 2008 y 2012.

En la herramienta de registro de Lync Server 2013, cuando finalice la sesión de depuración, haga clic en **analizar archivos de registro** para ver los archivos de registro mediante la herramienta de supervisión.

El visor de eventos mantiene registros sobre los eventos del sistema, la seguridad y la aplicación en el equipo. Lync Server 2013 y las condiciones de error y advertencias de los informes de Windows para los registros de eventos. Por lo tanto, revise los registros de eventos a diario.

Use el visor de eventos para:

  - Ver y administrar registros de eventos.

  - Obtenga información sobre los problemas de hardware, software y sistema que deben resolverse.

  - Identificar las tendencias que requieren acciones futuras.

Un servidor que ejecuta Lync Server en un sistema operativo Windows Server registra eventos en cuatro tipos de registros:

  - **Registros de aplicación**   el registro de aplicación contiene los eventos registrados por aplicaciones o programas. Los desarrolladores determinan los eventos que se registrarán. Por ejemplo, un programa de base de datos podría registrar un error de archivo en el registro de la aplicación. La mayoría de los eventos relacionados con Lync Server 2013 aparecen en el registro de la aplicación.

  - **Registros de seguridad**   el registro de seguridad registra eventos como intentos válidos y no válidos de inicio de sesión, además de eventos relacionados con el uso de recursos, como la creación, apertura o eliminación de archivos u otros objetos. Por ejemplo, si la auditoría de inicio de sesión está habilitada, los intentos de iniciar sesión en el sistema se registran en el registro de seguridad.

  - **Registros**   del sistema el registro del sistema contiene eventos registrados por los componentes del sistema de Windows. Por ejemplo, el error de la carga de un controlador u otro componente del sistema durante el inicio se registra en el registro del sistema. Los tipos de eventos registrados por los componentes del sistema están predeterminados por el servidor.

  - **Lync Server 2013**   la herramienta de registro registra eventos importantes relacionados con la autenticación, las conexiones y las acciones del usuario. Después de habilitar el registro de diagnóstico, puede ver las entradas de registro en el visor de eventos.

<div>


> [!NOTE]  
> No se recomienda usar la configuración de registro máxima a menos que se le indique a través de los servicios de soporte técnico de Microsoft. El registro máximo purga los recursos importantes y puede dar varios "falsos positivos", es decir, los errores que se registran solo en el registro máximo pero se esperan realmente y no son un motivo de preocupación. También le recomendamos que no habilite el registro de diagnóstico de forma permanente. Úselo solo para solucionar problemas.



</div>

En cada registro del visor de eventos, Lync Server 2013 registra eventos informativos, de advertencia y de error. Supervise estos registros atentamente para realizar un seguimiento de los tipos de transacciones que se realizan en los servidores de Lync Server 2013. Debe archivar periódicamente los registros o usar la sustitución automática para evitar quedarse sin espacio. Como los archivos de registro pueden ocupar una cantidad de espacio finita, aumente el tamaño del registro (por ejemplo, a 50 MB) y establézcalo en overwrite para que el servidor de Lync Server 2013 pueda seguir escribiendo nuevos eventos.

También puede automatizar la administración de registros de eventos mediante las siguientes herramientas y tecnologías:

  - System Center Operations Manager supervisa el estado y el uso de los servidores de Lync Server 2013. El módulo de administración de Lync Server 2013 para Operations Manager amplía Operations Manager al ofrecer una supervisión especializada para los servidores que ejecutan Lync Server 2013.

  - El paquete de administración de Lync Server 2013 para los monitores de Operations Manager Standard y Enterprise Edition de Lync Server 2013. Esta versión también incorpora el módulo de administración de calidad de la experiencia (QoE), que anteriormente era un módulo de administración independiente.

Los tipos supervisados son entradas de registro de eventos, contadores de rendimiento y supervisión de estado de QoE. Esta versión del módulo de administración solo supervisa Lync Server 2013 y 2010, y no se puede usar para supervisar Office Communications Server 2007.

El módulo de administración proporciona las siguientes características:

  - Alertas que indican eventos que afectan al servicio

  - Alertas que indican la configuración y otros problemas que no afectan al servicio

  - Supervisión de estado de los servicios de Lync Server

  - Conocimiento del producto: causa y solución de problemas identificados

Para obtener más información acerca del paquete de administración de Lync Server 2013, consulte [Monitoring Lync server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).

**Event COMB**   la herramienta Event COMB recopila eventos específicos de los registros de eventos de varios equipos en una ubicación central. Permite informar únicamente de los identificadores de evento o los orígenes de eventos que especifica. Para obtener más información acerca de Event COMB, consulte el sitio web de [herramientas de bloqueo y administración de cuentas](https://go.microsoft.com/fwlink/?linkid=35607) .

**Desencadenadores de eventos**   en Windows Server 2012 puede "adjuntar una tarea a este evento" en el visor de eventos de Windows, donde un administrador puede ejecutar un programa, enviar un mensaje de correo electrónico o mostrar un mensaje en pantalla. Para obtener más información acerca de esta característica, vea el tema sobre Windows Server 2008 R2 [ejecutar una tarea en respuesta a un evento determinado](https://technet.microsoft.com/library/cc748900.aspx). También puede usar herramientas de línea de comandos como "EventTrigger. exe" para crear y consultar registros de eventos y asociar programas con determinados eventos registrados. Mediante eventtriggers. exe, puede crear desencadenadores de eventos que ejecutan programas cuando se producen eventos específicos.

<div>

## <a name="see-also"></a>Vea también


[Visor de eventos de Windows](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

