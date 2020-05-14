---
title: Planeación de conferencias en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Resumen: Lea este tema para obtener información sobre las características y capacidades de conferencia en Skype empresarial Server.'
ms.openlocfilehash: 1c67eecda6c7691dfbb042f4743733b73864a426
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221170"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planeación de conferencias en Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre las características y capacidades de conferencia en Skype empresarial Server.
  
Las conferencias en Skype empresarial Server permiten a los usuarios reunirse y retener conferencias en línea con el cliente de Skype empresarial en lugar de que todos se reúnan en la misma habitación. Los participantes de la reunión pueden conectarse a una reunión con el cliente de Skype empresarial para obtener una experiencia de audio y vídeo completa, o llamar a una conferencia con un teléfono. Las conferencias también admiten la mensajería instantánea, el uso compartido de aplicaciones y escritorios y las tarjetas blancas interactivas.
  
En este tema se incluyen las siguientes secciones:
  
- Características y capacidades de la Conferencia
    
- Componentes de conferencia
    
- Directivas de conferencia
    
- Compatibilidad con reuniones grandes
    
- Determinación de las necesidades de la organización
    
## <a name="conferencing-features-and-capabilities"></a>Características y capacidades de la Conferencia

Hay cuatro tipos de conferencias disponibles en Skype empresarial Server: Conferencia Web, Conferencia de audio y vídeo (A/V), Conferencia de acceso telefónico local y Conferencia de mensajes instantáneos (mi). 
  
Puede optar por habilitar todos los tipos de conferencia o usar un solo tipo, según sus necesidades. Por ejemplo, puede habilitar todos los tipos, incluidas las conferencias de acceso telefónico local, para permitir que los usuarios que no pueden unirse a una conferencia con un cliente de Skype empresarial puedan llamar y participar en el audio de la reunión desde un teléfono. Al implementar Skype empresarial Server, las capacidades de conferencia de mensajería instantánea se implementan automáticamente; Especifique si desea implementar la web, a/V y las conferencias de acceso telefónico local con el generador de topologías. Para obtener más información, vea [deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
En las subsecciones siguientes se describen las características y capacidades de cada tipo de conferencia.
  
### <a name="web-conferencing"></a>Conferencia web

La conferencia web permite a los asistentes a la reunión colaborar en documentos compartidos durante la reunión y para que el moderador de la reunión comparta las aplicaciones a través del cliente de Skype empresarial. La conferencia web proporciona las siguientes características: 
  
- **Pizarra y anotaciones.** Una pizarra es un lienzo en blanco que se puede usar para la colaboración con texto, lápiz, dibujos e imágenes. Las anotaciones hechas en las pizarras pueden verlas todos los participantes en la reunión. La característica de pizarra mejora la colaboración porque permite a los participantes de la reunión debatir, intercambiar ideas, tomar notas, etc.
    
- **Sondeo.** La característica de sondeo mejora la colaboración al permitir que los moderadores determinen rápidamente las preferencias de los participantes. Durante las conversaciones y reuniones en línea, los moderadores pueden usar el sondeo para recabar respuestas anónimas de los participantes. Todos los moderadores pueden ver los resultados y elegir entre ocultarlos o mostrarlos a todos los asistentes.
    
- **Uso compartido de aplicaciones y uso compartido de escritorio.** Durante una conferencia, el moderador de la reunión puede compartir todo el escritorio, una aplicación individual o monitores individuales en un entorno de varios monitores. Aparte de ver el contenido, otros participantes de la Conferencia pueden solicitar el control de la pantalla del moderador y, con permiso, interactuar con el contenido (incluido el desplazamiento y la edición). Los participantes de la reunión también pueden tomar el control como moderador y empezar a compartir contenido durante la reunión.
    
- **Uso compartido de PowerPoint.** Permite a los usuarios compartir presentaciones de PowerPoint en la reunión a través de un servidor de Office Web Apps, que permite:
    
  - Pantallas de alta resolución y compatibilidad con las capacidades de PowerPoint, como animaciones, transiciones de diapositivas y vídeo incrustado.
    
  - Los dispositivos móviles pueden tener acceso a estas presentaciones.
    
  - Los usuarios con los permisos adecuados pueden desplazarse por una presentación de PowerPoint independientemente de la propia presentación. Por ejemplo, aunque Ken está presentando su presentación con diapositivas, Heidi puede mirar cualquier diapositiva que quiera sin afectar a la presentación de Ken.
    
### <a name="audio-and-video-conferencing"></a>Conferencias de audio y vídeo

La Conferencia de audio y vídeo permite el audio y el vídeo en la reunión. El audio permite que los asistentes se comuniquen entre sí como si estuvieran en la misma habitación. El vídeo permite mostrar vídeo en el cliente de Skype empresarial de los asistentes o moderadores que se unen a la reunión con una cámara web o un dispositivo de conferencia que admita vídeo.
  
 Skype empresarial Server proporciona varias características que los usuarios pueden usar para configurar la experiencia de audioconferencia del usuario, entre las que se incluyen las siguientes:
  
- **Silenciar la audiencia.** El moderador puede usar esta opción para desactivar el audio de todos los participantes en la conferencia y poner la conferencia en un estado en el que los participantes que no son moderadores no puedan activar su audio.
    
- **Anuncios de entrada y salida de conferencia.** Si ha habilitado las conferencias de acceso telefónico, los moderadores pueden usar esta opción para activar o desactivar los anuncios de entrada para minimizar las distracciones cuando una conferencia está en curso.
    
- **Adición de un usuario mediante llamadas salientes.** Los moderadores y asistentes a los que se haya concedido permiso pueden agregar números RTC a las conferencias y hacer que la Conferencia realice llamadas de salida a esos números.
    
  Skype empresarial Server proporciona varias características que los usuarios pueden usar para configurar la experiencia de las conferencias de vídeo del usuario, entre las que se incluyen las siguientes:
  
- **Vista de galería.** En las videoconferencias con más de dos personas, los usuarios se ven entre sí automáticamente. Si la conferencia tiene más de cinco participantes, el vídeo de los participantes más activos se muestra en la fila superior y solo se muestra la foto de los demás participantes. De forma predeterminada, el vídeo entre varias partes está activado.
    
- **Vídeo panorámico.** Si hay instalado un dispositivo de videoconferencia RoundTable en la sala de conferencias, esta característica ofrece una vista de 360 grados de la sala de conferencias. La tira de vídeo panorámico solo está disponible con dispositivos RoundTable.
    
- **Modo de vídeo de solo moderador.** Los moderadores pueden configurar la reunión para que solo se muestre el vídeo del moderador. Así se evitan distracciones en reuniones grandes cuando hay disponibles varias secuencias de vídeo y se bloquean los diferentes orígenes. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable.
    
- **Foco de vídeo.** Los moderadores pueden configurar la reunión para que los participantes de la conferencia solo vean el vídeo de un participante seleccionado que sea un origen de vídeo. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable de vídeo panorámico.
    
### <a name="dial-in-conferencing"></a>Conferencia de acceso telefónico local

Las conferencias de acceso telefónico local permiten a los asistentes a la reunión unirse a la parte de audio de una reunión llamando a la reunión desde un teléfono. La conferencia de acceso telefónico local es un subconjunto de la conferencia de audio y requiere configuración adicional. Para obtener más información sobre las conferencias de acceso telefónico local, vea [Plan for Dial-in Conferencing in Skype for Business Server](dial-in-conferencing.md) y [Configure Dial-in Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conferencia de mensajería instantánea

La Conferencia de mensajería instantánea permite que más de dos partes se comuniquen en una sola sesión de mi. Para obtener más información sobre las conferencias de mensajería instantánea, vea [Plan for Instant Messaging and Presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Componentes de conferencia

Entre los componentes que admiten características de conferencia se incluyen los siguientes:
  
- **Servicio de aplicación.** El servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas (UC). Las conferencias de acceso telefónico local usan dos aplicaciones de comunicaciones unificadas que requieren el servicio de aplicación: operador de conferencia y anuncio de conferencia. El servicio de aplicación se instala y activa de forma predeterminada en cada servidor front-end de un grupo de servidores front-end. También se instala en todos los servidores Standard Edition para habilitar y configurar las conferencias de acceso telefónico local.
    
- **Aplicación de operador de conferencia.** La aplicación de operador de conferencia es una aplicación de comunicaciones unificadas que acepta llamadas de red telefónica conmutada (RTC), reproduce preguntas y une las llamadas a una conferencia a/V. La aplicación de operador de conferencia se instala y activa de forma predeterminada al habilitar las conferencias de acceso telefónico local.
    
- **Aplicación de anuncio de conferencia.** La aplicación de anuncio de conferencia es una aplicación de comunicaciones unificadas que reproduce tonos y mensajes a los participantes de RTC en determinadas acciones, como cuando un participante se une a una conferencia o la abandona, los participantes se silencian o se desactivan, por ejemplo, alguien entra en la sala de espera o la Conferencia está bloqueada o desbloqueada. La aplicación de anuncio de conferencia también es compatible con los comandos de tono de marcado de frecuencia múltiple (DTMF) del teclado del teléfono. La aplicación de anuncio de conferencia se instala y activa automáticamente de forma predeterminada al habilitar las conferencias de acceso telefónico local.
    
- **Página configuración de conferencia de acceso telefónico local.** La página de configuración de la Conferencia de acceso telefónico local muestra los números de acceso telefónico de conferencia con los idiomas disponibles, la información de conferencia asignada (es decir, para las reuniones que no necesitan programarse) y los controles de DTMF en conferencia, y admite la administración del número de identificación personal (PIN) y la información de conferencia asignada. La página de configuración de la Conferencia de acceso telefónico local se instala automáticamente como parte de los servicios Web.
    
- **Servidor de mediación y puerta de enlace RTC.** La Conferencia de acceso telefónico local requiere un servidor de mediación para convertir la señalización (y los medios en algunas configuraciones) entre Skype empresarial Server y la puerta de enlace RTC, y una puerta de enlace RTC para convertir la señalización y los medios entre el servidor de mediación y la puerta de enlace RTC. Para las conferencias de acceso telefónico local, debe implementar al menos un servidor de mediación y, al menos, uno de los siguientes elementos:
    
  - Una puerta de enlace RTC
    
  - IP-PBX
    
  - Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta mediante la configuración de un tronco SIP
    
  > [!NOTE]
  > Si también está implementando la telefonía IP empresarial, el servidor de mediación y las puertas de enlace RTC forman parte de la implementación de telefonía IP empresarial. Si no está implementando Enterprise Voice, debe implementar al menos un servidor de mediación y al menos una puerta de enlace RTC, IP-PBX o SBC para las conferencias de acceso telefónico local. 
  
- **Almacén de archivos.** El almacenamiento de archivos se usa para los archivos de audio de los nombres grabados. El almacenamiento de archivos es un componente estándar de toda implementación Enterprise Edition o Standard Edition.
    
- **Almacén de usuario.** El almacén de usuario se usa para almacenar los pin de Skype empresarial Server del usuario. Los PIN tienen asignado un algoritmo hash. El almacenamiento de usuarios es un componente estándar de toda implementación Enterprise Edition o Standard Edition.
    
- **Office Web Apps Server.** Para poder usar las capacidades de conferencia Web, los administradores deben instalar Office Web Apps Server y deben configurar Skype empresarial Server para comunicarse con Office Web Apps Server.
    
## <a name="conferencing-policies"></a>Directivas de conferencia

Para aplicar las directivas de la organización y controlar el uso del ancho de banda, puede establecer directivas para los tipos de reuniones que los usuarios pueden organizar. Puede definir una amplia variedad de directivas de conferencia y asignarlas a usuarios individuales y grupos de usuarios. También se pueden establecer las directivas que rigen las conversaciones de punto a punto. Para obtener más información sobre cómo establecer directivas de conferencia, consulte [Manage Conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md). Para obtener más información acerca de la administración del ancho de banda, consulte [Plan for Call Admission Control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Compatibilidad con reuniones grandes

El tamaño de las reuniones que Skype empresarial Server puede admitir depende de si las conferencias se hospedan en un grupo de servidores compartido o dedicado:
  
- En un grupo compartido, Skype empresarial Server puede hospedar reuniones con hasta 250 usuarios. Un grupo compartido es un grupo que hospeda todas las cargas de trabajo de Skype empresarial Server, incluidas la mensajería instantánea (mi) y la presencia, la Conferencia y la telefonía IP empresarial. 
    
- En un grupo de servidores dedicado, Skype empresarial Server puede admitir reuniones con un máximo de 1000 participantes mediante la Conferencia de audio/vídeo (A/V), incluido el uso compartido de presentaciones de PowerPoint. Esta compatibilidad requiere un grupo dedicado configurado para admitir reuniones grandes y administrado de manera que garantice que solo hospedará una reunión grande al mismo tiempo. 
    
Para obtener más información acerca de la administración de reuniones grandes, vea [Plan for Large Meetings in Skype for Business Server](large-meetings.md).
  
Si su organización requiere capacidades de reunión mayores, considere la posibilidad de implementar un entorno híbrido que aprovecha la difusión de reunión de Skype, un servicio en línea que forma parte de Microsoft 365 y Office 365. La difusión de reunión de Skype permite a los usuarios hospedar y difundir reuniones a grandes audiencias en línea de hasta 10.000 participantes. El uso de difusión de reunión de Skype requiere que Skype empresarial Server ya esté configurado en una configuración híbrida con una organización de producción Microsoft 365 u Office 365. Todos los usuarios deben tener un inquilino en línea establecido como requisito previo. Si está interesado en implementar una solución híbrida que puede aprovechar la difusión de reunión de Skype, vea [Configure Your on-premises Deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Determinar las necesidades de la organización

Al determinar qué capacidades de conferencia se van a implementar, debe tener en cuenta las características que desea que estén disponibles para los usuarios y las capacidades de ancho de banda de la red. La siguiente lista le guía a través del proceso de planeación de la Conferencia para determinar qué características de la Conferencia debe implementar en función de los requisitos de la organización.
  
> [!NOTE]
> Cuando se habilita la Conferencia durante la implementación, se habilitan automáticamente las conferencias web y A/V. Sin embargo, puede deshabilitar características específicas mediante la configuración de directivas de conferencia como se describió anteriormente en este tema. 
  
- **¿Desea habilitar la conferencia web, lo que incluye colaboración en documentos y uso compartido de aplicaciones?**
    
    Si es así, debe habilitar las conferencias para el grupo de servidores front-end mediante la herramienta de planeación o mediante el generador de topologías. Para obtener más información, vea [deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    El uso compartido de aplicaciones requiere y usa un mayor ancho de banda que la colaboración en documentos. Skype empresarial Server proporciona un mecanismo de limitación para controlar cada sesión de uso compartido de aplicaciones. De forma predeterminada, este está establecido en 1,5 KB/segundo para cada sesión. Si no desea habilitar el uso compartido de aplicaciones, pero sí desea colaborar en los documentos, puede habilitar la Conferencia y usar directivas de conferencia para deshabilitar el uso compartido de aplicaciones. Para obtener más información sobre cómo configurar directivas de conferencia, consulte [Manage Conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    Para permitir que los usuarios compartan presentaciones de PowerPoint, debe configurar Office Web Apps Server. Para más información sobre la configuración de Office Web Apps Server, vea [Configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **¿Desea habilitar las conferencias de audio y vídeo?**
    
    Si es así, debe habilitar las conferencias para el grupo de servidores front-end mediante la herramienta de planeación o mediante el generador de topologías. Para obtener más información, vea [deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    La Conferencia de audio y vídeo requiere y usa más ancho de banda de red que las conferencias web (lo que incluye colaboración en documentos y uso compartido de aplicaciones). Si no desea habilitar la Conferencia de audio y vídeo, pero desea habilitar la conferencia Web, puede habilitar la Conferencia y usar directivas de conferencia para deshabilitar las conferencias de A/V.
    
    Si desea habilitar conferencias de audio, pero no videoconferencias, puede habilitar las conferencias a/V y usar directivas de conferencia para evitar las conferencias de vídeo. Como alternativa, puede habilitar la conferencia A/V y habilitar solo a determinados usuarios para que inicien conferencias A/V o participen en ellas. 
    
    Para obtener más información acerca de la configuración de directivas de conferencia, consulte [Manage Conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > La telefonía IP empresarial no es necesaria para usar la conferencia A/V. Si habilita las conferencias A/V, los usuarios pueden agregar audio a sus conferencias si tienen dispositivos de audio, incluso si usa una PBX para la solución telefónica. 
  
- **¿Desea permitir que los usuarios se unan a secciones de audio de conferencias al usar un teléfono RTC?**
    
    Si es así, implemente y habilite las conferencias de acceso telefónico local. De este modo, los usuarios invitados, tanto de dentro como de fuera de la organización, podrán unirse a la sección de audio de las conferencias a través de un teléfono RTC.
    
    La Conferencia de acceso telefónico local es una característica opcional que puede configurar al implementar la Conferencia de Skype empresarial Server. Aunque la Conferencia de acceso telefónico local usa algunos de los mismos componentes que usa la telefonía IP empresarial, puede implementar la Conferencia de acceso telefónico local aunque no implemente la telefonía IP empresarial. Las conferencias de acceso telefónico local admiten tanto a usuarios de empresa como a usuarios anónimos. Para obtener más información acerca de la configuración de conferencias de acceso telefónico local y usuarios anónimos, consulte [implementar conferencias en Skype empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md) y [configurar la Conferencia de acceso telefónico local en Skype empresarial Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **¿Desea permitir que los usuarios externos con clientes de Skype empresarial se unan a conferencias?**
    
    Al permitir la participación externa en las reuniones, se maximiza la inversión en Skype empresarial Server. Entre los usuarios externos se pueden incluir:
    
  - **Usuarios remotos.** Los propios usuarios de su organización, cuando trabajan fuera de los firewalls y están usando sus equipos portátiles u otros dispositivos de Skype empresarial Server.
    
  - **Usuarios federados.** Usuarios de compañías con las que trabaja y que también ejecutan Skype empresarial Server. Para habilitar a sus usuarios para que se pongan en contacto fácilmente con estos usuarios, cree relaciones federadas con estas compañías.
    
  - **Usuarios anónimos.** Cualquier otro usuario externo al que sus usuarios inviten específicamente a unirse a determinadas conferencias. Un organizador de reuniones de su compañía puede enviar una invitación por correo electrónico a un usuario externo para una conferencia. El correo electrónico incluye un vínculo en el que el usuario externo puede hacer clic para unirse a la conferencia.
    
    Si desea permitir usuarios externos, deberá implementar servidores perimetrales. Además, con los servidores perimetrales implementados se pueden crear relaciones federadas con otras organizaciones (como los clientes o proveedores) y los usuarios de dichas organizaciones podrán colaborar más fácilmente con los usuarios.
    
    Para obtener más información sobre la implementación de servidores perimetrales, vea Plan for Edge Servers e deploy Edge servers. Para obtener información detallada sobre cómo habilitar el acceso externo para Office Web Apps Server, vea [Configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **¿Desea controlar los clientes que pueden unirse a reuniones de Skype empresarial Server?**
    
    Si es así, debe configurar la página de participación en la reunión para que solo estén disponibles las opciones de cliente que desea admitir. Cada vez que un usuario hace clic en un vínculo para unirse a una reunión programada, Skype empresarial Server detecta si un cliente ya está instalado en el equipo. A continuación, inicia el cliente predeterminado y abre la página de participación en la reunión, que contiene vínculos para clientes alternativos. La página de participación en la reunión siempre contiene la opción de usar la aplicación Web de Skype empresarial. Además de esta opción, puede decidir si desea incluir vínculos para asistentes y versiones anteriores de Communicator. 
    

