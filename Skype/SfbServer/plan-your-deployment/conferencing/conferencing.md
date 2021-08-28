---
title: Planear conferencias en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Resumen: lea este tema para obtener información sobre las funciones y características de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: 90200648c8e370bd0e59f0b6759717cd706b683d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628592"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planear conferencias en Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre las funciones y características de conferencia en Skype Empresarial Server.
  
La conferencia en Skype Empresarial Server permite a los usuarios reunirse y celebrar conferencias en línea con su cliente Skype Empresarial en lugar de que todos se reúnan en la misma sala. Los participantes de la reunión pueden conectarse a una reunión con su cliente de Skype Empresarial para disfrutar de una experiencia completa de audio y vídeo, o llamar a una conferencia mediante un teléfono. Las conferencias también admiten mensajería instantánea, uso compartido de aplicaciones y escritorio, y pizarras interactivas.
  
En este tema se incluyen las secciones siguientes:
  
- Características y funcionalidades de conferencia
    
- Componentes de conferencia
    
- Directivas de conferencia
    
- Compatibilidad con reuniones grandes
    
- Determinar las necesidades de la organización
    
## <a name="conferencing-features-and-capabilities"></a>Características y funcionalidades de conferencia

Hay cuatro tipos de conferencias disponibles en Skype Empresarial Server: conferencia web, conferencias de audio y vídeo (A/V), conferencias de acceso telefónico local y conferencias de mensajes instantáneos (MI). 
  
Puede elegir habilitar todos los tipos de conferencia o usar solo un tipo, según sus necesidades. Por ejemplo, puede habilitar todos los tipos, incluidas las conferencias de acceso telefónico local, para permitir que los usuarios que no puedan unirse a una conferencia con un cliente de Skype Empresarial puedan llamar y participar en el audio de la reunión desde un teléfono. Al implementar Skype Empresarial Server, las capacidades de conferencia de mensajería instantánea se implementan automáticamente; especifique si desea implementar conferencias web, A/V y de acceso telefónico local mediante el Generador de topologías. Para obtener más información, vea [Deploy conferencing in Skype Empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
En las subsecciones siguientes se describen las características y capacidades de cada tipo de conferencia.
  
### <a name="web-conferencing"></a>Conferencia web

La conferencia web permite a los asistentes a la reunión colaborar en documentos compartidos durante la reunión y para que el moderador de la reunión comparta aplicaciones a través del Skype Empresarial cliente. La conferencia web proporciona las siguientes características: 
  
- **Pizarra y anotaciones.** Una pizarra es un lienzo en blanco que se puede usar para la colaboración con texto, lápiz, dibujos e imágenes. Las anotaciones hechas en las pizarras pueden verlas todos los participantes en la reunión. La característica de pizarra mejora la colaboración porque permite a los participantes de la reunión debatir, intercambiar ideas, tomar notas, etc.
    
- **Sondeo.** La característica de sondeo mejora la colaboración al permitir a los presentadores determinar rápidamente las preferencias de los participantes. Durante las conversaciones y reuniones en línea, los moderadores pueden usar el sondeo para recabar respuestas anónimas de los participantes. Todos los moderadores pueden ver los resultados y elegir entre ocultarlos o mostrarlos a todos los asistentes.
    
- **Uso compartido de aplicaciones y uso compartido de escritorio.** Durante una conferencia, el moderador de la reunión puede compartir todo su escritorio, una aplicación individual o monitores individuales en un entorno de varios monitores. Aparte de solo ver el contenido, otros participantes en la conferencia pueden solicitar el control de la pantalla del moderador y, con permiso, interactuar con el contenido (incluido el desplazamiento y la edición). Los participantes de la reunión también pueden asumir el cargo de moderador y empezar a compartir contenido durante la reunión.
    
- **PowerPoint Uso compartido.** Permite a los usuarios compartir PowerPoint presentaciones en la reunión a través de un servidor Office Web Apps, lo que permite:
    
  - Pantallas de alta resolución y compatibilidad con PowerPoint funciones, como animaciones, transiciones de diapositivas y vídeo incrustado.
    
  - Los dispositivos móviles pueden acceder a estas presentaciones.
    
  - Los usuarios con los permisos adecuados pueden desplazarse por una PowerPoint independiente de la propia presentación. Por ejemplo, mientras Ken presenta su presentación con diapositivas, Heidi puede ver cualquier diapositiva que quiera sin afectar a la presentación de Ken.
    
### <a name="audio-and-video-conferencing"></a>Conferencias de audio y vídeo

Las conferencias de audio y vídeo permiten audio y vídeo en la reunión. El audio permite a los asistentes hablar entre sí como si estuvieran en la misma sala. El vídeo habilita la visualización de vídeo en el Skype Empresarial de los asistentes o presentadores que se unan a la reunión con una cámara web o un dispositivo de conferencia que admita vídeo.
  
 Skype Empresarial Server proporciona varias características que los usuarios pueden usar para configurar la experiencia de audioconferencia para el usuario, incluidas las siguientes:
  
- **Silencio de audiencia.** El moderador puede usar esta opción para desactivar el audio de todos los participantes en la conferencia y poner la conferencia en un estado en el que los participantes que no son moderadores no puedan activar su audio.
    
- **Anuncios de entrada y salida de conferencia.** Si ha habilitado las conferencias de acceso telefónico, los moderadores pueden usar esta opción para activar o desactivar los anuncios de entrada para minimizar las distracciones cuando una conferencia está en curso.
    
- **Agregar un usuario marcando hacia fuera.** Los presentadores y asistentes a los que se les ha concedido permiso, pueden agregar números RTC a las conferencias y hacer que la conferencia llame a esos números.
    
  Skype Empresarial Server proporciona varias características que los usuarios pueden usar para configurar la experiencia de videoconferencia para el usuario, incluidas las siguientes:
  
- **Vista Galería.** En las videoconferencias con más de dos personas, los usuarios se ven entre sí automáticamente. Si la conferencia tiene más de cinco participantes, el vídeo de los participantes más activos se muestra en la fila superior y solo se muestra la foto de los demás participantes. De forma predeterminada, el vídeo entre varias partes está activado.
    
- **Vídeo panorámico.** Si hay instalado un dispositivo de videoconferencia RoundTable en la sala de conferencias, esta característica ofrece una vista de 360 grados de la sala de conferencias. La tira de vídeo panorámico solo está disponible con dispositivos RoundTable.
    
- **Modo de vídeo solo moderador.** Los moderadores pueden configurar la reunión para que solo se muestre el vídeo del moderador. Así se evitan distracciones en reuniones grandes cuando hay disponibles varias secuencias de vídeo y se bloquean los diferentes orígenes. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable.
    
- **Foco de vídeo.** Los moderadores pueden configurar la reunión para que los participantes de la conferencia solo vean el vídeo de un participante seleccionado que sea un origen de vídeo. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable de vídeo panorámico.
    
### <a name="dial-in-conferencing"></a>Conferencia de acceso telefónico local

La conferencia de acceso telefónico local permite a los asistentes a la reunión unirse a la parte de audio de una reunión llamando a la reunión desde un teléfono. La conferencia de acceso telefónico local es un subconjunto de la conferencia de audio y requiere configuración adicional. Para obtener más información acerca de las conferencias de acceso telefónico local, vea [Plan for dial-in conferencing in Skype Empresarial Server](dial-in-conferencing.md) and Configure [dial-in conferencing in Skype Empresarial Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conferencias de mensajería instantánea

Las conferencias de mensajería instantánea (MI) permiten que más de dos partes se comuniquen en una sola sesión de mensajería instantánea. Para obtener más información acerca de las conferencias de mensajería instantánea, vea [Plan for instant messaging and presence in Skype Empresarial Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Componentes de conferencia

Entre los componentes que admiten las características de conferencia se incluyen los siguientes:
  
- **Servicio de aplicaciones.** El servicio de aplicaciones proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas (UC). Las conferencias de acceso telefónico local usan dos aplicaciones UC que requieren el servicio de aplicaciones: Operador de conferencia y Anuncio de conferencia. El servicio de aplicaciones se instala y activa de forma predeterminada en todos los servidores front-end de un grupo de servidores front-end. También se instala en todos los servidores Standard Edition para habilitar y configurar conferencias de acceso telefónico local.
    
- **aplicación Operador de conferencia.** El aplicación Operador de conferencia es una aplicación de comunicaciones unificadas que acepta llamadas de red telefónica conmutada (RTC), reproduce mensajes y une las llamadas a una conferencia A/V. El aplicación Operador de conferencia se instala y se activa de forma predeterminada al habilitar las conferencias de acceso telefónico local.
    
- **aplicación Anuncio de conferencia.** El aplicación Anuncio de conferencia es una aplicación de comunicaciones unificadas que reproduce tonos y avisos a los participantes rtc en determinadas acciones, como cuando los participantes se unen o salen de una conferencia, los participantes se silencian o no se conmutan, alguien entra en la sala de espera de la conferencia o la conferencia está bloqueada o desbloqueada. aplicación Anuncio de conferencia también admite comandos de tono dual multifrecuencia (DTMF) desde el teclado del teléfono. El aplicación Anuncio de conferencia se instala y activa automáticamente de forma predeterminada al habilitar las conferencias de acceso telefónico local.
    
- **Página de conferencia de acceso Configuración acceso telefónico local.** La página Conferencia de acceso telefónico local Configuración muestra números de acceso telefónico local de conferencia con sus idiomas disponibles, información de conferencia asignada (es decir, para reuniones que no es necesario programar) y controles DTMF en la conferencia, y admite la administración del número de identificación personal (PIN) y la información de conferencia asignada. La página de conferencias de acceso telefónico Configuración se instala automáticamente como parte de servicios web.
    
- **Servidor de mediación y puerta de enlace RTC.** Las conferencias de acceso telefónico local requieren que un servidor de mediación traduzca la señalización (y los medios en algunas configuraciones) entre Skype Empresarial Server y la puerta de enlace RTC, y una puerta de enlace RTC para traducir la señalización y los medios entre el servidor de mediación y la puerta de enlace RTC. Para las conferencias de acceso telefónico local, debe implementar al menos un servidor de mediación y, al menos, uno de los siguientes elementos:
    
  - Una puerta de enlace RTC
    
  - IP-PBX
    
  - Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta mediante la configuración de un tronco SIP
    
  > [!NOTE]
  > Si también va a implementar Telefonía IP empresarial, el servidor de mediación y las puertas de enlace RTC forman parte de la Telefonía IP empresarial implementación. Si no está implementando Enterprise Voice, debe implementar al menos un servidor de mediación y al menos una puerta de enlace RTC, IP-PBX o SBC para las conferencias de acceso telefónico local. 
  
- **Almacén de archivos.** El almacenamiento de archivos se usa para los archivos de audio de los nombres grabados. El almacenamiento de archivos es un componente estándar de toda implementación Enterprise Edition o Standard Edition.
    
- **Almacén de usuarios.** El almacén de usuarios se usa para almacenar los Skype Empresarial Server los PIN. Los PIN tienen asignado un algoritmo hash. El almacenamiento de usuarios es un componente estándar de toda implementación Enterprise Edition o Standard Edition.
    
- **Office Web Apps Server.** Para poder usar las capacidades de conferencia web, los administradores deben instalar Office Web Apps Server y deben configurar Skype Empresarial Server para comunicarse con Office Web Apps Server.
    
## <a name="conferencing-policies"></a>Directivas de conferencia

Para aplicar las directivas de su organización y controlar el uso del ancho de banda, puede establecer directivas para los tipos de reuniones que los usuarios pueden organizar. Puede definir una amplia variedad de directivas de conferencia y asignarlas a usuarios individuales y grupos de usuarios. También se pueden establecer las directivas que rigen las conversaciones de punto a punto. Para obtener más información sobre cómo establecer directivas de conferencia, vea [Manage conferencing policies in Skype Empresarial Server](../../manage/conferencing/conferencing-policies.md). Para obtener más información acerca de la administración de ancho de banda, vea [Plan for call admission control in Skype Empresarial Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Compatibilidad con reuniones grandes

El tamaño de las reuniones que Skype Empresarial Server pueden admitir depende de si las conferencias se hospedan en un grupo compartido o dedicado:
  
- En un grupo compartido, Skype Empresarial Server puede hospedar reuniones con hasta 250 usuarios. Un grupo compartido es un grupo de servidores que hospeda todas las Skype Empresarial Server de trabajo, incluida la mensajería instantánea (MI) y la presencia, las conferencias y Telefonía IP empresarial. 
    
- En un grupo dedicado, Skype Empresarial Server puede admitir reuniones con hasta 1000 participantes mediante conferencias web y de audio y vídeo (A/V), incluido el uso compartido de PowerPoint presentación. Esta compatibilidad requiere un grupo dedicado configurado para admitir reuniones grandes y administrado de manera que garantice que solo hospedará una reunión grande al mismo tiempo. 
    
Para obtener más información acerca de la administración de reuniones grandes, vea [Plan for large meetings in Skype Empresarial Server](large-meetings.md).
  
Si su organización requiere capacidades de reunión más grandes, debe considerar la posibilidad de implementar un entorno híbrido que aproveche la difusión de reuniones de Skype, un servicio en línea que forma parte de Microsoft 365 y Office 365. Skype Difusión de reuniones permite a los usuarios hospedar y difundir reuniones a grandes audiencias en línea de hasta 10 000 participantes. El uso de Skype de reunión requiere que Skype Empresarial Server esté configurado en una configuración híbrida con una organización Microsoft 365 o Office 365 de producción. Todos los usuarios deben tener un inquilino en línea establecido como requisito previo. Si está interesado en implementar una solución híbrida que pueda aprovechar Skype difusión de reuniones, vea [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Determinar las necesidades de las organizaciones

Al determinar qué capacidades de conferencia implementar, debe tener en cuenta las características que desea que estén disponibles para los usuarios y las capacidades de ancho de banda de red. La siguiente lista le guía a través del proceso de planeación de conferencias para determinar qué características de conferencia debe implementar, en función de los requisitos de su organización.
  
> [!NOTE]
> Al habilitar las conferencias en la implementación, se habilitan automáticamente las conferencias web y A/V. Sin embargo, puede deshabilitar características específicas mediante la configuración de directivas de conferencia como se describe anteriormente en este tema. 
  
- **¿Desea habilitar la conferencia web, lo que incluye colaboración en documentos y uso compartido de aplicaciones?**
    
    Si es así, debe habilitar las conferencias para el grupo de servidores front-end mediante la Herramienta de planeación o mediante el Generador de topologías. Para obtener más información, vea [Deploy conferencing in Skype Empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    El uso compartido de aplicaciones requiere y usa un mayor ancho de banda que la colaboración en documentos. Skype Empresarial Server proporciona un mecanismo de limitación para controlar cada sesión de uso compartido de aplicaciones. De forma predeterminada, este está establecido en 1,5 KB/segundo para cada sesión. Si no desea habilitar el uso compartido de aplicaciones, pero sí desea la colaboración de documentos, puede habilitar las conferencias y usar directivas de conferencia para deshabilitar el uso compartido de aplicaciones. Para obtener más información sobre cómo configurar directivas de conferencia, vea [Manage conferencing policies in Skype Empresarial Server](../../manage/conferencing/conferencing-policies.md).
    
    Para permitir a los usuarios compartir PowerPoint presentaciones, debe configurar Office Web Apps Server. Para obtener más información sobre cómo configurar Office Web Apps Server, vea [Configure integration with Office Web Apps Server in Skype Empresarial Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **¿Desea habilitar las conferencias de audio y vídeo?**
    
    Si es así, debe habilitar las conferencias para el grupo de servidores front-end mediante la Herramienta de planeación o mediante el Generador de topologías. Para obtener más información, vea [Deploy conferencing in Skype Empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Las conferencias de audio y vídeo requieren y usan más ancho de banda de red que las conferencias web (lo que incluye la colaboración de documentos y el uso compartido de aplicaciones). Si no desea habilitar las conferencias de audio y vídeo, pero sí desea habilitar la conferencia web, puede habilitar las conferencias y usar directivas de conferencia para deshabilitar las conferencias A/V.
    
    Si desea habilitar audioconferencias pero no videoconferencias, puede habilitar las conferencias A/V y usar directivas de conferencia para evitar las videoconferencias. Como alternativa, puede habilitar la conferencia A/V y habilitar solo a determinados usuarios para que inicien conferencias A/V o participen en ellas. 
    
    Para obtener más información acerca de cómo configurar directivas de conferencia, vea [Manage conferencing policies in Skype Empresarial Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > Telefonía IP empresarial no es necesario que use conferenciaS/V. Si habilita las conferencias A/V, los usuarios pueden agregar audio a sus conferencias si tienen dispositivos de audio, incluso si usa una PBX para la solución telefónica. 
  
- **¿Desea permitir que los usuarios se unan a secciones de audio de conferencias al usar un teléfono RTC?**
    
    Si es así, implemente y habilite las conferencias de acceso telefónico local. De este modo, los usuarios invitados, tanto de dentro como de fuera de la organización, podrán unirse a la sección de audio de las conferencias a través de un teléfono RTC.
    
    Las conferencias de acceso telefónico local son una característica opcional que puede configurar al implementar Skype Empresarial Server conferencia. Aunque las conferencias de acceso telefónico local usan algunos de los mismos componentes que Telefonía IP empresarial, puede implementar conferencias de acceso telefónico local incluso si no implementa Telefonía IP empresarial. Las conferencias de acceso telefónico local admiten tanto a usuarios de empresa como a usuarios anónimos. Para obtener más información acerca de la configuración de conferencias de acceso telefónico local para usuarios anónimos y empresariales, vea [Deploy conferencing in Skype Empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md) y Configure [dial-in conferencing in Skype Empresarial Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **¿Desea permitir que los usuarios externos con Skype Empresarial clientes se unan a conferencias?**
    
    Al permitir la participación externa en reuniones, maximiza la inversión en Skype Empresarial Server. Entre los usuarios externos se pueden incluir:
    
  - **Usuarios remotos.** Los propios usuarios de la organización, cuando trabajan fuera de los firewalls y usan sus portátiles u otros Skype Empresarial Server dispositivos.
    
  - **Usuarios federados.** Usuarios de empresas con las que trabaja que también ejecutan Skype Empresarial Server. Para habilitar a sus usuarios para que se pongan en contacto fácilmente con estos usuarios, cree relaciones federadas con estas compañías.
    
  - **Usuarios anónimos.** Cualquier otro usuario externo al que sus usuarios inviten específicamente a unirse a determinadas conferencias. Un organizador de reuniones de su compañía puede enviar una invitación por correo electrónico a un usuario externo para una conferencia. El correo electrónico incluye un vínculo en el que el usuario externo puede hacer clic para unirse a la conferencia.
    
    Si desea permitir usuarios externos, deberá implementar servidores perimetrales. Además, con los servidores perimetrales implementados puede crear relaciones federadas con otras organizaciones ,como sus clientes o proveedores, y los usuarios de dichas organizaciones pueden colaborar más fácilmente con los usuarios.
    
    Para obtener más información acerca de la implementación de servidores perimetrales, vea Plan for Edge Servers e Deploy Edge Servers. Para obtener más información sobre cómo habilitar el acceso externo para Office Web Apps Server, vea [Configure integration with Office Web Apps Server in Skype Empresarial Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **¿Desea controlar los clientes que pueden unirse a Skype Empresarial Server reuniones?**
    
    Si es así, debe configurar la página de participación en la reunión para que solo estén disponibles las opciones de cliente que desea admitir. Cada vez que un usuario hace clic en un vínculo para unirse a una reunión programada, Skype Empresarial Server detecta si un cliente ya está instalado en el equipo. A continuación, inicia el cliente predeterminado y abre la página de participación en la reunión, que contiene vínculos para clientes alternativos. La página de unión a la reunión siempre contiene la opción de usar aplicación web de Skype Empresarial. Además de esta opción, puede decidir si desea incluir vínculos para Attendee y versiones anteriores de Communicator. 
    

