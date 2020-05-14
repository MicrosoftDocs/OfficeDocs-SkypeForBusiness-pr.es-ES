---
title: Novedades de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Resumen: Lea este tema para obtener información sobre las nuevas características de Skype empresarial Server 2015. Para obtener información detallada sobre la nueva experiencia del cliente, consulte Lync ahora es Skype empresarial: vea las novedades.'
ms.openlocfilehash: b8d0d8334977b5367419991d1bcabba303718c89
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221090"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novedades de Skype empresarial Server 2015

**Resumen:** Lea este tema para obtener información sobre las nuevas características de Skype empresarial Server 2015. Para obtener información detallada sobre la nueva experiencia del cliente, consulte [Lync ahora es Skype empresarial: vea](https://go.microsoft.com/fwlink/p/?LinkId=529022)las novedades.
  
Lync ahora es Skype empresarial, una plataforma de comunicaciones y colaboración que reúne una experiencia inspirado en Skype con la seguridad, el cumplimiento y el control de la categoría empresarial de Lync. Skype empresarial ofrece características como la presencia, la mensajería instantánea, las llamadas de voz y vídeo, y las reuniones en línea. Skype empresarial proporciona una nueva experiencia de cliente, una nueva versión del servidor y actualizaciones del servicio en Microsoft 365 u Office 365. Si los usuarios de su organización ya están familiarizados con Skype, apreciarán la potencia y la simplicidad de Skype empresarial, donde es fácil encontrar y conectarse con compañeros de trabajo. Si los usuarios de su organización llegan a Skype empresarial desde Lync, reconocerán todas las características que ya usan, pero en una nueva interfaz nueva con controles simplificados y nuevas adiciones. Además de la nueva experiencia del cliente, Skype empresarial Server 2015 ofrece varias características nuevas para mejorar la facilidad de administración de los servidores locales y las soluciones híbridas.
  
Las nuevas características de Skype empresarial Server 2015 incluyen mejoras para:
  
- Experiencia del usuario  
- Compatibilidad con voz y vídeo
- Compatibilidad con dispositivos móviles
- Administración de servidores locales
- Implementación y administración de soluciones híbridas
- Compatibilidad con multi-factor Authentication
    
## <a name="user-experience"></a>Experiencia del usuario

El cliente de Skype empresarial es muy similar a la versión de consumidor de Skype y usa los mismos botones e iconos. Menos menús y una jerarquía de tareas más plana permiten a los usuarios encontrar fácilmente los controles y comandos que necesitan. 
  
Skype empresarial incluye la nueva experiencia de usuario descrita anteriormente y la experiencia de usuario de Lync 2013 que se ha lanzado anteriormente. La inclusión de ambas experiencias permite a las empresas administrar los cambios para sus usuarios mediante el control del proceso y el momento en que se implementa el nuevo cliente. La experiencia de usuario predeterminada depende de la versión del servidor que esté usando. Los administradores eligen la experiencia preferida usando el cmdlet **set-CsClientPolicy** con el parámetro EnableSkypeUI. Para obtener más información acerca de la configuración de la experiencia del cliente, vea [configurar la experiencia del cliente con](deploy/deploy-clients/configure-the-client-experience.md) la [comparación de características de cliente de escritorio y Skype empresarial para Skype empresarial](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype empresarial 2016. Antes de intentar configurar el entorno del cliente para usar el cliente Lync 2013, Compruebe la versión del cliente para asegurarse de que no empieza con el número 16; por ejemplo: 16. x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Mejoras en las características de voz y vídeo

Skype empresarial Server 2015 incluye mejoras en la funcionalidad de voz y vídeo, incluidos la recopilación y el análisis de datos de llamadas, y la interoperabilidad mejorada con sistemas de teleconferencia de terceros.
  
### <a name="call-data-collection-and-analysis"></a>Recopilación y análisis de datos de llamadas

La característica valorar mi llamada permite a los administradores de Skype empresarial Server 2015 recopilar datos de llamadas. Esta característica solo está disponible para implementaciones locales. Se pide a los usuarios que realicen una encuesta después de completar una llamada. Para obtener más información, consulte [valorar mi llamada en Skype empresarial Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Interoperabilidad mejorada con sistemas de videoconferencia de terceros

El servidor de interoperabilidad de vídeo (VIS) actúa como intermediario entre Skype empresarial Server y sistemas de videoconferencia (VTC) de Cisco. Al unirse a una reunión, ahora los usuarios pueden seleccionar un sistema Cisco VTC. El servidor de interoperabilidad de vídeo (VIS) se implementa como un rol de servidor independiente para las implementaciones locales. Para obtener más información, consulte [Plan for video Interop Server in Skype for Business server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Llamar a través del trabajo

La característica llamar a través del trabajo permite a los usuarios de la empresa realizar llamadas de voz desde el cliente de Skype empresarial. Cuando un usuario realiza una llamada de voz, se enruta desde Skype empresarial al teléfono PBX o RTC del autor. Una vez que el remitente responde al teléfono, la llamada se dirige al número de destino. El destinatario de la llamada responde y la llamada se establece con Skype empresarial Server como panel de control. El creador puede administrar su presencia y los controles de llamadas desde Skype empresarial. Los administradores de servidores habilitan y configuran llamadas mediante trabajo para la empresa. Para obtener más información, consulte [Plan for Call Via Work in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Mejoras en la compatibilidad con dispositivos móviles

Entre las mejoras de compatibilidad con dispositivos móviles se incluyen características para mejorar la experiencia móvil para los usuarios de Enterprise Edition, como el acceso al historial de conversaciones y a los datos de registro, las experiencias de reuniones móviles mejoradas y el soporte de inicio de sesión único en Office. Además, hay mejoras en el soporte de Android, las mejoras de rendimiento y las características para simplificar la integración a través del marco de la aplicación común. 
  
> [!NOTE]
> Los servidores de Lync 2013 UCWA deben actualizarse a Skype empresarial Server 2015 para admitir clientes móviles. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>El historial de conversaciones del lado servidor ya está disponible en los dispositivos móviles

Para habilitar el acceso móvil al historial de conversaciones, la mensajería instantánea perdida y los datos de registro de llamadas, el archivado de esta información se procesa ahora a través del servidor para todos los clientes móviles. La característica de aceptación automática para mensajería instantánea mejora la confiabilidad al impedir que se agoten los mensajes de tiempo de espera del servidor cuando un usuario móvil no responde a un mensaje instantáneo inmediatamente. Para aprovechar las ventajas de la integración de carpetas de Exchange/Outlook basadas en servidor, se necesitan Exchange Server 2013 o versiones más recientes y clientes móviles actualizados. 
  
### <a name="enhanced-meeting-experiences"></a>Experiencias de reunión mejoradas

La funcionalidad de reunión disponible en el escritorio ahora también está disponible para los usuarios móviles. La nueva funcionalidad incluye:
  
- Navegación asincrónica de contenido de PowerPoint compartido
- Capacidad del moderador para tomar el control del contenido compartido de PowerPoint
- Administración de la sala de espera para los moderadores, permitiéndoles admitir o denegar participantes
    
### <a name="skype-for-business-on-android-improvements"></a>Mejoras de Skype empresarial para Android

Skype empresarial en Android ahora ofrece características similares a las disponibles en Skype empresarial en iOS y Skype empresarial en Windows:
  
- Continuar o volver a unirse a las conversaciones
- Habilitar el certificado y la autenticación pasiva
- Invitar a otros usuarios a una conversación
- Inicio sencillo de conversaciones de grupo
- Unirse a una reunión sin ser un usuario de Skype empresarial
- Habilitar la interfaz de usuario de smartphone en tabletas Android
- Administrar reuniones agregando o quitando participantes
    
> [!NOTE]
> Estas características requieren Android OS versión 4,0 o posterior. 
  
## <a name="management-of-on-premises-servers"></a>Administración de servidores locales

Skype empresarial Server 2015 proporciona varias características nuevas para mejorar la facilidad de administración de los servidores locales, como la actualización en el lugar, la configuración inteligente, los procesos mejorados de revisión y actualización, la funcionalidad de inicio en frío del grupo de servidores front-end, la compatibilidad con AlwaysOn de SQL Server y el registro y la solución de problemas centralizados.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Actualización en el lugar para servidores locales

Ahora puede actualizar sistemas de Lync Server 2013 a Skype empresarial Server 2015 mediante la nueva característica de actualización local, que usa inversiones existentes de hardware y servidor de Lync Server 2013, lo que reduce el costo general de implementación de Skype empresarial Server 2015.
  
Hay dos escenarios para la actualización local: el método de mover usuarios, que no requiere tiempo de inactividad, y el método sin conexión, que requiere tiempo de inactividad. Para obtener más información sobre qué procedimiento de actualización es el más adecuado para su empresa, consulte [plan to Upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> La opción local no está disponible si actualiza desde Lync Server 2010. Para obtener más información acerca de la actualización desde Lync Server 2010, consulte [plan to Upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Instalación inteligente

La característica de configuración inteligente, que detecta y descarga automáticamente las actualizaciones, ahora forma parte del programa de instalación. Durante el proceso de instalación, se le preguntará al usuario si el proceso de instalación debe comprobar si hay actualizaciones. Para obtener más información, consulte [instalar Skype empresarial Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Proceso mejorado de revisión y actualización de servidores front-end

Skype empresarial Server presenta dos nuevos cmdlets que ayudan a hacer que la actualización o la revisión de los servidores front-end sean mucho más sencillas que en versiones anteriores de Lync Server.
  
Cuando necesite aplicar una revisión o realizar cualquier otro mantenimiento en un servidor front-end, simplemente escriba **Invoke-CsComputerFailOver** y especifique el nombre del servidor. Skype empresarial Server mueve temporalmente la carga de trabajo de ese servidor a los demás servidores del grupo. A continuación, puede realizar el mantenimiento y, a continuación, usar el cmdlet **Invoke-CsComputerFailback** para volver a poner el servidor en servicio. Si necesita aplicar una revisión a cada servidor de un grupo de servidores, siga este procedimiento para cada servidor, uno cada vez. Estos nuevos cmdlets permiten revisar los servidores de forma mucho más rápida que en versiones anteriores y con más confiabilidad y un flujo de trabajo más sencillo.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Funcionalidad de inicio en frío del grupo de servidores front-end mejorada

Skype empresarial Server introduce un nuevo cmdlet que simplifica y mejora el proceso de inicio en frío de un grupo de servidores front-end completo. Cuando usa el nuevo cmdlet **Start-CsPool** , comprueba los requisitos previos de todos los servidores front-end del grupo de servidores y, a continuación, intenta iniciar cada servidor. Si encuentra algún problema, lo diagnostica y le alerta de detalles y soluciones. En algunos casos, le permite iniciar el grupo incluso si algunos de los servidores individuales no se pueden iniciar.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Compatibilidad con SQL Server AlwaysOn para servidores locales

Skype empresarial Server 2015 agrega compatibilidad para los grupos de disponibilidad AlwaysOn de SQL Server y las instancias de clúster de conmutación por error AlwaysOn de SQL Server. Además de estas características, Skype empresarial Server sigue admitiendo la creación de reflejo de la base de datos y la agrupación en clústeres de SQL Server, como en versiones anteriores de Lync Server.
  
Los grupos de disponibilidad AlwaysOn de SQL Server son una solución de alta disponibilidad y recuperación ante desastres en SQL Server 2012 y SQL Server 2014 que proporciona una alternativa a la creación de reflejo de la base de datos. Un grupo de disponibilidad admite un entorno de conmutación por error para un conjunto discreto de bases de datos (conocidas como bases de datos de disponibilidad) que conmutan por error juntos. Un grupo de disponibilidad admite un conjunto de bases de datos principales de lectura y escritura y de uno a cuatro conjuntos de bases de datos secundarias correspondientes. Opcionalmente, las bases de datos secundarias pueden estar disponibles para acceso de solo lectura y para algunas operaciones de copia de seguridad.
  
Las instancias de clúster de conmutación por error de SQL Server aprovechan la funcionalidad de clústeres de conmutación por error de Windows Server (WSFC) para proporcionar alta disponibilidad local mediante redundancia en el nivel de instancia de servidor (una instancia de clúster de conmutación por error (FCI). Un FCI es una instancia única de SQL Server que se instala en los nodos de clústeres de conmutación por error de Windows Server (WSFC) y, posiblemente, en varias subredes.
  
Para obtener más información, vea [Plan for High Availability and Disaster Recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Mejoras de registro y solución de problemas centralizadas para servidores locales

El servicio de registro centralizado es el entorno de registro preferido para Skype empresarial Server 2015. No hay nuevas características en esta versión, pero la confiabilidad y el rendimiento se han mejorado para el servicio y el agente de servicio de registro centralizado (ClsAgent. exe), el servicio ejecutable que se comunica con el controlador y recibe comandos emitidos por el administrador.
  
Skype empresarial Server 2015 usa cmdlets de Windows PowerShell para administrar los agentes del servicio de registro, iniciar el seguimiento y generar informes. (Lync Server 2013 usó ClsController. exe para realizar estas tareas).
  
El servicio de registro centralizado se puede ejecutar en cualquier Skype empresarial Server 2015. Los escenarios integrados (seguimientos predefinidos) siguen siendo los mismos, al igual que la capacidad de crear escenarios personalizados. Hay un escenario especial denominado AlwaysOn que siempre se está ejecutando y permite a los administradores localizar problemas comunes casi en tiempo real.
  
La herramienta de depuración de Snoop también se ha actualizado para permitir la depuración de registros de movilidad y funcionará con los dispositivos que se conectan a Lync 2013 o a Skype empresarial Server 2015. La herramienta está disponible como descarga de la web desde [las herramientas de depuración](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Implementación y administración híbridas

Skype empresarial Server 2015 permite la administración de la implementación híbrida y las capacidades de administración mediante la introducción de las siguientes características:
  
- Recomendaciones para implementaciones híbridas basadas en el estado de los activos locales del cliente, tal y como se determina en la herramienta de asistencia automatizada de la implementación de Office 365.
- Mejoras en el panel de control de Skype empresarial Server y el centro de administración de Skype empresarial Server para que los administradores puedan usar estas herramientas para administrar una implementación híbrida.
- Mejoras del panel de control que permiten a los administradores iniciar sesión en un inquilino de Microsoft 365 o de Office 365 y configurar una implementación híbrida con Skype empresarial online mediante el Asistente para la configuración híbrida.
- Compatibilidad del panel de control para mover los usuarios locales a Skype empresarial online o mover a los usuarios de Skype empresarial online de nuevo a local.
- Características del panel de control para identificar y filtrar los objetos de usuario locales que se han movido a Skype empresarial online (es decir, usuarios híbridos) de los usuarios locales.
- Características del centro de administración para identificar y filtrar los usuarios de la nube creados inicialmente en Skype empresarial online desde usuarios híbridos migrados de local a en línea.
- La capacidad de administrar usuarios híbridos mediante el panel de control para propiedades administrables desde el entorno local y el centro de administración para propiedades que se pueden administrar desde Skype empresarial online.
- Uso de la sincronización de contraseñas con DirSync, la capacidad de sincronizar contraseñas locales de Active Directory con el inquilino en línea. Si se configura, esta característica elimina la necesidad de implementar AD FS para la autenticación federada, pero AD FS todavía es necesario para la autenticación multifactor. 
- Soporte continuo para la coexistencia entre Skype empresarial online y Exchange local.
    
> [!NOTE]
> No hay ningún cambio en la experiencia de soporte técnico y la coexistencia de Lync Online 2013 y Exchange local. 
  
## <a name="multi-factor-authentication"></a>Autenticación multifactor

La autenticación multifactor es un método de autenticación que requiere el uso de más de un método de comprobación y agrega una segunda capa crítica de seguridad a los inicios de sesión y las transacciones de usuario. Por ejemplo, requiere un nombre de usuario y una contraseña y un certificado. Skype empresarial Server 2015 sigue compilando las características de multi-factor Authentication disponibles en las actualizaciones acumulativas de Lync Server 2013. Los cambios significativos en la autenticación multifactor son los siguientes:
  
- Uso de la biblioteca de autenticación de Active Directory de Office 2013 SP1 para la integración con Exchange y SharePoint
- Compatibilidad con la característica de multi-factor Authentication en el cliente de la aplicación Web de Skype empresarial
    
Con la autenticación multifactor de Skype empresarial, ahora es posible proporcionar diferentes opciones de autenticación basadas en la geografía. Por ejemplo, los clientes pueden configurar su entorno para que la autenticación interna se base en la autenticación de Windows integrada, mientras que los empleados que se autentican desde fuera de la organización usan la autenticación multifactor. 
  
La experiencia de la autenticación multifactor de Skype empresarial es perfecta independientemente de:
  
- Ubicación geográfica: ya sea que el usuario inicie sesión desde dentro o fuera de la organización 
- Tipo de cliente o dispositivo: se usa el cliente de Skype empresarial y el dispositivo en el que se ejecuta el cliente (PC, móvil, iPad, etc.).
- Ubicación de la cuenta: Si el usuario está hospedado en un Active Directory local o en Azure Active Directory online.
