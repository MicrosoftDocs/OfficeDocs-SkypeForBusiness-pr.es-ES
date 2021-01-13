---
title: Información general sobre características (Herramienta de planeación)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Herramienta de planeación de Skype Empresarial Server 2015
ms.openlocfilehash: 3aa259314d8a92142cf37dcd3611773490248e02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834790"
---
# <a name="feature-overview-planning-tool"></a>Información general sobre características (Herramienta de planeación)
 
Herramienta de planeación de Skype Empresarial Server 2015
  
Puede usar la página **Sitios centrales** de la Herramienta de planeación para diseñar la implementación de Skype Empresarial Server. Puede crear dos implementaciones centralizadas o distribuidas. Una implementación centralizada solo tiene un sitio central, que alberga a todos los usuarios de Skype Empresarial de su organización. Una implementación distribuida tiene más de un sitio central. Si implementa Skype Empresarial Server en varios sitios centrales, introducirá el número de usuarios en cada sitio central en la Herramienta de planeación.
  
Para completar la definición del sitio central, primero debe proporcionar la siguiente información:
  
- **Nombre del sitio** Escriba el nombre del sitio central.
    
- **Número de usuarios** Escriba el número de usuarios, incluidos los usuarios de los sitios de sucursal que están en el sitio central.
    
- **Usuarios en la nube** Escriba el número de usuarios que se encuentran en el sitio central desde Skype Empresarial Online.
    
> [!NOTE]
> Esta herramienta no se actualizará para Skype Empresarial Server 2019.

## <a name="ui-elements"></a>Elementos de la interfaz de usuario

Los elementos restantes se han rellenado con las respuestas que proporcionó a las preguntas presentadas en el Asistente para introducción o, si omitió el asistente, rellenados automáticamente por la herramienta de planeación. 
  
### <a name="online-collaboration"></a>Colaboración en línea

 **La colaboración en** línea contiene las siguientes opciones:
  
- **Mensajería instantánea y presencia**
    
    La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real en sus equipos mediante mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. La presencia proporciona información a los usuarios sobre el estado de otros usuarios en la red. El estado de presencia de un usuario proporciona información para ayudar a otros usuarios a determinar si el usuario está en línea y cómo ponerse en contacto mejor con él. Por ejemplo, es mejor ponerse en contacto por correo electrónico con un usuario que se encuentra en una reunión.
    
- **Conferencia de audio y vídeo**
    
    Las conferencias de audio y vídeo (A/V) permiten conferencias de audio y vídeo en tiempo real.
    
- **Conferencias de acceso telefónico local**
    
    Las conferencias de acceso telefónico local permiten a los usuarios unirse a una A/V desde un teléfono en la RTC. Las conferencias de acceso telefónico local requieren que implemente las aplicaciones operador de conferencia y servicio de anuncio de conferencia.
    
- **Conexión web**
    
    Las conferencias web permiten a los usuarios empresariales dentro y fuera del firewall crear y unirse a conferencias en tiempo real hospedadas en los servidores internos.
    
- **Chat persistente**
    
    El chat persistente permite a varios usuarios participar en conversaciones en las que publican y acceden a contenido sobre temas específicos, como texto, vínculos y archivos. Aunque todos los usuarios se pueden comunicar en tiempo real durante una sesión, el contenido de cada sesión puede ser persistente, lo que significa que sigue disponible después de que finalice una sesión.
    
### <a name="users"></a>Usuarios

 **Los usuarios** contienen las siguientes opciones:
  
- **Organización interna**
    
- **Federación con otras organizaciones**
    
- **Federación con versiones anteriores**
    
- **Federación con proveedores de servicios de mensajería instantánea pública** Permite a los usuarios de su organización establecer comunicación con proveedores de servicios de mensajería instantánea públicos, como MSN, Yahoo!, y AOL. Se requiere una licencia independiente para establecer la federación con redes públicas de mensajería instantánea.
    
- **Federación con proveedor de servicios basado en XMPP**
    
    Skype Empresarial Server 2015 presenta un proxy XMPP totalmente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP implementada en los servidores front-end. You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server 2015 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.

> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019. Consulte [Migración de la federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información.
    
- **Movilidad**
    
    Al implementar el servicio de movilidad de Skype Empresarial Server 2015, los usuarios pueden usar dispositivos móviles Apple iOS, Android, Windows Phone o Nokia compatibles para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver la presencia.
    
- **Buzón de Exchange W15**
    
    Skype Empresarial Server 2015 le permite tener mensajes de correo de voz almacenados en mensajería unificada de Exchange; esos mensajes de correo de voz aparecerán como mensajes de correo electrónico en las bandejas de entrada de los usuarios.
    
### <a name="voice"></a>Voz

 **La voz** contiene las siguientes opciones:
  
- **Telefonía IP empresarial**
    
    Enterprise Voice es la solución VoIP de software de Microsft. La telefonía IP empresarial permite a los usuarios usar Skype Empresarial para realizar una llamada de teléfono desde su equipo.
    
- **Mensajería unificada de Exchange**
    
    La mensajería unificada de Exchange combina el correo de voz y el correo electrónico en una única infraestructura de mensajería. Skype Empresarial Server 2015 usa la mensajería unificada de Exchange para proporcionar servicios de respuesta a llamadas, acceso de suscriptor, notificación de llamadas y operador automático. Si usa estos servicios, deberá integrar la mensajería unificada de Exchange y Skype Empresarial Server en una topología compartida de Active Directory.
    
### <a name="additional-deployment-options"></a>Opciones de implementación adicionales

 **Las opciones de implementación adicionales** contienen las siguientes opciones:
  
- **Alta disponibilidad**
    
    La alta disponibilidad permite que los servidores en espera admitan la conmutación por error.
    
- **Recuperación ante desastres**
    
    Las medidas de recuperación ante desastres permiten emparejar grupos de servidores front-end ubicados en dos centros de datos.
    
- **Supervisión**
    
    La supervisión captura registros de detalles de llamadas relacionados con las sesiones de comunicación. También recopila métricas de sesiones de audio y vídeo en los puntos de conexión de los participantes. El servidor de supervisión proporciona estadísticas de uso, tendencias y estadísticas de calidad de medios.
    
- **Archivado**
    
    El archivado almacena conversaciones y conferencias de mensajería instantánea.
    
- **Integración de archivado de Exchange**
    
    Si tiene usuarios que están en Exchange 2013 y sus buzones se han puesto en retención In-Place, puede seleccionar la opción para integrar el almacenamiento de Skype Empresarial Server 2015 con el almacenamiento de Exchange.
    
- **IPv4**
    
    Las direcciones IPv4 son direcciones de 32 bits que permiten a los equipos comunicarse a través de Internet. Debido al creciente número de dispositivos en todo el mundo, se han ejecutado las direcciones IPv4 disponibles. Debido a esto, muchos dispositivos nuevos se están moviendo al uso de direcciones IPv6.
    
- **IPv6**
    
    Las direcciones IPv6 realizan la misma función que las direcciones IPv4 (con algunas funciones adicionales), pero en lugar de usar solo 32 bits, usan 128 bits. Esto no solo proporciona un nuevo conjunto de direcciones, sino también un número mucho más elevado de ellas.
    
- **Servicio web de actualización de dispositivos**
    
    El servicio web de actualización de dispositivos proporciona una forma automatizada de actualizar todos los dispositivos, como Skype Empresarial para Windows Phone, que se implementan fuera de su organización.
    
### <a name="server-applications"></a>Aplicaciones de servidor

 **Las aplicaciones de** servidor contienen las siguientes opciones:
  
- **Grupo de respuesta**
    
    La aplicación Grupo de respuesta responde y distribuye automáticamente las llamadas a un agente del departamento de soporte técnico disponible.
    
- **Anuncio**
    
    Si planea implementar Telefonía IP empresarial, es posible que desee configurar cómo se administran las llamadas telefónicas si el número marcado es válido pero no está asignado a un área común del usuario. Los administradores pueden configurar el servicio de anuncio para que estas llamadas se transfieran a un destino predeterminado (número de teléfono o URI de SIP) o reprodúyes un anuncio de audio o ambos. El uso del servicio de anuncio evita la situación en la que el autor de la llamada marca y oye un tono de ocupado o el cliente SIP recibe un mensaje de error. La funcionalidad de servicio de anuncios es una característica típica de PBX. 
    
- **Estacionamiento de llamada**
    
    La aplicación Estacionamiento de llamadas permite a un usuario de Telefonía IP empresarial poner una llamada en espera desde un teléfono y, a continuación, recibir la llamada desde otro teléfono sin tener que poner en contacto los recursos del teléfono que recibió la llamada. La aplicación Estacionamiento de llamadas es útil cuando un usuario necesita transferir una llamada, pero el destinatario específico es desconocido. 
    
- **Operador de conferencia**
    
    La aplicación operador de conferencia proporciona capacidades de audioconferencia a los usuarios de teléfono sin el servicio de un proveedor de servicios de audioconferencia de terceros.
    
- **Anuncio de conferencia**
    
    La aplicación anuncio de conferencia produce tonos que señalan cuándo los usuarios entran o salen de una conferencia, así como notificaciones a los usuarios de teléfono cuando están silenciados o sin silenciar.
    
- **Control de admisión de llamadas**
    
    El control de admisión de llamadas (CAC), también conocido como administración de ancho de banda WAN, ayuda a evitar una mala calidad de la experiencia de los usuarios en redes congestionadas al determinar, en función del ancho de banda disponible, si se va a permitir y establecer nuevas sesiones de comunicación en tiempo real. 
    
    > [!NOTE]
    > El CAC solo controla el tráfico en tiempo real y no afecta al tráfico de datos. 
  
    Si una nueva sesión de voz o vídeo supera los límites de ancho de banda que ha asignado en una WAN, la sesión se bloquea o (solo para llamadas telefónicas) se vuelve a enrutar a la RTC.
    

