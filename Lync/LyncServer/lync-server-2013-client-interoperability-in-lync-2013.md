---
title: 'Lync Server 2013: Interoperabilidad de clientes en Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b28d0de09a46a2be8b968e55c8f551e397da6ae8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Interoperabilidad de clientes en Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-03-04_

En este tema se describe la capacidad de los clientes de Microsoft Lync Server 2013 para coexistir e interactuar con clientes de versiones anteriores de Lync Server y Office Communications Server.

<div>

## <a name="server-and-client-compatibility"></a>Compatibilidad de servidor y cliente

En la tabla siguiente se muestran las combinaciones compatibles de versiones de cliente y versiones de servidor. Esta tabla indica si el inicio de sesión es compatible cuando el cliente intenta conectarse al servidor indicado. Lync Server 2013 admite la versión de cliente anterior. Además, a diferencia de las versiones anteriores, Lync Server 2010 admite los nuevos clientes de Lync 2013. Esto permite a las organizaciones que están actualizando desde Lync Server 2010 implementar nuevos clientes independientes de las actualizaciones de Lync Server.


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
<td><p>Supported5</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="odd">
<td><p>Operador de Lync 2010</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Chat en grupo de Lync 2010</p></td>
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>No compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>No Supported3</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="even">
<td><p>Operador de Microsoft Office Communications Server 2007 R2</p></td>
<td><p>No compatible</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>No compatible</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>No compatible</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="odd">
<td><p>Aplicación de la Tienda Windows de Lync</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
</tr>
</tbody>
</table>


1Para obtener más información, consulte [migración desde Lync Server 2010, chat grupal u Office Communications server 2007 R2 conversación grupal a Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2In Microsoft Lync Server 2010, la funcionalidad de chats grupales estaba disponible con el servidor de chats grupales, una aplicación de confianza de terceros para Lync Server 2010. Los clientes de Lync 2013 no son compatibles con Lync Server 2010, chat grupal.

3Lync Web App 2013 ahora ofrece una experiencia de reunión completa, incluyendo el audio y el vídeo del equipo, y se considera el reemplazo de Lync 2010 asistente. El Asistente de Lync 2010 se conectará a Lync Server 2013 solo cuando esté usando un explorador no admitido (Internet Explorer 6 o Internet Explorer 7) y Windows XP.

las características de presencia y mensajería instantánea de 4The en Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no. Durante la migración de Office Communications Server 2007 R2, Office Communicator 2007 R2 es apto para la presencia y la interoperabilidad de mensajes instantáneos, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.

5 para obtener las limitaciones, consulte "soporte técnico de las características de conferencia para clientes de Lync 2013 en Lync Server 2010 reuniones" más adelante en este tema.

</div>

<div>

## <a name="interoperability-among-clients"></a>Interoperabilidad entre clientes

Con la versión de Lync Server 2013, varias versiones de cliente pueden interactuar perfectamente en escenarios de punto a punto y de conferencia. En esta sección se describe la disponibilidad de las características cuando los usuarios interactúan con otros usuarios que usan distintas versiones de clientes y servidores.

<div>

## <a name="peer-to-peer-feature-support"></a>Compatibilidad con características de punto a punto

Las características de punto a punto son compatibles con los usuarios alojados en diferentes versiones del servidor y que están usando diferentes versiones de cliente. La experiencia del usuario final y las características disponibles son coherentes con las capacidades del cliente del usuario y la versión del servidor en el que el usuario ha iniciado sesión. Dicho de otra manera:

  - Si un usuario ha iniciado sesión en Lync Server 2013 con un cliente antiguo, el usuario tendrá la misma experiencia a la que está acostumbrado. Ninguna de las nuevas características introducidas en Lync Server 2013 estará disponible hasta que se actualice el cliente del usuario. Algunos ejemplos son la vista de galería de vídeos, vídeo de alta definición, uso compartido de PowerPoint actualizado y la opción de silenciar el audio y vídeo de todos los asistentes al entrar en la reunión. Las nuevas características se describen en [las nuevas características de conferencia de Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

  - Si un usuario ha iniciado sesión en Lync Server 2010 con un cliente de Lync 2013, las nuevas características que no sean compatibles con Lync Server 2010 no estarán disponibles hasta que se mueva el usuario a Lync Server 2013.

En la tabla siguiente se compara la disponibilidad de las características de las sesiones de punto a punto en las que el cliente ha iniciado sesión en Lync Server 2013 o Lync Server 2010.

<div>


> [!NOTE]  
> Lync Web App y Lync 2010 son clientes de solo reunión y no se incluyen en esta tabla.



</div>


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
<th>Presence</th>
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
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td></td>
<td></td>
<td></td>
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
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Mensajería instantánea pública (MSN, Windows Live Messenger)</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta la fecha de cierre del servicio. Una fecha de fin de vida de junio de 2014 para AOL y Yahoo! ha sido anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>..</P>
> <LI>
> <P>El PIC USL es una licencia por usuario y por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo! Mensajería. La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el cual no se renovará.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard. La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de la mensajería instantánea y la voz.</P></LI></UL>



</div>

1 en Office Communicator 2007 R2, solo está disponible el uso compartido del escritorio (y no el uso compartido de programas).

<div>


> [!NOTE]  
> El uso compartido de escritorio entre Office Communicator 2007 R2 y Skype empresarial 2015 no se puede iniciar desde el cliente más reciente cuando se aplica la interfaz de usuario del cliente 2015 de Skype empresarial.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Compatibilidad con características de conferencia para clientes de Lync 2013 en reuniones de 2010 de Lync Server

Cuando los usuarios se unen a reuniones de Lync Server 2010 con un cliente de Lync 2013, tienen acceso a las características de cliente de Lync 2013 con las siguientes excepciones:

  - En las opciones de administración de **participantes** , a las que se puede acceder seleccionando el icono de personas en la ventana de la reunión, la opción **sin mensajería instantánea** no funciona.

  - La vista de Galería no funciona en las videoconferencias. El usuario solo ve el orador activo en lugar de todos los altavoces. En la lista de opciones de **diseño** , la **vista de Galería** no está disponible

  - La lista de participantes se muestra de forma predeterminada en las videoconferencias.

  - Al hacer clic con el botón derecho en un usuario de la lista participantes, las opciones **bloquear las imágenes destacadas** y **anclar a la Galería** no estarán disponibles.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Compatibilidad con características de conferencia en reuniones de Lync Server 2013

Lync Server 2013 proporciona nuevas características de conferencia que estarán disponibles para los usuarios después de que sus cuentas se muevan a Lync Server 2013 y que inicien sesión con el cliente de Lync 2013. Algunos ejemplos son la vista de galería de vídeos, vídeo de alta definición, uso compartido de PowerPoint y la opción de silenciar el audio y vídeo de todos los asistentes al entrar en la reunión. Las nuevas características se describen en [las nuevas características de conferencia de Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

En las reuniones de Lync Server 2013, se admiten determinadas características de conferencia para los usuarios alojados en diferentes versiones del servidor y que están usando diferentes clientes y versiones de cliente. Cuando los clientes se unan a una reunión de 2013 de Lync Server, los usuarios tendrán acceso a las características y capacidades que se muestran en esta tabla.


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
<th>Mensajería instantánea de punto a punto</th>
<th>Voz</th>
<th>Vídeo</th>
<th>Uso compartido de aplicaciones</th>
<th>PowerPoint</th>
<th>Transferencia de archivos</th>
<th>Whiteboard</th>
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
<td><p>Office Communicator 2007 R2 4</p></td>
<td><p>Sí</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


1 en Office Communicator 2007 R2, solo está disponible el uso compartido del escritorio (y no el uso compartido de programas).

2 Lync Server 2013 usa un mecanismo actualizado para cargar archivos de PowerPoint. Los usuarios de Lync Web App que se unen a una reunión que se programó originalmente en Lync Server 2010 pueden ver y navegar por las presentaciones de PowerPoint, pero no pueden cargar archivos de PowerPoint.

3 si la reunión se programó en Lync Server 2013 y se cargaron diapositivas de PowerPoint en un cliente de Lync 2013, los usuarios de Lync 2010 solo tienen acceso de vista a las diapositivas. Por el contrario, si un usuario de Lync 2010 cargó las diapositivas de PowerPoint, los usuarios de Lync Server 2013 podrán ver y diapositivas y, si Office Web Apps Server está configurado, accederán a nuevas capacidades, como la visualización de mayor resolución, las animaciones, las transiciones de diapositivas y vídeo incorporado. Para obtener más información, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

las características de presencia y mensajería instantánea de 4The en Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no. Durante la migración de Office Communications Server 2007 R2, Office Communicator 2007 R2 es apto para la presencia y la interoperabilidad de mensajes instantáneos, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>Programación de la compatibilidad de complementos

La compatibilidad del servidor para los distintos complementos de programación es coherente con la compatibilidad de versiones de servidor y cliente. En general, los complementos de programación siguientes son compatibles con Lync Server 2013. Sin embargo, las versiones anteriores de complementos no proporcionan nuevas características de complemento de Lync 2013, como la opción de silenciar el audio y vídeo de todos los asistentes en la entrada de la reunión.

  - **Complemento de reunión en línea para Lync 2013**   proporciona las mismas características que el complemento de reunión en línea para Lync 2010, con la adición de controles de silencio de asistente, que permiten a los organizadores de reuniones programar conferencias en las que se ha silenciado el audio y el vídeo del asistente de forma predeterminada. Los administradores también pueden personalizar las invitaciones a reuniones de la organización agregando un logotipo personalizado, una dirección URL de soporte técnico, una dirección URL de renuncia legal o texto de pie de página personalizado.

  - **Complemento de reunión en línea para Lync 2010**   proporciona programación para reuniones de Lync y elimina la capacidad de programar conferencias de Office Live Meeting.

  - **El complemento de conferencia de Office Communicator 2007 R2**   proporciona una programación para las conferencias de Office Live Meeting y las conferencias de Office Communicator 2007 R2. 

<div>


> [!NOTE]  
> Las conferencias de Live Meeting no se pueden programar en Lync Server 2013.



</div>


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
<td><p>Complemento de reunión en línea para Lync 2013 (se puede usar con Office 2013, Outlook 2010 y Outlook 2007)</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible (las nuevas características de complemento no están disponibles)</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Programador web de Lync 2013</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="odd">
<td><p>Complemento para conferencia en línea para Lync 2010</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Complemento de conferencia de Office Communicator 2007 R2</p></td>
<td><p>No compatible</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>Compatibilidad para unirse a reuniones

Todos los clientes que admite Lync Server 2013 pueden unirse a reuniones de Lync 2013. Puesto que Lync Web App es un componente web del servidor, en los casos en que Lync Web App se usa para unirse a una reunión de Lync Server 2013, se usa siempre la versión más reciente de Lync Web App.

Los clientes de Lync 2013 pueden unirse a reuniones hospedadas en Lync 2010 y Office Communications Server 2007 R2 con la funcionalidad de escalado vertical. Las características de la reunión están limitadas por la versión del servidor en el que se hospeda la reunión.

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de la aplicación de la tienda Windows de Lync para Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  
[Nuevas funciones de conferencia en Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Novedades para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

