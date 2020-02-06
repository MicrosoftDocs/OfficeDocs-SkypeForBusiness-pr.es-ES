---
title: Planear la Conferencia en Skype empresarial Server
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
description: 'Resumen: Lea este tema para obtener información sobre las características y capacidades de conferencia de Skype empresarial Server.'
ms.openlocfilehash: f91c815cf0b5d0b69ad5815157cba7a56bb28307
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816008"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planear la Conferencia en Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre las características y capacidades de conferencia de Skype empresarial Server.
  
Las conferencias de Skype empresarial Server permiten a los usuarios reunirse y mantener conferencias en línea con el cliente de Skype empresarial en lugar de que todos se reúnan en la misma habitación. Los participantes de la reunión pueden conectarse a una reunión con el cliente de Skype empresarial para obtener una experiencia de audio y vídeo completa, o llamar a una conferencia con un teléfono. Las conferencias también admiten la mensajería instantánea, el uso compartido del escritorio y aplicaciones y las pizarras interactivas.
  
Este tema incluye las secciones siguientes:
  
- Características y funciones de las conferencias
    
- Componentes de conferencia
    
- Directivas de conferencia
    
- Compatibilidad con reuniones grandes
    
- Determinar las necesidades de su organización
    
## <a name="conferencing-features-and-capabilities"></a>Características y funciones de las conferencias

Existen cuatro tipos de conferencias disponibles en Skype empresarial Server: conferencias web, conferencias de audio y vídeo (A/V), conferencias de acceso telefónico local y conferencias de mensajes instantáneos (mi). 
  
Puede optar por activar todos los tipos de conferencia o por usar solo un tipo, según sus necesidades. Por ejemplo, puede habilitar todos los tipos, incluidas las conferencias de acceso telefónico local, para permitir que los usuarios que no pueden unirse a una conferencia con un cliente de Skype empresarial puedan llamar y participar en el audio de la reunión desde un teléfono. Al implementar Skype empresarial Server, las capacidades de conferencia de mensajería instantánea se implementan automáticamente; puede especificar si desea implementar una web, una/V y una conferencia de acceso telefónico local con el generador de topología. Para obtener más información, consulte [implementar conferencias en Skype empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
En las siguientes subsecciones se describen las características y funciones de cada tipo de conferencia.
  
### <a name="web-conferencing"></a>Conferencia web

Las conferencias web permiten a los asistentes a la reunión colaborar en documentos compartidos durante la reunión y que el moderador de la reunión comparta las aplicaciones a través del cliente de Skype empresarial. La conferencia web dispone de las siguientes características: 
  
- **Pizarra y anotaciones.** Una pizarra es un lienzo en blanco que se puede usar para la colaboración con texto, lápiz, dibujos e imágenes. Las anotaciones hechas en las pizarras pueden verlas todos los participantes en la reunión. La característica de pizarra mejora la colaboración porque permite a los participantes de la reunión debatir, intercambiar ideas, tomar notas, etc.
    
- **Sondeo.** La característica de sondeo mejora la colaboración, ya que permite a los moderadores determinar rápidamente las preferencias de los participantes. Durante las conversaciones y reuniones en línea, los moderadores pueden usar el sondeo para recabar respuestas anónimas de los participantes. Todos los moderadores pueden ver los resultados y elegir entre ocultarlos o mostrarlos a todos los asistentes.
    
- **Uso compartido de aplicaciones y escritorios.** Durante una conferencia, el moderador de la reunión puede compartir el escritorio completo, una aplicación individual o monitores individuales en un entorno de varios monitores. Aparte de ver solo el contenido, otros participantes en la conferencia pueden solicitar control de la pantalla del moderador y, con permiso, interactuar con el contenido (incluyendo desplazarse y editar). Los participantes de la reunión también pueden tomar el control como moderador y empezar a compartir contenido durante la reunión.
    
- **Uso compartido de PowerPoint.** Permite a los usuarios compartir presentaciones de PowerPoint en la reunión a través de un Office Web Apss Server, que le permite:
    
  - Pantallas de mayor resolución y compatibilidad con las capacidades de PowerPoint, como animaciones, transiciones de diapositivas y vídeo incrustado.
    
  - Los dispositivos móviles pueden tener acceso a estas presentaciones.
    
  - Los usuarios con los permisos adecuados pueden desplazarse a través de una presentación de PowerPoint independiente de la propia presentación. Por ejemplo, mientras que Ken realiza su presentación, Heidi puede ver cualquier diapositiva que quiera, sin que esto afecte a la presentación de Ken.
    
### <a name="audio-and-video-conferencing"></a>Conferencia de audio y vídeo

Las conferencias de audio y vídeo permiten el uso de audio y vídeo en la reunión. El audio permite a los asistentes hablar unos con otros como si estuvieran en la misma sala. El vídeo muestra la pantalla de vídeo en el cliente de Skype empresarial de cualquier asistente o moderador que se una a la reunión con un dispositivo de conferencia o cámara web compatible con el vídeo.
  
 Skype empresarial Server proporciona varias características que los usuarios pueden usar para configurar la experiencia de audioconferencia para el usuario, entre las que se incluyen las siguientes:
  
- **Silencio de la audiencia.** El moderador puede usar esta opción para desactivar el audio de todos los participantes en la conferencia y poner la conferencia en un estado en el que los participantes que no son moderadores no puedan activar su audio.
    
- **Entrada y salida de conferencias.** Si ha habilitado las conferencias de acceso telefónico, los moderadores pueden usar esta opción para activar o desactivar los anuncios de entrada para minimizar las distracciones cuando una conferencia está en curso.
    
- **Agregar un usuario mediante la llamada.** Los moderadores y los asistentes a los que se les ha concedido permiso pueden agregar números de RTC a las conferencias y hacer que la Conferencia se llame a esos números.
    
  Skype empresarial Server proporciona varias características que los usuarios pueden usar para configurar la experiencia de videoconferencia para el usuario, entre las que se incluyen las siguientes:
  
- **Vista de galería.** En las videoconferencias con más de dos personas, los usuarios se ven entre sí automáticamente. Si la conferencia tiene más de cinco participantes, el vídeo de los participantes más activos se muestra en la fila superior y solo se muestra la foto de los demás participantes. De forma predeterminada, el vídeo entre varias partes está activado.
    
- **Vídeo panorámico.** Si hay instalado un dispositivo de videoconferencia RoundTable en la sala de conferencias, esta característica ofrece una vista de 360 grados de la sala de conferencias. La tira de vídeo panorámico solo está disponible con dispositivos RoundTable.
    
- **Modo de vídeo solo para el moderador.** Los moderadores pueden configurar la reunión para que solo se muestre el vídeo del moderador. Así se evitan distracciones en reuniones grandes cuando hay disponibles varias secuencias de vídeo y se bloquean los diferentes orígenes. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable.
    
- **Foco de video.** Los moderadores pueden configurar la reunión para que los participantes de la conferencia solo vean el vídeo de un participante seleccionado que sea un origen de vídeo. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable de vídeo panorámico.
    
### <a name="dial-in-conferencing"></a>Conferencia de acceso telefónico local

Las conferencias de acceso telefónico local permiten a los asistentes a la reunión unirse a la parte de audio de una reunión llamando a la reunión desde un teléfono. La conferencia de acceso telefónico local es un subconjunto de la conferencia de audio y requiere configuración adicional. Para obtener más información sobre las conferencias de acceso telefónico local, consulte [planear las conferencias de acceso telefónico local en Skype empresarial Server](dial-in-conferencing.md) y [configurar conferencias de acceso telefónico local en Skype empresarial Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conferencias de mensajería instantánea

La conferencia de mensajería instantánea permite a más de dos participantes comunicarse en una única sesión de mensajería instantánea. Para obtener más información sobre las conferencias de mensajería instantánea, consulte [planear la mensajería instantánea y la presencia en Skype empresarial Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Componentes de conferencia

Los componentes compatibles con las características de conferencia son los siguientes:
  
- **Servicio de aplicación.** El servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas (UC). Las conferencias de acceso telefónico usan dos aplicaciones de UC que requieren el servicio de aplicación: operador de conferencia y anuncio de conferencia. El servicio de aplicación se instala y activa de forma predeterminada en todos los servidores front-end de un grupo de servidores front-end. También se instala en cada servidor Standard Edition para permitir y configurar la conferencia de acceso telefónico local.
    
- **Aplicación de operador de conferencia.** La aplicación de operador de conferencia es una aplicación de comunicaciones unificadas que acepta las llamadas de la red telefónica conmutada (RTC), reproduce avisos e introduce las llamadas en una conferencia A/V. La aplicación de operador de conferencia se instala y activa de forma predeterminada al habilitar las conferencias de acceso telefónico.
    
- **Aplicación de anuncio de conferencia.** La aplicación de anuncio de conferencia es una aplicación de comunicaciones unificadas que reproduce tonos y avisos para los participantes de RTC en determinadas acciones como, por ejemplo, cuando los participantes entran o salen de una conferencia, cuando se activa o se desactiva el audio de los participantes, cuando alguien entra en la sala de espera de la conferencia o cuando se bloquea o se desbloquea la conferencia. La aplicación de anuncio de conferencia también es compatible con los comandos de tono de marcado de frecuencia múltiple (DTMF) desde el teclado del teléfono. La aplicación de anuncio de conferencia se instala y se activa automáticamente de forma predeterminada al habilitar las conferencias de acceso telefónico local.
    
- **Página de Configuración de conferencia de acceso telefónico local.** La página de Configuración de conferencia de acceso telefónico local muestra los números de acceso telefónico a conferencias con sus idiomas disponibles, la información de las conferencias asignadas (es decir, de las reuniones que no requieren programación) y los controles DTMF de la conferencia, y es compatible con la administración de números de identificación personal (PIN) y la información de conferencias asignadas. La página de Configuración de conferencia de acceso telefónico local se instala automáticamente como parte de los servicios web.
    
- **Servidor de mediación y puerta de enlace RTC.** Las conferencias de acceso telefónico local requieren un servidor de mediación para traducir la señalización (y los medios de algunas configuraciones) entre Skype empresarial Server y la puerta de enlace PSTN, y una puerta de enlace RTC para traducir la señalización y los medios entre el servidor de mediación y la puerta de enlace PSTN . Para las conferencias de acceso telefónico local, debe implementar al menos un servidor de mediación y al menos uno de los siguientes elementos:
    
  - Puerta de enlace RTC
    
  - Un sistema IP-PBX
    
  - Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta por medio de la configuración de un tronco SIP
    
  > [!NOTE]
  > Si también va a implementar la telefonía IP empresarial, el servidor de mediación y las puertas de enlace RTC forman parte de la implementación de telefonía IP empresarial. Si no está implementando la telefonía IP empresarial, debe implementar al menos un servidor de mediación y, como mínimo, una puerta de enlace PSTN, IP-PBX o SBC para las conferencias de acceso telefónico local. 
  
- **Almacenamiento de archivos.** El almacenamiento de archivos se usa para los archivos de audio de los nombres grabados. El almacenamiento de archivos es un componente estándar de toda implementación Enterprise Edition o Standard Edition.
    
- **Almacenamiento de usuarios.** El almacén de usuario se usa para almacenar los pin de los usuarios de Skype empresarial. Los PIN tienen asignado un algoritmo hash. El almacenamiento de usuarios es un componente estándar de toda implementación Enterprise Edition o Standard Edition.
    
- **Office Web Apps Server.** Para poder usar las capacidades de conferencia Web, los administradores deben instalar Office Web Apps Server y deben configurar Skype empresarial Server para comunicarse con Office Web Apps Server.
    
## <a name="conferencing-policies"></a>Directivas de conferencia

Para exigir las directivas de la organización y controlar el uso del ancho de banda, puede establecer directivas para los tipos de reuniones que los usuarios pueden organizar. Puede definir una amplia variedad de directivas de conferencia y asignarlas a usuarios individuales y grupos de usuarios. También puede establecer las directivas que rigen las conversaciones de punto a punto. Para obtener más información sobre cómo configurar directivas de conferencia, consulte [Administrar directivas de conferencia en Skype empresarial Server](../../manage/conferencing/conferencing-policies.md). Para obtener más información acerca de la administración del ancho de banda, consulte [Plan for Call Admission Control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Compatibilidad con reuniones grandes

El tamaño de las reuniones que puede admitir Skype empresarial Server depende de si las conferencias se hospedan en un grupo compartido o dedicado:
  
- En un grupo compartido, Skype empresarial Server puede hospedar reuniones con un máximo de 250 usuarios. Un grupo compartido es un grupo que hospeda todas las cargas de trabajo de Skype empresarial Server, incluidas la mensajería instantánea (mi) y la presencia, Conferencia y telefonía IP empresarial. 
    
- En un grupo dedicado, Skype empresarial Server puede admitir reuniones con un máximo de 1000 participantes que usan conferencias web y de audio/vídeo (A/V), entre las que se incluyen compartir presentaciones de PowerPoint. Esta compatibilidad requiere un grupo dedicado configurado para admitir reuniones grandes y administrado de manera que garantice que solo hospedará una reunión grande al mismo tiempo. 
    
Para obtener más información acerca de la administración de reuniones grandes, vea [planear reuniones grandes en Skype empresarial Server](large-meetings.md).
  
Si su organización requiere capacidades de reunión mayores, considere la posibilidad de implementar un entorno híbrido que aproveche las ventajas de la difusión de reunión de Skype, un servicio en línea que forma parte de Office 365. La difusión de reunión de Skype permite a los usuarios hospedar y difundir reuniones a grandes públicos en línea de hasta 10.000 participantes. El uso de la difusión de reunión de Skype requiere que Skype Empresarial Server ya esté configurado en una configuración híbrida con un inquilino de producción de Office 365. Todos los usuarios necesitan tener un inquilino en línea establecido como requisito previo. Si está interesado en implementar una solución híbrida que puede aprovechar la difusión de reunión de Skype, vea [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Determinar las necesidades de su organización

Al determinar qué funciones de conferencia se van a implementar, es necesario tener en cuenta las características que quiere poner a disposición de los usuarios, así como la capacidad de ancho de banda de la red. La siguiente lista le guiará a través del proceso de planeación de conferencias para determinar qué características de las conferencias debe implementar, en función de los requisitos de la organización.
  
> [!NOTE]
> Al habilitar las conferencias en la implementación, activa automáticamente tanto las conferencias web como las A/V. Pero, puede deshabilitar características específicas al configurar directivas de conferencia según se ha descrito anteriormente en este tema. 
  
- **¿Desea habilitar la conferencia web, que incluye la colaboración con documentos y el uso compartido de aplicaciones?**
    
    En caso afirmativo, necesita habilitar las conferencias para el grupo de servidores front-end con la Herramienta de planeación o por medio del Generador de topologías. Para obtener más información, consulte [implementar conferencias en Skype empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    El uso compartido de aplicaciones requiere y utiliza más ancho de banda de red que la colaboración en documentos. Skype empresarial Server proporciona un mecanismo de limitación para controlar cada sesión de uso compartido de aplicaciones. De forma predeterminada, esto se establece en 1,5 KB por segundo para cada sesión. Si no desea habilitar el uso compartido de aplicaciones pero desea la colaboración de documentos, puede habilitar las directivas de conferencia y de uso para deshabilitar el uso compartido de aplicaciones. Para obtener más información sobre cómo configurar directivas de conferencia, consulte [Administrar directivas de conferencia en Skype empresarial Server](../../manage/conferencing/conferencing-policies.md).
    
    Para que los usuarios puedan compartir presentaciones de PowerPoint, necesita configurar Office Web Apps Server. Para obtener más información sobre cómo configurar Office Web Apps Server, vea [configurar la integración con Office Web Apps Server en Skype empresarial Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **¿Desea habilitar las conferencias de audio y vídeo?**
    
    En caso afirmativo, necesita habilitar las conferencias para el grupo de servidores front-end con la Herramienta de planeación o por medio del Generador de topologías. Para obtener más información, consulte [implementar conferencias en Skype empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Las conferencias de audio y vídeo requieren y usan más ancho de banda que las conferencias web (lo que incluye la colaboración en documentos y los recursos compartidos de aplicaciones). Si no desea habilitar las conferencias de audio y vídeo, pero sí las conferencias web, puede habilitar las conferencias y usar las directivas de conferencia para deshabilitar las conferencias A/V.
    
    Si desea habilitar las conferencias de audio pero no videoconferencias, puede habilitar la conferencia A/V y usar las directivas de conferencia para evitar las conferencias de vídeo. Como alternativa, puede habilitar la conferencia A/V y habilitar únicamente determinados usuarios para que inicien o participen en conferencias A/V. 
    
    Para obtener más información sobre cómo configurar directivas de conferencia, consulte [Administrar directivas de conferencia en Skype empresarial Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > No se necesita la telefonía IP empresarial para usar las conferencias A/V. Si habilita las conferencias A/V, los usuarios que dispongan de dispositivos de audio podrán agregar audio a las conferencias, aun cuando se use una PBX como solución de telefonía. 
  
- **¿Desea permitir que los usuarios se unan a la parte de audio de las conferencias al usar un teléfono PSTN?**
    
    Si es así, implemente y habilite la conferencia de acceso telefónico. Los usuarios invitados, tanto dentro como fuera de su organización, puede unirse entonces a la parte de audio de las conferencias por medio de un teléfono RTC.
    
    Las conferencias de acceso telefónico local son una característica opcional que puede configurar al implementar conferencias de servidor de Skype empresarial. Aunque la conferencia de acceso telefónico local usa algunos de los mismos componentes que usa la telefonía IP empresarial, puede implementar la conferencia de acceso telefónico local aunque no implemente la telefonía IP empresarial. Las conferencias de acceso telefónico local admiten tanto a usuarios de empresa como a usuarios anónimos. Para obtener más información sobre cómo configurar conferencias de acceso telefónico local y usuarios anónimos, consulte [implementar conferencias en Skype empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md) y [configurar conferencias de acceso telefónico local en Skype empresarial Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **¿Desea permitir que los usuarios externos con clientes de Skype Empresarial se unan a conferencias?**
    
    Al permitir la participación externa en las reuniones, podrá maximizar su inversión en Skype empresarial Server. Los usuarios externos pueden incluir:
    
  - **Usuarios remotos.** Los usuarios de su organización, cuando trabajan fuera de los servidores de seguridad y están usando sus equipos portátiles u otros dispositivos de Skype empresarial Server.
    
  - **Usuarios federados.** Usuarios de empresas con las que trabaja y que también ejecutan Skype empresarial Server. Si desea habilitar a sus usuarios para que se pongan en contacto fácilmente con estos otros usuarios, cree relaciones federadas con estas compañías.
    
  - **Usuarios anónimos.** Cualquier otro usuario externo al que sus usuarios inviten específicamente a unirse a determinadas conferencias. Un organizador de reuniones de su compañía puede enviar una invitación por correo electrónico a un usuario externo para una conferencia. El correo electrónico incluye un vínculo en el que el usuario externo puede hacer clic para unirse a la conferencia.
    
    Si desea permitir usuarios externos, tendrá que implementar servidores perimetrales. Además, con los servidores perimetrales implementados se pueden crear relaciones federadas con otras organizaciones (por ejemplo, los clientes o proveedores) y los usuarios de dichas organizaciones podrán colaborar más fácilmente con los usuarios.
    
    Para más información sobre la implementación de servidores perimetrales, vea el tema sobre cómo planificar servidores perimetrales e implementar servidores perimetrales. Para obtener más información sobre cómo habilitar el acceso externo para Office Web Apps Server, vea [configurar la integración con Office Web Apps Server en Skype empresarial Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **¿Desea controlar los clientes que pueden unirse a reuniones de Skype empresarial Server?**
    
    En caso afirmativo, necesitará configurar una página de participación en la reunión para que solo estén disponibles las opciones de cliente que quiera permitir. Cada vez que un usuario hace clic en un vínculo para unirse a una reunión programada, Skype empresarial Server detecta si un cliente ya está instalado en el equipo. Luego inicia el cliente predeterminado y abre la página de participación en la reunión, que contiene vínculos para clientes alternativos. La página de la combinación de reuniones siempre contiene la opción de usar la aplicación Web de Skype empresarial. Además de esta opción, puede decidir si desea incluir vínculos para asistentes y para versiones anteriores de Communicator. 
    

