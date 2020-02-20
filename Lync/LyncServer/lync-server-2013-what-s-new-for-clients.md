---
title: 'Lync Server 2013: novedades para clientes'
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
ms.openlocfilehash: 9035ace6a3cfbb65c8effb786bcd6a7568f92252
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a>Novedades para clientes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-19_

Microsoft Lync 2013 tiene una interfaz de usuario rediseñada y nuevas características importantes. Para los administradores, el cliente se incluye ahora con el programa de instalación de Office, lo que proporciona un método más simplificado para implementar Office y personalizar clientes en su organización.

<div>


> [!NOTE]  
> Para obtener una vista ilustrada de las actualizaciones de la interfaz de usuario de Lync 2013, consulte "What's <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>New in Lync 2013" en.



</div>

<div>

## <a name="integration-with-office-setup"></a>Integración con el programa de instalación de Office

El cliente de Lync 2013 y el complemento de reunión en línea para Lync 2013 (que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook) se incluyen ahora ambos con el programa de instalación de Office 2013.

En versiones anteriores de Lync y Office Communicator, podía usar las propiedades de Windows Installer para personalizar y controlar la instalación de Office. Como Lync 2013 está integrado con el programa de instalación de Office, puede usar los siguientes métodos para personalizar la instalación de Lync 2013:

  - Usar la herramienta de personalización de Office (OCT)

  - Uso de config. XML para realizar tareas de instalación

  - Usar las opciones de la línea de comandos del programa de instalación

<div>


> [!NOTE]  
> El programa de instalación de Lync 2013 no desinstala versiones anteriores de Lync u Office Communicator. El cliente de Lync 2013 se instala en paralelo con otros clientes de Lync u Office Communicator



</div>

Para obtener más información, consulte [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).

</div>

<div>

## <a name="group-policy-deployment"></a>Implementación de la Directiva de grupo

Como Lync 2013 ahora se incluye en el programa de instalación de Office, el método para implementar la configuración de la Directiva de grupo de Lync ha cambiado. En versiones anteriores de Lync y Office Communicator, podía usar Communicator. ADM para definir la configuración de la Directiva de grupo, mientras que en Lync 2013 ahora puede usar las plantillas administrativas de ADMX y ADML de Lync que se proporcionan junto con la Directiva de grupo de Office. Plantillas administrativas.

Para obtener más información, consulte [configuración de directiva de grupo para Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Actualizaciones de complementos de programación de Outlook

El complemento para reunión en línea para Lync 2013 incluye personalización de invitaciones de reunión y nuevas opciones de reunión.

  - Los administradores pueden personalizar las invitaciones a reuniones de la organización agregando un logotipo personalizado, una dirección URL de soporte, una dirección URL de exención de responsabilidad legal o un texto de pie de página personalizado. Para obtener más información, consulte [Customizing the online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - Los controles de silencio de los nuevos asistentes permiten que los organizadores de la reunión programen conferencias en las que el audio y el vídeo del asistente están silenciados de forma predeterminada.

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>Complemento de infraestructura de escritorio virtual

El cliente de Lync 2013 ahora admite audio y vídeo en un entorno de infraestructura de escritorio virtual (VDI). Un usuario puede conectar un dispositivo de audio o vídeo (por ejemplo, un auricular o una cámara) al equipo local (por ejemplo, un cliente ligero o un equipo con un repropósito). El usuario puede conectarse a la máquina virtual, iniciar sesión en el cliente de Lync 2013 que se ejecuta en la máquina virtual y participar en la comunicación de audio y vídeo en tiempo real como si el cliente se ejecuta de forma local. Las siguientes características se admiten en un entorno de escritorio virtual:

  - Integración de dispositivos para audio y vídeo, incluidos los siguientes:
    
      - Llamar a controles desde el dispositivo
    
      - Integración de presencia en el dispositivo
    
      - Compatibilidad con varios HID (dispositivos de interfaz humana)

  - Compatibilidad con servicios de emergencia y ubicación.

  - Soporte para todas las modalidades de Lync, como mensajería instantánea, audio, vídeo, uso compartido de aplicaciones, uso compartido de escritorio, uso compartido de PowerPoint, pizarra y transferencia de archivos.

  - Compatibilidad con audio y vídeo en llamadas de persona a persona y llamadas de conferencia.

Para obtener información acerca de la implementación del complemento VDI, consulte [Deploying The Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

</div>

<div>

## <a name="video-enhancements"></a>Mejoras de vídeo

Varias características nuevas mejoran significativamente la experiencia de vídeo para los participantes de la Conferencia.

  - El vídeo se ha mejorado con la detección de rostro y las tramas inteligentes, de modo que el vídeo de un participante se mueva para ayudarle a centrarse en el marco.

  - El vídeo de alta definición ahora es compatible con llamadas de dos participantes y conferencias de varios participantes. Los usuarios pueden disfrutar de resoluciones de hasta HD 1080P.

  - Los participantes pueden seleccionar entre diferentes diseños de reunión: la vista de Galería muestra las imágenes o vídeos de todos los participantes; La vista de orador muestra el contenido de la reunión y solo el vídeo o la imagen del orador actual; La vista de presentación muestra solo el contenido de la reunión; La vista compacta muestra solo los controles de la reunión.

  - Con la nueva característica de galería, los participantes pueden ver varias fuentes de vídeo al mismo tiempo. Si la Conferencia tiene más de cinco participantes, las fuentes de vídeo de los participantes más activos aparecen en la fila superior y las imágenes aparecen para los demás participantes.

  - Los participantes pueden usar el anclaje de vídeo para seleccionar una o varias de las fuentes de vídeo disponibles para que sean visibles en todo momento.

  - Los moderadores pueden usar la característica de foco de vídeo para seleccionar la fuente de vídeo de una persona para que todos los participantes de la reunión solo vean a ese participante.

</div>

<div>

## <a name="chat-room-integration"></a>Integración del salón de chat

Lync 2013 ahora integra las características proporcionadas anteriormente por el chat en grupo de Lync 2010. Ya no se necesita un cliente de chat en grupo independiente.

  - Desde dentro de Lync 2013, los usuarios pueden buscar salones de chat, agregar salones de chat a sus contactos, supervisar la actividad de los salones de chat y leer y publicar mensajes.

  - Los usuarios pueden crear suministros de temas para que reciban una notificación si alguien de uno de sus salones de chat agrega una publicación que contiene palabras clave específicas.

  - Con la nueva página Opciones de **chat persistente** , los usuarios pueden configurar alertas y sonidos de notificación que se aplican cuando los usuarios envían mensajes a sus salones de chat.

</div>

<div>

## <a name="lync-web-app-updates"></a>Actualizaciones de Lync Web App

Lync Web App es el cliente de conferencia basado en web para reuniones de Lync Server 2013. En esta versión, la adición de audio y vídeo de equipo a Lync Web App ofrece una experiencia de reunión completa para todos los usuarios que no tengan un cliente de Lync instalado de forma local. Los participantes de la reunión tienen acceso a todas las características de colaboración y uso compartido, así como a los controles de la reunión del mediador.

Cuando un usuario intenta unirse a una reunión, pero no tiene un cliente instalado localmente, se abre Lync Web App. Si desea permitir opciones adicionales para unirse a la reunión, puede configurar la página de participación en la reunión; consulte [configurar la página de participación en la reunión en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) en la documentación sobre implementación.

Debido a las mejoras realizadas en Lync Web App, hay una versión actualizada del asistente que no está disponible para Lync Server 2013. Lync Web App es el cliente preferido para los participantes externos a la organización. No es necesaria una instalación de cliente local, a pesar de que las características de audio, vídeo y uso compartido requieren que se instale un complemento al utilizar por primera vez.

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>Lync 2013 para actualizaciones de clientes móviles

Además de la presencia mejorada, los contactos y las capacidades de mensajería instantánea, los clientes móviles de Lync 2013 proporcionan ahora llamadas de voz y vídeo a través de Internet y conexiones de datos móviles. Con un solo punteo en el vínculo de la reunión en un elemento de calendario, los usuarios móviles pueden unirse a reuniones de Lync Voice y vídeo. Para obtener más información sobre los clientes móviles de Lync 2013, consulte [Planning for Mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Actualizaciones de la interfaz de usuario de Lync 2013

<div>

## <a name="accessibility-updates"></a>Actualizaciones de accesibilidad

Lync 2013 incorpora varias características de accesibilidad nuevas.

  - Lync 2013 admite alta resolución de PPP, lo que permite a los usuarios ajustar el texto y los gráficos del 125% y el 150% de puntos por pulgada.

  - Lync ofrece compatibilidad de alto contraste para que la interfaz de usuario permanezca completamente operativa cuando se usa con temas de contraste alto en Windows.

  - Lync ofrece más de 100 métodos abreviados de teclado para que los usuarios puedan acceder a las funciones importantes sin el mouse. Por ejemplo, los usuarios pueden presionar ALT + C para aceptar una llamada o Alt + I para omitirla, sin tener que usar el tabulador o establecer el foco. Al presionar (Alt + Q), se finaliza una llamada, (Ctrl + N) se inicia OneNote y (Alt + T) se abre el menú herramientas.

  - La compatibilidad con un lector de pantalla extensivo en Lync 2013 garantiza que todas las notificaciones, las solicitudes entrantes y los mensajes instantáneos se lean en voz alta cuando se habilita un lector de pantalla.

</div>

<div>

## <a name="presence-while-sharing"></a>Presencia al compartir

Cuando Lync detecta que un usuario está compartiendo un usuario, Lync asigna automáticamente un estado de presencia en el que se presenta el usuario. Este estado bloquea todas las comunicaciones entrantes a menos que el remitente tenga asignada la relación de privacidad grupo de trabajo. Si el usuario usa la característica de uso compartido en un monitor secundario, Lync no asigna un estado de presencia de presentación.

</div>

<div>

## <a name="conversation-window-updates"></a>Actualizaciones de la ventana de conversación

La ventana de conversación rediseñada proporciona un acceso más rápido a características importantes.

  - Con la nueva característica de conversaciones en pestañas, ahora los usuarios pueden mantener todos sus salones de chat y IMs en una ventana de conversación. Las pestañas situadas en el lado izquierdo de la ventana de conversación permiten a los usuarios desplazarse fácilmente entre todas las conversaciones activas.

  - Los usuarios pueden extraer una conversación individual en una ventana independiente y, a continuación, cambiar el tamaño de la ventana. También pueden volver a extraer la ventana en la ventana de conversación principal.

  - Lync 2013 vuelve a abrir las conversaciones de un usuario cuando el usuario cierra sesión y vuelve a iniciar sesión en Lync.

  - Los usuarios pueden agregar rápidamente mensajería instantánea, vídeo, uso compartido de programas, uso compartido de escritorio o herramientas de conferencia web (pizarra, notas de reunión, blocs de notas compartidos y datos adjuntos) a cualquier conversación.

  - En una reunión en la que se comparte el vídeo o el contenido, los usuarios pueden extraer el contenido compartido o el vídeo de la reunión y, a continuación, cambiar el tamaño de la ventana.

</div>

<div>

## <a name="lync-main-window-updates"></a>Actualizaciones de la ventana principal de Lync

El nuevo aspecto simplificado conserva características familiares, como el campo **¿Qué está ocurriendo?** , el selector de estado y el selector **de ubicación** .

  - Cuando los salones de chat están habilitados, los usuarios ven un icono nuevo de **salones de chat** en la Página principal de Lync. Con el icono de los **salones de chat** , los usuarios pueden acceder rápidamente a sus salones de chat y filtros.

  - Los usuarios pueden hacer clic en el icono Ver iconos para cambiar a la vista de **contactos** , a la vista de **salones de chat** , a la vista **conversaciones** o a la vista de **teléfono** .

  - Si los usuarios se han migrado a Exchange 2013, pueden cargar una imagen de alta resolución.

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>Vista de contactos y actualizaciones de tarjetas de contacto

Lync 2013 proporciona a los usuarios distintas formas de ver los contactos y grupos en su vista de **contactos** .

  - Con el nuevo almacén de contactos unificado, después de migrar los contactos de Lync de los usuarios a Exchange 2013, los usuarios pueden tener acceso a los contactos y administrarlos desde Lync 2013, Outlook o Outlook Web App, y sus favoritos se mantienen sincronizados. Por ejemplo, si un usuario agrega un contacto a favoritos en Outlook, el contacto aparece en el grupo favoritos en Lync 2013.

  - Si ha agregado y configurado el proxy XMPP y la puerta de enlace XMPP, los usuarios pueden agregar contactos de socios basados en XMPP para la mensajería instantánea y la presencia.

  - Una nueva característica **Agregar un contacto que no está en mi organización** ofrece a los usuarios una forma sencilla de agregar personas externas a la organización.

  - Un nuevo grupo de **Favoritos** permite a los usuarios crear una lista de personas a las que se puede contactar con mayor frecuencia para obtener un acceso más rápido.

  - Los usuarios pueden usar la página nuevas opciones de **lista de contactos** para elegir el modo en que los usuarios desean ordenar y mostrar los contactos. Los usuarios pueden seleccionar una vista expandida de dos líneas que muestre las imágenes de los contactos o una vista de una línea comprimida. Los usuarios también pueden ordenar los contactos alfabéticamente o por disponibilidad.

</div>

<div>

## <a name="conferencing-updates"></a>Actualizaciones de conferencia

Lync 2013 ofrece varias mejoras a las características de conferencia.

  - En función del tipo de reunión, los usuarios ahora pueden silenciar la audiencia y permitir o bloquear el uso compartido de vídeo al programar la reunión. Estas opciones están disponibles en la página **Opciones de reunión** y se recomiendan para reuniones grandes con más de 20 participantes.

  - Los controles de audio fáciles de usar en la sala de reuniones permiten al usuario controlar las opciones de audio, como silenciar, reactivar audio, cambiar dispositivo, etc.

  - Al compartir programas, los usuarios pueden seleccionar varios programas para compartir si necesitan trabajar con más de un programa.

  - Ahora, los usuarios pueden cargar presentaciones que contienen clips de vídeo cargando el archivo de PowerPoint y señalando el mouse sobre la diapositiva para mostrar controles de vídeo, como los controles de reproducción, pausa y audio.

  - Durante una reunión, los usuarios pueden combinar otra conversación abierta con la reunión mediante la **combinación de esta llamada** en el menú **más opciones** (**...**).

  - Para ver los nombres de los participantes, los usuarios pueden situar el mouse sobre el botón **Ver participantes** o hacer clic en **Mostrar lista de participantes** para acoplar el panel en la reunión.

  - Según el tipo de reunión, los usuarios pueden seleccionar entre varias vistas de contenido y participantes diferentes.

  - Las grabaciones de reuniones se guardan automáticamente en un formato que se reproduce en el reproductor de Windows Media (MP4). Los usuarios pueden compartir fácilmente el archivo con cualquier usuario o usar la característica **publicar** del administrador de grabaciones para publicar la grabación en una ubicación compartida.

  - OneNote habilita nuevas formas de colaborar en una reunión. Durante una reunión, los usuarios pueden tomar notas con OneNote para su uso personal después de la reunión, o usar blocs de notas compartidos y realizar la edición conjunta con participantes en la reunión en tiempo real. Todos los miembros del equipo pueden acceder a las notas compartidas para colaborar en la información, recopilar ideas o usar las páginas de los blocs de notas como una pizarra virtual. Las personas y el contenido compartido en la reunión se agregan automáticamente a las notas.

  - Los usuarios pueden cambiar entre los tipos de contenido mediante **compartir contenido y coordinar actividades de reunión** en la parte inferior de la sala de reuniones. Los usuarios también pueden usar el menú **administrar contenido** presentable para elegir el contenido que desean compartir.

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación de clientes en Lync Server 2013](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

