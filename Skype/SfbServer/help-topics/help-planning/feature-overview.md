---
title: Skype Empresarial Server Herramienta de planeación de información general de características
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/6/2016
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
description: Información sobre la herramienta de planeación Skype Empresarial Server de características.
ms.openlocfilehash: 0d342ec6aa1434c3f9245688f38a0c435de557d1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772371"
---
# <a name="skype-for-business-server-feature-overview-planning-tool"></a>Skype Empresarial Server Herramienta de planeación de información general de características
 
Skype Empresarial Server de planeación de 2015
  
Puede usar la página **Sitios centrales** de la Herramienta de planeación para diseñar la Skype Empresarial Server implementación. Puede crear dos implementaciones centralizadas o distribuidas. Una implementación centralizada solo tiene un sitio central, que alberga todos los Skype Empresarial de la organización. Una implementación distribuida tiene más de un sitio central. Si implementas Skype Empresarial Server en varios sitios centrales, escribirá el número de usuarios en cada sitio central en la Herramienta de planeación.
  
Para completar la definición del sitio central, primero debe proporcionar la siguiente información:
  
- **Nombre del sitio** Escriba el nombre del sitio central.
    
- **Número de usuarios** Escriba el número de usuarios, incluidos los usuarios de los sitios de sucursal que se encuentran en el sitio central.
    
- **Usuarios en la nube** Escriba el número de usuarios que se encuentran en el sitio central desde Skype Empresarial Online.
    
## <a name="ui-elements"></a>Elementos de la interfaz de usuario

Los elementos restantes se han rellenado con las respuestas que proporcionó a las preguntas presentadas en el asistente de **Introducción** o, si omitió el asistente, rellenadas automáticamente por la herramienta de planeación.
  
### <a name="online-collaboration"></a>Colaboración en línea

 **Colaboración en** línea contiene las siguientes opciones:
  
- **Mensajería instantánea y presencia**
    
    La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real en sus equipos mediante mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. La presencia proporciona información a los usuarios sobre el estado de otros usuarios en la red. El estado de presencia de un usuario proporciona información para ayudar a otros usuarios a determinar si el usuario está en línea y cómo ponerse en contacto mejor con el usuario. Por ejemplo, un usuario que está en una reunión se contacta mejor por correo electrónico.
    
- **Conferencia de audio y vídeo**
    
    Las conferencias de audio y vídeo (A/V) permiten conferencias de audio y vídeo en tiempo real.
    
- **Conferencias de acceso telefónico local**
    
    Las conferencias de acceso telefónico local permiten a los usuarios unirse a una A/V desde un teléfono en la RTC. Las conferencias de acceso telefónico local requieren que implemente las aplicaciones Operador de conferencia y Anuncio de conferencia servicio.
    
- **Conexión web**
    
    Las conferencias web permiten a los usuarios empresariales dentro y fuera del firewall crear y unirse a conferencias en tiempo real hospedadas en los servidores internos.
    
- **Chat persistente**
    
    El chat persistente permite a varios usuarios participar en conversaciones en las que publican y acceden al contenido sobre temas específicos, incluidos texto, vínculos y archivos. Aunque todos los usuarios se pueden comunicar en tiempo real durante una sesión, el contenido de cada sesión puede ser persistente, lo que significa que sigue disponible después de que finalice una sesión.
    
### <a name="users"></a>Usuarios

 **Los** usuarios contienen las siguientes opciones:
  
- **Organización interna**
    
- **Federación con otras organizaciones**
    
- **Federación con versiones anteriores**
    
- **Federación con proveedores de servicios de mensajería instantánea públicos** Permite a los usuarios de la organización establecer comunicación con proveedores de servicios públicos de mensajería instantánea como MSN, Yahoo!, y AOL. Se requiere una licencia independiente para establecer la federación con redes públicas de mensajería instantánea.
    
- **Federación con proveedor de servicios basado en XMPP**
    
    Skype Empresarial Server 2015 presenta un proxy XMPP totalmente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP implementada en los servidores front-end. Puede implementar Agregar y configurar el proxy XMPP y la puerta de enlace XMPP permitirá a los usuarios de Skype Empresarial Server 2015 agregar contactos de socios basados en XMPP para mensajería instantánea (MI) y presencia.
    
- **Movilidad**
    
    Al implementar el servicio de movilidad de Skype Empresarial Server 2015, los usuarios pueden usar dispositivos móviles apple iOS, Android, Windows Phone o Nokia compatibles para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver presencia.
    
- **Buzón de Exchange W15**
    
    Skype Empresarial Server 2015 permite tener mensajes de correo de voz almacenados en Exchange mensajería unificada (UM); esos mensajes de correo de voz aparecerán como mensajes de correo electrónico en las bandejas de entrada de los usuarios.
    
### <a name="voice"></a>Voz

 **La** voz contiene las siguientes opciones:
  
- **Telefonía IP empresarial**
    
    Enterprise voz es la solución VoIP con software de Microsft. Enterprise voz permite a los usuarios usar Skype Empresarial realizar una llamada desde su equipo.
    
- **Mensajería unificada de Exchange**
    
    Exchange La mensajería unificada (MU) combina el correo de voz y el correo electrónico en una única infraestructura de mensajería. Skype Empresarial Server 2015 usa Exchange mensajería unificada para proporcionar servicios de contestación de llamadas, acceso de suscriptor, notificación de llamadas y operador automático. Si usa estos servicios, deberá integrar Exchange mensajería unificada y Skype Empresarial Server en una topología compartida de Active Directory.
    
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
    
- **Exchange Integración de archivado**
    
    Si tiene usuarios que se encuentran en Exchange 2013 y sus buzones se han puesto en retención In-Place, puede seleccionar la opción para integrar el almacenamiento de Skype Empresarial Server 2015 con Exchange almacenamiento.
    
- **IPv4**
    
    Las direcciones IPv4 son direcciones de 32 bits que permiten a los equipos comunicarse a través de Internet. Debido al número creciente de dispositivos en todo el mundo, las direcciones IPv4 disponibles se han quedo sin funcionar. Debido a esto, muchos dispositivos nuevos se están moviendo al uso de direcciones IPv6.
    
- **IPv6**
    
    Las direcciones IPv6 realizan la misma función que las direcciones IPv4 (con algunas funciones adicionales), pero en lugar de usar solo 32 bits, usan 128 bits. Esto no solo proporciona un nuevo conjunto de direcciones, sino también un número mucho más elevado de ellas.
    
- **Servicio web de actualización de dispositivos**
    
    El servicio web de actualización de dispositivos proporciona una forma automatizada de actualizar todos los dispositivos, como Skype Empresarial para Windows Phone, que se implementan fuera de la organización.
    
### <a name="server-applications"></a>Aplicaciones de servidor

 **Aplicaciones de** servidor contiene las siguientes opciones:
  
- **Grupo de respuesta**
    
    La aplicación Grupo de respuesta responde automáticamente y distribuye llamadas a un agente de soporte técnico disponible.
    
- **Anuncio**
    
    Si planea implementar Telefonía IP empresarial, es posible que desee configurar cómo se controlan las llamadas telefónicas si el número marcado es válido pero no está asignado a un área común del usuario. Los administradores pueden configurar el servicio de anuncios para que estas llamadas se transfieran a un destino predeterminado (número de teléfono o URI de SIP) o reproducir un anuncio de audio o ambos. El uso del servicio de anuncios evita la situación en la que un autor de la llamada desaconseje y oye un tono ocupado o el cliente SIP recibe un mensaje de error. La funcionalidad del servicio de anuncios es una característica típica de PBX. 
    
- **Estacionamiento de llamada**
    
    La aplicación estacionamiento de llamadas permite a un usuario de Telefonía IP empresarial poner una llamada en espera desde un teléfono y, a continuación, recibir la llamada de otro teléfono sin apare los recursos del teléfono que recibió la llamada. La aplicación de estacionamiento de llamadas es útil cuando un usuario necesita transferir una llamada, pero el destinatario específico es desconocido. 
    
- **Operador de conferencia**
    
    aplicación Operador de conferencia proporciona capacidades de audioconferencia a usuarios de teléfono sin el servicio de un proveedor de audioconferencia de terceros.
    
- **Anuncio de conferencia**
    
    aplicación Anuncio de conferencia genera tonos que señalen cuando los usuarios entran o salen de una conferencia, así como notificaciones a los usuarios de teléfono cuando se silencian o no se conmutan.
    
- **Control de admisión de llamadas**
    
    El control de admisión de llamadas (CAC), también conocido como administración de ancho de banda WAN, ayuda a evitar la mala calidad de la experiencia de los usuarios en redes congestionadas al determinar, en función del ancho de banda disponible, si se permiten y se establecen nuevas sesiones de comunicaciones en tiempo real. 
    
    > [!NOTE]
    > El CAC solo controla el tráfico en tiempo real y no afecta al tráfico de datos. 
  
    Si una nueva sesión de voz o vídeo supera los límites de ancho de banda que ha asignado en una WAN, la sesión se bloquea o (solo para llamadas telefónicas) se redirige a la RTC.
    

