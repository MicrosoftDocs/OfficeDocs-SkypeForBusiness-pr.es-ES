---
title: Instalación de los paquetes de administración de Lync Server 2013
TOCTitle: Instalación de los paquetes de administración de Lync Server 2013
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48276444
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalación de los paquetes de administración de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Por sí mismo, System Center Operations Manager tiene la capacidad de supervisar solo una pequeña parte del sistema operativo Windows. Pero puede extender las capacidades de System Center Operations Manager instalando módulos de administración, software que determina los elementos que System Center Operations Manager puede supervisar, cómo deben supervisarse estos elementos, y cómo deben desencadenarse y notificarse las alertas. Microsoft Lync Server 2013 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes capacidades:

  - El módulo de administración de componentes y usuarios (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) hace un seguimiento de los problemas de Lync Server que se han registrado en los registros de eventos, desde los contadores de rendimiento, en los registros detallados de llamadas (CDR) o en las bases de datos de calidad de la experiencia (QoE). Si se detectan problemas graves, System Center Operations Manager puede configurarse para notificarlos inmediatamente a los administradores a través del correo electrónico, mensajes instantáneos o del servicio de mensajes cortos (SMS). SMS es la tecnología que se usa para enviar mensajes de texto entre dispositivos móviles.
    

    > [!NOTE]
    > Para más información sobre cómo configurar de la notificación de Operations Manager, consulte Configuración de notificaciones en la Biblioteca de TechNet en <A href="http://go.microsoft.com/fwlink/?linkid=268785%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268785&amp;clcid=0xC0A</A>.



  - El módulo de supervisión activa (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) prueba de forma proactiva componentes clave de Lync Server, como el inicio de sesión en el sistema, el intercambio de mensajes instantáneos o la realización de llamadas a un teléfono que se encuentra en una Red telefónica conmutada (RTC). Estas pruebas se llevan a cabo con los cmdlets de transacción sintética de Lync Server. Por ejemplo, el cmdlet **Test-CsIM** se usa para simular una conversación de mensajería instantánea entre dos usuarios de prueba. Si esta conversación de mensajería simulada tiene errores, se genera una alerta.

Los dos módulos de administración incluidos con Lync Server 2013 cuentan con numerosas mejoras en relación con los módulos de administración que se usan con Microsoft Lync Server 2010. Por ejemplo, el módulo de administración de componentes de Lync Server 2013 no se limita a la supervisión de Lync Server. Además de supervisar registros de eventos y contadores de rendimiento para Lync Server, este módulo también hace un seguimiento del rendimiento de los elementos vitales y emite alertas para ellos. Estos elementos pueden ser:

  - **Internet Information Services (IIS)**   Se emitirán alertas si Internet Information Services se desconecta. Esto es importante porque los servicios web de Lync Server dependen de IIS.

  - **Uso de procesos**   Se emitirán alertas si empiezan a escasear recursos del sistema (como la memoria disponible). Estas alertas se emitirán aunque Lync Server no sea el responsable del uso intensivo del sistema.

  - **Eventos de errores de PC**   Se emitirán alertas si se produce un problema de hardware o software que ponga en peligro la viabilidad de un servidor. Por ejemplo, los administradores de Lync Server recibirán una notificación si parece que un servidor está en peligro de sufrir un error de disco duro.

En los nuevos módulos de administración también se ha mejorado la creación de informes. Algunos de los nuevos informes para Lync Server 2013 son:

  - **Informe de disponibilidad de situación de descentralización**   Este informe detalla la disponibilidad o el tiempo de actividad de servicios clave de Lync Server, como el registro o la presencia.

  - **Informe de capacidad**   Con información de los contadores de rendimiento, este informe muestra las tendencias de los componentes del sistema, como la disponibilidad de memoria y el uso del procesador.

  - **Informe de componentes**   Este informe enumera los componentes que más alertas generan agrupados por componentes de Lync Server.

Además de estos informes prediseñados, los módulos de administración de Lync Server 2013 notifican automáticamente alertas para los estados de confiabilidad de llamadas (según las métricas del registro detallado de llamadas) y QoE (según las métricas de calidad de la experiencia). Si ha habilitado el registro detallado de llamadas, siga este procedimiento desde la consola de System Center Operations Manager para revisar las alertas de confiabilidad de llamadas:

  - Expanda **Supervisión**, **Estado de Microsoft Lync Server 2013** y **Confiabilidad de llamadas y calidad de medios**, y haga clic en **Confiabilidad de llamadas**.

Para ver las alertas de calidad de la experiencia, complete este procedimiento desde la consola de System Center Operations Manager:

  - Expanda **Supervisión**, **Estado de Microsoft Lync Server 2013**, **Confiabilidad de llamadas y calidad de medios** y **Calidad de medios**.

Los módulos de administración de Lync Server 2013 ahora usan la detección en el nivel de máquina en lugar del mecanismo de detección central que se usa en Microsoft Lync Server 2010. Esto significa que cada agente de System Center básicamente se detecta a sí mismo y notifica su existencia a Servidor de administración central. Con la detección en el nivel de máquina, se simplifica la administración de la infraestructura de System Center y también se permite que coexistan diferentes versiones de los módulos de administración de Lync Server (por ejemplo, los módulos de Lync Server 2010 y los de Lync Server 2013).

