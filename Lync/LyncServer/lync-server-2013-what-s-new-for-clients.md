---
title: 'Lync Server 2013: Novedades para clientes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f938ccc4e4a040307a7cf86a8084353c480cfdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a>Novedades para clientes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-19_

Microsoft Lync 2013 tiene una interfaz de usuario rediseñada y características nuevas importantes. Para los administradores, el cliente está ahora incluido con el programa de instalación de Office, lo que proporciona un método más simplificado para implementar Office y personalizar clientes de su organización.

<div>


> [!NOTE]  
> Para ver una vista ilustrada de actualizaciones de la interfaz de usuario de Lync 2013, vea "Novedades de <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>Lync 2013" en.



</div>

<div>

## <a name="integration-with-office-setup"></a>Integración con la configuración de Office

El cliente de Lync 2013 y el complemento de reunión en línea para Lync 2013 (que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook) ya están incluidos en el programa de instalación de Office 2013.

En versiones anteriores de Lync y Office Communicator, se pueden usar las propiedades de Windows Installer para personalizar y controlar la instalación de Office. Puesto que Lync 2013 está integrado con el programa de instalación de Office, puede usar los siguientes métodos para personalizar la configuración de Lync 2013:

  - Usar la Herramienta de personalización de Office (OCT)

  - Usar el archivo config. XML para realizar tareas de instalación

  - Usar las opciones de la línea de comandos de configuración

<div>


> [!NOTE]  
> El programa de instalación de Lync 2013 no desinstala versiones anteriores de Lync u Office Communicator. El cliente de Lync 2013 se instala en paralelo con otros clientes de Lync u Office Communicator



</div>

Para obtener más información, vea [implementación de clientes de Lync en Lync Server 2013](lync-server-2013-deploying-lync-clients.md).

</div>

<div>

## <a name="group-policy-deployment"></a>Implementación de directiva de grupo

Puesto que Lync 2013 ahora está incluido en el programa de instalación de Office, el método para implementar la configuración de la Directiva de grupo de Lync ha cambiado. En las versiones anteriores de Lync y Office Communicator, se puede usar Communicator. ADM para definir la configuración de directiva de grupo, mientras que en Lync 2013 ahora puede usar las plantillas administrativas de ADMX y ADML de Lync que se proporcionan junto con la Directiva de grupo de Office. Plantillas administrativas.

Para obtener más información, consulte [configuración de directiva de grupo para Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Actualizaciones de complementos de programación de Outlook

El complemento de reunión en línea para Lync 2013 incluye personalización de invitaciones de reuniones y nuevas opciones de reunión.

  - Los administradores pueden personalizar las invitaciones a reuniones de la organización agregando un logotipo personalizado, una dirección URL de soporte técnico, una dirección URL de renuncia legal o texto de pie de página personalizado. Para obtener más información, consulte [personalizar el complemento de reunión en línea en Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - Los controles de silencio de nuevo asistente permiten a los organizadores de reuniones programar conferencias en las que el asistente está silenciado de audio y vídeo de forma predeterminada.

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>Complemento de infraestructura de escritorio virtual

El cliente de Lync 2013 ahora admite audio y vídeo en un entorno de infraestructura de escritorio virtual (VDI). Un usuario puede conectar un dispositivo de audio o vídeo (por ejemplo, unos auriculares con micrófono o una cámara) al equipo local (por ejemplo, un equipo de cliente ligero o un equipo con un propósito). El usuario puede conectarse a la máquina virtual, inicie sesión en el cliente de Lync 2013 que se ejecuta en la máquina virtual y participe en la comunicación de audio y vídeo en tiempo real como si el cliente se ejecuta de forma local. Las siguientes características son compatibles con un entorno de escritorio virtual:

  - Integración de dispositivos para audio y vídeo, entre los que se incluyen los siguientes:
    
      - Llamar a controles desde el dispositivo
    
      - Integración de presencia en el dispositivo
    
      - Compatibilidad con varios HID (dispositivo de interfaz humana)

  - Soporte de servicios de emergencia y ubicación.

  - Compatibilidad con todas las modalidades de Lync, como la mensajería instantánea, el audio, el vídeo, el uso compartido de aplicaciones, el uso compartido de PowerPoint, la pizarra y la transferencia de archivos.

  - Compatibilidad de audio y vídeo en llamadas entre usuarios y llamadas en conferencia.

Para obtener información sobre cómo implementar el complemento VDI, consulte [implementar el complemento de VDI para Lync en Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

</div>

<div>

## <a name="video-enhancements"></a>Mejoras de video

Varias características nuevas mejoran significativamente la experiencia de vídeo para los participantes de la Conferencia.

  - El video se ha mejorado con la detección de rostro y las tramas inteligentes, de modo que el video de un participante se mueve para ayudarle a mantenerlos centrados en el marco.

  - Ahora se admite el video de alta definición en las llamadas de dos participantes y en las conferencias de varias partes. Los usuarios pueden tener resoluciones de hasta HD 1080P.

  - Los participantes pueden seleccionar entre diferentes diseños de reunión: la vista de Galería muestra las imágenes o los vídeos de todos los participantes; Vista de orador muestra el contenido de la reunión y solo el vídeo o la imagen del orador; La vista de presentación muestra solo el contenido de la reunión; La vista compacta muestra solo los controles de la reunión.

  - Con la nueva característica de galería, los participantes pueden ver varias fuentes de video al mismo tiempo. Si la Conferencia tiene más de cinco participantes, las fuentes de vídeo de los participantes más activos aparecerán en la fila superior y las imágenes aparecerán para los demás participantes.

  - Los participantes pueden usar el anclaje de video para seleccionar una o varias de las fuentes de video disponibles para que sean visibles en todo momento.

  - Los moderadores pueden usar la característica noticias destacadas de vídeo para seleccionar una fuente de vídeo de una persona para que todos los participantes de la reunión puedan ver únicamente a ese participante.

</div>

<div>

## <a name="chat-room-integration"></a>Integración del salón de chat

Lync 2013 ahora integra las características proporcionadas previamente por la conversación grupal de Lync 2010. Ya no se necesita un cliente de conversación grupal independiente.

  - Desde dentro de Lync 2013, los usuarios pueden buscar salas de chats, agregar salones de chat a sus contactos, supervisar la actividad de los salones de chat y leer y publicar mensajes.

  - Los usuarios pueden crear fuentes de temas para que reciban una notificación si alguien de uno de sus salones de chat agrega una publicación que contiene palabras clave específicas.

  - Con la página nuevas opciones de **chat persistente** , los usuarios pueden configurar alertas y sonidos de notificación que se aplican cuando los usuarios publican mensajes en sus salones de chat.

</div>

<div>

## <a name="lync-web-app-updates"></a>Actualizaciones de Lync Web App

Lync Web App es el cliente de conferencia basado en web para reuniones de Lync Server 2013. En esta versión, la adición de audio y vídeo de PC a Lync Web App proporciona una experiencia de reunión completa para cualquier persona que no tenga un cliente Lync instalado de forma local. Los participantes de las reuniones obtienen acceso a todas las características de uso compartido y colaboración, y a todos los controles de la reunión del moderador.

Cuando un usuario intenta unirse a una reunión pero no tiene un cliente instalado localmente, se abre Lync Web App. Si desea permitir opciones adicionales para unirse a la reunión, puede configurar la página de la combinación de reuniones; consulte [configurar la página de la combinación de reuniones en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) en la documentación de implementación.

Debido a las mejoras de Lync Web App, no está disponible una versión actualizada del Asistente para Lync Server 2013. Lync Web App es el cliente que elige para los participantes fuera de su organización. No se requiere instalación de cliente local, aunque las características de audio, vídeo y uso compartido requieren que se instale un complemento al utilizar por primera vez.

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>Lync 2013 para actualizaciones de clientes móviles

Además de las capacidades mejoradas de presencia, contactos y mensajería instantánea, los clientes móviles de Lync 2013 ahora proporcionan llamadas y videollamadas a través de Internet y de las conexiones de datos móviles. Con un solo toque en el vínculo de la reunión en un elemento de calendario, los usuarios móviles pueden unirse a reuniones de Lync y de vídeo. Para obtener más información sobre los clientes móviles de Lync 2013, consulte [planificación de clientes móviles en Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Actualizaciones de la interfaz de usuario de Lync 2013

<div>

## <a name="accessibility-updates"></a>Actualizaciones de accesibilidad

Lync 2013 incorpora varias nuevas características de accesibilidad.

  - Lync 2013 admite una resolución alta de PPP, lo que permite a los usuarios ajustar el texto y los gráficos de 125% y 150 puntos por pulgada.

  - Lync proporciona compatibilidad de contraste alto para que la interfaz de usuario siga funcionando completamente cuando se usa con los temas de contraste alto de Windows.

  - Lync ofrece más de 100 métodos abreviados de teclado para que los usuarios puedan obtener acceso a funciones importantes sin un mouse. Por ejemplo, los usuarios pueden presionar ALT + C para aceptar una llamada o Alt + I para ignorarla, sin tener que utilizar la tecla TAB o establecer el foco. Si pulsa (Alt + Q) finaliza una llamada, (Ctrl + N) inicia OneNote y (Alt + T) se abre el menú herramientas.

  - La compatibilidad con un lector de pantalla extensivo en Lync 2013 garantiza que todas las notificaciones, las solicitudes entrantes y los mensajes instantáneos se lean en voz alta cuando se habilita un lector de pantalla.

</div>

<div>

## <a name="presence-while-sharing"></a>Presencia al compartir

Cuando Lync detecta que un usuario está compartiendo, Lync asigna automáticamente un estado de presencia para el usuario. Este estado bloquea todas las comunicaciones entrantes a menos que el remitente tenga asignada la relación de privacidad grupo de trabajo. Si el usuario usa la característica de uso compartido por completo en un monitor secundario, Lync no asigna un estado de presencia de presentación.

</div>

<div>

## <a name="conversation-window-updates"></a>Actualizaciones de la ventana de conversación

La ventana de conversación rediseñada ofrece un acceso más rápido a las características importantes.

  - Con la nueva característica de conversaciones en pestañas, los usuarios pueden conservar todos los mensajes instantáneos y salones de chat en una ventana de conversación. Las pestañas de la parte izquierda de la ventana de conversación permiten a los usuarios desplazarse fácilmente entre todas las conversaciones activas.

  - Los usuarios pueden mostrar una conversación individual en una ventana independiente y, a continuación, cambiar el tamaño de la ventana. También pueden volver a mostrar la ventana en la ventana de conversación principal.

  - Lync 2013 vuelve a abrir las conversaciones de un usuario cuando el usuario cierra sesión e inicia sesión en Lync.

  - Los usuarios pueden agregar rápidamente mensajería instantánea, vídeo, uso compartido de programas, uso compartido de escritorio o herramientas de conferencia web (pizarra, notas de reunión, blocs de notas compartidos y datos adjuntos) a cualquier conversación.

  - En una reunión en la que el vídeo o contenido se comparte, los usuarios pueden mostrar el vídeo de la reunión o el contenido compartido y, a continuación, cambiar el tamaño de la ventana.

</div>

<div>

## <a name="lync-main-window-updates"></a>Actualizaciones de la ventana principal de Lync

El nuevo aspecto simplificado conserva características conocidas, como el campo **¿Qué está sucediendo?** , el selector de estado y el selector **de ubicación** .

  - Cuando los salones de chat estén habilitados, los usuarios verán un nuevo icono de **salones de chat** en la Página principal de Lync. Con el icono de los **salones de chat** , los usuarios pueden acceder rápidamente a sus salones de chat y filtros.

  - Los usuarios pueden hacer clic en Ver iconos para cambiar a la vista **contactos** , a la vista de **salones de chat** , a la vista **conversaciones** o a la vista de **teléfono** .

  - Si los usuarios han migrado a Exchange 2013, pueden cargar una imagen de alta resolución.

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>Vista contactos y actualizaciones de tarjetas de contacto

Lync 2013 ofrece a los usuarios distintas formas de ver los contactos y grupos en su vista **contactos** .

  - Con el nuevo almacén de contactos unificado, después de migrar los contactos de Lync de los usuarios a Exchange 2013, los usuarios pueden tener acceso y administrar sus contactos desde Lync 2013, Outlook o Outlook Web App, y sus favoritos permanecen sincronizados. Por ejemplo, si un usuario agrega un contacto a favoritos en Outlook, el contacto aparece en el grupo favoritos de Lync 2013.

  - Si ha agregado y configurado el proxy XMPP y la puerta de enlace XMPP, los usuarios pueden agregar contactos de socios basados en XMPP para la mensajería instantánea y la presencia.

  - Una nueva característica **Agregar un contacto que no está en mi organización** ofrece a los usuarios una forma fácil de agregar personas externas a la organización.

  - Un nuevo grupo de **Favoritos** permite a los usuarios crear una lista de personas con las que los usuarios se comunican con mayor frecuencia para obtener acceso más rápido.

  - Los usuarios pueden usar la página de opciones de la nueva **lista de contactos** para elegir cómo desean ordenar y mostrar los contactos. Los usuarios pueden seleccionar una vista expandida de dos líneas en la que se muestran las imágenes de los contactos o una vista de una línea comprimida. Los usuarios también pueden ordenar los contactos por orden alfabético o por disponibilidad.

</div>

<div>

## <a name="conferencing-updates"></a>Actualizaciones de conferencias

Lync 2013 ofrece varias mejoras para las características de conferencia.

  - En función del tipo de reunión, los usuarios pueden silenciar la audiencia y permitir o bloquear el uso compartido de vídeo al programar la reunión. Estas opciones están disponibles en la página Opciones de la **reunión** y se recomiendan para reuniones grandes con más de 20 participantes.

  - Los controles de audio fáciles de usar en la sala de reuniones permiten que el usuario controle las opciones de audio, como silenciar, reactivar el audio, cambiar el dispositivo, etc.

  - Al compartir programas, los usuarios pueden seleccionar varios programas para compartirlos si necesitan trabajar con más de un programa.

  - Ahora los usuarios pueden cargar presentaciones que contienen clips de vídeo cargando el archivo de PowerPoint y haciendo clic con el mouse sobre la diapositiva para mostrar los controles de vídeo, como los controles de reproducción, pausa y audio.

  - Durante una reunión, los usuarios pueden combinar otra conversación abierta en la reunión mediante la **combinación de esta llamada** en el menú **más opciones** (**...**).

  - Para ver los nombres de los participantes, los usuarios pueden situar el mouse sobre el botón **Ver participantes** o hacer clic en **Mostrar lista de participantes** para acoplar el panel en la reunión.

  - Según el tipo de reunión, los usuarios pueden seleccionar entre varias vistas de contenido y participantes diferentes.

  - Las grabaciones de reuniones se guardan automáticamente en un formato que se reproduce en el reproductor de Windows Media (MP4). Los usuarios pueden compartir fácilmente el archivo con cualquier persona o usar la característica **publicar** en el administrador de grabaciones para publicar la grabación en una ubicación compartida.

  - OneNote habilita nuevas maneras de colaborar en una reunión. Durante una reunión, los usuarios pueden tomar notas con OneNote para su uso personal después de la reunión, o usar blocs de notas compartidos y coautoría en la reunión en tiempo real. Todos los miembros del equipo pueden acceder a las notas compartidas para colaborar en la información, recopilar ideas o usar las páginas de los blocs de notas como una pizarra virtual. Las personas y el contenido compartido en la reunión se agregan automáticamente a las notas.

  - Los usuarios pueden cambiar de un tipo de contenido a otro usando **compartir contenido y coordinar actividades** de la reunión en la parte inferior de la sala de reuniones. Los usuarios también pueden usar el menú **administrar contenido** presentable para elegir el contenido que desean compartir.

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planificación de clientes en Lync Server 2013](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

