---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Herramienta de planeación de Skype empresarial Server
ms.openlocfilehash: b43c2ffef0c2e85413cda1720ea62527fece1556
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288257"
---
# <a name="feature-overview-planning-tool"></a>Feature Overview (Planning Tool)
 
Herramienta de planeación de Skype empresarial Server
  
Puede usar la página **sitios centrales** de la herramienta de planeación para diseñar la implementación de Skype empresarial Server. Puede crear una implementación distribuida o centralizada. Una implementación centralizada solo tiene un sitio central, que aloja todos los usuarios de Skype empresarial de su organización. Una implementación distribuida tiene más de un sitio central. Si implementa Skype empresarial Server en varios sitios centrales, tendrá que introducir el número de usuarios en cada sitio central en la herramienta de planificación.
  
Para completar la definición del sitio central, primero debe proporcionar la siguiente información:
  
- **Nombre del sitio** Escriba el nombre del sitio central.
    
- **Número de usuarios** Escriba el número de usuarios, incluidos los usuarios de sitios de sucursal alojados en el sitio central.
    
- **Usuarios domésticos en la nube** Escriba el número de usuarios que están alojados en el sitio central desde Skype empresarial online.
    
## <a name="ui-elements"></a>Elementos de la interfaz de usuario

Los elementos restantes se rellenaron con las respuestas proporcionadas a las preguntas presentadas en el Asistente para **introducción** o, si omitió el asistente, se rellenaron automáticamente con la herramienta de planeación.
  
### <a name="online-collaboration"></a>Colaboración en línea

 **Colaboración en línea** contiene las siguientes opciones:
  
- **Mensajería instantánea (MI) y presencia**
    
    La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos mediante mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. La presencia proporciona información a los usuarios acerca del estado de los otros usuarios en la red. El estado de presencia de un usuario proporciona información para ayudar a otros usuarios a determinar si el usuario está conectado y cómo debe comunicarse mejor con el usuario. Por ejemplo, la mejor forma de ponerse en contacto con un usuario que se encuentra en una reunión es mediante correo electrónico.
    
- **Conferencias de audio y vídeo**
    
    La característica de conferencia de audio y vídeo permite realizar este tipo de conferencias en tiempo real.
    
- **Conferencias de acceso telefónico local**
    
    La conferencia de acceso telefónico local permite a los usuarios unirse a una conferencia de audio y vídeo desde un teléfono en la RTC. La conferencia de acceso telefónico local requiere la implementación de las aplicaciones Operador de conferencia y Servicio de anuncio de conferencia.
    
- **Conferencia web**
    
    La conferencia web permite a los usuarios de empresa dentro y fuera del firewall crear y unirse a conferencias en tiempo real hospedadas en los servidores internos.
    
- **Chat persistente**
    
    El chat persistente permite que varios usuarios participen en conversaciones en las que publican y obtienen acceso a contenido de temas específicos, incluidos texto, vínculos y archivos. Aunque los usuarios se pueden comunicar en tiempo real durante una sesión, el contenido de cada sesión es persistente, lo que significa que sigue disponible después de que finaliza la sesión.

    > [!NOTE] 
    > Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [actualización de Skype empresarial a Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams). Si necesita usar una conversación persistente, su elección es migrar los usuarios que necesitan esta funcionalidad a teams o seguir usando Skype empresarial Server 2015.
    
### <a name="users"></a>Usuarios

 **Usuarios** contiene las siguientes opciones:
  
- **Organización interna**
    
- **Federación con otras organizaciones**
    
- **Federación con versiones anteriores**
    
- **Federación con proveedores de servicios de mensajería instantánea pública**. Permite a los usuarios de la organización establecer una comunicación con proveedores de servicios de mensajería instantánea pública, como MSN, Yahoo! y AOL. Se requiere una licencia independiente para establecer la federación con redes de mensajería instantánea pública.
    
- **Federación con proveedores de servicios basados en XMPP**
    
    Skype empresarial Server 2015 presentó un proxy XMPP completamente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP implementada en los servidores front-end. Puede desplegar agregar y configurar el proxy XMPP y la puerta de enlace XMPP permite que los usuarios de Skype empresarial Server agreguen contactos de socios basados en XMPP para mensajería instantánea (mi) y presencia.
    
- **Movilidad**
    
    Al implementar el servicio de movilidad de Skype empresarial Server, los usuarios pueden usar dispositivos móviles compatibles con Apple iOS, Android, Windows Phone o Nokia para realizar estas actividades, como enviar y recibir mensajes instantáneos, ver contactos y ver presencia.
    
- **Buzón de correo de W15 Exchange**
    
    Skype empresarial Server le permite almacenar mensajes de voz en mensajería unificada de Exchange (UM); esos mensajes de voz aparecerán como mensajes de correo electrónico en las bandejas de los usuarios.

    > [!NOTE]
    > La mensajería unificada de Exchange, tal como se conocía anteriormente, ya no está disponible en Exchange 2019, pero puede usar el sistema telefónico para grabar mensajes de voz y, a continuación, dejar la grabación en el buzón de Exchange de un usuario. Consulte [planear el servicio de buzón de voz en la nube](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obtener más información.
    
### <a name="voice"></a>Voz

 **Voz** contiene las siguientes opciones:
  
- **Telefonía IP empresarial**
    
    Telefonía IP empresarial es una solución de VoIP con software de la tecnología de voz. La telefonía IP empresarial permite a los usuarios usar Skype empresarial para realizar una llamada telefónica desde su equipo.
    
- **Mensajería unificada de Exchange**
    
    La mensajería unificada de Exchange combina el correo de voz y el correo electrónico en una sola infraestructura de mensajería. Skype empresarial Server 2015 usa la mensajería unificada de Exchange para proporcionar respuesta de llamadas, acceso de suscriptores, notificación de llamadas y servicios de operador automático. Si usa estos servicios, tendrá que integrar la mensajería unificada de Exchange y Skype empresarial Server en una topología de Active Directory compartida.

    > [!NOTE]
    > La mensajería unificada de Exchange, tal como se conocía anteriormente, ya no está disponible en Exchange 2019, pero puede usar el sistema telefónico para grabar mensajes de voz y, a continuación, dejar la grabación en el buzón de Exchange de un usuario. Consulte [planear el servicio de buzón de voz en la nube](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obtener más información.
    
### <a name="additional-deployment-options"></a>Opciones de implementación adicionales

 **Opciones de implementación adicionales** contiene las siguientes opciones:
  
- **Alta disponibilidad**
    
    La alta disponibilidad habilita la compatibilidad de los servidores en espera con la conmutación por error.
    
- **Recuperación ante desastres**
    
    Las medidas de recuperación ante desastres le permiten emparejar grupos de aplicaciones para el usuario que se encuentran en dos centros de recursos.
    
- **Supervisión**
    
    La supervisión captura registros de detalles de llamadas relacionados con las sesiones de comunicación. También recopila métricas de sesiones de audio y vídeo en los puntos de conexión de los participantes. El servidor de supervisión proporciona estadísticas de uso, tendencias y estadísticas de calidad de medios.
    
- **Archivado**
    
    El archivado almacena conferencias y conversaciones de mensajería instantánea.
    
- **Integración de archivado de Exchange**
    
    Si tiene usuarios alojados en Exchange y sus buzones se han colocado en conservación local, puede seleccionar la opción para integrar el almacenamiento de información de Skype empresarial Server con el almacenamiento de Exchange.
    
- **IPv4**
    
    Las direcciones IPv4 son direcciones de 32 bits que permiten a los equipos comunicarse a través de Internet. Debido al cada vez mayor número de dispositivos en todo el mundo, las direcciones IPv4 disponibles se han agotado. Por ello, muchos dispositivos nuevos están pasando a usar direcciones IPv6.
    
- **IPv6**
    
    Las direcciones IPv6 cumplen la misma función que las direcciones IPv4 (con algunas características adicionales), pero en lugar de usar solo 32 bits, usan 128 bits. Esto no solo proporciona un nuevo conjunto de direcciones, sino también un número mucho más elevado de ellas.
    
- **Servicio web de actualización de dispositivos**
    
    El servicio Web de actualización de dispositivos proporciona una forma automatizada de actualizar todos los dispositivos, como Skype empresarial para Windows Phone, que se han implementado fuera de su organización.
    
### <a name="server-applications"></a>Aplicaciones de servidor

 **Aplicaciones de servidor** contiene las siguientes opciones:
  
- **Grupo de respuesta**
    
    La aplicación de grupo de respuesta responde automáticamente y distribuye las llamadas a un agente del servicio de asistencia al usuario.
    
- **Anuncio**
    
    Si planea implementar la telefonía IP empresarial, es posible que desee poder configurar las llamadas de teléfono si el número marcado es válido pero no se asigna a un área común de usuario. Los administradores pueden configurar el servicio de anuncio para que estas llamadas se transfieran a un destino predeterminado (número de teléfono o URI de SIP) o para que se reproduzca un anuncio de audio, o bien para que se lleven a cabo ambas acciones. Con el servicio de anuncio, se evita la situación en la que el autor de una llamada marca el número de forma incorrecta y escucha un tono de línea ocupada o el cliente SIP recibe un mensaje de error. La funcionalidad del servicio de anuncio es una característica típica de PBX. 
    
- **Estacionamiento de llamadas**
    
    La aplicación de estacionamiento de llamadas permite a un usuario de telefonía empresarial poner una llamada en espera desde un teléfono y, a continuación, recibir la llamada de otro teléfono sin ocupar recursos en el teléfono que ha recibido la llamada. La aplicación de estacionamiento de llamadas es útil cuando un usuario necesita transferir una llamada, pero no se conoce el destinatario específico. 
    
- **Operador de conferencia**
    
    La aplicación operador de conferencias proporciona capacidades de audioconferencia a usuarios de telefonía sin el servicio de un proveedor de servicios de audioconferencia de terceros.
    
- **Anuncio de conferencia**
    
    La aplicación anuncio de conferencia produce tonos que indican cuándo los usuarios entran o salen de una conferencia, así como las notificaciones a los usuarios de telefonía cuando se silencian o se desactivan.
    
- **Control de admisión de llamadas**
    
    El servicio de control de admisión de llamadas, también llamado administración de ancho de banda de la WAN, ayuda a evitar que los usuarios experimenten una calidad deficiente en las redes congestionadas, ya que determina si se permitirá que se establezcan nuevas sesiones de comunicación en tiempo real según el ancho de banda disponible. 
    
    > [!NOTE]
    > El servicio de control de admisión de llamadas solo controla el tráfico en tiempo real y no afecta al tráfico de datos. 
  
    Si una sesión de vídeo o voz nueva supera los límites de ancho de banda que se han asignado en una WAN, la sesión se bloquea o (solo para llamadas telefónicas) se desvía a la RTC.
    

