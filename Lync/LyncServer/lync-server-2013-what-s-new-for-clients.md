---
title: 'Lync Server 2013: Novedades para clientes'
TOCTitle: Novedades para clientes
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48275393
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Novedades para clientes en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Microsoft Lync 2013 tiene una interfaz de usuario rediseñada y funciones nuevas e importantes. Desde el punto de vista de los administradores, el cliente ahora se incluye con el programa de instalación de Office, lo que proporciona un enfoque más sencillo para implementar Office y personalizar los clientes de la organización.


> [!NOTE]
> Para obtener una vista ilustrada de las actualizaciones de la interfaz de usuario de Lync 2013, consulte “Novedades de Lync 2013” en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?linkid=273885</A>.



## Integración con la instalación de Office

El cliente de Lync 2013 y el Complemento para conferencia en línea para Lync 2013 (que admite la administración de reuniones desde dentro del cliente de mensajería y colaboración de Outlook) están incluidos ahora en el programa de instalación de Office 2013.

En versiones anteriores de Lync y Office Communicator, se podían usar las propiedades de Windows Installer para personalizar y controlar la instalación de Office. Como ahora Lync 2013 está integrado en la instalación de Office, puede recurrir a los siguientes métodos para personalizar la instalación de Lync 2013:

  - Usar la Herramienta de personalización de Office (OCT)

  - Usar el archivo Config.xml para realizar tareas de instalación

  - Usar las opciones de la línea de comandos del programa de instalación


> [!NOTE]
> El programa de instalación de Lync 2013 no hace que se desinstalen las versiones anteriores de Lync u Office Communicator, sino que el cliente de Lync 2013 se instala en paralelo con otros clientes de Lync u Office Communicator.



Para ver información detallada, consulte [Implementación de clientes de Lync en Lync Server 2013](lync-server-2013-deploying-lync-clients.md).

## Implementación de la directiva de grupo

Dado que Lync 2013 ahora se incluye en la instalación de Office, el método para implementar la configuración de la directiva de grupo de Lync ha cambiado. En versiones anteriores de Lync y Office Communicator, se podía usar Communicator.adm para definir la configuración de la directiva de grupo, mientras que en Lync 2013 ahora se pueden usar las plantillas administrativas ADMX y ADML de Lync que se suministran junto con las plantillas administrativas de la directiva de grupo de Office.

Para ver información detallada, consulte [Configuración de directivas de grupo para Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

## Actualizaciones del complemento de programación de Outlook

El Complemento para conferencia en línea para Lync 2013 permite personalizar las invitaciones a reuniones y contempla nuevas opciones de reunión.

  - Para personalizar las invitaciones a reuniones, los administradores pueden agregar un logotipo personalizado, una dirección URL de soporte o de renuncia legal o, incluso, texto de pie de página personalizado. Para obtener más información, consulte [Personalización del complemento para reunión en línea en Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - Con los nuevos controles para desactivar el audio de los asistentes, los organizadores de reuniones pueden programar conferencias que tengan desactivado el audio y el vídeo de los asistentes de forma predeterminada.

## Complemento de infraestructura de escritorio virtual

El cliente de Lync 2013 ahora admite audio y vídeo en un entorno de Infraestructura de escritorio virtual (VDI). Así, un usuario puede conectar un dispositivo de audio o vídeo (por ejemplo, un auricular o una cámara web) al equipo local (por ejemplo, un cliente ligero o equipo reasignado). El usuario puede conectarse a la máquina virtual, iniciar sesión en el cliente de Lync 2013 que se ejecuta en ella y participar en la comunicación de vídeo y audio en tiempo real, como si el cliente se ejecutara de manera local. En un entorno de escritorio virtual se admiten las siguientes características:

  - Integración de dispositivos de audio y vídeo, incluidos los siguientes:
    
      - Controles de llamada desde el dispositivo
    
      - Integración de presencia en el dispositivo
    
      - Compatibilidad con varios HID (dispositivos de interfaz humana)

  - Soporte de servicios de emergencia y ubicación.

  - Soporte para todas las modalidades de Lync, como la mensajería instantánea, audio, vídeo, uso compartido de aplicaciones, uso compartido de escritorio, uso compartido de PowerPoint, pizarra y transferencia de archivos.

  - Compatibilidad con audio y vídeo en llamadas de persona a persona y en las llamadas de conferencia.

Para obtener información sobre cómo implementar el complemento de VDI, consulte [Implementación del complemento VDI de Lync en Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

## Mejoras en el vídeo

Son varias las características nuevas que mejoran la experiencia de vídeo de los participantes en una conferencia.

  - El vídeo se ha mejorado con características de detección de rostro y fotograma inteligente, de modo que el vídeo de los participantes se mueve para que estos aparezcan centrados en el fotograma en todo momento.

  - Ahora se admite el vídeo de alta definición en las llamadas entre dos participantes o las conferencias con varios participantes. Los usuarios disfrutarán de resoluciones de alta definición de hasta 1.080p.

  - Los participantes pueden seleccionar uno de los diversos diseños de reunión disponibles: la vista de galería muestra las imágenes o vídeos de todos los participantes; la vista de orador muestra el contenido de la reunión y la imagen o vídeo de quien esté hablando en ese momento; la vista de presentación muestra únicamente el contenido de la reunión; y la vista compacta muestra solo los controles de la reunión.

  - Gracias a la nueva característica de galería, los participantes podrán ver varios vídeos al mismo tiempo. Si la conferencia cuenta con más de cinco participantes, aparecerán solo los vídeos de los que sean más activos en la fila superior, mientras que del resto de participantes se mostrarán las imágenes.

  - Los participantes pueden anclar el vídeo para seleccionar una o varias de las fuentes de vídeo disponibles de forma que estén visibles en todo momento.

  - Los moderadores pueden usar la característica de primer plano de vídeo para seleccionar la fuente de vídeo de una persona de forma que el resto de asistentes de la reunión solo vean a esa persona.

## Integración del salón de chat

Lync 2013 contiene ahora las características que antes proporcionaba el Chat en grupo de Lync 2010. Ya no se necesita un cliente de chat en grupo por separado.

  - Los usuarios pueden usar Lync 2013 para buscar salones de chat, agregar salones de chat a sus contactos, supervisar la actividad de los salones de chat y leer y publicar mensajes.

  - Los usuarios pueden crear fuentes de temas para que se les avise si alguien en uno de sus salones de chat agrega una publicación que contiene palabras clave específicas.

  - Con la nueva página de opciones de **Chat persistente** , los usuarios pueden establecer sonidos y alertas de notificación que se activan cuando la gente publica mensajes en sus salones de chat.

## Actualizaciones de Lync Web App

Lync Web App es el cliente de conferencias basado en web que se usa en las reuniones de Lync Server 2013. En esta versión, el audio y vídeo del equipo se incorpora a Lync Web App, de modo que cualquiera que no tenga un cliente de Lync instalado localmente podrá disfrutar de una experiencia de reunión completa. Los participantes de las reuniones disponen de acceso a todas las características de colaboración y uso compartido, y a los controles de reunión del moderador.

Lync Web App se abre cuando un usuario trata de unirse a una reunión, pero no tiene el cliente instalado localmente. Si desea incluir más opciones para unirse a una reunión, puede configurar la página de participación en reuniones. Consulte [Configuración de la página de participación en reuniones en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) en la documentación de implementación para informarse al respecto.

Debido a las mejoras realizadas en Lync Web App, no existe una versión actualizada de Asistente en Lync Server 2013. Lync Web App es el cliente que eligen los participantes ajenos a la organización. No se necesita instalar ningún cliente local, si bien las características de audio, vídeo y uso compartido requieren que se instale un complemento la primera vez que se usen.

## Actualizaciones de Lync 2013 para clientes móviles

Además de funcionalidades mejoradas de mensajería instantánea, contactos y presencia, los clientes móviles de Lync 2013 ahora proporcionan llamadas de voz y vídeo a través de conexiones de Internet y de datos móviles. Con un simple punteo en el vínculo de reunión de un elemento del calendario, los usuarios móviles pueden unirse a reuniones de voz y vídeo de Lync. Para obtener más información sobre los clientes móviles de Lync 2013, consulte [Planeación de clientes móviles](lync-server-2013-planning-for-mobile-clients.md).

## Actualizaciones en la interfaz de usuario de Lync 2013

## Actualizaciones de accesibilidad

Lync 2013 incluye nuevas características de accesibilidad.

  - Lync 2013 admite alta resolución de ppp, de modo que los usuarios pueden escalar texto y gráficos de 125 % y 150 % puntos por pulgada.

  - Lync admite altos contrastes, con lo cual la interfaz de usuario seguirá funcionando completamente cuando se usen temas de alto contraste de Windows.

  - Lync ofrece más de 100 métodos abreviados de teclado para que se pueda acceder a las funciones importantes prescindiendo del mouse. Así, se puede presionar Alt+C para aceptar una llamada o Alt+I para omitirla, todo ello sin necesidad de usar el tabulador o establecer el foco. Con Alt+Q se finaliza una llamada, con Ctrl+N se inicia OneNote y con Alt+T se abre el menú Herramientas.

  - La compatibilidad extendida de Lync 2013 con el lector de pantalla garantiza que todas las notificaciones, solicitudes entrantes y mensajes instantáneos se van a leer en voz alta cuando haya un lector de pantalla habilitado.

## Presencia al compartir

Cuando Lync detecta que un usuario está compartiendo contenido, Lync le asigna automáticamente el estado de presencia Presentando. Con este estado se bloquean todas las comunicaciones entrantes, a menos que el remitente tenga asignada una relación de privacidad Grupo de trabajo. Si el usuario usa la característica de uso compartido completamente en un segundo monitor, Lync no asignará el estado Presentando.

## Actualizaciones en la ventana de conversación

El nuevo diseño de la ventana de conversación proporciona un acceso más rápido a las funciones importantes.

  - Con la nueva función de conversaciones en pestaña, ahora los usuarios pueden mantener todos sus mensajes instantáneos y salones de chat en una ventana de conversación. Las pestañas situadas en la parte izquierda de la ventana de conversación permiten a los usuarios desplazarse con facilidad entre todas las conversaciones activas.

  - Los usuarios pueden separar una conversación individual en una ventana propia cuyo tamaño puede cambiarse. También pueden devolver la ventana a la ventana de conversión principal.

  - Lync 2013 vuelve a abrir las conversaciones de un usuario cuando este cierra una sesión y vuelve a iniciarla en Lync.

  - Los usuarios pueden agregar rápidamente mensajes instantáneos, vídeo, uso compartido de programas, uso compartido de escritorio o herramientas de conferencia web (pizarra, notas de reunión, blocs de notas compartidos y archivos adjuntos) a cualquier conversación.

  - En una reunión donde se comparte vídeo o contenido, los usuarios pueden separar el contenido compartido o el vídeo de la reunión, y cambiar el tamaño de la ventana.

## Actualizaciones en la ventana principal de Lync

El nuevo aspecto optimizado conserva características familiares como el campo de nota **¿Qué sucede hoy?** , el selector de estado y el selector **Establecer su ubicación** .

  - Cuando los salones de chat se habilitan, los usuarios verán un nuevo icono **Salones de chat** en la página principal de Lync. Con este icono, los usuarios podrán acceder rápidamente a sus salones de chat y filtros.

  - Los usuarios pueden hacer clic en los iconos de vista para alternar entre las vistas **Contactos**, **Salones de chat**, **Conversaciones** o **Teléfono**.

  - En caso de que los usuarios hayan migrado a Exchange 2013, podrán cargar una imagen de alta resolución.

## Actualizaciones en la vista de contactos y la tarjeta de contacto

Lync 2013 proporciona a los usuarios diferentes formas de ver contactos y grupos en la vista **Contactos**.

  - Con el nuevo almacén de contactos unificados, cuando los contactos de Lync de un usuario se migren a Exchange 2013, dicho usuario podrá acceder a sus contactos desde Lync 2013, Outlook o Outlook Web App y administrarlos desde allí. Además, sus Favoritos permanecerán sincronizados en todo momento. Así, por ejemplo, si un usuario agrega un contacto a Favoritos en Outlook, aparecerá también en el grupo de Favoritos de Lync 2013.

  - Si ha agregado y configurado el proxy XMPP y la puerta de enlace XMPP, los usuarios podrán agregar contactos procedentes de asociados basados en XMPP para la mensajería instantánea y presencia.

  - La nueva característica para agregar contactos que no son de la organización constituye una forma sencilla de agregar personas ajenas a la organización.

  - Un nuevo grupo **Favoritos** permite a los usuarios crear una lista de personas con las que más a menudo se comunican para agilizar el acceso.

  - Los usuarios pueden usar la nueva página de opciones **Lista de contactos** para elegir cómo desean ordenar y mostrar los contactos. De este modo, pueden seleccionar una vista expandida de dos líneas que muestra las imágenes de los contactos o una vista condensada de una línea. También pueden ordenar los contactos alfabéticamente o por la disponibilidad.

## Actualizaciones en las conferencias

Lync 2013 realiza diversas mejoras en las características de conferencias.

  - En función del tipo de reunión, ahora los usuarios pueden silenciar la audiencia y permitir o bloquear el uso compartido de video al programar la reunión. Estas opciones están disponibles en la página **Opciones de reunión** y se recomiendan para grandes reuniones con más de 20 participantes.

  - Los controles de audio fáciles de usar en la sala de reuniones permiten al usuario controlar las opciones de audio, tales como silenciar, quitar silencio, cambiar el dispositivo y así sucesivamente.

  - Al compartir programas, los usuarios pueden seleccionar varios programas para compartir si necesitan trabajar con más de un programa.

  - Los usuarios ahora pueden cargar presentaciones que contienen clips de vídeo cargando el archivo de PowerPoint y apuntando el ratón en la diapositiva para mostrar los controles de vídeo, como reproducir, pausar y los controles de audio.

  - En una reunión, los usuarios pueden usar la opción **Combinar esta llamada con** del menú **Más opciones** ( **…** ) para combinar otra conversación ya abierta con la reunión.

  - Para ver los nombres de los participantes, los usuarios pueden colocar el ratón sobre el botón **Ver participantes** o hacer clic en **Mostrar lista de participantes** para acoplar el panel de la reunión.

  - En función del tipo de reunión, los usuarios pueden seleccionar entre varias vistas distintas de contenidos y participantes.

  - Las grabaciones de reunión se guardan automáticamente en un formato que se reproduce en el Reproductor de Windows Media (MP4). Los usuarios fácilmente pueden compartir el archivo con cualquier persona o utilizar la función **Publicar** del administrador de grabación para publicar la grabación en una ubicación compartida.

  - OneNote ofrece nuevas maneras para colaborar en una reunión. Durante una reunión, los usuarios pueden tomar notas con OneNote para uso personal después de la reunión, o utilizar blocs de notas compartidos y colaborar en su edición con los otros participantes en tiempo real. Todos los miembros del equipo pueden tener acceso a las notas compartidas para aportar información, intercambiar ideas o usar las páginas del bloc de notas como pizarra virtual. Las personas y el contenido compartidos en la reunión se agregan automáticamente a las notas.

  - Los usuarios pueden cambiar entre los tipos de contenido con la opción **Compartir contenido y coordinar actividades de la reunión** en la parte inferior de la sala de reuniones. También pueden usar el menú **Administrar contenido presentable** para elegir qué contenido desean compartir.

## Vea también

#### Otros recursos

[Planeación de clientes en Lync Server 2013](lync-server-2013-planning-for-clients.md)

