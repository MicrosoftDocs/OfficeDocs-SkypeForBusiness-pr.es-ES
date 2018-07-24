---
title: Novedades de Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Resumen: Lea este tema para obtener más información acerca de las nuevas características de Skype para Business Server 2015. Para obtener información detallada acerca de la nueva experiencia del cliente, vea que Lync ahora está Skype para la empresa: consulte cuáles son las novedades.'
ms.openlocfilehash: 9c5dd3996cb6c15de93b564fa800e01270d92b66
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012454"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novedades de Skype Empresarial Server 2015

**Resumen:** Lea este tema para obtener más información acerca de las nuevas características de Skype para Business Server 2015. Para obtener información detallada acerca de la nueva experiencia del cliente, vea [Lync es ahora Skype para la empresa: vea las novedades](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync es ahora Skype para plataforma empresarial, un comunicaciones y colaboración que reúne una experiencia de inspiración por Skype con la seguridad de nivel empresarial, el cumplimiento de normas y el control de Lync. Skype para la empresa ofrece características que incluyen la presencia, mensajería instantánea, voz y llamadas de vídeo y reuniones en línea. Skype para la empresa proporciona a un nuevo cliente experiencia, una nueva versión de servidor y actualizaciones para el servicio en Office 365. Si los usuarios de su organización ya están familiarizados con Skype, podrá disfrutar de la capacidad y la simplicidad de Skype para la empresa sea fácil de encontrar y conectarse con compañeros de trabajo. Si los usuarios de su organización se proceden a Skype para la empresa de Lync, podrá reconocer todas las características que ya usan, aunque en una nueva interfaz actualizada con controles y nuevas adiciones simplificadas. Además de la nueva experiencia del cliente, Skype para Business Server 2015 proporciona varias características nuevas para mejorar la capacidad de administración de los servidores locales y soluciones híbridas.
  
Nuevas características de Skype para Business Server 2015 incluyen mejoras en:
  
- Experiencia de usuario  
- Compatibilidad para voz y vídeo
- Compatibilidad con clientes móviles
- Administración de servidores locales
- Implementación y administración de soluciones híbridas
- Compatibilidad con la autenticación multifactor
    
## <a name="user-experience"></a>Experiencia de usuario

El Skype para cliente empresarial es muy similar a la versión del consumidor de Skype y usa el mismo botones e iconos. El menor número de menús y la jerarquía de tareas más plana facilita la búsqueda de los controles y comandos que se necesitan. 
  
Skype para la empresa incluye la nueva experiencia de usuario se ha descrito anteriormente y la experiencia del usuario de Lync 2013 publicado anteriormente. La inclusión de ambos experiencias permite a las empresas administrar cambio para sus usuarios mediante el control del proceso y el momento de la nueva cliente implantación. La experiencia de usuario predeterminado depende de la versión del servidor que está utilizando. Los administradores eligen la experiencia que prefieren con el cmdlet **Set-Cs ClientPolicy** con el parámetro EnableSkypeUI. Para obtener más información acerca de cómo configurar la experiencia del cliente, vea [Configurar el cliente de experiencia con Skype para la empresa](deploy/deploy-clients/configure-the-client-experience.md) y [comparación de características de cliente de escritorio de Skype para la empresa](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> La experiencia del cliente Lync 2013 no es una opción de Skype para versiones de cliente de 2016 empresarial. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Mejoras de voz y vídeo

Skype para Business Server 2015 incluye mejoras a la funcionalidad de voz y vídeo, incluida la llamada y recopilación de datos y análisis, mejor interoperabilidad con sistemas de videoconferencias de terceros.
  
### <a name="call-data-collection-and-analysis"></a>Recopilación y análisis de datos de llamadas

La característica Mis llamadas de tasa, permite Skype para los administradores de Business Server 2015 recopila datos de la llamada. Solo está disponible para implementaciones locales. Se pedirá a los usuarios que rellenen una encuesta tras completar una llamada. Para obtener más información, consulte [tasa de mi llamada de Skype para Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Interoperabilidad mejorada con sistemas de videoconferencia de terceros

El servidor de vídeo de interoperabilidad (VISIBLES) actúa como intermediario entre Skype para Business Server y Cisco sistemas de videoconferencias (VTC). Al unirse a una reunión, ahora los usuarios pueden optar por un sistema Cisco VTC. El servidor de interoperabilidad de vídeo está implementado como un rol de servidor independiente para implementaciones locales. Para obtener más información, consulte [Plan para servidor de interoperabilidad de vídeo de Skype para Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Vía trabajo

La llamada a través de la característica de trabajo permite a los usuarios de empresa realizar llamadas de voz desde el Skype para clientes empresariales. Cuando un usuario realiza una llamada de voz, se enruta de Skype para la empresa al teléfono del autor de la PBX o RTC. Cuando responde, la llamada se dirige al número del destinatario. Las respuestas de destinatario de la llamada y la llamada se establece con Skype para la empresa que actúa como el panel de control. El autor puede administrar su presencia y controles de llamada de Skype para la empresa. Los administradores de servidores son los encargados de habilitar y configurar las llamadas Vía trabajo en la empresa. Para obtener más información, consulte [Plan para llamar vía trabajo en Skype para Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Mejoras de compatibilidad con dispositivos móviles

Mejoras en la compatibilidad con dispositivos móviles incluyen características para mejorar la experiencia móvil de los usuarios de Enterprise Edition, como el acceso a los datos de registro y el historial de conversación, experiencias de reunión móvil mejorada y soporte de inicio de sesión único a través de Office. Además, hay mejoras a soporte de Android, mejoras de rendimiento y las características para simplificar la integración a través del marco de aplicación comunes. 
  
> [!NOTE]
> Servidores de Lync 2013 UCWA deben actualizarse a Skype para Business Server 2015 admitir a clientes móviles. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>El historial de conversaciones del servidor ahora está disponible en los dispositivos móviles

Para habilitar el acceso móvil a historial de conversaciones, mi perdida y datos de registro de llamadas, el archivado de esta información es ahora procesan a través del servidor para todos los clientes móviles. La función de aceptación automática de mensajes instantáneos mejora la fiabilidad y previene los mensajes de tiempo agotado del servidor cuando un usuario móvil no responde inmediatamente a un mensaje. Para aprovechar la integración de las carpetas de Exchange/Outlook en función de servidor, se requiere Exchange Server 2013 o más reciente y actualizados de los clientes móviles. 
  
### <a name="enhanced-meeting-experiences"></a>Experiencia de reunión mejorada

Las funciones de reunión de la versión de escritorio ahora también están disponibles para usuarios móviles. Entre las nuevas características se incluyen las siguientes:
  
- Navegación asíncrona de contenido de PowerPoint compartido
- Capacidad del moderador para tomar el control de PowerPoint compartida contenido
- Administración de la sala de espera por parte de los moderadores, que pueden admitir y rechazar participantes
    
### <a name="skype-for-business-on-android-improvements"></a>Skype para la empresa en las mejoras de Android

Skype para la empresa en Android ahora ofrece características similares a lo que está disponible en Skype para la empresa en iOS y Skype para la empresa en Windows:
  
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

Skype para Business Server 2015 proporciona varias características nuevas para mejorar la manejabilidad de los servidores locales, incluidos actualización en contexto, el programa de instalación inteligente, mejorada de aplicar las revisiones y actualizaciones procesos, capacidad mejorada de Front-End del grupo Inicio pasiva, SQL Server AlwaysOn soporte técnico y centralizado de registro y solución de problemas.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Actualización local de servidores

Ahora puede actualizar los sistemas de Lync Server 2013 a Skype para Business Server 2015 utilizando la característica nueva de actualización en contexto, que usa Lync Server 2013 hardware y server las inversiones existentes, lo que reduce el costo total para implementar Skype para Business Server 2015.
  
Hay dos escenarios posibles: el método Mover usuario, que no causa tiempo de inactividad, y el método Sin conexión, que sí lo provoca. Para obtener más información acerca de qué es la adecuada para su negocio procedimiento de actualización, vea [Planear la actualización a Skype para Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> La opción en contexto no está disponible si está actualizando de Lync Server 2010. Para obtener más información sobre la actualización de Lync Server 2010, vea [Planear la actualización a Skype para Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Configuración inteligente

La función Configuración inteligente, que detecta y descarga automáticamente las actualizaciones, ahora forma parte del programa de configuración. Durante el proceso de instalación, se pregunta al usuario si el proceso de instalación debe buscar actualizaciones. Para obtener más información, vea [Instalar Skype para Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Proceso mejorado de revisión y actualización de servidores front-end

Skype para Business Server presenta dos nuevos cmdlets que ayudan a realizar la actualización o la aplicación de revisiones de servidor front-end mucho más fácil que en versiones anteriores de Lync Server.
  
Cuando debe aplicar una revisión, o realizar ningún mantenimiento, a un servidor Front-End, simplemente escriba **Invoke-CsComputerFailOver** y especifique el nombre de ese servidor. Skype para Business Server mueve la carga de trabajo de ese servidor temporalmente a los demás servidores del grupo de servidores. Cuando acabe, use el cmdlet **Invoke-CsComputerFailback** para devolver el servidor al servicio. Si necesita revisar todos los servidores de un grupo, siga este procedimiento en cada uno de ellos, de uno en uno. Estos nuevos cmdlets le permiten revisar los servidores mucho más rápido que antes, de forma más fiable y con un proceso más sencillo.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Mayor capacidad de arranque en frío de un grupo front-end

Skype para Business Server presenta un nuevo cmdlet que simplifica y mejora el proceso de inicio de fría de un grupo de servidores Front-End todo. El nuevo cmdlet **Start-CsPool** comprueba los requisitos previos de todos los servidores front-end del grupo e intenta encenderlos. Si encuentra algún problema, realiza un diagnóstico y le ofrece detalles y soluciones alternativas. En algunos casos, podrá iniciar el grupo aunque algunos de los servidores no sean capaces.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Compatibilidad con SQL Server AlwaysOn para servidores locales

Skype para Business Server 2015 agrega compatibilidad con grupos de disponibilidad de SQL Server AlwaysOn e instancias de clúster de conmutación por error de SQL Server AlwaysOn. Además de estas características, Skype para Business Server sigue siendo compatible con la creación de reflejo de base de datos y agrupación en clústeres de SQL Server, al igual que en las versiones anteriores de Lync Server.
  
Grupos de disponibilidad de SQL Server AlwaysOn es una alta disponibilidad y la solución de recuperación ante desastres en SQL Server 2012 y SQL Server 2014 que proporciona una alternativa a la creación de reflejo de base de datos. Un grupo de disponibilidad es compatible con un entorno de conmutación por error para un conjunto discreto de bases de datos (conocido como bases de datos de disponibilidad) que conmutar por error juntos. Un grupo de disponibilidad es compatible con un conjunto de bases de datos principales de lectura y escritura y uno a cuatro conjuntos de bases de datos secundarias correspondientes. De forma opcional, bases de datos secundarias pueden estar disponibles para acceso de sólo lectura y para algunas operaciones de copia de seguridad.
  
Instancias de clúster de conmutación por error de SQL Server aprovecha la funcionalidad de agrupación en clústeres de conmutación por error de servidor de Windows (WSFC) para proporcionar alta disponibilidad local a través de redundancia en el nivel de instancia de servidor, una instancia de clúster de conmutación por error (FCI). Un FCI es una sola instancia de SQL Server que está instalado en todos los nodos de clústeres de conmutación por error de servidor de Windows (WSFC) y, posiblemente, en varias subredes.
  
Para obtener más información, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Mejoras en el registro de eventos centralizado y la solución de problemas para servidores locales

El servicio de registro centralizado es el entorno de registro preferida para Skype para Business Server 2015. En esta versión no hay nuevas funciones, pero se ha mejorado la fiabilidad y el rendimiento tanto del servicio como de su agente (ClsAgent.exe), el ejecutable que se comunica con el controlador y recibe órdenes del administrador.
  
Skype para Business Server 2015 usa cmdlets de Windows PowerShell para administrar a los agentes del servicio de registro, iniciar el seguimiento y generación de informes. (Lync Server 2013 usa ClsController.exe para realizar estas tareas).
  
El servicio de registro centralizado puede ejecutar en cualquier Skype para Business Server 2015. Los escenarios integrados (seguimientos predefinidos) son los mismos y sigue siendo posible crear escenarios personalizados. Hay un escenario especial, AlwaysOn, que siempre está en ejecución y permite a los administradores localizar problemas comunes casi en tiempo real.
  
La herramienta de depuración también se ha actualizado para permitir la depuración de los registros de movilidad y funcionará con dispositivos que se conectan a Lync 2013 o Skype para Business Server 2015. La herramienta está disponible como una descarga Web desde [las herramientas de depuración](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Administración de implementaciones híbridas

Skype para Business Server 2015 permite la administración de implementación híbrida y capacidades de administración mediante la introducción de las siguientes características:
  
- Recomendaciones para las implementaciones híbridas en función del estado de los activos del cliente local, según lo determinado por la OnRamp para la herramienta de ayuda automatizada de Office 365.
- Mejoras en la Skype para el Panel de Control de servidor empresarial y la Skype centro de administración de servidor empresarial de modo que los administradores pueden usar estas herramientas para administrar una implementación híbrida.
- Control de mejoras en el Panel que permiten a los administradores iniciar sesión en un inquilino de Office 365 y configurar híbrida con Skype para profesionales Online mediante el Asistente de configuración híbrida.
- Compatibilidad con Panel para mover usuarios locales a Skype para profesionales en línea o mover Skype para usuarios profesionales en línea de vuelta a local el control.
- Controlar las características de Panel para identificar y filtrar los objetos de usuario local que se han movido a Skype para profesionales en línea (es decir, los usuarios de híbrido) desde los usuarios locales.
- Las características del centro de administración para identificar y filtrar los usuarios de la nube creados inicialmente en Skype para profesionales en línea de los usuarios híbrida migran desde local a en línea.
- La capacidad de administrar los usuarios de híbrido mediante el Panel de Control para las propiedades que se puede administrar desde local y el centro de administración de propiedades se puede administrar desde Skype para profesionales en línea.
- Posibilidad de sincronizar contraseñas locales de Active Directory con el inquilino online mediante la sincronización de contraseñas de DirSync. Cuando se configura, esta función elimina la necesidad de implementar AD FS para la autenticación federada, aunque sigue siendo necesario para la autenticación multifactor. 
- El soporte para la coexistencia de Skype para profesionales en línea y local de Exchange continuo.
    
> [!NOTE]
> No hay ningún cambio respecto a la Lync Online 2013 y Exchange local coexistencia y compatibilidad con experiencia. 
  
## <a name="multi-factor-authentication"></a>Autenticación multifactor

La autenticación multifactor es un método de autenticación que requiere el uso de más de un método de comprobación y agrega una segunda capa de seguridad crítica para el inicio de sesión de usuarios y transacciones. Por ejemplo, requiere un nombre de usuario y contraseña y un certificado. Skype para Business Server 2015 continúa crear sobre las características de autenticación multifactor disponibles en las actualizaciones acumulativas de Lync Server 2013. Los cambios significativos en la autenticación multifactor son:
  
- Uso de la biblioteca de Active Directory de Office 2013 SP1 para la integración con Exchange y SharePoint
- Compatibilidad con la característica de autenticación multifactor en el Skype para clientes empresariales Web App
    
Con Skype para la autenticación multifactor de negocio, ahora es posible proporcionar diferentes opciones de autenticación basadas en la ubicación geográfica. Por ejemplo, los clientes pueden configurar su entorno para que la autenticación interna se base en la autenticación integrada de Windows, mientras que los empleados que se autentiquen desde fuera de la organización usan la autenticación multifactor. 
  
El Skype para la experiencia de la autenticación multifactor Business es perfecta independientemente de:
  
- Ubicación geográfica - si el usuario es iniciar sesión desde dentro o fuera de la organización 
- Se utiliza el tipo de cliente o dispositivo - qué Skype para clientes empresariales y el dispositivo al que el cliente se ejecuta en (PC, mobile, iPad, etcetera).
- Cuenta ubicación - si el usuario está hospedado en un Active Directory local o en Azure Active Directory Online (Office 365)