---
title: 'Lync Server 2013: supervisar el sistema operativo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3857ffa37ac3b50be6dc35ed281616aafff87c48
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a>Supervisar el sistema operativo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-01-26_

Debe supervisar el rendimiento de todos los servidores y componentes en el 2013 de Lync Server. Obviamente, uno de los componentes más importantes es el propio sistema operativo. Lync Server 2013 admite ediciones x64 de:

  - Windows Server 2008 R2

  - Windows Server 2012 y Windows Server 2012 R2

La forma más transparente de supervisar un sistema operativo es mediante el módulo de administración del sistema operativo de Windows Server. Proporciona los conceptos básicos de supervisión fundamentales, como rendimiento, estado y disponibilidad para los equipos que ejecutan Windows Server 2012, Windows Server 2012 R2 y Windows Server 2008 R2.

Al detectar, alertar y responder automáticamente a eventos importantes y indicadores de rendimiento, estos módulos de administración reducen los tiempos de resolución de problemas y aumentan la disponibilidad y el rendimiento generales de los sistemas que ejecutan Windows Server. sistemas operativos.

Aparte de los paquetes de administración de Windows Server relevantes para System Center Operations Manager, se pueden usar las siguientes herramientas y recursos del sistema para supervisar el estado del sistema operativo (en función de la versión del sistema operativo).

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 incluye las siguientes características y herramientas adicionales para ayudar a los administradores con la supervisión y administración básica del sistema operativo:

  - El **monitor de recursos de Windows** es una herramienta eficaz para comprender cómo los procesos y servicios usan los recursos del sistema. Además de supervisar el uso de los recursos en tiempo real, el monitor de recursos puede ayudar a analizar los procesos que no responden, identificar qué aplicaciones usan los archivos y controlar los procesos y servicios.

  - El **componente de análisis de confiabilidad** es un agente en el equipo que proporciona información detallada sobre el uso y la confiabilidad del sistema. Esta información se expone a través de una interfaz WMI para que esté disponible para su consumo por parte de los lectores portátiles. Al exponer el componente de análisis de confiabilidad a través de una interfaz WMI, los desarrolladores pueden supervisar y analizar aplicaciones, lo que aumenta la confiabilidad y el rendimiento.

  - **Windows Server 2008 R2** utiliza el componente de análisis de confiabilidad integrado para calcular un índice de confiabilidad, que proporciona información sobre el uso y la estabilidad generales del sistema a lo largo del tiempo. El componente de análisis de confiabilidad también realiza un seguimiento de cualquier cambio importante en el sistema que pueda afectar a la estabilidad, como las actualizaciones de Windows y las instalaciones de aplicaciones.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Monitor de confiabilidad y rendimiento de Windows Server 2008

El monitor de confiabilidad y rendimiento de Windows es un complemento MMC que combina la funcionalidad de herramientas independientes anteriores, como registros y alertas de rendimiento, asesor de rendimiento del servidor y monitor del sistema. Proporciona una interfaz gráfica para la personalización de sesiones de seguimiento de eventos y recopilación de datos de rendimiento.

También incluye el monitor de confiabilidad, un complemento de MMC que realiza un seguimiento de los cambios en el sistema y los compara con los cambios en la estabilidad del sistema, y proporciona una vista gráfica de su relación.

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Monitor de confiabilidad y rendimiento de Windows

Mientras que el monitor de confiabilidad y rendimiento de Windows combina funcionalidades de algunas herramientas independientes anteriores, como registros y alertas de rendimiento, y el monitor del sistema y el asesor de rendimiento del servidor, también proporciona funcionalidad nueva a Windows Server 2008 y Windows Server 2008 R2, como el siguiente:

  - Conjuntos de recopiladores de datos

  - Vista de recursos

  - Monitor de confiabilidad

  - Asistentes y plantillas para crear registros

El **conjunto de recopiladores de datos** agrupa los recopiladores de datos en elementos reutilizables para su uso con diferentes escenarios de supervisión de rendimiento. Una vez que se almacena un grupo de recopiladores de datos como un conjunto de recopiladores de datos, se pueden aplicar operaciones como la programación a todo el conjunto mediante un único cambio de propiedad. El monitor de confiabilidad y rendimiento de Windows incluye plantillas predeterminadas de conjunto de recopiladores de datos para ayudar a los administradores de sistema a recopilar inmediatamente datos de rendimiento específicos de un rol de servidor o un escenario de supervisión.

La Página principal del monitor de confiabilidad y rendimiento de Windows es la nueva pantalla **vista de recursos** , que proporciona una introducción gráfica en tiempo real del uso de la CPU, el disco, la red y la memoria. Expandiendo cada uno de estos elementos supervisados, los administradores del sistema pueden identificar qué recursos usan qué recursos. En versiones anteriores de Windows, estos datos en tiempo real y específicos del proceso solo estaban disponibles en un formulario limitado en el administrador de tareas.

El **monitor de confiabilidad** calcula un índice de estabilidad del sistema que refleja si los problemas inesperados han reducido la confiabilidad del sistema. Un gráfico del índice de estabilidad a lo largo del tiempo identifica rápidamente las fechas en las que comenzaron a producirse los problemas. El informe de estabilidad del sistema adjunto proporciona detalles para ayudar a solucionar la causa de la menor confiabilidad. Mediante la visualización de los cambios en el sistema (instalación o eliminación de aplicaciones, actualizaciones del sistema operativo o adición o modificación de controladores) en paralelo con los errores (errores de aplicaciones, bloqueos del sistema operativo o errores de hardware), una estrategia para el direccionamiento de los problemas se puede desarrollar rápidamente.

La adición de contadores a los archivos de registro y la programación de inicio, detención y duración se pueden realizar ahora a través de una **interfaz de asistente**. Además, si se guarda esta configuración como una plantilla, los administradores del sistema pueden recopilar el mismo registro en otros equipos sin repetir los procesos de programación y selección del recopilador de datos. Las características de registros y alertas de rendimiento se incorporaron en el monitor de confiabilidad y rendimiento de Windows para su uso con cualquier conjunto de recopiladores de datos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

