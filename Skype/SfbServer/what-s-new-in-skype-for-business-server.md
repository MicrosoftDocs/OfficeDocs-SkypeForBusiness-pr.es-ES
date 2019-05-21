---
title: Novedades de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Resumen: Lea este tema para obtener información sobre las nuevas características de Skype empresarial Server 2015. Para obtener información detallada sobre la nueva experiencia del cliente, vea Lync ahora es Skype empresarial: vea las novedades.'
ms.openlocfilehash: e59d158242a5d2dd4b129da3a531749b22e3eadc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291518"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novedades de Skype Empresarial Server 2015

**Resumen:** Lea este tema para obtener información sobre las nuevas características de Skype empresarial Server 2015. Para obtener información detallada sobre la nueva experiencia del cliente, vea [Lync ahora es Skype empresarial: vea](https://go.microsoft.com/fwlink/p/?LinkId=529022)las novedades.
  
Lync ahora es Skype empresarial, una plataforma de comunicaciones y colaboración que reúne una experiencia inspirada por Skype con la seguridad, el cumplimiento y el control de la calidad empresarial de Lync. Skype empresarial ofrece características como presencia, mensajería instantánea, llamadas de voz y videollamadas, y reuniones en línea. Skype empresarial proporciona una nueva experiencia de cliente, una nueva versión de servidor y actualizaciones del servicio en Office 365. Si los usuarios de su organización ya están familiarizados con Skype, agradecerán la potencia y sencillez de Skype empresarial cuando sea fácil encontrarlos y conectarse con ellos. Si los usuarios de su organización llegan a Skype empresarial desde Lync, reconocerán todas las características que ya usan, pero en una nueva interfaz con controles simplificados y nuevos complementos. Además de la nueva experiencia de cliente, Skype empresarial Server 2015 ofrece varias características nuevas para mejorar la capacidad de administración de los servidores locales y las soluciones híbridas.
  
Las nuevas características de Skype empresarial Server 2015 incluyen mejoras a:
  
- Experiencia de usuario  
- Compatibilidad para voz y vídeo
- Compatibilidad con clientes móviles
- Administración de servidores locales
- Implementación y administración de soluciones híbridas
- Compatibilidad con la autenticación multifactor
    
## <a name="user-experience"></a>Experiencia de usuario

El cliente de Skype empresarial es muy similar a la versión comercial de Skype y usa los mismos botones e iconos. El menor número de menús y la jerarquía de tareas más plana facilita la búsqueda de los controles y comandos que se necesitan. 
  
Skype empresarial incluye la nueva experiencia de usuario descrita anteriormente y la experiencia de usuario de Lync 2013 publicada anteriormente. La inclusión de ambas experiencias permite a las empresas administrar los cambios para sus usuarios controlando el proceso y el momento de la implementación del nuevo cliente. La experiencia de usuario predeterminada depende de la versión del servidor que esté usando. Los administradores eligen la experiencia que prefieren con el cmdlet **Set-Cs ClientPolicy** con el parámetro EnableSkypeUI. Para obtener más información sobre la configuración de la experiencia del cliente, consulte [configurar la experiencia de cliente con Skype empresarial](deploy/deploy-clients/configure-the-client-experience.md) y la [comparación de características del cliente de escritorio en Skype empresarial](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype empresarial 2016. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Mejoras de voz y vídeo

Skype empresarial Server 2015 incluye mejoras en la funcionalidad de voz y vídeo, como la recopilación y el análisis de datos de llamadas, y mejoras en la interoperabilidad con sistemas de videoconferencias de terceros.
  
### <a name="call-data-collection-and-analysis"></a>Recopilación y análisis de datos de llamadas

La característica calificar mi llamada permite a los administradores de Skype empresarial Server 2015 recopilar datos de llamadas. Solo está disponible para implementaciones locales. Se pedirá a los usuarios que rellenen una encuesta tras completar una llamada. Para obtener más información, consulte [Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Interoperabilidad mejorada con sistemas de videoconferencia de terceros

El servidor de interoperabilidad de video (VIS) actúa como intermediario entre los sistemas de Skype empresarial Server y de videoconferencias Cisco (VTC). Al unirse a una reunión, ahora los usuarios pueden optar por un sistema Cisco VTC. El servidor de interoperabilidad de vídeo está implementado como un rol de servidor independiente para implementaciones locales. Para obtener más información, consulte [planear el servidor de interoperabilidad de vídeo en Skype empresarial server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Vía trabajo

La característica llamar a través del trabajo permite a los usuarios de la empresa realizar llamadas de voz desde el cliente de Skype empresarial. Cuando un usuario realiza una llamada, se dirige de Skype empresarial al teléfono PBX o RTC del creador. Cuando responde, la llamada se dirige al número del destinatario. Las respuestas a los destinatarios de la llamada y la llamada se establece con Skype empresarial como el panel de control. El creador puede administrar sus controles de presencia y llamada de Skype empresarial. Los administradores de servidores son los encargados de habilitar y configurar las llamadas Vía trabajo en la empresa. Para obtener más información, consulte [Plan for Call Via work on Skype empresarial Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Mejoras de compatibilidad con dispositivos móviles

Entre las mejoras en la compatibilidad con dispositivos móviles se incluyen características para mejorar la experiencia móvil de los usuarios de Enterprise Edition, como el acceso al historial de conversaciones y los datos de registro, las experiencias de reunión móvil mejoradas y la compatibilidad de inicio de sesión único en Office. Además, se han incorporado mejoras en la compatibilidad con Android, las mejoras de rendimiento y las características para simplificar la integración a través del marco de aplicaciones común. 
  
> [!NOTE]
> Los servidores de Lync 2013 UCWA deben actualizarse a Skype empresarial Server 2015 para admitir clientes móviles. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>El historial de conversaciones del servidor ahora está disponible en los dispositivos móviles

Para habilitar el acceso móvil a historial de conversaciones, mensajes instantáneos perdidos y datos de registro de llamadas, el archivado de esta información se procesa ahora a través del servidor para todos los clientes móviles. La función de aceptación automática de mensajes instantáneos mejora la fiabilidad y previene los mensajes de tiempo agotado del servidor cuando un usuario móvil no responde inmediatamente a un mensaje. Para aprovechar las ventajas de la integración de carpetas de Exchange/Outlook basadas en el servidor, Exchange Server 2013 o posterior, y los clientes móviles actualizados, son necesarios. 
  
### <a name="enhanced-meeting-experiences"></a>Experiencia de reunión mejorada

Las funciones de reunión de la versión de escritorio ahora también están disponibles para usuarios móviles. Entre las nuevas características se incluyen las siguientes:
  
- Navegación asíncrona de contenido de PowerPoint compartido
- Capacidad del moderador para tomar el control del contenido compartido de PowerPoint
- Administración de la sala de espera por parte de los moderadores, que pueden admitir y rechazar participantes
    
### <a name="skype-for-business-on-android-improvements"></a>Mejoras de Skype empresarial para Android

Skype empresarial en Android ahora ofrece características similares a las de Skype empresarial en iOS y Skype empresarial en Windows:
  
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

Skype empresarial Server 2015 ofrece varias características nuevas para mejorar la capacidad de administración de los servidores locales, como la actualización local, la configuración inteligente, los procesos mejorados de actualización y revisión, la capacidad de inicio en frío del grupo frontal de aplicaciones mejoradas, SQL Server AlwaysOn soporte técnico y registro centralizado y solución de problemas.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Actualización local de servidores

Ahora puede actualizar sistemas de Lync Server 2013 a Skype empresarial Server 2015 con la nueva característica de actualización local, que usa inversiones existentes de hardware y servidor de Lync Server 2013, lo que reduce el costo general de implementación de Skype empresarial Server 2015.
  
Hay dos escenarios posibles: el método Mover usuario, que no causa tiempo de inactividad, y el método Sin conexión, que sí lo provoca. Para obtener más información sobre cuál es el más adecuado para su negocio, consulte [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> La opción local no está disponible si está actualizando desde Lync Server 2010. Para obtener más información sobre la actualización de Lync Server 2010, consulte [planear la actualización a Skype empresarial server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Configuración inteligente

La función Configuración inteligente, que detecta y descarga automáticamente las actualizaciones, ahora forma parte del programa de configuración. Durante el proceso de instalación, se le pregunta al usuario si el proceso de instalación debe comprobar si hay actualizaciones. Para obtener más información, consulte [Install Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Proceso mejorado de revisión y actualización de servidores front-end

Skype empresarial Server presenta dos nuevos cmdlets que ayudan a que la actualización o la revisión de los servidores de solicitudes de cliente sean mucho más fáciles que en versiones anteriores de Lync Server.
  
Cuando necesite aplicar una revisión o realizar cualquier otro mantenimiento, en un servidor front-end, simplemente escriba **Invoke-CsComputerFailOver** y especifique el nombre del servidor. Skype empresarial Server mueve temporalmente la carga de trabajo de ese servidor a los demás servidores del grupo. Cuando acabe, use el cmdlet **Invoke-CsComputerFailback** para devolver el servidor al servicio. Si necesita revisar todos los servidores de un grupo, siga este procedimiento en cada uno de ellos, de uno en uno. Estos nuevos cmdlets le permiten revisar los servidores mucho más rápido que antes, de forma más fiable y con un proceso más sencillo.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Mayor capacidad de arranque en frío de un grupo front-end

Skype empresarial Server presenta un nuevo cmdlet que simplifica y mejora el proceso de inicio Cold de un grupo de servidores front-end. El nuevo cmdlet **Start-CsPool** comprueba los requisitos previos de todos los servidores front-end del grupo e intenta encenderlos. Si encuentra algún problema, realiza un diagnóstico y le ofrece detalles y soluciones alternativas. En algunos casos, podrá iniciar el grupo aunque algunos de los servidores no sean capaces.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Compatibilidad con SQL Server AlwaysOn para servidores locales

Skype empresarial Server 2015 agrega compatibilidad con los grupos de disponibilidad AlwaysOn de SQL Server y las instancias de clúster de conmutación por error de SQL Server AlwaysOn. Además de estas características, Skype empresarial Server continúa siendo compatible con el reflejo de bases de datos y la organización en clústeres de SQL Server, como en versiones anteriores de Lync Server.
  
Grupos de disponibilidad AlwaysOn de SQL Server es una solución de alta disponibilidad y recuperación ante desastres en SQL Server 2012 y SQL Server 2014 que proporciona una alternativa a la creación de reflejo de la base de datos. Un grupo de disponibilidad admite un entorno de conmutación por error para un conjunto discreto de bases de datos (conocidas como bases de datos de disponibilidad) que conmutan por error juntos. Un grupo de disponibilidad admite un conjunto de bases de datos principales de lectura y escritura y de una a cuatro conjuntos de bases de datos secundarias correspondientes. De manera opcional, las bases de datos secundarias pueden estar disponibles para el acceso de solo lectura y para algunas operaciones de copia de seguridad.
  
Las instancias de clúster de conmutación por error de SQL Server aprovechan la funcionalidad de clústeres de conmutación por error de Windows Server (WSFC) para proporcionar alta disponibilidad local mediante redundancia en el nivel de instancia de servidor, una instancia de clúster de conmutación por error (FCI). Un FCI es una única instancia de SQL Server que se instala en los nodos de clúster de conmutación por error de Windows Server (WSFC) y, posiblemente, en varias subredes.
  
Para más información, vea [Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Mejoras en el registro de eventos centralizado y la solución de problemas para servidores locales

El servicio de registro centralizado es el entorno de registro preferido para Skype empresarial Server 2015. En esta versión no hay nuevas funciones, pero se ha mejorado la fiabilidad y el rendimiento tanto del servicio como de su agente (ClsAgent.exe), el ejecutable que se comunica con el controlador y recibe órdenes del administrador.
  
Skype empresarial Server 2015 usa cmdlets de Windows PowerShell para administrar los agentes del servicio de registro, iniciar el seguimiento y generar informes. (Lync Server 2013 usó ClsController. exe para realizar estas tareas).
  
El servicio de registro centralizado puede ejecutarse en cualquier Skype empresarial Server 2015. Los escenarios integrados (seguimientos predefinidos) son los mismos y sigue siendo posible crear escenarios personalizados. Hay un escenario especial, AlwaysOn, que siempre está en ejecución y permite a los administradores localizar problemas comunes casi en tiempo real.
  
La herramienta de depuración de Snoop también se ha actualizado para permitir la depuración de registros de movilidad y funcionará con dispositivos que se conectan a Lync 2013 o a Skype empresarial Server 2015. La herramienta está disponible como descarga desde [herramientas](https://go.microsoft.com/fwlink/?LinkId=285257)de depuración.
  
## <a name="hybrid-deployment-and-management"></a>Administración de implementaciones híbridas

Skype empresarial Server 2015 permite la administración híbrida de la implementación y las capacidades de administración al introducir las siguientes características:
  
- Recomendaciones para implementaciones híbridas basadas en el estado de los activos locales del cliente, según lo determine la herramienta de asistencia automatizada de O365 para O365.
- Mejoras en el panel de control de Skype empresarial Server y el centro de administración de Skype empresarial Server para que los administradores puedan usar estas herramientas para administrar una implementación híbrida.
- Mejoras del panel de control que permiten a los administradores iniciar sesión en un inquilino de O365 y configurar una implementación híbrida con Skype empresarial online mediante el Asistente para la configuración híbrida.
- Compatibilidad del panel de control para mover usuarios locales a Skype empresarial online o mover los usuarios de Skype empresarial online de nuevo a local.
- Características del panel de control para identificar y filtrar objetos de usuario locales que se han movido a Skype empresarial online (es decir, usuarios híbridos) de usuarios locales.
- Características del centro de administración para identificar y filtrar los usuarios de la nube inicialmente creados en Skype empresarial online desde usuarios híbridos migrados de local a conectado.
- La capacidad de administrar los usuarios híbridos mediante el panel de control para las propiedades que se pueden administrar desde el entorno local y el centro de administración para las propiedades que se pueden administrar desde Skype empresarial online.
- Posibilidad de sincronizar contraseñas locales de Active Directory con el inquilino online mediante la sincronización de contraseñas de DirSync. Cuando se configura, esta función elimina la necesidad de implementar AD FS para la autenticación federada, aunque sigue siendo necesario para la autenticación multifactor. 
- Soporte técnico continuado para la coexistencia entre Skype empresarial online y Exchange local.
    
> [!NOTE]
> No hay ningún cambio en la coexistencia de Lync Online y en la experiencia de soporte técnico de Lync Online 2013 y Exchange local. 
  
## <a name="multi-factor-authentication"></a>Autenticación multifactor

La autenticación multifactor es un método de autenticación que requiere el uso de más de un método de comprobación y agrega una segunda capa de seguridad crítica para el inicio de sesión de usuarios y transacciones. Por ejemplo, requiere un nombre de usuario y contraseña y un certificado. Skype empresarial Server 2015 continúa con la compilación de las características de autenticación multifactor disponibles en las actualizaciones acumulativas de Lync Server 2013. Los cambios significativos en la autenticación multifactor son:
  
- Uso de la biblioteca de Active Directory de Office 2013 SP1 para la integración con Exchange y SharePoint
- Compatibilidad con la característica de autenticación multifactor en el cliente de la aplicación Web de Skype empresarial
    
Con la autenticación multifactor de Skype empresarial, ahora es posible proporcionar diferentes opciones de autenticación basadas en la geografía. Por ejemplo, los clientes pueden configurar su entorno para que la autenticación interna se base en la autenticación integrada de Windows, mientras que los empleados que se autentiquen desde fuera de la organización usan la autenticación multifactor. 
  
La experiencia de la autenticación multifactor de Skype empresarial es fluida, independientemente de:
  
- Ubicación geográfica: ya sea que el usuario inicie sesión desde dentro o fuera de la organización 
- Tipo de cliente o dispositivo: el cliente de Skype empresarial que se usa y el dispositivo en el que se está ejecutando el cliente (PC, móvil, iPad, etc.)
- Ubicación de la cuenta: Si el usuario está hospedado en un Active Directory local o en Azure Active Directory online (O365)
