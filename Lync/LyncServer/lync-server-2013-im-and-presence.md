---
title: 'Lync Server 2013: Mensajería instantánea (MI) y presencia'
TOCTitle: Mensajería instantánea (MI) y presencia
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48275551
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mensajería instantánea (MI) y presencia en Lync Server 2013

 

_**Última modificación del tema:** 2013-10-07_

La mensajería instantánea (MI) y la presencia se instalan automáticamente en cualquier implementación de Lync Server.

La información de *Presencia* permite que los usuarios puedan dirigirse a sus colegas en el momento oportuno y usando el canal de comunicación adecuado y, así, lograr un entorno de trabajo más productivo. La presencia de los usuarios es una colección de información que incluye la disponibilidad, el deseo de comunicarse, otras notas (como la ubicación y el estado) y el modo de establecer contacto con el usuario. En Lync Server, la presencia se ha ampliado con fotos, información sobre la ubicación y un conjunto completo de estados de presencia, entre los que incluyen “Día libre”, “No molestar” y “Vuelvo enseguida”, además de los estados básicos como “Disponible”, “Ocupado” y “En conferencia”. Los administradores también pueden definir estados de presencia personalizados o específicos de una organización.

Las opciones de administración de contactos y de acceso de usuarios permiten a los usuarios controlar la información que pueden ver los demás. Los usuarios pueden establecer varios niveles de contactos, que podrán ver diferentes niveles de información de presencia.

Con solo mirar la lista de contactos, los usuarios podrán encontrar de inmediato todo lo que necesiten. Unos iconos sencillos de colores indican el estado de presencia de otros usuarios, y además aparecen la foto y la ubicación.

Gracias a la integración entre Lync Server y otros productos como Outlook y SharePoint, cada vez que aparece el nombre de un contacto (por ejemplo, en un mensaje de correo electrónico o en el sitio web de un equipo), se muestra también su estado e información del estado. Además, si implementa Exchange 2013, Lync Server y Exchange 2013 podrán compartir un almacén de contactos unificados al que podrán acceder los clientes de ambos productos.

La mensajería instantánea de Lync Server permite que los usuarios puedan enviarse mensajes inmediatos con información puntual. Si lo prefiere, sus usuarios también pueden comunicarse con usuarios de redes de mensajería instantánea pública como MSN/Windows Live, Yahoo\! y AOL. Tenga en cuenta que quizá sea necesaria otra licencia para la conectividad de mensajería instantánea pública con Windows Live, AOL y Yahoo\!. Lync Server también es compatible con el protocolo extensible de mensajería y presencia (XMPP), con lo cual los usuarios podrán intercambiar mensajes de mensajería instantánea e información de presencia con usuarios de servicios XMPP como, por ejemplo, Google Talk.

> [!IMPORTANT]  
> <ul>
> <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
> <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
> <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
> </ul>


El historial de la conversación permite que los usuarios mantengan un registro de las conversaciones de mensajería instantánea antiguas, y que puedan recuperar información que hayan enviado mediante mensajería instantánea hace meses.

La característica de Chat persistente permite a los usuarios participar en conversaciones temáticas con varios participantes que perduran a lo largo del tiempo. Los mensajes enviados a los salones de chat (foros de discusión) pueden ser persistentes (esto es, disponibles en el tiempo) para que las personas en diferentes ubicaciones y departamentos puedan participar, incluso cuando no están todos en línea al mismo tiempo.

Si su organización debe seguir normativas de cumplimiento, puede implementar una característica de archivado de mensajes para almacenar el contenido de los mensajes instantáneos de todos los usuarios de su organización, o solo de algunos usuarios que se especifiquen. Si implementa Exchange 2013 también, el archivo de mensajería instantánea se puede integrar con la característica de conservación local de Exchange a fin de proporcionar una única experiencia de administración de cara al cumplimiento.

