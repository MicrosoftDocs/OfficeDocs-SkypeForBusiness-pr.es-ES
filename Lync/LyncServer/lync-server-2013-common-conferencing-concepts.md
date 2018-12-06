---
title: Conceptos comunes relativos a las conferencias en Lync Server 2013
TOCTitle: Conceptos comunes relativos a las conferencias en Lync Server 2013
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49889510
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conceptos comunes relativos a las conferencias en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-19_

Todos los tipos de conferencias tienen varios conceptos en común. Se describen en las siguientes secciones.

## Directivas y administración de ancho de banda

Lync Server 2013 permite a los administradores establecer directivas para los tipos de reuniones que los usuarios pueden organizar. Esto ayuda a aplicar las directivas de la organización y a controlar el uso de ancho de banda. Puede definirse una gran variedad de directivas de reunión y asignarlas a usuarios individuales y grupos de usuarios. También se pueden establecer las directivas que rigen las conversaciones de punto a punto. Para obtener más información sobre cómo establecer directivas de conferencia, consulte [Directivas de conferencia de Lync Server 2013](lync-server-2013-conferencing-policies.md) en la documentación sobre operaciones. Para obtener más información sobre administración de ancho de banda, consulte [Información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) y [Configuración de ancho de banda de vídeo en Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

## Características de Archivado y Cumplimiento

Lync Server 2013 proporciona características que se pueden usar si la organización debe seguir normativas de cumplimiento. Pueden usarse las capacidades de archivado para archivar contenido presentado en las reuniones, así como el contenido de conversaciones y conferencias de mensajería instantánea (MI). Para obtener más información, consulte [Planificar el archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación sobre planeamiento. Puede usar las características de cumplimiento de Servidor de Chat persistente para archivar conversaciones con varios participantes y basadas en temas que persistan durante mucho tiempo. Para obtener más información, consulte [Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación sobre planeamiento.

## Función de supervisión

La función Servidor de supervisión permite capturar registros de detalles de llamadas (CDR) que puede usar para controlar qué usuarios hablan con qué otros usuarios mediante Lync Server 2013. Para obtener más información sobre cómo implementar y configurar la supervisión, consulte [Implementación de supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md).

## Habilitar la participación externa en conferencias

Puede aumentar enormemente los beneficios de su inversión en conferencias de Lync Server 2013 si habilita a usuarios externos para que participen también en conferencias cuando se les invite. Entre los usuarios externos se pueden incluir:

  - **Usuarios remotos**   Los propios usuarios de su organización cuando están trabajando desde fuera de los firewalls y están usando sus equipos portátiles u otros dispositivos de Lync Server 2013.

  - **Usuarios federados**   Usuarios de compañías con las que colabora y que también ejecutan Lync Server 2013. Para habilitar a sus usuarios para que se pongan en contacto fácilmente con estos usuarios, cree relaciones federadas con estas compañías.

  - **Usuarios anónimos**   Cualquier otro usuario externo al que sus usuarios inviten específicamente a unirse a determinadas conferencias. Un organizador de reuniones de su compañía puede enviar una invitación por correo electrónico a un usuario externo para una conferencia. El correo electrónico incluye un vínculo en el que el usuario externo puede hacer clic para unirse a la conferencia.

Para habilitar uno o todos estos escenarios, deberá implementar un servidor perimetral para que le ayude a habilitar comunicaciones seguras entre su implementación de Lync Server 2013 y los usuarios externos. La solución Lync Server 2013 con servidores perimetrales proporciona medios de mayor calidad que otras soluciones como, por ejemplo, una red privada virtual (VPN). Para obtener más información, consulte [Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

Además, tanto si su organización implementa o no servidores perimetrales, puede habilitar usuarios (ya sean de dentro o de fuera de la organización) para que realicen marcados desde teléfonos RTC para unirse a conferencias de audio locales. Esto se logra mediante la implementación de conferencia de acceso telefónico local de Lync Server 2013.

## Compatibilidad entre tipos de reunión y versiones de cliente

Si va a hacer que Lync Server 2013 interactúe con versiones anteriores de Office Communications Server y sus clientes, debe conocer los aspectos siguientes:

  - Los usuarios que empleen Lync Server 2013 no pueden programar conferencias de Live Meeting ni modificar ninguna reunión migrada de este tipo.

  - Los usuarios que empleen Lync Server 2013 y necesiten participar en conferencias de Live Meeting hospedadas en servidores que funcionen con Office Communications Server 2007 R2 deben tener instalado en su equipo el cliente de Live Meeting (además de Lync Server 2013) para participar en dichas reuniones.

  - Al migrar conferencias en línea de Live Meeting a Lync Server 2013, el contenido de la reunión no se migra. Si necesita dicho contenido, deberá volver a cargarlo.

