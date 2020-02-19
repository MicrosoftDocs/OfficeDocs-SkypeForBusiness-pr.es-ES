---
title: 'Lync Server 2013: interoperabilidad de clientes en Lync 2013'
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
ms.openlocfilehash: 69a4616cbe9519a8196ce78e35f21c673a0d2c95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Interoperabilidad de clientes en Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-03-04_

En este tema se describe la capacidad de los clientes de Microsoft Lync Server 2013 para coexistir e interactuar con clientes de versiones anteriores de Lync Server y Office Communications Server.

<div>

## <a name="server-and-client-compatibility"></a>Compatibilidad con servidores y clientes

En la siguiente tabla se muestran las combinaciones compatibles de versiones de cliente y versiones de servidor. Esta tabla indica si se admite el inicio de sesión cuando el cliente intenta conectarse al servidor indicado. Lync Server 2013 admite la versión de cliente anterior. Además, a diferencia de las versiones anteriores, Lync Server 2010 admite los nuevos clientes de Lync 2013. Esto permite a las organizaciones que actualizan desde Lync Server 2010 implementar nuevos clientes independientes de las actualizaciones de Lync Server.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Compatible.</p></td>
<td><p>Supported5</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Compatible.</p></td>
<td><p>Compatible.</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Compatible.</p></td>
<td><p>No compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Compatible.</p></td>
<td><p>Compatible.</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Compatible.</p></td>
<td><p>Compatible.</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Group Chat</p></td>
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible.</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>No Supported3</p></td>
<td><p>Compatible.</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Compatible.</p></td>
<td><p>Compatible.</p></td>
</tr>
<tr class="even">
<td><p>Operador de Microsoft Office Communications Server 2007 R2</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible.</p></td>
<td><p>Compatible.</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible.</p></td>
<td><p>Compatible.</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible.</p></td>
<td><p>Compatible.</p></td>
</tr>
<tr class="odd">
<td><p>Aplicación Lync de la tienda Windows</p></td>
<td><p>Compatible.</p></td>
<td><p>Compatible.</p></td>
<td><p>No compatible</p></td>
</tr>
</tbody>
</table>


1Para obtener más información, consulte [Migration from Lync server 2010, Group chat o Office Communications server 2007 R2 Group chat to Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2In Microsoft Lync Server 2010, la funcionalidad de chat en grupo estaba disponible con el servidor de chat en grupo, una aplicación de confianza de terceros para Lync Server 2010. Los clientes de Lync 2013 no son compatibles con Lync Server 2010, chat en grupo.

3Lync Web App 2013 ahora proporciona una experiencia completa para la reunión, incluido el audio y el vídeo del equipo, y se considera el reemplazo de Lync 2010 asistente. Lync 2010 Attendee se conectará a Lync Server 2013 solo cuando use un explorador no admitido (Internet Explorer 6 o Internet Explorer 7) y Windows XP.

las características de presencia y mensajería instantánea de 4The en Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no lo son. Durante la migración de Office Communications Server 2007 R2, Office Communicator 2007 R2 es apto para la presencia y la interoperabilidad de mi, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.

5 para conocer las limitaciones, consulte "compatibilidad con la característica de conferencia para clientes de Lync 2013 en Lync Server 2010 reuniones" más adelante en este tema.

</div>

<div>

## <a name="interoperability-among-clients"></a>Interoperabilidad entre clientes

Con la versión 2013 de Lync Server, varias versiones de cliente pueden interactuar sin problemas en escenarios de punto a punto y de conferencia. En esta sección se describe la disponibilidad de la función cuando los usuarios interactúan con otros usuarios que hayan iniciado sesión usando un tipo de cliente diferente o una versión anterior del mismo cliente.

<div>

## <a name="peer-to-peer-feature-support"></a>Compatibilidad con la característica de punto a punto

Las características de punto a punto son compatibles con los usuarios que están hospedados en versiones distintas del servidor y que utilicen diferentes versiones de cliente. La experiencia del usuario final y las características disponibles consistentes con las capacidades del cliente del usuario y la versión del servidor en el cual el usuario ha iniciado sesión. Dicho de otra manera:

  - Si un usuario ha iniciado sesión en Lync Server 2013 con un cliente antiguo, el usuario tendrá la misma experiencia en la que se usa. Ninguna de las nuevas características que se incluyen en Lync Server 2013 estará disponible hasta que se actualice el cliente del usuario. Algunos ejemplos son la vista de la galería de vídeos, vídeo HD, uso compartido de PowerPoint actualizado y la opción de silenciar el audio y vídeo de todos los asistentes tras la entrada de la reunión. Las nuevas características se describen en [nuevas características de conferencia en Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

  - Si un usuario ha iniciado sesión en Lync Server 2010 con un cliente de Lync 2013, las nuevas características que no son compatibles con Lync Server 2010 no estarán disponibles hasta que el usuario se mueva a Lync Server 2013.

En la tabla siguiente se compara la disponibilidad de las características de las sesiones punto a punto en las que el cliente ha iniciado sesión en Lync Server 2013 o Lync Server 2010.

<div>


> [!NOTE]  
> Lync Web App y Lync 2010 Attendee son clientes de solo reunión que no se incluyen en esta tabla.



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
<th>Client</th>
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
<td><p>Lync 2010 Attendant</p></td>
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
<td><p>Yes1</p></td>
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
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta la fecha de cierre del servicio. Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>La capa de PIC es una licencia por usuario, por mes, que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo! Service. La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente que no se renovará.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de mensajería instantánea y voz.</P></LI></UL>



</div>

1 en Office Communicator 2007 R2, solo está disponible el uso compartido de escritorio (y no el uso compartido de programas).

<div>


> [!NOTE]  
> El uso compartido de escritorio entre Office Communicator 2007 R2 y Skype empresarial 2015 no se puede iniciar desde el cliente más reciente cuando se aplica la interfaz de usuario del cliente 2015 de Skype empresarial.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Compatibilidad con la característica de conferencia para clientes de Lync 2013 en reuniones de Lync Server 2010

Cuando los usuarios se unen a reuniones de Lync Server 2010 con un cliente de Lync 2013, tienen acceso a las características de cliente de Lync 2013 con las siguientes excepciones:

  - En las opciones de administración de **participantes** , a las que se puede tener acceso seleccionando el icono de personas en la ventana de la reunión, la opción de **mensajería instantánea sin reunión** no funciona.

  - La vista de Galería no funciona en las videoconferencias. El usuario solo ve el participante activo en lugar de todos los altavoces. En la lista de opciones de **selección de un diseño** , la **vista de Galería** no está disponible

  - La lista de participantes se muestra de forma predeterminada en las videoconferencias.

  - Al hacer clic con el botón derecho en un usuario de la lista participantes, las opciones **bloquear la luz de vídeo** y **anclar al** participante de la galería no están disponibles.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Compatibilidad con la característica de conferencias en reuniones de Lync Server 2013

Lync Server 2013 proporciona nuevas características de conferencia que se ponen a disposición de los usuarios después de que sus cuentas se muevan a Lync Server 2013 y inician sesión con el cliente de Lync 2013. Algunos ejemplos son la vista de la galería de vídeos, vídeo HD, uso compartido de PowerPoint y la opción de silenciar todo el audio y vídeo de los asistentes tras la entrada de la reunión. Las nuevas características se describen en [nuevas características de conferencia en Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

En las reuniones de Lync Server 2013, se admiten ciertas características de conferencia para los usuarios hospedados en distintas versiones del servidor y que usan clientes y versiones de cliente diferentes. Cuando los clientes se unen a una reunión de 2013 de Lync Server, los usuarios tienen acceso a las características y funciones que se muestran en esta tabla.


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
<th>Client</th>
<th>Mensajería instantánea punto a punto</th>
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
<td><p>Yes3</p></td>
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


1 en Office Communicator 2007 R2, solo está disponible el uso compartido de escritorio (y no el uso compartido de programas).

2 Lync Server 2013 usa un mecanismo actualizado para cargar archivos de PowerPoint. Lync Web App los usuarios que se unen a una reunión programada originalmente en Lync Server 2010 pueden ver y navegar por las presentaciones de PowerPoint, pero no pueden cargar archivos de PowerPoint.

3 si la reunión se programó en Lync Server 2013 y un cliente de Lync 2013 cargó las diapositivas de PowerPoint, los usuarios de Lync 2010 tienen acceso de solo vista a las diapositivas. Por el contrario, si un usuario de Lync 2010 cargó las diapositivas de PowerPoint, los usuarios de Lync Server 2013 podrán ver y diapositivas y, si Office Web Apps Server está configurado, accederá a nuevas capacidades como, por ejemplo, la visualización de una mayor resolución, animaciones, transiciones de diapositivas y vídeo incrustado. Para obtener más información, consulte Configuración de la [integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

las características de presencia y mensajería instantánea de 4The en Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no lo son. Durante la migración de Office Communications Server 2007 R2, Office Communicator 2007 R2 es apto para la presencia y la interoperabilidad de mi, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>Compatibilidad con el complemento de programación

La compatibilidad del servidor con varios complementos de programación es consistente con la compatibilidad de versión del cliente y del servidor. En general, los siguientes complementos de programación se admiten en Lync Server 2013. Sin embargo, las versiones anteriores de los complementos no proporcionan nuevas características de complemento de Lync 2013, como la opción de silenciar todo el audio y vídeo de los asistentes tras la entrada de la reunión.

  - **Complemento para reunión en línea para Lync 2013**   proporciona las mismas características que el complemento de conferencia en línea para Lync 2010, con la adición de controles de silencio de asistentes, que permiten a los organizadores de la reunión programar conferencias en las que el audio y el vídeo del asistente están silenciados de forma predeterminada. Los administradores también pueden personalizar las invitaciones de la organización para la reunión agregando un logo personalizado, una URL de ayuda, una dirección URL del aviso legal o un texto de pie de página personalizado.

  - **Complemento para reunión en línea para Lync 2010**   proporciona una programación para reuniones de Lync y elimina la capacidad de programar conferencias de Office Live Meeting.

  - **El complemento para conferencias de Office Communicator 2007 R2**   proporciona programación para conferencias de Office Live Meeting y para conferencias de Office Communicator 2007 R2. 

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
<td><p>Complemento para reunión en línea para Lync 2013 (se puede usar con Office 2013, Outlook 2010 y Outlook 2007)</p></td>
<td><p>Compatible.</p></td>
<td><p>Compatible (nuevas características del complemento no disponibles)</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="even">
<td><p>Programador web de Lync 2013</p></td>
<td><p>Compatible.</p></td>
<td><p>No compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="odd">
<td><p>Complemento de conferencia en línea para Lync 2010</p></td>
<td><p>Compatible.</p></td>
<td><p>Compatible.</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="even">
<td><p>Complemento para conferencias de Office Communicator 2007 R2</p></td>
<td><p>No compatible</p></td>
<td><p>Compatible.</p></td>
<td><p>Compatible.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>Ayuda para unirse a una conferencia

Todos los clientes que admite Lync Server 2013 pueden unirse a reuniones de Lync 2013. Dado que Lync Web App es un componente web del servidor, en los casos en que Lync Web App se usa para unirse a una reunión de Lync Server 2013, siempre se usa la versión más reciente de Lync Web App.

Los clientes de Lync 2013 pueden unirse a reuniones hospedadas en Lync 2010 y Office Communications Server 2007 R2 con funcionalidad de escalado. Las características de reunión están limitadas por la versión del servidor en el cual se hospeda la reunión.

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de aplicaciones de la tienda Windows Lync para Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  
[Nuevas características de conferencia en Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Novedades para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

