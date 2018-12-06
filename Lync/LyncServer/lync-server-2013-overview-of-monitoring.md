---
title: 'Lync Server 2013: Información general de supervisión'
TOCTitle: Información general de supervisión
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48275411
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general de supervisión en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-05_

En Microsoft Lync Server 2013, la supervisión sirve para recopilar información sobre el uso y datos de calidad de la experiencia relativos a las sesiones de comunicación en las que participan los usuarios. Una sesión es un término genérico que abarca una conexión de usuario a:

  - Conferencia

  - Una modalidad de conferencia (como audio/vídeo o uso compartido de aplicaciones)

  - Otro usuario a través de una conversación punto a punto, como un mensaje instantáneo o una llamada de audio


> [!NOTE]
> Lync Server 2013 realiza un seguimiento de la información de cada sesión: quién llamó a quién, qué extremos se usaron en la sesión, cuánto duró la sesión, cuál fue la calidad percibida de la sesión, etc. A pesar de esto, Lync Server no registra ni almacena la llamada en sí y lo mismo sucede con las sesiones de mensajería instantánea: Lync Server registra información sobre las sesiones de mensajería instantánea, pero no mantiene un registro de cada mensaje instantáneo que se haya enviado durante la sesión.



Los detalles de llamada que Lync Server recopila pueden servir para diversos fines, como los siguientes:

  - **Rendimiento de la inversión (ROI)** . Los administradores pueden comparar los datos de uso que recopila el Servidor de supervisión con otros datos similares recopilados por el sistema de telefonía anterior para constatar el ahorro económico y justificar la implementación de Lync Server.

  - **Administración del inventario de dispositivos** . La información de administración de activos ayuda a los administradores a identificar los dispositivos antiguos que todavía se usan y que deben reemplazarse, así como aquellos que son demasiado costosos y no parece que se estén usando.

  - Servicio de asistencia. Con los datos de solución de problemas, los ingenieros pueden averiguar los motivos por los que se ha producido un error en una llamada del usuario sin tener que recopilar registros de servidor o de cliente. El personal de soporte tendrá acceso a esta información al instante, y no es necesario que posea grandes conocimientos técnicos sobre Microsoft Lync 2013 y Lync Server 2013.

  - **Solución de problemas del sistema**. Los administradores pueden detectar problemas importantes que pueden impedir que los usuarios finales lleven a cabo tareas básicas, como unirse a una conferencia, realizar una llamada o enviar un mensaje instantáneo.

Además de esta información de llamadas básica, el Servidor de supervisión también proporciona un mecanismo que permite que los extremos SIP (como Lync 2013) puedan ofrecer información de solución de problemas que, de otro modo, no estaría disponible para el servidor:

  - **Métricas de medios que inciden en la calidad** . Son métricas que se centran en la transmisión real de la llamada; es decir, ofrecen una especie de cuaderno de viaje de todo el recorrido de la llamada a través de la red. Estas métricas (que engloban aspectos como la pérdida de paquetes, la vibración y los tiempos de ida y vuelta) informan de lo que ha sucedido en la llamada desde que dejó su extremo hasta que llegó al extremo de la otra persona.

  - **Problemas notificados al usuario final** . Estas métricas incluyen las notificaciones sobre calidad deficiente que Lync 2013 muestra a los usuarios finales cuando están demasiado alejados de un micrófono, hablan muy bajo, tienen una mala conexión de red o experimentan problemas de calidad porque hay otro programa en el equipo que consume los recursos disponibles.

  - **Información del entorno**. Estas métricas detallan los factores de calidad de la llamada, como el tipo de micrófono y altavoces que se usan, si el usuario se conecta a través de una conexión VPN o si tiene una conexión inalámbrica.

Al término de cada llamada, los extremos compatibles con SIP transmiten esta información automáticamente al servidor front-end que hizo posible la llamada. No hay que hacer absolutamente nada para que esto suceda, puesto que este comportamiento está integrado en el protocolo SIP. Con todo, si desea recopilar y guardar esta información, deberá instalar y habilitar la supervisión, ya que, de no hacerlo, los agentes de los servidores front-end reunirán la información de las llamadas y la transmitirán a un par de bases de datos de SQL Server.

Observe que el proceso de instalación y configuración de la supervisión se ha simplificado en Lync Server 2013. En versiones anteriores del software, la supervisión necesitaba un rol Servidor de supervisión independiente, que solía hacer necesario otro equipo para usarlo como Servidor de supervisión. En Lync Server 2013, en cambio, este rol se ha eliminado y, en su lugar, el servicio de supervisión (en forma de "agentes de recopilación de datos unificados") se ha combinado con todos los servidores front-end. La combinación del servicio de supervisión aporta al menos dos ventajas fundamentales:

  - Disminuye el número de roles de servidor necesarios al implementar Lync Server 2013. La eliminación del rol Servidor de supervisión contribuye igualmente a reducir los costos, ya que se pone fin a la necesidad de mantener servidores dedicados exclusivamente a supervisar.

  - Se reduce la complejidad de la instalación y administración de Lync Server 2013. Al combinar los servicios de supervisión en cada servidor front-end, ya no tendrá que instalar, configurar y administrar el rol Servidor de supervisión.

Para obtener más información, vea el tema [Implementación de supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md) en la guía de implementación de Lync Server 2013.

