---
title: Novedades de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: lea este tema para obtener información sobre las nuevas características de Skype Empresarial Server 2015. Para obtener información detallada sobre la nueva experiencia de cliente, consulte Lync es ahora Skype Empresarial. Vea las novedades.'
ms.openlocfilehash: 09774f722020ef750ae16ad01a29873d43d25e76
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827590"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novedades de Skype Empresarial Server 2015

**Resumen:** Lea este tema para obtener información sobre las nuevas características de Skype Empresarial Server 2015. Para obtener información detallada sobre la nueva experiencia de cliente, consulte Lync es ahora Skype Empresarial, vea [las novedades.](https://go.microsoft.com/fwlink/p/?LinkId=529022)
  
Lync es ahora Skype Empresarial, una plataforma de comunicaciones y colaboración que reúne una experiencia que se inspira en Skype con la seguridad, el cumplimiento y el control empresariales de Lync. Skype Empresarial ofrece características como presencia, mensajería instantánea, llamadas de voz y vídeo y reuniones en línea. Skype Empresarial ofrece una nueva experiencia de cliente, una nueva versión de servidor y actualizaciones del servicio en Microsoft 365 u Office 365. Si los usuarios de su organización ya están familiarizados con Skype, apreciarán la eficacia y simplicidad de Skype Empresarial, donde es fácil encontrar y conectarse con compañeros de trabajo. Si los usuarios de su organización vienen a Skype Empresarial desde Lync, reconocerán todas las características que ya usan, pero en una nueva interfaz nueva con controles simplificados y nuevas adiciones. Además de la nueva experiencia de cliente, Skype Empresarial Server 2015 proporciona varias características nuevas para mejorar la capacidad de administración de los servidores locales y las soluciones híbridas.
  
Las nuevas características de Skype Empresarial Server 2015 incluyen mejoras para:
  
- Experiencia del usuario  
- Compatibilidad con voz y vídeo
- Compatibilidad con dispositivos móviles
- Administración de servidores locales
- Implementación y administración de soluciones híbridas
- Compatibilidad con la autenticación multifactor
    
## <a name="user-experience"></a>Experiencia del usuario

El cliente de Skype Empresarial se parece mucho a la versión de consumidor de Skype y usa los mismos botones e iconos. El menor número de menús y una jerarquía de tareas más plana facilita a los usuarios encontrar rápidamente los controles y comandos que necesitan. 
  
Skype Empresarial incluye la nueva experiencia de usuario descrita anteriormente y la experiencia de usuario de Lync 2013 publicada anteriormente. La inclusión de ambas experiencias permite a las empresas administrar los cambios de sus usuarios mediante el control del proceso y el tiempo de lanzamiento del nuevo cliente. La experiencia de usuario predeterminada depende de la versión del servidor que use. Los administradores eligen la experiencia preferida mediante el cmdlet **Set-CsClientPolicy** con el parámetro EnableSkypeUI. Para obtener más información acerca de cómo configurar la experiencia de cliente, consulte Configurar la experiencia de cliente con la comparación de características de cliente de [Skype](deploy/deploy-clients/configure-the-client-experience.md) Empresarial y escritorio para [Skype Empresarial.](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
  
> [!NOTE]
> La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype Empresarial 2016. Antes de intentar configurar el entorno de cliente para usar el cliente de Lync 2013, compruebe la versión del cliente para asegurarse de que no comienza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Mejoras de voz y vídeo

Skype Empresarial Server 2015 incluye mejoras en la funcionalidad de voz y vídeo, incluida la recopilación y el análisis de datos de llamadas, y una interoperabilidad mejorada con sistemas de teleconferencia de vídeo de terceros.
  
### <a name="call-data-collection-and-analysis"></a>Recopilación y análisis de datos de llamadas

La característica Calificar mi llamada permite a los administradores de Skype Empresarial Server 2015 recopilar datos de llamadas. Esta característica solo está disponible para implementaciones locales. Se pide a los usuarios que tomen una encuesta después de completar una llamada. Para obtener más información, consulte [Calificar mi llamada en Skype Empresarial Server 2015.](manage/health-and-monitoring/rate-my-call.md)
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Interoperabilidad mejorada con sistemas de teleconferencia de vídeo de terceros

El servidor de interoperabilidad de vídeo (VIS) actúa como intermediario entre Skype Empresarial Server y los sistemas de teleconferencia de vídeo (VTC) de Cisco. Al unirse a una reunión, los usuarios ahora pueden seleccionar un sistema Cisco VTC. El servidor de interoperabilidad de vídeo (VIS) se implementa como un rol de servidor independiente para las implementaciones locales. Para obtener más información, consulte [Plan for Video Interop Server in Skype for Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Vía trabajo

La característica Vía trabajo permite a los usuarios empresariales realizar llamadas de voz desde el cliente de Skype Empresarial. Cuando un usuario hace una llamada de voz, se enruta desde Skype Empresarial al teléfono RTC o PBX del autor. Una vez que el autor responde al teléfono, la llamada se dirige al número de destino. El destinatario de la llamada responde y la llamada se establece con Skype Empresarial que sirve como panel de control. El autor puede administrar su presencia y llamar a los controles desde Skype Empresarial. Los administradores del servidor habilitan y configuran Vía trabajo para la empresa. Para obtener más información, vea [Plan for Call Via Work in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Mejoras en la compatibilidad con dispositivos móviles

Las mejoras en la compatibilidad con dispositivos móviles incluyen características para mejorar la experiencia móvil para los usuarios de Enterprise Edition, como el acceso al historial de conversaciones y a los datos de registro, las experiencias de reuniones móviles mejoradas y la compatibilidad con el inicio de sesión único en Office. Además, hay mejoras en la compatibilidad de Android, mejoras de rendimiento y características para simplificar la integración a través de Common App Framework. 
  
> [!NOTE]
> Los servidores de UCWA de Lync 2013 deben actualizarse a Skype Empresarial Server 2015 para admitir clientes móviles. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>El historial de conversaciones del lado servidor ya está disponible en dispositivos móviles

Para habilitar el acceso móvil al historial de conversaciones, la mensajería instantánea perdida y los datos del registro de llamadas, el archivado de esta información se procesa ahora a través del servidor para todos los clientes móviles. La característica De aceptación automática para mensajería instantánea mejora la confiabilidad al impedir mensajes de tiempo de espera del servidor cuando un usuario móvil no responde a una mensajería instantánea inmediatamente. Para aprovechar la integración de carpetas de Exchange/Outlook basadas en servidor, es necesario Exchange Server 2013 o versiones posteriores y clientes móviles actualizados. 
  
### <a name="enhanced-meeting-experiences"></a>Experiencias de reunión mejoradas

La funcionalidad de reunión disponible en el escritorio también está disponible para los usuarios móviles. Entre las nuevas funciones se incluyen:
  
- Navegación asincrónica del contenido compartido de PowerPoint
- Capacidad del moderador para controlar el contenido compartido de PowerPoint
- Administración de la sala de espera para los presentadores, lo que les permite admitir o denegar participantes
    
### <a name="skype-for-business-on-android-improvements"></a>Mejoras de Skype Empresarial en Android

Skype Empresarial en Android ahora ofrece características similares a las disponibles en Skype Empresarial en iOS y Skype Empresarial en Windows:
  
- Continuar o volver a unirse a conversaciones
- Habilitar el certificado y la autenticación pasiva
- Invitar a otros usuarios a una conversación
- Iniciar conversaciones de grupo fácilmente
- Unirse a una reunión sin ser un usuario de Skype Empresarial
- Habilitar la interfaz de usuario de smartphone en tabletas Android
- Administrar reuniones agregando o quitando participantes
    
> [!NOTE]
> Estas características requieren Android OS versión 4.0 o posterior. 
  
## <a name="management-of-on-premises-servers"></a>Administración de servidores locales

Skype Empresarial Server 2015 proporciona varias características nuevas para mejorar la capacidad de administración de los servidores locales, incluida la actualización local, la instalación inteligente, los procesos mejorados de revisión y actualización, la capacidad mejorada de inicio en frío del grupo de servidores front-end, la compatibilidad con SQL Server AlwaysOn y el registro y solución de problemas centralizados.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Actualización local para servidores locales

Ahora puede actualizar los sistemas Lync Server 2013 a Skype Empresarial Server 2015 con la nueva característica de actualización local, que usa las inversiones existentes de servidor y hardware de Lync Server 2013, lo que reduce el costo general para implementar Skype Empresarial Server 2015.
  
Existen dos escenarios para la actualización local: el método Move User, que no requiere tiempo de inactividad, y el método Offline, que requiere tiempo de inactividad. Para obtener más información sobre qué procedimiento de actualización es adecuado para su empresa, consulte [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> La opción local no está disponible si va a actualizar desde Lync Server 2010. Para obtener más información acerca de la actualización desde Lync Server 2010, consulte [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Configuración inteligente

La característica Configuración inteligente, que detecta y descarga actualizaciones automáticamente, ahora forma parte del programa de instalación. Durante el proceso de instalación, se pregunta al usuario si el proceso de instalación debe buscar actualizaciones. Para obtener más información, vea [Instalar Skype Empresarial Server 2015.](deploy/install/install.md)
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Proceso mejorado de revisión y actualización del servidor front-end

Skype Empresarial Server presenta dos nuevos cmdlets que ayudan a que la actualización o revisión de servidores front-end sea mucho más fácil que en versiones anteriores de Lync Server.
  
Cuando necesite aplicar una revisión o realizar cualquier otro mantenimiento a un servidor front-end, simplemente escriba **Invoke-CsComputerFailOver** y especifique el nombre del servidor. Skype Empresarial Server mueve la carga de trabajo de ese servidor temporalmente a los demás servidores del grupo. A continuación, puede realizar el mantenimiento y, a continuación, usar el cmdlet **Invoke-CsComputerFailback** para volver a poner ese servidor en servicio. Si necesita aplicar revisiones a cada servidor de un grupo de servidores, simplemente siga este procedimiento para cada servidor, de uno en uno. Estos nuevos cmdlets permiten aplicar revisiones a los servidores mucho más rápidos que en versiones anteriores y con mayor confiabilidad y un flujo de trabajo más sencillo.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Capacidad mejorada de inicio en frío del grupo de servidores front-end

Skype Empresarial Server presenta un nuevo cmdlet que simplifica y mejora el proceso de iniciar en frío un grupo de servidores front-end completo. Cuando se usa el nuevo cmdlet **Start-CsPool,** se comprueban los requisitos previos para todos los servidores front-end del grupo y, a continuación, se intenta iniciar cada servidor. Si encuentra algún problema, los diagnostica y le avisa con detalles y soluciones alternativas. En algunos casos, permite iniciar el grupo aunque algunos de los servidores individuales no puedan iniciarse.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL Server compatibilidad de AlwaysOn con servidores locales

Skype Empresarial Server 2015 agrega compatibilidad tanto para grupos de disponibilidad AlwaysOn SQL Server como para SQL Server clúster de conmutación por error AlwaysOn. Además de estas características, Skype Empresarial Server continúa siendo compatible con la creación de reflejo de la base de datos y SQL Server clústeres, como en versiones anteriores de Lync Server.
  
SQL Server Grupos de disponibilidad AlwaysOn es una solución de alta disponibilidad y recuperación ante desastres de SQL Server 2012 y SQL Server 2014 que proporciona una alternativa a la creación de reflejo de la base de datos. Un grupo de disponibilidad admite un entorno de conmutación por error para un conjunto discreto de bases de datos (conocidas como bases de datos de disponibilidad) que conmutan por error conjuntamente. Un grupo de disponibilidad admite un conjunto de bases de datos principales de lectura y escritura y de uno a cuatro conjuntos de bases de datos secundarias correspondientes. Opcionalmente, las bases de datos secundarias pueden estar disponibles para el acceso de solo lectura y para algunas operaciones de copia de seguridad.
  
SQL Server instancias de clúster de conmutación por error aprovechan la funcionalidad de clústeres de conmutación por error de Windows Server (WSFC) para proporcionar alta disponibilidad local a través de redundancia en el nivel de instancia de servidor: una instancia de clúster de conmutación por error (FCI). Una FCI es una única instancia de SQL Server que se instala en los nodos de clústeres de conmutación por error de Windows Server (WSFC) y, posiblemente, en varias subredes.
  
Para obtener más información, consulte [Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Mejoras de registro centralizado y solución de problemas para servidores locales

El servicio de registro centralizado es el entorno de registro preferido para Skype Empresarial Server 2015. No hay nuevas características en esta versión, pero se ha mejorado la confiabilidad y el rendimiento tanto para el servicio como para el agente de servicio de registro centralizado (ClsAgent.exe): el archivo ejecutable del servicio que se comunica con el controlador y recibe los comandos emitidos por el administrador.
  
Skype Empresarial Server 2015 usa cmdlets Windows PowerShell para administrar los agentes de servicio de registro, iniciar el seguimiento y generar informes. (Lync Server 2013 usó ClsController.exe para realizar estas tareas).
  
El servicio de registro centralizado se puede ejecutar en cualquier Skype Empresarial Server 2015. Los escenarios integrados (seguimientos predefinidos) siguen siendo los mismos, al igual que la capacidad de crear escenarios personalizados. Hay un escenario especial denominado AlwaysOn que siempre se está ejecutando y permite a los administradores localizar problemas comunes casi en tiempo real.
  
La herramienta de depuración Snooper también se ha actualizado para permitir la depuración de registros de movilidad y funcionará con dispositivos que se conecten a Lync 2013 o Skype Empresarial Server 2015. La herramienta está disponible como descarga web desde [las herramientas de depuración.](https://go.microsoft.com/fwlink/?LinkId=285257)
  
## <a name="hybrid-deployment-and-management"></a>Implementación y administración híbridas

Skype Empresarial Server 2015 habilita las funciones de administración y administración de implementaciones híbridas mediante la introducción de las siguientes características:
  
- Recomendaciones para implementaciones híbridas basadas en el estado de los activos locales del cliente, según lo determinado por la herramienta de asistencia automatizada OnRamp para Office 365.
- Mejoras en el Panel de control de Skype Empresarial Server y en el Centro de administración de Skype Empresarial Server para que los administradores puedan usar estas herramientas para administrar una implementación híbrida.
- Mejoras del Panel de control que permiten a los administradores iniciar sesión en un inquilino de Microsoft 365 u Office 365 y configurar la implementación híbrida con Skype Empresarial Online mediante el asistente de configuración híbrida.
- Compatibilidad con el Panel de control para mover usuarios locales a Skype Empresarial Online o mover usuarios de Skype Empresarial Online de nuevo a local.
- Características del Panel de control para identificar y filtrar objetos de usuario locales que se han movido a Skype Empresarial Online (es decir, usuarios híbridos) de usuarios locales.
- Características del Centro de administración para identificar y filtrar los usuarios en la nube creados inicialmente en Skype Empresarial Online a partir de usuarios híbridos migrados de local a online.
- La capacidad de administrar usuarios híbridos mediante el Panel de control para las propiedades que se pueden administrar desde local y el Centro de administración para las propiedades que se pueden administrar desde Skype Empresarial Online.
- Mediante la sincronización de contraseñas con DirSync, la capacidad de sincronizar contraseñas locales de Active Directory con el inquilino en línea. Si se configura, esta característica elimina la necesidad de implementar AD FS para la autenticación federada, pero AD FS sigue siendo necesario para la autenticación multifactor. 
- Soporte continuo para la coexistencia entre Skype Empresarial Online y Exchange local.
    
> [!NOTE]
> No hay ningún cambio en la experiencia de coexistencia y soporte de Lync Online 2013 y Exchange local. 
  
## <a name="multi-factor-authentication"></a>Autenticación multifactor

La autenticación multifactor es un método de autenticación que requiere el uso de más de un método de comprobación y agrega un segundo nivel crítico de seguridad a las transacciones y los inicios de sesión de los usuarios. Por ejemplo, requerir un nombre de usuario y una contraseña, y un certificado. Skype Empresarial Server 2015 continúa con las características de autenticación multifactor disponibles en las actualizaciones acumulativas de Lync Server 2013. Los cambios significativos en la autenticación multifactor son:
  
- Uso de la biblioteca de autenticación de Active Directory de Office 2013 SP1 para la integración con Exchange y SharePoint
- Compatibilidad con la característica de autenticación multifactor en el cliente de Skype Empresarial Web App
    
Con la autenticación multifactor de Skype Empresarial, ahora es posible proporcionar diferentes opciones de autenticación basadas en la zona geográfica. Por ejemplo, los clientes pueden configurar su entorno para que la autenticación interna se base en la autenticación integrada de Windows, mientras que los empleados que se autentican desde fuera de la organización usan la autenticación multifactor. 
  
La experiencia de autenticación multifactor de Skype Empresarial es perfecta, independientemente de lo siguiente:
  
- Ubicación geográfica: indica si el usuario inicia sesión desde dentro o fuera de la organización. 
- Tipo de cliente/dispositivo: qué cliente de Skype Empresarial se usa y en qué dispositivo se ejecuta el cliente (PC, móvil, iPad, etc.).
- Ubicación de la cuenta: indica si el usuario está hospedado en un Active Directory local o en Azure Active Directory Online.
