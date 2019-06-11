---
title: 'Lync Server 2013: supervisar el sistema operativo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f8124afcf2d1acbde3518ff625d528d6e34a3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a>Supervisar el sistema operativo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-01-26_

Debe supervisar el rendimiento de todos los servidores y componentes de Lync Server 2013. Como es obvio, uno de los componentes más importantes es el propio sistema operativo. Lync Server 2013 admite ediciones x64 de:

  - Windows Server 2008 R2

  - Windows Server 2012 y Windows Server 2012 R2

La manera más transparente de supervisar un sistema operativo es mediante el módulo de administración de Windows Server Operating System. Proporciona los conceptos básicos de supervisión fundamentales, como el rendimiento, la salud y la disponibilidad para equipos que ejecutan Windows Server 2012, Windows Server 2012 R2 y Windows Server 2008 R2.

Al detectar, alertar y responder automáticamente a los eventos importantes y a los indicadores de rendimiento, estos módulos de administración reducen los tiempos de resolución de problemas y aumentan la disponibilidad general y el rendimiento de los sistemas que ejecutan Windows Server sistemas operativos.

Aparte de los paquetes de administración de Windows Server relevantes para System Center Operations Manager, se pueden usar las siguientes herramientas y recursos del sistema para supervisar el estado del sistema operativo (según la versión del sistema operativo).

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 incluye las siguientes características y herramientas adicionales para ayudar a los administradores a supervisar y administrar sistemas operativos:

  - El **Monitor de recursos de Windows** es una potente herramienta para entender el uso que los procesos y servicios hacen de los recursos del sistema. Además de supervisar este uso en tiempo real, el Monitor de recursos puede ayudar a analizar procesos que no responden, identificar las aplicaciones que usan archivos y controlar los procesos y servicios.

  - El **Componente de análisis de confiabilidad** es un agente integrado que proporciona información de experiencia detallada sobre el uso y la fiabilidad del sistema. Esta información se muestra mediante una interfaz WMI para hacerla disponible en sistemas de lectura portátil. Al mostrar el Componente de análisis de confiabilidad en una interfaz WMI, los desarrolladores pueden supervisar y analizar las aplicaciones, lo que aumenta la fiabilidad y el rendimiento.

  - **Windows Server 2008 R2** usa el componente de análisis de confiabilidad integrado para calcular un índice de confiabilidad, que proporciona información sobre el uso y la estabilidad generales del sistema a lo largo del tiempo. The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Monitor de confiabilidad y rendimiento de Windows Server 2008

El Monitor de confiabilidad y rendimiento de Windows es un componente MMC que combina la funcionalidad de anteriores herramientas independientes, como Registros y alertas de rendimiento, Asesor de rendimiento de servidor y Monitor del sistema. Ofrece una interfaz gráfica para personalizar la obtención de datos y las sesiones de seguimiento de eventos.

También incluye el Monitor de confiabilidad, un componente MMC que hace un seguimiento de los cambios del sistema y los compara con los cambios en la estabilidad del mismo, ofreciendo una vista gráfica de la relación.

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Monitor de confiabilidad y rendimiento de Windows

Mientras que el monitor de confiabilidad y rendimiento de Windows combina funcionalidades de algunas herramientas independientes, como registros y alertas de rendimiento, y el monitor de sistema y el rendimiento del servidor, también proporciona una nueva funcionalidad a Windows Server 2008 y Windows Server 2008 R2, como el siguiente:

  - Conjuntos de recopiladores de datos

  - Vista de recursos

  - Monitor de confiabilidad

  - Asistentes y plantillas de creación de registros

Un **conjunto de recopiladores de datos** agrupa estos recopiladores en elementos reutilizables para su uso con distintos entornos de supervisión del rendimiento. Cuando un grupo se guarda como conjunto de recopiladores de datos, con solo cambiar una propiedad es posible aplicar al conjunto entero operaciones tales como la programación. El Monitor de confiabilidad y rendimiento de Windows incluye plantillas predeterminadas de conjuntos de recopiladores de datos para ayudar a los administradores del sistema a comenzar de inmediato a recopilar datos de rendimiento de un rol de servidor o un entorno de supervisión específicos.

La página de inicio del Monitor de confiabilidad y rendimiento de Windows es la nueva pantalla **Vista de recursos**, que proporciona una imagen gráfica y en tiempo real del uso de CPU, discos, red y memoria. Los administradores del sistema pueden expandir cada uno de estos elementos para identificar qué recursos emplea cada proceso. En versiones anteriores de Windows, estos datos en tiempo real de procesos concretos solo estaban disponibles, y de forma limitada, desde el Administrador de tareas.

El **Monitor de confiabilidad** calcula un índice de estabilidad que refleja si alguna incidencia inesperada ha reducido la fiabilidad del sistema. Un gráfico del índice a lo largo del tiempo identifica rápidamente el momento en que comenzaron a producirse incidencias. El informe de estabilidad del sistema proporciona detalles que ayudan a determinar la causa de la pérdida de fiabilidad. Ver los cambios producidos (instalación o eliminación de aplicaciones, actualizaciones del sistema operativo o agregación o modificación de controladores) junto a los errores (errores de aplicaciones, bloqueos del sistema operativo o errores de hardware) permite desarrollar rápidamente una estrategia para abordar las incidencias.

Una **interfaz de asistente** permite ahora agregar contadores a archivos de registro y programar su inicio, finalización y duración. Además, los administradores del sistema pueden guardar esta configuración como plantilla para recopilar el mismo registro en otro equipo sin necesidad de repetir la selección de recopiladores de datos y la programación de procesos. En el Monitor de confiabilidad y rendimiento de Windows si incorporaron características de Registros y alertas de rendimiento para su uso con cualquier conjunto de recopiladores de datos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

