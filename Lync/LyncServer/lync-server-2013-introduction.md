---
title: 'Lync Server 2013: Introducción'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8879bd2f3638df17215b7b8f0ee4a12c751277f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Introducción a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

Lync Server 2013 y su software cliente, como Lync 2013, permiten a los usuarios conectarse de nuevas maneras y permanecer conectados, independientemente de su ubicación física. Lync y Lync Server reúnen las diferentes maneras en las que las personas se comunican en una única interfaz de cliente, se implementan como una plataforma unificada y se administran a través de una única infraestructura de administración.

Esta tabla y las siguientes secciones ilustran los conjuntos de características principales, o las *cargas de trabajo*, que Lync Server proporciona a los usuarios.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Simula</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mensajería instantánea (MI) y presencia</p></td>
<td><p>La mensajería instantánea (mi) y el estado de presencia ayudan a los usuarios a buscar y comunicarse entre sí de manera eficiente y eficaz.</p>
<p>La mensajería instantánea proporciona una plataforma de mensajería instantánea con el historial de conversaciones y admite la conectividad de mensajería instantánea pública con usuarios de redes de mensajería instantánea pública, como MSN/Windows Live, Yahoo!, AOL y Google Talk.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de fin de vida de junio de 2014 para AOL y Yahoo! ha sido anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo! Mensajería. La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard. La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</P></LI></UL>


</div>
<p>La presencia establece y muestra la disponibilidad y el uso personal de un usuario para comunicarse a través del uso de Estados comunes como <strong>disponible</strong> u <strong>ocupado</strong>, así como de Estados más detallados, como <strong>ser devuelto</strong> y <strong>no molestar</strong>. Esta variada información de presencia permite que otros usuarios hagan opciones de comunicación eficaces inmediatamente.</p></td>
</tr>
<tr class="even">
<td><p>Conferencias</p></td>
<td><p>Lync Server incluye compatibilidad con conferencias de mensajería instantánea, conferencias de audio, conferencias web, videoconferencias y uso compartido de aplicaciones para reuniones programadas y no planeadas. Todos estos tipos de reunión son compatibles con un solo cliente. Lync Server también admite las conferencias de acceso telefónico local para que los usuarios de teléfonos de red telefónica pública conmutada (RTC) puedan participar en la parte de audio de las conferencias.</p>
<p>Las conferencias pueden cambiar y crecer sin problemas en tiempo real. Por ejemplo, una sola Conferencia puede comenzar solo como mensajes instantáneos entre unos pocos usuarios y escalar a una conferencia de audio con el uso compartido de escritorio y una audiencia más grande al instante, fácilmente y sin interrumpir el flujo de conversación.</p></td>
</tr>
<tr class="odd">
<td><p>Telefonía IP empresarial</p></td>
<td><p><em>Telefonía IP empresarial</em> es la oferta de voz sobre el protocolo de Internet (VoIP) de Lync Server. Ofrece una opción de voz para mejorar o reemplazar sistemas tradicionales de centrales de conmutación (PBX). Además de las capacidades de telefonía completas de un PBX IP, Enterprise Voice se integra con presencia, mensajería instantánea, colaboración y reuniones enriquecidas. Las características, como la respuesta a la llamada, mantener, reanudar, transferir, reenviar y desviar son directamente compatibles, mientras que las teclas de marcado rápido se reemplazan por las listas de contactos y la intercomunicación automática se reemplaza por mi.</p>
<p>Enterprise Voice es compatible con la alta disponibilidad mediante control de admisión de llamadas (CAC), la supervivencia de las sucursales y las opciones extendidas para la resiliencia de datos.</p></td>
</tr>
<tr class="even">
<td><p>Soporte técnico para usuarios remotos</p></td>
<td><p>Puede proporcionar toda la funcionalidad de Lync Server a los usuarios que se encuentren fuera de los firewalls de la organización si implementan servidores denominados <em>servidores perimetrales</em> para proporcionar una conexión a estos usuarios remotos. Estos usuarios remotos pueden conectarse a conferencias usando un equipo personal con Lync 2013 instalado, el teléfono o una interfaz Web.</p>
<p>La implementación de servidores perimetrales también le permite <em>federar</em> a organizaciones de socios o proveedores. Una relación federada permite a los usuarios poner a los usuarios federados en sus listas de contactos, intercambiar información de presencia y mensajes instantáneos con estos usuarios e invitarlos a llamadas de audio, videollamadas y conferencias.</p></td>
</tr>
<tr class="odd">
<td><p>Compatibilidad con clientes móviles</p></td>
<td><p>Además, con los servicios de movilidad de Lync Server, los usuarios pueden tener acceso a la funcionalidad de Lync al usar dispositivos móviles compatibles con Apple iOS, Android, Windows Phone o Nokia, y realizar estas actividades como enviar y recibir mensajes instantáneos, ver contactos, y ver la presencia. Además, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, llamar a través del trabajo, acceso a un número único, correo de voz y llamadas perdidas. Las notificaciones push también son compatibles con los dispositivos móviles que no son compatibles con aplicaciones que se ejecutan en segundo plano.</p></td>
</tr>
<tr class="even">
<td><p>Integración con otros productos</p></td>
<td><p>Lync Server se integra con otros productos para proporcionar ventajas adicionales a los usuarios y administradores.</p>
<p>Las herramientas de reuniones están integradas en Outlook para permitir a los organizadores programar una reunión o iniciar una conferencia improvisada con un solo clic y facilitar la participación de los asistentes.</p>
<p>La información de presencia está integrada en Outlook y SharePoint.</p>
<p>La mensajería unificada de Exchange (UM) proporciona varias características de integración. Los usuarios pueden ver si tienen el nuevo correo de voz dentro de Lync Server. Pueden hacer clic en un botón reproducir del mensaje de Outlook para oír el correo de voz de audio o ver una transcripción del correo de voz en el mensaje de notificación.</p>
<p>Además, la ejecución de Lync Server 2013 con Exchange 2013 habilita varias características nuevas, como un almacén de contactos unificado al que pueden acceder los clientes de ambos productos, así como las fotos de alta resolución de los contactos que se almacenan en la base de datos de Exchange 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Implementación simple</p></td>
<td><p>Para ayudarle a planear e implementar sus clientes y servidores, Lync Server proporciona el generador de topología.</p>
<p>El generador de topología es un componente de instalación de Lync Server. El generador de topología se usa para crear, ajustar y publicar su topología planeada. También valida su topología antes de empezar con las instalaciones del servidor. Al instalar Lync Server en servidores individuales, el programa de instalación implementa el servidor tal como se indica en la topología.</p></td>
</tr>
<tr class="even">
<td><p>Administración simple</p></td>
<td><p>Después de implementar Lync Server, ofrece las siguientes herramientas de administración simplificada y eficaz:</p>
<ul>
<li><p>Administración de la configuración central, que le permite administrar los cambios de forma centralizada y hacer que se repliquen rápidamente en toda la implementación.</p></li>
<li><p>Panel de control de Lync Server, interfaz gráfica de usuario basada en web para administradores. Con esta interfaz de usuario basada en Web, los administradores de Lync Server pueden administrar sus sistemas desde cualquier lugar de la red corporativa, sin necesidad de instalar un software de administración especializado en sus equipos.</p></li>
<li><p>Herramienta de administración de la línea de comandos del shell de administración de Lync Server, que se basa en la interfaz de línea de comandos de Windows PowerShell. Proporciona un conjunto de comandos enriquecido para la administración de todos los aspectos del producto y permite a los administradores de Lync Server automatizar tareas repetitivas usando una herramienta conocida.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Aunque las características de mensajería instantánea y de presencia se instalan automáticamente en todas las implementaciones de Lync Server, puede elegir si desea implementar las conferencias, la telefonía IP empresarial y el acceso de usuarios remotos para adaptar la implementación a las necesidades de su organización.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Mensajería instantánea (MI) y presencia en Lync Server 2013](lync-server-2013-im-and-presence.md)

  - [Conferencias en Lync Server 2013](lync-server-2013-conferencing.md)

  - [Telefonía IP empresarial en Lync Server 2013](lync-server-2013-enterprise-voice.md)

  - [Escalabilidad con Lync Server 2013](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

