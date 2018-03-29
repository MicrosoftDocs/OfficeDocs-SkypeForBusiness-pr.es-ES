---
title: Planificar conferencias en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Resumen: Leer este tema para aprender acerca de las características de conferencia y capacidades en Skype para Business Server 2015.'
ms.openlocfilehash: d53f3a787a32b784f8d0bd7514e9a6ae868076ba
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-conferencing-in-skype-for-business-server-2015"></a>Planificar conferencias en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender acerca de las características de conferencia y capacidades en Skype para Business Server 2015.
  
Conferencia en Skype para Business Server permite a los usuarios satisfacer y mantener conferencias en línea con su Skype para cliente de negocios en lugar de todos al obtener juntos en la misma sala. Los participantes de la reunión puede conectarse a una reunión con su Skype para el cliente de negocios para una experiencia de vídeo y audio completo, o llamar a una conferencia con un teléfono. Las conferencias también admiten la mensajería instantánea, el uso compartido del escritorio y aplicaciones y las pizarras interactivas.
  
Este tema incluye las secciones siguientes:
  
- Características y funciones de las conferencias
    
- Componentes de conferencia
    
- Directivas de conferencia
    
- Compatibilidad con reuniones grandes
    
- Determinar las necesidades de su organización
    
## <a name="conferencing-features-and-capabilities"></a>Características y funciones de las conferencias

Hay cuatro tipos de conferencia en Skype para Business Server: web de conferencias de audio y vídeo (A / V) conferencia, marcado en la conferencia y conferencia de mensajes instantáneos (IM). 
  
Puede optar por activar todos los tipos de conferencia o por usar solo un tipo, según sus necesidades. Por ejemplo, podría permitir todos los tipos, incluyendo conferencias de acceso telefónico permitir que a los usuarios que no son capaces de unirse a una conferencia con un Skype para Business client llamar y participar en el audio de la reunión desde un teléfono. Al implementar Skype para Business Server, automáticamente se implementan capacidades de conferencia de mensajería instantánea; especificar si se va a implementar el sitio web, A / V y conferencias de acceso telefónico mediante el generador de topología. Para obtener más información, vea [implementar conferencias en Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
En las siguientes subsecciones se describen las características y funciones de cada tipo de conferencia.
  
### <a name="web-conferencing"></a>Conferencia web

Conferencias Web permite asistentes a la reunión colaborar en documentos compartidos durante la reunión y para el moderador de la reunión compartir aplicaciones mediante el Skype para cliente de empresa. La conferencia web dispone de las siguientes características: 
  
- **Pizarra y anotaciones.** Una pizarra es un lienzo en blanco que se puede usar para la colaboración con texto, lápiz, dibujos e imágenes. Las anotaciones hechas en las pizarras pueden verlas todos los participantes en la reunión. La característica de pizarra mejora la colaboración porque permite a los participantes de la reunión debatir, intercambiar ideas, tomar notas, etc.
    
- **Sondeo.** La función de sondeo mejora la colaboración al permitir que los moderadores determinar rápidamente las preferencias de los participantes. Durante las conversaciones y reuniones en línea, los moderadores pueden usar el sondeo para recabar respuestas anónimas de los participantes. Todos los moderadores pueden ver los resultados y elegir entre ocultarlos o mostrarlos a todos los asistentes.
    
- **Uso compartido de aplicaciones y escritorios.** Durante una conferencia, el presentador de la reunión puede compartir su escritorio completo, una aplicación individual o monitores en un entorno de varios monitor. Aparte de ver solo el contenido, otros participantes en la conferencia pueden solicitar control de la pantalla del moderador y, con permiso, interactuar con el contenido (incluyendo desplazarse y editar). Los participantes de la reunión también pueden tomar el control como moderador y empezar a compartir contenido durante la reunión.
    
- **Uso compartido de PowerPoint.** Permite a los usuarios compartir presentaciones de PowerPoint en la reunión a través de un Office Web Apss Server, que le permite:
    
  - Pantallas de mayor resolución y compatibilidad con las capacidades de PowerPoint, como animaciones, transiciones de diapositivas y vídeo incrustado.
    
  - Los dispositivos móviles pueden tener acceso a estas presentaciones.
    
  - Los usuarios con los permisos adecuados pueden desplazarse a través de una presentación de PowerPoint independiente de la propia presentación. Por ejemplo, mientras que Ken realiza su presentación, Heidi puede ver cualquier diapositiva que quiera, sin que esto afecte a la presentación de Ken.
    
### <a name="audio-and-video-conferencing"></a>Conferencia de audio y vídeo

Las conferencias de audio y vídeo permiten el uso de audio y vídeo en la reunión. El audio permite a los asistentes hablar unos con otros como si estuvieran en la misma sala. Vídeo permite la visualización de vídeo en el Skype para cliente de negocio de los asistentes o moderadores que unirse a la reunión con un dispositivo de leva o conferencia web que soporta el vídeo.
  
 Skype para Business Server proporciona varias características que los usuarios pueden utilizar para configurar la audioconferencia experimentan para el usuario, incluidos los siguientes:
  
- **Silencio de audiencia.** El moderador puede usar esta opción para desactivar el audio de todos los participantes en la conferencia y poner la conferencia en un estado en el que los participantes que no son moderadores no puedan activar su audio.
    
- **Anuncios de entrada/salida de conferencia.** Si ha habilitado las conferencias de acceso telefónico, los moderadores pueden usar esta opción para activar o desactivar los anuncios de entrada para minimizar las distracciones cuando una conferencia está en curso.
    
- **Agregar un usuario mediante marcación.** Moderadores y asistentes que le ha concedido permiso, puede agregar números PSTN a las conferencias y la conferencia de acceso telefónico de salida para los números.
    
 Skype para Business Server proporciona varias características que los usuarios pueden utilizar para configurar los sistemas de videoconferencia de experiencia para el usuario, incluidos los siguientes:
  
- **Vista de la galería.** En las videoconferencias con más de dos personas, los usuarios se ven entre sí automáticamente. Si la conferencia tiene más de cinco participantes, el vídeo de los participantes más activos se muestra en la fila superior y solo se muestra la foto de los demás participantes. De forma predeterminada, el vídeo entre varias partes está activado.
    
- **Video panorámica.** Si hay instalado un dispositivo de videoconferencia RoundTable en la sala de conferencias, esta característica ofrece una vista de 360 grados de la sala de conferencias. La tira de vídeo panorámico solo está disponible con dispositivos RoundTable.
    
- **Modo de sólo vídeo del moderador.** Los moderadores pueden configurar la reunión para que solo se muestre el vídeo del moderador. Así se evitan distracciones en reuniones grandes cuando hay disponibles varias secuencias de vídeo y se bloquean los diferentes orígenes. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable.
    
- **Proyector de vídeo.** Los moderadores pueden configurar la reunión para que los participantes de la conferencia solo vean el vídeo de un participante seleccionado que sea un origen de vídeo. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable de vídeo panorámico.
    
### <a name="dial-in-conferencing"></a>Conferencia de acceso telefónico local

Conferencia de marcado permite asistentes a la reunión para unirse a la parte de audio de una reunión mediante una llamada la reunión desde un teléfono. La conferencia de acceso telefónico local es un subconjunto de la conferencia de audio y requiere configuración adicional. Para obtener más información acerca de las conferencias de acceso telefónico, consulte [Plan de acceso telefónico de la conferencia en Skype para Business Server 2015](dial-in-conferencing.md) y [Configurar acceso telefónico conferencia en Skype para Business Server 2015](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conferencias de mensajería instantánea

La conferencia de mensajería instantánea permite a más de dos participantes comunicarse en una única sesión de mensajería instantánea. Para obtener más información acerca de las conferencias de mensajería instantánea, consulte [Plan para mensajería instantánea y presencia en Skype para Business Server 2015](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Componentes de conferencia

Los componentes compatibles con las características de conferencia son los siguientes:
  
- **Servicio de aplicación.** El servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas (UC). Las conferencias de acceso telefónico usan dos aplicaciones de UC que requieren el servicio de aplicación: operador de conferencia y anuncio de conferencia. El servicio de aplicación está instalado y activado de forma predeterminada en cada servidor Front-End en un grupo de servidores Front-End. También se instala en cada servidor Standard Edition para permitir y configurar la conferencia de acceso telefónico local.
    
- **Aplicación de operador de conferencia.** La aplicación de operador de conferencia es una aplicación de comunicaciones unificadas que acepta las llamadas de la red telefónica conmutada (RTC), reproduce avisos e introduce las llamadas en una conferencia A/V. La aplicación de operador de conferencia se instala y activa de forma predeterminada al habilitar las conferencias de acceso telefónico.
    
- **Aplicación de anuncio de conferencia.** La aplicación de anuncio de conferencia es una aplicación de comunicaciones unificadas que reproduce tonos y avisos para los participantes de RTC en determinadas acciones como, por ejemplo, cuando los participantes entran o salen de una conferencia, cuando se activa o se desactiva el audio de los participantes, cuando alguien entra en la sala de espera de la conferencia o cuando se bloquea o se desbloquea la conferencia. La aplicación de anuncio de conferencia también es compatible con los comandos de tono de marcado de frecuencia múltiple (DTMF) desde el teclado del teléfono. La aplicación de anuncio de conferencia se instala y se activa automáticamente de forma predeterminada al habilitar las conferencias de acceso telefónico local.
    
- **Página de Configuración de conferencia de acceso telefónico local.** La página de Configuración de conferencia de acceso telefónico local muestra los números de acceso telefónico a conferencias con sus idiomas disponibles, la información de las conferencias asignadas (es decir, de las reuniones que no requieren programación) y los controles DTMF de la conferencia, y es compatible con la administración de números de identificación personal (PIN) y la información de conferencias asignadas. La página de Configuración de conferencia de acceso telefónico local se instala automáticamente como parte de los servicios web.
    
- **Puerta de enlace de servidor de mediación y PSTN.** Conferencia de acceso telefónico requiere un servidor de mediación para traducir la señalización (y la media en algunas configuraciones) entre Skype para Business Server y la puerta de enlace PSTN y una puerta de enlace PSTN para traducir la señalización y los medios de comunicación entre el servidor de mediación y la puerta de enlace PSTN . Para conferencias de acceso telefónico, debe implementar al menos un servidor de mediación y al menos uno de estos procedimientos:
    
  - Puerta de enlace RTC
    
  - Un sistema IP-PBX
    
  - Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta por medio de la configuración de un tronco SIP
    
  > [!NOTE]
  > Si también está implementando la Telefonía IP empresarial, las puertas de enlace de servidor de mediación y PSTN forman parte de la implementación de Telefonía IP empresarial. Si no está implementando la Telefonía IP empresarial, debe implementar al menos un servidor de mediación y al menos un PSTN gateway, IP-PBX o SBC para conferencias de acceso telefónico. 
  
- **Almacenamiento de archivos.** El almacenamiento de archivos se usa para los archivos de audio de los nombres grabados. El almacenamiento de archivos es un componente estándar de toda implementación Enterprise Edition o Standard Edition.
    
- **Almacenamiento de usuarios.** Almacén de usuario se utiliza para almacenar el usuario Skype para Business Server PINs. Los PIN tienen asignado un algoritmo hash. El almacenamiento de usuarios es un componente estándar de toda implementación Enterprise Edition o Standard Edition.
    
- **Office Web Apps Server.** Para poder utilizar capacidades de conferencias web, los administradores deben instalar a Office Web Apps Server y deben configurar Skype para Business Server para comunicarse con el servidor de Office Web Apps.
    
## <a name="conferencing-policies"></a>Directivas de conferencia

Para aplicar las políticas y controlar el uso de ancho de banda de su organización, puede establecer directivas para los tipos de reuniones que los usuarios pueden organizar. Puede definir una amplia variedad de directivas de conferencia y asignarlas a usuarios individuales y grupos de usuarios. También puede establecer las directivas que rigen las conversaciones de punto a punto. Para obtener más información acerca de cómo configurar las directivas de la conferencia, vea [Administrar directivas de conferencia en Skype para Business Server 2015](../../manage/conferencing/conferencing-policies.md). Para obtener más información acerca de la administración de ancho de banda, consulte [Plan de control de admisión de llamada en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Compatibilidad con reuniones grandes

El tamaño de las reuniones que Skype para Business Server puede admitir depende de si conferencia está alojada en un pool compartido o dedicado:
  
- En un grupo compartido, Skype para Business Server puede alojar reuniones con hasta 250 usuarios. Un grupo compartido es un grupo que aloja todos los Skype para cargas de trabajo de servidor empresarial incluida mensajería instantánea (IM) y presencia, conferencias y Telefonía IP empresarial. 
    
- En un grupo dedicado, Skype para Business Server puede soportar reuniones con hasta 1000 participantes mediante web y audio/vídeo (A / V) conferencia, incluido el uso compartido de presentaciones de PowerPoint. Esta compatibilidad requiere un grupo dedicado configurado para admitir reuniones grandes y administrado de manera que garantice que solo hospedará una reunión grande al mismo tiempo. 
    
Para obtener más información acerca de cómo administrar las reuniones grandes, consulte [Plan de grandes reuniones en Skype para Business Server 2015](large-meetings.md).
  
Si su organización necesita mayores capacidades de reunión, considere la posibilidad de implementar un entorno híbrido que saca partido de difundir reunión de Skype, un nuevo servicio en línea que forma parte de Office 365. La difusión de reunión de Skype permite a los usuarios hospedar y difundir reuniones a grandes públicos en línea de hasta 10.000 participantes. El uso de la difusión de reunión de Skype requiere que Skype Empresarial Server ya esté configurado en una configuración híbrida con un inquilino de producción de Office 365. Todos los usuarios necesitan tener un inquilino en línea establecido como requisito previo. Si está interesado en implementar una solución híbrida que puede beneficiarse de la difusión de la reunión de Skype, vea [Configurar la implementación local para difundir reunión de Skype](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Determinar las necesidades de su organización

Al determinar qué funciones de conferencia se van a implementar, es necesario tener en cuenta las características que quiere poner a disposición de los usuarios, así como la capacidad de ancho de banda de la red. La lista siguiente le guiará el proceso para determinar qué características de conferencia debe implementar, de planificación de conferencias en función de los requisitos de su organización.
  
> [!NOTE]
> Al habilitar las conferencias en la implementación, activa automáticamente tanto las conferencias web como las A/V. Pero, puede deshabilitar características específicas al configurar directivas de conferencia según se ha descrito anteriormente en este tema. 
  
- **¿Desea habilitar la conferencia web, que incluye la colaboración con documentos y el uso compartido de aplicaciones?**
    
    En caso afirmativo, necesita habilitar las conferencias para el grupo de servidores front-end con la Herramienta de planeación o por medio del Generador de topologías. Para obtener más información, vea [implementar conferencias en Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    El uso compartido de aplicaciones requiere y utiliza más ancho de banda de red que la colaboración en documentos. Skype para Business Server proporciona un mecanismo de límite para controlar cada sesión de uso compartido de aplicaciones. De forma predeterminada, esto se establece en 1,5 KB por segundo para cada sesión. Si no desea habilitar el uso compartido de aplicaciones, pero desea colaborar en los documentos, puede habilitar la conferencia y utilizar directivas de conferencias para deshabilitar el uso compartido de aplicaciones. Para obtener más información acerca de cómo configurar las directivas de la conferencia, vea [Administrar directivas de conferencia en Skype para Business Server 2015](../../manage/conferencing/conferencing-policies.md).
    
    Para que los usuarios puedan compartir presentaciones de PowerPoint, necesita configurar Office Web Apps Server. Para obtener más información acerca de cómo configurar el servidor de Office Web Apps, vea [Configurar la integración con Office Web Apps Server en Skype para Business Server 2015](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **¿Desea habilitar la conferencia de audio y vídeo?**
    
    En caso afirmativo, necesita habilitar las conferencias para el grupo de servidores front-end con la Herramienta de planeación o por medio del Generador de topologías. Para obtener más información, vea [implementar conferencias en Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Las conferencias de audio y vídeo requieren y usan más ancho de banda que las conferencias web (lo que incluye la colaboración en documentos y los recursos compartidos de aplicaciones). Si no desea habilitar las conferencias de audio y vídeo, pero sí las conferencias web, puede habilitar las conferencias y usar las directivas de conferencia para deshabilitar las conferencias A/V.
    
    Si desea habilitar las conferencias de audio pero no videoconferencias, puede habilitar la conferencia A/V y usar las directivas de conferencia para evitar las conferencias de vídeo. Como alternativa, puede habilitar la conferencia A/V y habilitar únicamente determinados usuarios para que inicien o participen en conferencias A/V. 
    
    Para obtener más información acerca de cómo configurar las directivas de la conferencia, vea [Administrar directivas de conferencia en Skype para Business Server 2015](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > No se necesita la telefonía IP empresarial para usar las conferencias A/V. Si habilita las conferencias A/V, los usuarios que dispongan de dispositivos de audio podrán agregar audio a las conferencias, aun cuando se use una PBX como solución de telefonía. 
  
- **¿Desea permitir a los usuarios a unirse a la parte de audio de conferencias cuando se utiliza un teléfono PSTN?**
    
    Si es así, implemente y habilite la conferencia de acceso telefónico. Los usuarios invitados, tanto dentro como fuera de su organización, puede unirse entonces a la parte de audio de las conferencias por medio de un teléfono RTC.
    
    Conferencia de marcado es una característica opcional que se puede configurar al implementar Skype para conferencia Business Server. Aunque la conferencia de acceso telefónico local usa algunos de los mismos componentes que usa la telefonía IP empresarial, puede implementar la conferencia de acceso telefónico local aunque no implemente la telefonía IP empresarial. Las conferencias de acceso telefónico local admiten tanto a usuarios de empresa como a usuarios anónimos. Para obtener más información acerca de cómo configurar acceso telefónico conferencias para la empresa y los usuarios anónimos, vea [implementar conferencias en Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md) y [Configurar acceso telefónico conferencia en Skype para Business Server 2015](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **¿Desea permitir que los usuarios externos con Skype para clientes de empresa para unirse a conferencias?**
    
    Al permitir externa participación en reuniones, maximice su inversión en Skype para Business Server. Los usuarios externos pueden incluir:
    
  - **Usuarios remotos.** Los usuarios de la organización, cuando están trabajando fuera de los servidores de seguridad y está usando sus equipos portátiles u otro Skype para dispositivos Business Server.
    
  - ** Los usuarios federados. ** Los usuarios de empresas trabaja con quien también ejecutan Skype para Business Server. Si desea habilitar a sus usuarios para que se pongan en contacto fácilmente con estos otros usuarios, cree relaciones federadas con estas compañías.
    
  - ** Los usuarios. ** Cualquier otros usuarios externos invitados específicamente por los usuarios a unirse a conferencias específicas. Un organizador de reuniones de su compañía puede enviar una invitación por correo electrónico a un usuario externo para una conferencia. El correo electrónico incluye un vínculo en el que el usuario externo puede hacer clic para unirse a la conferencia.
    
    Si desea permitir que a los usuarios externos, necesitará implementar los servidores perimetrales. Además, con los servidores perimetrales implementados se pueden crear relaciones federadas con otras organizaciones (por ejemplo, los clientes o proveedores) y los usuarios de dichas organizaciones podrán colaborar más fácilmente con los usuarios.
    
    Para más información sobre la implementación de servidores perimetrales, vea el tema sobre cómo planificar servidores perimetrales e implementar servidores perimetrales. Para obtener más información acerca de cómo habilitar el acceso externo de servidor de Office Web Apps, vea [Configurar la integración con Office Web Apps Server en Skype para Business Server 2015](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **¿Desea controlar a qué clientes pueden unirse Skype para reuniones Business Server?**
    
    En caso afirmativo, necesitará configurar una página de participación en la reunión para que solo estén disponibles las opciones de cliente que quiera permitir. Cada vez que un usuario hace clic en un vínculo para unirse a una reunión programada, detecta Skype para Business Server si un cliente ya está instalado en el equipo. Luego inicia el cliente predeterminado y abre la página de participación en la reunión, que contiene vínculos para clientes alternativos. La reunión página combinación siempre contiene la opción de usar Skype para el negocio de la aplicación Web. Además de esta opción, puede decidir si desea incluir vínculos para asistentes y para versiones anteriores de Communicator. 
    

