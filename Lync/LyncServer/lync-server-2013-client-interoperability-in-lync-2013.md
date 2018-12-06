---
title: 'Lync Server 2013: Interoperabilidad de clientes en Lync 2013'
TOCTitle: Interoperabilidad de clientes en Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48274447
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Interoperabilidad de clientes en Lync 2013

 

_**Última modificación del tema:** 2016-03-04_

Este tema trata la capacidad de los clientes de Microsoft Lync Server 2013 para coexistir e interactuar con versiones anteriores de clientes de Lync Server y Office Communications Server.

## Compatibilidad con servidores y clientes

En la siguiente tabla se muestran las combinaciones compatibles de versiones de cliente y versiones de servidor. Esta tabla indica si se admite el inicio de sesión cuando el cliente intenta conectarse al servidor indicado. Lync Server 2013 admite la versión de cliente anterior. Además, a diferencia de las versiones anteriores, Lync Server 2010 admite los nuevos clientes de Lync 2013. Esto permite a las organizaciones que realizan la actualización desde Lync Server 2010 implementar clientes nuevos independientemente de las actualizaciones de Lync Server.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cliente</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible5</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
<td><p>Incompatible</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="odd">
<td><p>Operador de Lync 2010</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="even">
<td><p>Chat en grupo de Lync 2010</p></td>
<td><p>Compatible1</p></td>
<td><p>Compatible2</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>No se admite3</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="even">
<td><p>Operador de Microsoft Office Communications Server 2007 R2</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="odd">
<td><p>Aplicación de la Tienda Windows de Lync</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
</tbody>
</table>


1Para obtener información detallada, vea [Migración del chat de grupo de Lync Server 2010 o el chat de grupo de Office Communications Server 2007 R2 al servidor de chat persistente de Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2En Microsoft Lync Server 2010, la funcionalidad de chat en grupo estaba disponible con el servidor de chat en grupo, una aplicación de confianza de terceros para Lync Server 2010. Los clientes de Lync 2013 no son compatibles con Lync Server 2010, chat en grupo.

3Lync Web App 2013 proporciona ahora una experiencia completa de reunión que incluye audio y vídeo basados en el equipo, y se lo considera el sustituto de Lync 2010 Attendee. Lync 2010 Attendee se conectará a Lync Server 2013 solo cuando use un explorador incompatible (Internet Explorer 6 o Internet Explorer 7) y Windows XP.

4Las características de mensajería instantánea y presencia de Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no lo son. Durante la migración desde Office Communications Server 2007 R2, Office Communicator 2007 R2 es adecuado para la interoperabilidad de mensajería instantánea y presencia, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.

5 Para conocer las restricciones, consulte "Compatibilidad con la característica de conferencia de clientes de Lync 2013 en reuniones de Lync Server 2010", más adelante en este tema.

## Interoperabilidad entre clientes

Con la versión de Lync Server 2013, varias versiones de clientes pueden interactuar perfectamente en escenarios de punto a punto y conferencias. En esta sección se describe la disponibilidad de la función cuando los usuarios interactúan con otros usuarios que hayan iniciado sesión usando un tipo de cliente diferente o una versión anterior del mismo cliente.

## Compatibilidad con la característica de punto a punto

Las características de punto a punto son compatibles con los usuarios que están hospedados en versiones distintas del servidor y que utilicen diferentes versiones de cliente. La experiencia del usuario final y las características disponibles consistentes con las capacidades del cliente del usuario y la versión del servidor en el cual el usuario ha iniciado sesión. Dicho de otra manera:

  - Si un usuario ha iniciado sesión en Lync Server 2013 con un cliente anterior, el usuario tendrá la misma experiencia que ya le es familiar. Ninguna de las características nuevas introducidas en Lync Server 2013 estarán disponibles hasta que se actualice el cliente del usuario. Algunos ejemplos son la vista de galería de vídeo, vídeo de alta definición, uso compartido de PowerPoint y la opción de desactivar el audio y el vídeo de todos los asistentes al entrar en la reunión. Las características nuevas se describen en [Nuevas funciones de conferencia en Lync Server 2013](lync-server-2013-new-conferencing-features.md) y [Novedades para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

  - Si un usuario ha iniciado sesión en Lync Server 2010 con un cliente de Lync 2013, todas las características nuevas no compatibles con Lync Server 2010 dejarán de estar disponibles hasta que el usuario se mueva a Lync Server 2013.

La tabla siguiente compara la disponibilidad de las características en las sesiones de punto a punto en las cuales el cliente ha iniciado sesión ya sea en Lync Server 2013 o en Lync Server 2010.


> [!NOTE]
> Lync Web App y Lync 2010 Attendee son clientes solo de reunión y no se incluyen en la tabla.




<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Cliente</th>
<th>Mensajería instantánea</th>
<th>Presencia</th>
<th>Voz</th>
<th>Vídeo</th>
<th>Uso compartido de aplicaciones</th>
<th>Transferencia de archivos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="even">
<td><p>Operador de Lync 2010</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí1</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="even">
<td><p>Mensajería instantánea pública (AOL, Yahoo!)</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Mensajería instantánea pública (MSN, Windows Live Messenger)</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]  
> <ul>
> <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
> <li><p>La PIC USL es una licencia de suscripción por usuario y mensual necesaria para que Lync Server o el servidor Office Communications Server puedan federarse con Yahoo! Messenger. La capacidad de Microsoft para prestar este servicio ha dependido siempre del soporte ofrecido por Yahoo!, cuyo acuerdo subyacente no se va a renovar.</p></li>
> <li><p>Lync es ahora más que nunca una poderosa herramienta de conexión entre empresas y con individuos de todo el mundo. La federación con Windows Live Messenger no precisa de ninguna licencia de usuario/dispositivo extra, aparte de la licencia CAL de Lync Standard. Esta lista incluirá también la federación con Skype, lo que permitirá a los usuarios de Lync llegar a cientos de millones de personas mediante voz y mensajería instantánea.</p></li>
> </ul>


1 En Office Communicator 2007 R2, solo está disponible el uso compartido de escritorio (y no el uso compartido de programas).

## Compatibilidad de la característica de conferencia de clientes de Lync 2013 en reuniones de Lync Server 2010

Cuando los usuarios se unen a reuniones de Lync Server 2010 con un cliente de Lync 2013, obtienen acceso a las características de cliente de Lync 2013, con las siguientes excepciones:

  - En las opciones de administración **Participantes**, donde puede acceder seleccionando el icono de contactos de la ventana de reuniones, la opción **No aceptar reuniones de MI** no funciona.

  - La vista Galería no funciona en las conferencias de vídeo. El usuario solo ve al hablante activo, en lugar de ver a todos los hablantes. En la lista de opciones **Seleccionar un diseño**, **Vista de galería** no se encuentra disponible.

  - La lista de participantes se muestra de manera predeterminada en las conferencias de vídeo.

  - Al hacer clic con el botón secundario en un usuario de la lista de participantes, las opciones de administración de participantes **Bloquear el foco de vídeo** y **Anclar a galería** no se encuentran disponibles.

## Compatibilidad con la característica de conferencia en reuniones de Lync Server 2013

Lync Server 2013 ofrece nuevas características de conferencia que quedan disponibles para los usuarios una vez que sus cuentas se mueven a Lync Server 2013 e inician sesión con el cliente de Lync 2013. Algunos ejemplos son la vista de galería de vídeo, vídeo de alta definición, uso compartido de PowerPoint y la opción de desactivar el audio y el vídeo de todos los asistentes al entrar en la reunión. Las características nuevas se describen en [Nuevas funciones de conferencia en Lync Server 2013](lync-server-2013-new-conferencing-features.md) y [Novedades para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

En las reuniones de Lync Server 2013, determinadas características de conferencia son compatibles con los usuarios que están hospedados en distintas versiones del servidor y que utilizan distintos clientes y versiones de clientes. Cuando los clientes se unen a una reunión de Lync Server 2013, los usuarios tienen acceso a las características y capacidades de esta tabla.


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>Cliente</th>
<th>Mensajería instantánea punto a punto</th>
<th>Voz</th>
<th>Vídeo</th>
<th>Uso compartido de aplicaciones</th>
<th>PowerPoint</th>
<th>Transferencia de archivos</th>
<th>Pizarra</th>
<th>Sondeo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí2</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí3</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R24</p></td>
<td><p>Sí</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


1 En Office Communicator 2007 R2, solo está disponible el uso compartido de escritorio (y no el uso compartido de programas).

2Lync Server 2013 usa un mecanismo actualizado para cargar los archivos de PowerPoint. Los usuarios de Lync Web App que se unen a una reunión que se haya programado originariamente en Lync Server 2010 pueden ver y navegar por las presentaciones de PowerPoint, pero no pueden actualizar los archivos de PowerPoint.

3 Si la reunión se programó en Lync Server 2013 y las dispositivas de PowerPoint se cargaron mediante un cliente de Lync 2013, los usuarios de Lync 2010 tienen acceso de solo lectura a las diapositivas. Por el contrario, si un usuario de Lync 2010 cargó las diapositivas de PowerPoint, los usuarios de Lync Server 2013 podrán verlas y, si el servidor de aplicaciones web de Office está configurado, podrán acceder a nuevas funciones como una pantalla de mayor resolución, animaciones, transiciones de diapositivas y vídeo incrustado. Para obtener más información, consulte [Configuración de la integración de Office Web Apps Server y Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

4Las características de mensajería instantánea y presencia de Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no lo son. Durante la migración desde Office Communications Server 2007 R2, Office Communicator 2007 R2 es adecuado para la interoperabilidad de mensajería instantánea y presencia, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.

## Compatibilidad con el complemento de programación

La compatibilidad del servidor con varios complementos de programación es consistente con la compatibilidad de versión del cliente y del servidor. En general, los siguientes complementos de programación son compatibles con Lync Server 2013. Sin embargo, las versiones anteriores de complementos no proporcionan nuevas características de complemento de Lync 2013 como la opción de desactivar el audio y el vídeo de todos los asistentes al entrar en la reunión.

  - **Complemento para conferencia en línea para Lync 2013** Proporciona las mismas características que el complemento de Online Meeting para Lync 2010, y además incluye controles para desactivar el audio de los asistentes, que permiten a los organizadores de la reunión programas conferencias que tengan el audio y el vídeo de los asistentes desactivados de manera predeterminada. Los administradores también pueden personalizar las invitaciones de la organización para la reunión agregando un logo personalizado, una URL de ayuda, una dirección URL del aviso legal o un texto de pie de página personalizado.

  - **Complemento para conferencia en línea para Lync 2010**  Proporciona programación para reuniones en línea de Lync y elimina la capacidad de programar conferencias de Office Live Meeting.

  - **El complemento para conferencias de Office Communicator 2007 R2**   Proporciona programación tanto para conferencias de Office Live Meeting como conferencias de Office Communicator 2007 R2.


> [!NOTE]
> No se pueden programar conferencias de Live Meeting en Lync Server 2013.




<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cliente de programación</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Complemento para conferencia en línea para Lync 2013 (se puede usar con Office 2013, Outlook 2010 y Outlook 2007)</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible (nuevas características del complemento no disponibles)</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="even">
<td><p>Programador web de Lync 2013</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="odd">
<td><p>Complemento para conferencia en línea para Lync 2010</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="even">
<td><p>Complemento para conferencias de Office Communicator 2007 R2</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
</tbody>
</table>


## Ayuda para unirse a una conferencia

Todos los clientes compatibles con Lync Server 2013 tienen permiso para unirse a reuniones de Lync 2013. Dado que Lync Web App es un componente web del servidor, en los casos en que Lync Web App se use para unirse a una reunión de Lync Server 2013, se usa siempre la versión más reciente de Lync Web App.

Los clientes de Lync 2013 pueden unirse a las reuniones hospedadas en Lync 2010 y Office Communications Server 2007 R2 con la funcionalidad restringida. Las características de reunión están limitadas por la versión del servidor en el cual se hospeda la reunión.

## Vea también

#### Conceptos

[Requisitos de la aplicación de la Tienda Windows de Lync](lync-server-2013-lync-windows-store-app-requirements.md)  
[Nuevas funciones de conferencia en Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Novedades para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)

