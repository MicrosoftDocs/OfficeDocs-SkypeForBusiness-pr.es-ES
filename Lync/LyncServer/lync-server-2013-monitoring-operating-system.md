---
title: 'Lync Server 2013: supervisar el sistema operativo'
TOCTitle: Supervisar el sistema operativo
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn720918(v=OCS.15)
ms:contentKeyID: 62246709
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supervisar el sistema operativo en Lync Server 2013

 

_**Última modificación del tema:** 2015-01-26_

Debe supervisar el rendimiento de todos los servidores y componentes del Lync Server 2013. Como es obvio, uno de los componentes más importantes es el propio sistema operativo. Lync Server 2013 es compatible con las ediciones x64 de:

  - Windows Server 2008 R2

  - Windows Server 2012 y Windows Server 2012 R2

El modo más transparente de realizar esta supervisión son los paquetes de administración del sistema operativo de Windows Server, que permiten supervisar elementos fundamentales como el rendimiento, el estado y la disponibilidad de los equipos que ejecutan Windows Server 2012, Windows Server 2012 R2 y Windows Server 2008 R2.

Mediante la detección, alerta y respuesta automática ante eventos e indicadores de rendimiento importantes, estos paquetes de administración reducen los tiempos de resolución de incidencias y mejoran la disponibilidad general y el rendimiento en sistemas que ejecutan los sistemas operativos Windows Server.

Además de los paquetes de administración de Windows Server relevantes para System Center Operations Manager, pueden usarse las siguientes herramientas y recursos del sistema para supervisar el estado del sistema operativo (según su versión).

## Windows Server 2008 R2

Windows Server 2008 R2 incluye las siguientes características y herramientas adicionales para ayudar a los administradores con la supervisión y administración básica del sistema operativo:

  - El **Monitor de recursos de Windows** es una potente herramienta para entender el uso que los procesos y servicios hacen de los recursos del sistema. Además de supervisar este uso en tiempo real, el Monitor de recursos puede ayudar a analizar procesos que no responden, identificar las aplicaciones que usan archivos y controlar los procesos y servicios.

  - El **Componente de análisis de confiabilidad** es un agente integrado que proporciona información de experiencia detallada sobre el uso y la fiabilidad del sistema. Esta información se muestra mediante una interfaz WMI para hacerla disponible en sistemas de lectura portátil. Al mostrar el Componente de análisis de confiabilidad en una interfaz WMI, los desarrolladores pueden supervisar y analizar las aplicaciones, lo que aumenta la fiabilidad y el rendimiento.

  - **Windows Server 2008 R2** usa el Componente de análisis de confiabilidad integrado para calcular un índice de fiabilidad que proporciona información sobre el uso general del sistema y su estabilidad a lo largo del tiempo. El Componente también hace un seguimiento de cualquier cambio importante susceptible de afectar a la estabilidad del sistema, como las actualizaciones de Windows o la instalación de aplicaciones.

## Monitor de confiabilidad y rendimiento de Windows para Windows Server 2008

El Monitor de confiabilidad y rendimiento de Windows es un componente MMC que combina la funcionalidad de anteriores herramientas independientes, como Registros y alertas de rendimiento, Asesor de rendimiento de servidor y Monitor del sistema. Ofrece una interfaz gráfica para personalizar la obtención de datos y las sesiones de seguimiento de eventos.

También incluye el Monitor de confiabilidad, un componente MMC que hace un seguimiento de los cambios del sistema y los compara con los cambios en la estabilidad del mismo, ofreciendo una vista gráfica de la relación.

## Monitor de confiabilidad y rendimiento de Windows

El Monitor de confiabilidad y rendimiento de Windows combina funcionalidades de anteriores herramientas independientes como Registros y alertas de rendimiento, Monitor del sistema y Asesor de rendimiento de servidor, pero también proporciona nuevas funciones para Windows Server 2008 y Windows Server 2008 R2, como las siguientes:

  - Conjuntos de recopiladores de datos

  - Vista de recursos

  - Monitor de confiabilidad

  - Asistentes y plantillas de creación de registros

Un **conjunto de recopiladores de datos** agrupa estos recopiladores en elementos reutilizables para su uso con distintos entornos de supervisión del rendimiento. Cuando un grupo se guarda como conjunto de recopiladores de datos, con solo cambiar una propiedad es posible aplicar al conjunto entero operaciones tales como la programación. El Monitor de confiabilidad y rendimiento de Windows incluye plantillas predeterminadas de conjuntos de recopiladores de datos para ayudar a los administradores del sistema a comenzar de inmediato a recopilar datos de rendimiento de un rol de servidor o un entorno de supervisión específicos.

La página de inicio del Monitor de confiabilidad y rendimiento de Windows es la nueva pantalla **Vista de recursos**, que proporciona una imagen gráfica y en tiempo real del uso de CPU, discos, red y memoria. Los administradores del sistema pueden expandir cada uno de estos elementos para identificar qué recursos emplea cada proceso. En versiones anteriores de Windows, estos datos en tiempo real de procesos concretos solo estaban disponibles, y de forma limitada, desde el Administrador de tareas.

El **Monitor de confiabilidad** calcula un índice de estabilidad que refleja si alguna incidencia inesperada ha reducido la fiabilidad del sistema. Un gráfico del índice a lo largo del tiempo identifica rápidamente el momento en que comenzaron a producirse incidencias. El informe de estabilidad del sistema proporciona detalles que ayudan a determinar la causa de la pérdida de fiabilidad. Ver los cambios producidos (instalación o eliminación de aplicaciones, actualizaciones del sistema operativo o agregación o modificación de controladores) junto a los errores (errores de aplicaciones, bloqueos del sistema operativo o errores de hardware) permite desarrollar rápidamente una estrategia para abordar las incidencias.

Una **interfaz de asistente** permite ahora agregar contadores a archivos de registro y programar su inicio, finalización y duración. Además, los administradores del sistema pueden guardar esta configuración como plantilla para recopilar el mismo registro en otro equipo sin necesidad de repetir la selección de recopiladores de datos y la programación de procesos. En el Monitor de confiabilidad y rendimiento de Windows si incorporaron características de Registros y alertas de rendimiento para su uso con cualquier conjunto de recopiladores de datos.

