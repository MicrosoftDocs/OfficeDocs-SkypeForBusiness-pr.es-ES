---
title: 'Lync Server 2013: Introducción'
TOCTitle: Introducción a Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48276183
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Introducción a Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Lync Server 2013 y su software cliente, como por ejemplo Lync 2013, habilitan a los usuarios para conectarse de formas nuevas y permanecer conectados independientemente de su ubicación física. Lync y Lync Server aúnan las distintas formas en las que las personas se pueden comunicar con una interfaz de cliente única, se implementan como una plataforma unificada y se administran a través de una infraestructura de administración única.

Esta tabla y las secciones siguientes ilustran los conjuntos de características principales o *cargas de trabajo* que proporciona Lync Server para los usuarios.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Carga de trabajo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mensajería instantánea (IM) y presencia</p></td>
<td><p>La mensajería instantánea y la presencia ayudan a los usuarios a buscarse y comunicarse entre sí de forma eficaz y efectiva.</p>
<p>La mensajería instantánea ofrece una plataforma de mensajería instantánea con un historial de conversación y admite conectividad con la mensajería instantánea pública con usuarios de redes públicas para este tipo de mensajería, como por ejemplo, MSN/Windows Live, Yahoo!, AOL y Google Talk.</p>

> [!IMPORTANT]  
> <ul>
> <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
> <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
> <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
> </ul>

<p>La presencia establece y muestra la disponibilidad personal de un usuario, así como su deseo de comunicarse, para lo cual usa unos estados comunes como <strong>Disponible</strong> u <strong>Ocupado</strong> , así como estados más detallados como <strong>Vuelvo enseguida</strong> y <strong>No molestar</strong> . Esta información enriquecida sobre la presencia hace posible que otros usuarios realicen de forma inmediata elecciones de comunicación efectivas.</p></td>
</tr>
<tr class="even">
<td><p>Conferencia</p></td>
<td><p>Lync Server incluye compatibilidad para conferencias de mensajería instantánea, audioconferencias, conferencias web, videoconferencias y uso compartido de aplicaciones para reuniones programadas e improvisadas. Todos estos tipos de reunión se admiten con un solo cliente. Lync Server admite asimismo conferencias de acceso telefónico, de forma que los usuarios de teléfonos de red telefónica conmutada (RTC) puedan participar en la parte de audio de las conferencias.</p>
<p>Las conferencias pueden cambiar y crecer en tiempo real sin ningún tipo de problema. Por ejemplo, una sola conferencia puede iniciarse a modo de mensajes instantáneos entre varios usuarios y puede ampliarse a una conferencia de audio con uso compartido de escritorio y con una audiencia más amplia de forma instantánea, con facilidad, y sin necesidad de interrumpir el flujo de la conversación.</p></td>
</tr>
<tr class="odd">
<td><p>Telefonía IP empresarial</p></td>
<td><p><em>Enterprise Voice</em> es el protocolo de voz a través de IP (VoIP) que se ofrece en Lync Server. Aporta una opción de voz para mejorar o sustituir los sistemas de central de conmutación (PBX) tradicionales. Además de las capacidades íntegras de telefonía de un sistema PBX IP, Enterprise Voice está integrado con funcionalidad de presencia enriquecida, mensajería instantánea, colaboración y reuniones. Se admiten directamente características como respuesta a llamadas, espera, reanudación, transferencia y desvío, mientras que las teclas de marcado rápido personalizadas se sustituyen por listas de contactos y la intercomunicación automática por mensajería instantánea.</p>
<p>Enterprise Voice admite una gran disponibilidad a través del control de admisión de llamadas (CAC), supervivencia de sucursales y opciones ampliadas para la resistencia de datos.</p></td>
</tr>
<tr class="even">
<td><p>Compatibilidad para usuarios remotos</p></td>
<td><p>Puede proporcionar funcionalidad íntegra de Lync Server para usuarios que no estén actualmente protegidos por los firewalls de la organización; para ello, implemente servidores denominados <em>servidores perimetrales</em> con el fin de proporcionar una conexión para estos usuarios remotos. Dichos usuarios se pueden conectar a conferencias mediante un ordenador personal que tenga instalado Lync 2013, un teléfono o una interfaz web.</p>
<p>La implementación de servidores perimetrales también le permite <em>federarse</em> con organizaciones de socios o proveedores. Con una relación federada, los usuarios pueden poner a usuarios federados en sus listas de contactos, intercambiar información de presencia y mensajes instantáneos con estos usuarios, además de invitarlos a llamadas de audio, llamadas de vídeo y a conferencias.</p></td>
</tr>
<tr class="odd">
<td><p>Compatibilidad con clientes móviles</p></td>
<td><p>Además, con los servicios de movilidad de Lync Server, sus usuarios pueden obtener acceso a la funcionalidad de Lync al usar dispositivos móviles con Apple iOS, Android, Windows Phone o Nokia, y llevar a cabo actividades como el envío y la recepción de mensajes instantáneos, ver contactos y presencia. Asimismo, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y llamadas perdidas. También se admiten las notificaciones push para dispositivos móviles que no admiten aplicaciones en ejecución en segundo plano.</p></td>
</tr>
<tr class="even">
<td><p>Integración con otros productos</p></td>
<td><p>Lync Server se integra con diversos productos para proporcionar ventajas adicionales a usuarios y administradores.</p>
<p>Las herramientas de reunión se integran en Outlook para permitir que los organizadores programen una reunión o inicien una conferencia espontánea con un solo clic y hacen que sea igual de sencilla la asistencia de los participantes.</p>
<p>La información de presencia se integra en Outlook y en SharePoint.</p>
<p>La mensajería unificada (MU) de Exchange proporciona diversas características de integración. Los usuarios pueden ver si tienen correos de voz nuevos en Lync Server. Pueden hacer clic en un botón de reproducción en el mensaje de Outlook para oír el mensaje de voz o ver una transcripción de este en el mensaje de notificación.</p>
<p>Además, al ejecutar Lync Server 2013 con Exchange 2013 se habilitan nuevas características como un almacén de contactos unificados al que los clientes de ambos productos pueden obtener acceso, así como fotografías de alta resolución para contactos que se almacenan en la base de datos de Exchange 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Implementación sencilla</p></td>
<td><p>Para ayudarle a planear e implementar los servidores y clientes, Lync Server proporciona Generador de topologías.</p>
<p></p>
<p>Generador de topologías es un componente de instalación de Lync Server. Generador de topologías se usa para crear, ajustar y publicar la topología planeada. Asimismo, valida la topología antes de comenzar a realizar las instalaciones del servidor. Cuando instala Lync Server en servidores individuales, el programa de instalación implementa el servidor tal como se indica en la topología.</p></td>
</tr>
<tr class="even">
<td><p>Administración sencilla</p></td>
<td><p>Una vez haya implementado Lync Server, obtendrá las eficaces y simplificadas herramientas de administración siguientes:</p>
<ul>
<li><p>Administración de configuración central, que le permite administrar cambios de manera centralizada y hacer que se repliquen rápidamente a toda la implementación.</p></li>
<li><p>Panel de control de Lync Server, una interfaz de usuario gráfica basada en web para administradores. Con esta interfaz de usuario basada en web, los administradores de Lync Server pueden administrar sus sistemas desde cualquier punto de la red corporativa, sin necesidad de tener instalado en sus equipos ningún tipo de software de administración especializado.</p></li>
<li><p>La herramienta de administración de línea de comandos de Shell de administración de Lync Server, que está basada en Interfaz de la línea de comandos Windows PowerShell. Ofrece un conjunto de comandos enriquecidos para la administración de todos los aspectos del producto, y habilita a los administradores de Lync Server para que puedan automatizar las tareas repetitivas mediante una herramienta que les resulte familiar.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Aunque las características de mensajería instantánea (IM) y presencia se instalan automáticamente en cada implementación de Lync Server, puede elegir si implementar las conferencias, Enterprise Voice y el acceso remoto de usuarios para personalizar la implementación según las necesidades de la organización.

## En esta sección

  - [Mensajería instantánea (MI) y presencia en Lync Server 2013](lync-server-2013-im-and-presence.md)

  - [Conferencias en Lync Server 2013](lync-server-2013-conferencing.md)

  - [Telefonía IP empresarial en Lync Server 2013](lync-server-2013-enterprise-voice.md)

  - [Escalabilidad con Lync Server 2013](lync-server-2013-scalability.md)

