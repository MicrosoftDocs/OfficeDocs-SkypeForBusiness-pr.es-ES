---
title: Lync Server 2013 introducción
description: Lync Server 2013 Introduction.
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
ms.openlocfilehash: fac65eec8334ff96b32e5a01d72386e677ec19b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553136"
---
# <a name="introduction-to-lync-server-2013"></a>Introducción a Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

Lync Server 2013 y su software de cliente, como Lync 2013, permiten que los usuarios se conecten de manera nueva y permanezcan conectados, independientemente de su ubicación física. Lync y Lync Server reúnen las distintas formas que se comunican los usuarios en una única interfaz de cliente, se implementan como una plataforma unificada y se administran a través de una única infraestructura de administración.

Esta tabla y las siguientes secciones ilustran los conjuntos de características principales, o *cargas de trabajo*, que Lync Server proporciona a los usuarios.


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
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo! Service. La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</P></LI></UL>


</div>
<p>La presencia establece y muestra la disponibilidad personal de un usuario, así como su deseo de comunicarse, para lo cual usa unos estados comunes como <strong>Disponible</strong> u <strong>Ocupado</strong>, así como estados más detallados como <strong>Vuelvo enseguida</strong> y <strong>No molestar</strong>. Esta información enriquecida sobre la presencia hace posible que otros usuarios realicen de forma inmediata elecciones de comunicación efectivas.</p></td>
</tr>
<tr class="even">
<td><p>Conferencia</p></td>
<td><p>Lync Server incluye compatibilidad con conferencias de mensajería instantánea, audioconferencias, conferencias web, videoconferencias y uso compartido de aplicaciones, tanto para reuniones programadas como improvisadas. Todos estos tipos de reunión se admiten con un solo cliente. Lync Server también admite conferencias de acceso telefónico local, de modo que los usuarios de teléfonos de red telefónica conmutada (RTC) puedan participar en la parte de audio de las conferencias.</p>
<p>Las conferencias pueden cambiar y crecer en tiempo real sin ningún tipo de problema. Por ejemplo, una sola conferencia puede iniciarse a modo de mensajes instantáneos entre varios usuarios y puede ampliarse a una conferencia de audio con uso compartido de escritorio y con una audiencia más amplia de forma instantánea, con facilidad, y sin necesidad de interrumpir el flujo de la conversación.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice</p></td>
<td><p>La <em>telefonía IP empresarial</em> es la oferta de protocolo de voz sobre IP (VoIP) de Lync Server. Aporta una opción de voz para mejorar o sustituir los sistemas de central de conmutación (PBX) tradicionales. Además de las capacidades íntegras de telefonía de un sistema PBX IP, Enterprise Voice está integrado con funcionalidad de presencia enriquecida, mensajería instantánea, colaboración y reuniones. Se admiten directamente características como respuesta a llamadas, espera, reanudación, transferencia y desvío, mientras que las teclas de marcado rápido personalizadas se sustituyen por listas de contactos y la intercomunicación automática por mensajería instantánea.</p>
<p>Enterprise Voice admite una gran disponibilidad a través del control de admisión de llamadas (CAC), supervivencia de sucursales y opciones ampliadas para la resistencia de datos.</p></td>
</tr>
<tr class="even">
<td><p>Compatibilidad para usuarios remotos</p></td>
<td><p>Puede proporcionar la funcionalidad completa de Lync Server a los usuarios que están actualmente fuera de los firewalls de la organización mediante la implementación de servidores denominados <em>servidores perimetrales</em> para proporcionar una conexión a estos usuarios remotos. Estos usuarios remotos pueden conectarse a conferencias con un equipo personal con Lync 2013 instalado, el teléfono o una interfaz Web.</p>
<p>La implementación de servidores perimetrales también le permite <em>federarse</em> con organizaciones de socios o proveedores. Con una relación federada, los usuarios pueden poner a usuarios federados en sus listas de contactos, intercambiar información de presencia y mensajes instantáneos con estos usuarios, además de invitarlos a llamadas de audio, llamadas de vídeo y a conferencias.</p></td>
</tr>
<tr class="odd">
<td><p>Compatibilidad con clientes móviles</p></td>
<td><p>Además, con los servicios de movilidad de Lync Server, los usuarios pueden acceder a la funcionalidad de Lync cuando usan dispositivos móviles Apple iOS, Android, Windows Phone o Nokia compatibles, y realizan actividades como enviar y recibir mensajes instantáneos, ver contactos y ver presencia. Asimismo, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y llamadas perdidas. También se admiten las notificaciones push para dispositivos móviles que no admiten aplicaciones en ejecución en segundo plano.</p></td>
</tr>
<tr class="even">
<td><p>Integración con otros productos</p></td>
<td><p>Lync Server se integra con varios otros productos para proporcionar ventajas adicionales a los usuarios y administradores.</p>
<p>Las herramientas de reunión se integran en Outlook para permitir que los organizadores programen una reunión o inicien una conferencia improvisada con un solo clic, y que sea tan fácil unirse a los asistentes.</p>
<p>La información de presencia está integrada en Outlook y SharePoint.</p>
<p>La mensajería unificada (MU) de Exchange proporciona diversas características de integración. Los usuarios pueden ver si tienen correo de voz nuevo en Lync Server. Pueden hacer clic en un botón de reproducción en el mensaje de Outlook para oír el mensaje de voz o ver una transcripción de este en el mensaje de notificación.</p>
<p>Además, la ejecución de Lync Server 2013 con Exchange 2013 habilita varias características nuevas, como un almacén de contactos unificado al que pueden obtener acceso los clientes de ambos productos, así como fotos de alta resolución para los contactos que se almacenan en la base de datos de Exchange 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Implementación sencilla</p></td>
<td><p>Para ayudarle a planear e implementar los servidores y clientes, Lync Server proporciona el generador de topologías.</p>
<p>El generador de topologías es un componente de instalación de Lync Server. El generador de topologías se usa para crear, ajustar y publicar la topología planeada. Asimismo, valida la topología antes de comenzar a realizar las instalaciones del servidor. Al instalar Lync Server en servidores individuales, el programa de instalación implementa el servidor tal como se indicó en la topología.</p></td>
</tr>
<tr class="even">
<td><p>Administración sencilla</p></td>
<td><p>Después de implementar Lync Server, ofrece las siguientes herramientas de administración mejoradas y eficaces:</p>
<ul>
<li><p>Administración de configuración central, que le permite administrar cambios de manera centralizada y hacer que se repliquen rápidamente a toda la implementación.</p></li>
<li><p>Panel de control de Lync Server, una interfaz gráfica de usuario basada en web para los administradores. Con esta interfaz de usuario basada en Web, los administradores de Lync Server pueden administrar sus sistemas desde cualquier lugar de la red corporativa, sin necesidad de instalar software de administración especializado en sus equipos.</p></li>
<li><p>Herramienta de administración de línea de comandos del shell de administración de Lync Server, que se basa en la interfaz de línea de comandos de Windows PowerShell. Proporciona un conjunto de comandos enriquecidos para la administración de todos los aspectos del producto y permite a los administradores de Lync Server automatizar tareas repetitivas con una herramienta conocida.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Aunque las características de mensajería instantánea y presencia se instalan automáticamente en todas las implementaciones de Lync Server, puede elegir si desea implementar la Conferencia, la telefonía IP empresarial y el acceso de usuarios remotos para adaptar la implementación a las necesidades de su organización.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Mensajería instantánea y presencia en Lync Server 2013](lync-server-2013-im-and-presence.md)

  - [Conferencias en Lync Server 2013](lync-server-2013-conferencing.md)

  - [Telefonía IP empresarial en Lync Server 2013](lync-server-2013-enterprise-voice.md)

  - [Escalabilidad con Lync Server 2013](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

