---
title: Novedades de Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Resumen: Leer este tema para obtener información sobre nuevas características de Skype para Business Server 2015. Para obtener información detallada acerca de la nueva experiencia de cliente, consulte que Lync es ahora Skype para empresas: Ver novedades.'
ms.openlocfilehash: 0d8172e5031f8b2e51373051b2674e99f5539b6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novedades de Skype Empresarial Server 2015

**Resumen:** Leer este tema para obtener información sobre nuevas características de Skype para Business Server 2015. Para obtener información detallada acerca de la nueva experiencia de cliente, consulte [Lync es ahora Skype para empresas: Ver novedades](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync es ahora Skype para plataforma empresarial, comunicaciones y colaboración que reúne una experiencia inspirado en Skype con la seguridad de nivel empresarial, cumplimiento de normas y control de Lync. Skype para empresas ofrece características como la presencia, mensajería instantánea, voz y videollamadas y reuniones en línea. Skype para empresas proporciona a un nuevo cliente experiencia, una nueva versión de servidor y las actualizaciones con el servicio de Office 365. Si los usuarios de la organización ya están familiarizados con Skype, apreciará la capacidad y la simplicidad de Skype para el negocio que sea fácil de encontrar y conectarse con compañeros de trabajo. Si los usuarios de la organización viene a Skype para el negocio de Lync, podrá reconocer todas las características que ya usan, aunque en una nueva interfaz fresca con controles y nuevas incorporaciones simplificadas. Además de la nueva experiencia de cliente, Skype para el año 2015 de Business Server ofrece varias características nuevas para mejorar la administración de servidores locales y soluciones híbridas.
  
Nuevas características de Skype para el año 2015 de servidor empresarial incluyen mejoras en:
  
- Experiencia de usuario  
- Compatibilidad para voz y vídeo
- Compatibilidad con clientes móviles
- Administración de servidores locales
- Implementación y administración de soluciones híbridas
- Compatibilidad con la autenticación multifactor
    
## <a name="user-experience"></a>Experiencia de usuario

El Skype para cliente de negocios muy parecida a la versión del consumidor de Skype y usa los mismos botones y los iconos. El menor número de menús y la jerarquía de tareas más plana facilita la búsqueda de los controles y comandos que se necesitan. 
  
Skype para empresas incluye la nueva experiencia de usuario descrito anteriormente y la experiencia del usuario de Lync 2013 publicado anteriormente. La inclusión de dos experiencias permite a las empresas administrar los cambios para los usuarios mediante el control del proceso y el momento del nuevo cliente roll-out. La experiencia de usuario predeterminada depende de la versión del servidor que está utilizando. Los administradores eligen la experiencia que prefieren con el cmdlet **Set-Cs ClientPolicy** con el parámetro EnableSkypeUI. Para obtener más información acerca de cómo configurar la experiencia del cliente, consulte [Configurar el cliente experiencia con Skype para el negocio](deploy/deploy-clients/configure-the-client-experience.md) y [comparación de características de cliente de escritorio de Skype para el negocio](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> La experiencia del cliente Lync 2013 no es una opción de Skype para versiones de cliente de empresa 2016. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Mejoras de voz y vídeo

Skype para Business Server 2015 incluye mejoras en la funcionalidad de voz y vídeo, incluyendo interoperabilidad mejorada con sistemas de teleconferencia por vídeo de otros fabricantes y análisis y recopilación de datos de llamada.
  
### <a name="call-data-collection-and-analysis"></a>Recopilación y análisis de datos de llamadas

La característica llame a Mi velocidad, permite Skype para los administradores de servidor de negocios 2015 recopila datos de llamada. Solo está disponible para implementaciones locales. Se pedirá a los usuarios que rellenen una encuesta tras completar una llamada. Para obtener más información, consulte [tasa de mi llamada en Skype para Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Interoperabilidad mejorada con sistemas de videoconferencia de terceros

El servidor de vídeo de interoperabilidad (VIS) actúa como intermediario entre Skype para Business Server y Cisco sistemas de teleconferencia por vídeo (VTC). Al unirse a una reunión, ahora los usuarios pueden optar por un sistema Cisco VTC. El servidor de interoperabilidad de vídeo está implementado como un rol de servidor independiente para implementaciones locales. Para obtener más información, consulte [Plan para servidor de interoperabilidad de vídeo en Skype para Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Vía trabajo

La llamada a través de la función de trabajo permite a los usuarios de empresa realizar llamadas de voz desde el Skype para cliente de empresa. Cuando un usuario realiza una llamada de voz, se enruta de Skype para empresas al teléfono PBX o RTC del ordenante. Cuando responde, la llamada se dirige al número del destinatario. Las respuestas de destinatario de la llamada y la llamada se establece con Skype para el negocio que sirve como el panel de control. El originador puede administrar su presencia y llamar a controles de Skype para el negocio. Los administradores de servidores son los encargados de habilitar y configurar las llamadas Vía trabajo en la empresa. Para obtener más información, consulte [Plan para llamar a través de trabajo en Skype para Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Mejoras de compatibilidad con dispositivos móviles

Mejoras en la compatibilidad con dispositivos móviles incluyen características para mejorar la experiencia móvil de los usuarios de Enterprise Edition, como el acceso a los datos de registro y el historial de conversación, experiencias de reunión móvil mejorado y compatibilidad de inicio de sesión único de Office. Además, hay mejoras de soporte Android, rendimiento y características para simplificar la integración a través del marco de aplicación comunes. 
  
> [!NOTE]
> Servidores de Lync 2013 UCWA deben actualizarse a Skype para Business Server 2015 admitir a clientes móviles. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>El historial de conversaciones del servidor ahora está disponible en los dispositivos móviles

Para habilitar el acceso móvil a historial de las conversaciones IM perdida y datos de registro de llamada, archiving de esta información es ahora procesado a través del servidor para todos los clientes móviles. La función de aceptación automática de mensajes instantáneos mejora la fiabilidad y previene los mensajes de tiempo agotado del servidor cuando un usuario móvil no responde inmediatamente a un mensaje. Para beneficiarse de la integración de carpetas de Exchange u Outlook basado en server, se requiere Exchange Server 2013 o más reciente y actualizados de los clientes móviles. 
  
### <a name="enhanced-meeting-experiences"></a>Experiencia de reunión mejorada

Las funciones de reunión de la versión de escritorio ahora también están disponibles para usuarios móviles. Entre las nuevas características se incluyen las siguientes:
  
- Navegación asíncrona de contenido de PowerPoint compartido
- Capacidad del moderador para tomar el control de PowerPoint compartido contenido
- Administración de la sala de espera por parte de los moderadores, que pueden admitir y rechazar participantes
    
### <a name="skype-for-business-on-android-improvements"></a>Skype para empresas sobre mejoras Android

Skype para el negocio en Android ahora ofrece características similares a lo que está disponible en Skype para el negocio en iOS y Skype para el negocio en Windows:
  
- Continuar o volver a unirse a una conversación
- Autenticación pasiva y mediante certificado
- Invitar a otros a una conversación
- Inicio sencillo de conversaciones en grupo
- Unirse a una reunión sin ser usuario de Skype Empresarial
- Habilitar la IU de smartphones en tabletas Android
- Administrar reuniones agregando o quitando participantes
    
> [!NOTE]
> Estas funciones requieren Android OS 4.0 o superior. 
  
## <a name="management-of-on-premises-servers"></a>Administración de servidores locales

Skype para el año 2015 de Business Server ofrece varias características nuevas para mejorar la administración de servidores locales, como actualización in situ, instalación inteligente, revisión mejorada y actualizar los procesos, capacidad mejorada de Front-End grupo Inicio en frío, SQL Server AlwaysOn soporte, centralizada y el registro solución de problemas.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Actualización local de servidores

Ahora puede actualizar sistemas de Lync Server 2013 a Skype para Business Server 2015 mediante la característica nueva de actualización in situ, que utiliza las inversiones existentes de hardware y servidor Lync Server 2013, lo que reduce el costo total para implementar Skype para Business Server 2015.
  
Hay dos escenarios posibles: el método Mover usuario, que no causa tiempo de inactividad, y el método Sin conexión, que sí lo provoca. Para obtener más información acerca de qué procedimiento de actualización es adecuada para su empresa, consulte [previsto actualizar a Skype para Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> La opción en el lugar no está disponible si está actualizando desde Lync Server 2010. Para obtener más información sobre la actualización de Lync Server 2010, consulte [previsto actualizar a Skype para Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Configuración inteligente

La función Configuración inteligente, que detecta y descarga automáticamente las actualizaciones, ahora forma parte del programa de configuración. Durante el proceso de instalación, se pregunta al usuario si el proceso de instalación debe buscar actualizaciones. Para obtener más información, vea [Instalar Skype para Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Proceso mejorado de revisión y actualización de servidores front-end

Skype para Business Server introduce dos nuevos cmdlets que ayudan a que la actualización o la revisión de servidores frontales mucho más fácil que en versiones anteriores de Lync Server.
  
Cuando necesite aplicar una revisión o realizar ningún mantenimiento, a un servidor Front-End, simplemente escriba **Invoke-CsComputerFailOver** y especifique el nombre de ese servidor. Skype para Business Server mueve cargas de trabajo de ese servidor temporalmente a los otros servidores del grupo. Cuando acabe, use el cmdlet **Invoke-CsComputerFailback** para devolver el servidor al servicio. Si necesita revisar todos los servidores de un grupo, siga este procedimiento en cada uno de ellos, de uno en uno. Estos nuevos cmdlets le permiten revisar los servidores mucho más rápido que antes, de forma más fiable y con un proceso más sencillo.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Mayor capacidad de arranque en frío de un grupo front-end

Skype para Business Server presenta un nuevo cmdlet que simplifica y mejora el proceso de iniciar en frío todo un grupo Front-End. El nuevo cmdlet **Start-CsPool** comprueba los requisitos previos de todos los servidores front-end del grupo e intenta encenderlos. Si encuentra algún problema, realiza un diagnóstico y le ofrece detalles y soluciones alternativas. En algunos casos, podrá iniciar el grupo aunque algunos de los servidores no sean capaces.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Compatibilidad con SQL Server AlwaysOn para servidores locales

Skype para Business Server 2015 agrega soporte para grupos de disponibilidad de SQL Server AlwaysOn e instancias de clúster de conmutación por error de SQL Server AlwaysOn. Además de estas características, Skype para Business Server continúa la compatibilidad para la creación de reflejo de base de datos y SQL Server clustering, al igual que en versiones anteriores de Lync Server.
  
Grupos de disponibilidad de SQL Server AlwaysOn es una alta disponibilidad y la solución de recuperación ante desastres en SQL Server 2012 y 2014 de SQL Server que proporciona una alternativa a la creación de reflejo de base de datos. Un grupo de disponibilidad es compatible con un entorno de conmutación por error para un conjunto discreto de bases de datos (conocido como bases de datos de disponibilidad) que conmute juntos. Un grupo de disponibilidad admite un conjunto de bases de datos principales de lectura y escritura y de uno a cuatro conjuntos de bases de datos secundarias correspondientes. Opcionalmente, bases de datos secundarias pueden hacerse disponibles para acceso de sólo lectura y para algunas operaciones de copia de seguridad.
  
Instancias de clúster de conmutación por error de SQL Server aprovechar la funcionalidad de Windows Server Failover Clustering (WSFC) para proporcionar alta disponibilidad local a través de la redundancia en el nivel de instancia de servidor, una instancia de clúster de conmutación por error (FCI). Un FCI es una sola instancia de SQL Server que está instalado en todos los nodos de clústeres de conmutación por error de servidor de Windows (WSFC) y, posiblemente, a través de varias subredes.
  
Para obtener más información, vea [Planear la alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Mejoras en el registro de eventos centralizado y la solución de problemas para servidores locales

El servicio de registro centralizado es el entorno de registro preferida para Skype para Business Server 2015. En esta versión no hay nuevas funciones, pero se ha mejorado la fiabilidad y el rendimiento tanto del servicio como de su agente (ClsAgent.exe), el ejecutable que se comunica con el controlador y recibe órdenes del administrador.
  
Skype para Business Server 2015 usa cmdlets de Windows PowerShell para administrar a los agentes del servicio de registro, iniciar seguimiento y generar informes. (Lync Server 2013 utiliza ClsController.exe para realizar estas tareas.)
  
El servicio de registro centralizado puede funcionar en cualquier Skype para Business Server 2015. Los escenarios integrados (seguimientos predefinidos) son los mismos y sigue siendo posible crear escenarios personalizados. Hay un escenario especial, AlwaysOn, que siempre está en ejecución y permite a los administradores localizar problemas comunes casi en tiempo real.
  
La herramienta de depuración también se ha actualizado para permitir la depuración de los registros de movilidad y funciona con dispositivos que se conectan a Lync 2013 o Skype para Business Server 2015. La herramienta está disponible como una descarga Web desde [Herramientas de depuración](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Administración de implementaciones híbridas

Skype para Business Server 2015 permite administración de implementación híbrida y capacidades de administración mediante la introducción de las características siguientes:
  
- Recomendaciones para las implementaciones de híbrido en función del estado de los activos del cliente local, según lo determinado por el OnRamp de O365 herramienta de asistencia automatizada.
- Mejoras en el Skype para Panel de Control de servidor de negocios y el Skype para Business Server Admin Center para que los administradores pueden utilizar estas herramientas para administrar una implementación híbrida.
- Mejoras de Panel que permiten a los administradores iniciar sesión en un arrendatario O365 y configurar híbrido con Skype para los negocios en línea mediante el Asistente para la configuración híbrida de control.
- Ayuda para mover usuarios locales a Skype para los negocios en línea o se desplaza Skype para usuarios de negocios en línea a local del Panel de control.
- Controlar las características de Panel para identificar y filtrar los objetos de usuario local que se han movido a Skype para los negocios en línea (es decir, usuarios híbrido) de usuarios locales.
- Características de Admin Center para identificar y filtrar los usuarios de la nube creados inicialmente en Skype para los negocios en línea de usuarios híbrido migran desde local a en línea.
- La capacidad de administrar los usuarios de híbridos mediante el Panel de Control para las propiedades que se puede administrar desde locales y centro de administración de propiedades se puede administrar desde Skype para los negocios en línea.
- Posibilidad de sincronizar contraseñas locales de Active Directory con el inquilino online mediante la sincronización de contraseñas de DirSync. Cuando se configura, esta función elimina la necesidad de implementar AD FS para la autenticación federada, aunque sigue siendo necesario para la autenticación multifactor. 
- Continuó el soporte para la coexistencia de Skype para los negocios en línea y en instalaciones de Exchange.
    
> [!NOTE]
> No hay ningún cambio de la Lync Online 2013 e intercambio locales coexistencia y compatibilidad con experiencia. 
  
## <a name="multi-factor-authentication"></a>Autenticación multifactor

La autenticación multifactor es un método de autenticación que requiere el uso de más de un método de comprobación y agrega una segunda capa de seguridad crítica para el inicio de sesión de usuarios y transacciones. Por ejemplo, requiere un nombre de usuario y contraseña y un certificado. Skype para Business Server 2015 continúa ampliando las características de autenticación con varios factores disponibles en las actualizaciones de Lync Server 2013 acum. Los cambios significativos en la autenticación multifactor son:
  
- Uso de la biblioteca de Active Directory de Office 2013 SP1 para la integración con Exchange y SharePoint
- Compatibilidad con la característica de autenticación con varios factores en el Skype para el negocio de la aplicación Web cliente
    
Con Skype para la autenticación con varios factores empresariales, es posible proporcionar distintas opciones de autenticación basados en consideraciones geográficas. Por ejemplo, los clientes pueden configurar su entorno para que la autenticación interna se base en la autenticación integrada de Windows, mientras que los empleados que se autentiquen desde fuera de la organización usan la autenticación multifactor. 
  
El Skype para la experiencia de autenticación con varios factores de negocios es transparente con independencia de:
  
- Ubicación geográfica - si el usuario es inicio de sesión desde dentro o fuera de la organización 
- Tipo de cliente o dispositivo - qué Skype para Business client se utiliza y el dispositivo que el cliente se ejecuta en (PC, móvil, iPad, etcetera).
- Cuenta: ubicación - si el usuario está alojado en un local de Active Directory o en Azure Active Directory en línea (O365)