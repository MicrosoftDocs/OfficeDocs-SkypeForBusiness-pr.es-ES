---
title: Información general sobre características (herramienta de planeación)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Herramienta de planeación de Skype Empresarial Server
ms.openlocfilehash: 4084d263a693a064e06a814d2fab4542ca3142c0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093328"
---
# <a name="feature-overview-planning-tool"></a>Información general sobre características (herramienta de planeación)
 
Herramienta de planeación de Skype Empresarial Server
  
Puede usar la página **Sitios centrales** de la Herramienta de planeación para diseñar la implementación de Skype Empresarial Server. Puede crear dos implementaciones centralizadas o distribuidas. Una implementación centralizada solo tiene un sitio central, que alberga a todos los usuarios de Skype Empresarial de su organización. Una implementación distribuida tiene más de un sitio central. Si implementa Skype Empresarial Server en varios sitios centrales, escriba el número de usuarios en cada sitio central en la Herramienta de planeación.
  
Para completar la definición del sitio central, primero debe proporcionar la siguiente información:
  
- **Nombre del sitio** Escriba el nombre del sitio central.
    
- **Número de usuarios** Escriba el número de usuarios, incluidos los usuarios de los sitios de sucursal que se encuentran en el sitio central.
    
- **Usuarios en la nube** Escriba el número de usuarios que se encuentran en el sitio central desde Skype Empresarial Online.
    
## <a name="ui-elements"></a>Elementos de la interfaz de usuario

Los elementos restantes se han rellenado con las respuestas proporcionadas a las preguntas presentadas en el Asistente para introducción o, si omitió el asistente, rellenadas automáticamente por la herramienta de planeación. 
  
### <a name="online-collaboration"></a>Colaboración en línea

 **Colaboración en** línea contiene las siguientes opciones:
  
- **Mensajería instantánea y presencia**
    
    La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real en sus equipos mediante mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. La presencia proporciona información a los usuarios sobre el estado de otros usuarios en la red. El estado de presencia de un usuario proporciona información para ayudar a otros usuarios a determinar si el usuario está en línea y cómo ponerse en contacto mejor con el usuario. Por ejemplo, un usuario que está en una reunión se contacta mejor por correo electrónico.
    
- **Conferencia de audio y vídeo**
    
    Las conferencias de audio y vídeo (A/V) permiten conferencias de audio y vídeo en tiempo real.
    
- **Conferencias de acceso telefónico local**
    
    Las conferencias de acceso telefónico local permiten a los usuarios unirse a una A/V desde un teléfono en la RTC. Las conferencias de acceso telefónico local requieren que implemente las aplicaciones de servicio de anuncio de conferencia y operador de conferencia.
    
- **Conexión web**
    
    Las conferencias web permiten a los usuarios empresariales dentro y fuera del firewall crear y unirse a conferencias en tiempo real hospedadas en los servidores internos.
    
- **Chat persistente**
    
    El chat persistente permite a varios usuarios participar en conversaciones en las que publican y acceden al contenido sobre temas específicos, incluidos texto, vínculos y archivos. Aunque todos los usuarios se pueden comunicar en tiempo real durante una sesión, el contenido de cada sesión puede ser persistente, lo que significa que sigue disponible después de que finalice una sesión.

    > [!NOTE] 
    > El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, [vea Skype Empresarial to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015.
    
### <a name="users"></a>Usuarios

 **Los** usuarios contienen las siguientes opciones:
  
- **Organización interna**
    
- **Federación con otras organizaciones**
    
- **Federación con versiones anteriores**
    
- **Federación con proveedores de servicios de mensajería instantánea públicos** Permite a los usuarios de la organización establecer comunicación con proveedores de servicios públicos de mensajería instantánea como MSN, Yahoo!, y AOL. Se requiere una licencia independiente para establecer la federación con redes públicas de mensajería instantánea.
    
- **Federación con proveedor de servicios basado en XMPP**
    
    Skype Empresarial Server 2015 introdujo un proxy XMPP totalmente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP implementada en los servidores front-end. Puede implementar Agregar y configurar el proxy XMPP y la puerta de enlace XMPP permitirá a los usuarios de Skype Empresarial Server agregar contactos de socios basados en XMPP para mensajería instantánea (MI) y presencia.
    
- **Movilidad**
    
    Al implementar el Servicio de movilidad de Skype Empresarial Server, los usuarios pueden usar dispositivos móviles apple iOS, Android, Windows Phone o Nokia compatibles para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver presencia.
    
- **Buzón de Exchange W15**
    
    Skype Empresarial Server permite tener mensajes de correo de voz almacenados en mensajería unificada de Exchange (UM); esos mensajes de correo de voz aparecerán como mensajes de correo electrónico en las bandejas de entrada de los usuarios.

    > [!NOTE]
    > La mensajería unificada de Exchange como se conocía anteriormente ya no está disponible en Exchange 2019, pero aún puede usar sistema telefónico para grabar mensajes de correo de voz y, a continuación, dejar la grabación en el buzón de Exchange de un usuario. Consulte [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obtener más información.
    
### <a name="voice"></a>Voz

 **La** voz contiene las siguientes opciones:
  
- **Telefonía IP empresarial**
    
    Enterprise voice es la solución VoIP con software de Microsft. Enterprise voice permite a los usuarios usar Skype Empresarial para realizar una llamada telefónica desde su equipo.
    
- **Mensajería unificada de Exchange**
    
    La mensajería unificada (UM) de Exchange combina el correo de voz y el correo electrónico en una única infraestructura de mensajería. Skype Empresarial Server 2015 usa mensajería unificada de Exchange para proporcionar servicios de contestación de llamadas, acceso de suscriptor, notificación de llamadas y operador automático. Si usa estos servicios, deberá integrar la mensajería unificada de Exchange y Skype Empresarial Server en una topología compartida de Active Directory.

    > [!NOTE]
    > La mensajería unificada de Exchange como se conocía anteriormente ya no está disponible en Exchange 2019, pero aún puede usar sistema telefónico para grabar mensajes de correo de voz y, a continuación, dejar la grabación en el buzón de Exchange de un usuario. Consulte [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obtener más información.
    
### <a name="additional-deployment-options"></a>Opciones de implementación adicionales

 **Las opciones de implementación adicionales** contienen las siguientes opciones:
  
- **Alta disponibilidad**
    
    La alta disponibilidad habilita los servidores en espera para la compatibilidad con conmutación por error.
    
- **Recuperación ante desastres**
    
    Las medidas de recuperación ante desastres permiten emparejar grupos de servidores front-end ubicados en dos centros de datos.
    
- **Supervisión**
    
    La supervisión captura registros de detalles de llamadas relacionados con sesiones de comunicación. También recopila métricas de sesiones de audio y vídeo en los puntos de conexión de los participantes. El servidor de supervisión proporciona estadísticas de uso, tendencias y estadísticas de calidad de medios.
    
- **Archivado**
    
    El archivado almacena conversaciones y conferencias de mensajería instantánea.
    
- **Integración de archivado de Exchange**
    
    Si tiene usuarios que se encuentran en Exchange y sus buzones se han puesto en retención In-Place, puede seleccionar la opción para integrar el almacenamiento de Skype Empresarial Server con el almacenamiento de Exchange.
    
- **IPv4**
    
    Las direcciones IPv4 son direcciones de 32 bits que permiten a los equipos comunicarse a través de Internet. Debido al número creciente de dispositivos en todo el mundo, las direcciones IPv4 disponibles se han quedo sin funcionar. Debido a esto, muchos dispositivos nuevos se están moviendo al uso de direcciones IPv6.
    
- **IPv6**
    
    Las direcciones IPv6 realizan la misma función que las direcciones IPv4 (con algunas funciones adicionales), pero en lugar de usar solo 32 bits, usan 128 bits. Esto no solo proporciona un nuevo conjunto de direcciones, sino también un número mucho más elevado de ellas.
    
- **Servicio web de actualización de dispositivos**
    
    El servicio web device update proporciona una forma automatizada de actualizar todos los dispositivos, como Skype Empresarial para Windows Phone, que se implementan fuera de la organización.
    
### <a name="server-applications"></a>Aplicaciones de servidor

 **Aplicaciones de** servidor contiene las siguientes opciones:
  
- **Grupo de respuesta**
    
    La aplicación Grupo de respuesta responde automáticamente y distribuye llamadas a un agente de soporte técnico disponible.
    
- **Anuncio**
    
    Si planea implementar Telefonía IP empresarial, es posible que desee configurar cómo se administran las llamadas telefónicas si el número marcado es válido pero no está asignado a un área común del usuario. Los administradores pueden configurar el servicio de anuncios para que estas llamadas se transfieran a un destino predeterminado (número de teléfono o URI de SIP) o reproducir un anuncio de audio o ambos. El uso del servicio de anuncios evita la situación en la que un autor de la llamada desaconseje y oye un tono ocupado o el cliente SIP recibe un mensaje de error. La funcionalidad del servicio de anuncios es una característica típica de PBX. 
    
- **Estacionamiento de llamada**
    
    La aplicación estacionamiento de llamadas permite a un usuario de Telefonía IP empresarial poner una llamada en espera desde un teléfono y, a continuación, recibir la llamada de otro teléfono sin apare los recursos del teléfono que recibió la llamada. La aplicación de estacionamiento de llamadas es útil cuando un usuario necesita transferir una llamada, pero el destinatario específico es desconocido. 
    
- **Operador de conferencia**
    
    La aplicación operador de conferencia proporciona capacidades de audioconferencia a los usuarios de teléfono sin el servicio de un proveedor de audioconferencia de terceros.
    
- **Anuncio de conferencia**
    
    La aplicación de anuncio de conferencia produce tonos que señalen cuando los usuarios entran o salen de una conferencia, así como notificaciones a los usuarios de teléfono cuando se silencian o no se conmutan.
    
- **Control de admisión de llamadas**
    
    El control de admisión de llamadas (CAC), también conocido como administración de ancho de banda WAN, ayuda a evitar la mala calidad de la experiencia de los usuarios en redes congestionadas al determinar, en función del ancho de banda disponible, si se permiten y se establecen nuevas sesiones de comunicaciones en tiempo real. 
    
    > [!NOTE]
    > El CAC solo controla el tráfico en tiempo real y no afecta al tráfico de datos. 
  
    Si una nueva sesión de voz o vídeo supera los límites de ancho de banda que ha asignado en una WAN, la sesión se bloquea o (solo para llamadas telefónicas) se redirige a la RTC.
