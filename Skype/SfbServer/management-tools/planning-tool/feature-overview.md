---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Herramienta de planeación de Skype Empresarial Server 2015
ms.openlocfilehash: 19f84f9d20ade5f4f7bd8bac1395d3d2070f65d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929577"
---
# <a name="feature-overview-planning-tool"></a>Feature Overview (Planning Tool)
 
Herramienta de planeación de Skype Empresarial Server 2015
  
Puede usar la página **Sitios centrales** de la herramienta de planeación para diseñar la Skype para la implementación de Business Server. Puede crear una implementación distribuida o centralizada. Una implementación centralizada sólo tiene un sitio central, que hospede todos los Skype para usuarios profesionales de la organización. Una implementación distribuida tiene más de un sitio central. Si implementa Skype para Business Server en varios sitios centrales, va a escribir el número de usuarios en cada sitio central en la herramienta de planeación.
  
Para completar la definición del sitio central, primero debe proporcionar la siguiente información:
  
- **Nombre del sitio** Escriba el nombre del sitio central.
    
- **Número de usuarios** Escriba el número de usuarios, incluidos los usuarios de sitios de sucursal alojados en el sitio central.
    
- **Usuarios alojados de nube** Introduzca el número de usuarios que están hospedados en el sitio central de Skype para profesionales en línea.
    
> [!NOTE]
> Esta herramienta no se actualizarán para Skype para Business Server 2019.

## <a name="ui-elements"></a>Elementos de la interfaz de usuario

Los elementos restantes se rellenaron con las respuestas proporcionadas a las preguntas presentadas en el Asistente para **introducción** o, si omitió el asistente, se rellenaron automáticamente con la herramienta de planeación.
  
### <a name="online-collaboration"></a>Colaboración en línea

 **Colaboración en línea** contiene las siguientes opciones:
  
- **Mensajería instantánea (MI) y presencia**
    
    La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos mediante mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. La presencia proporciona información a los usuarios acerca del estado de los otros usuarios en la red. El estado de presencia de un usuario proporciona información para ayudar a otros usuarios a determinar si el usuario está conectado y cómo mejor póngase en contacto con el usuario. Por ejemplo, la mejor forma de ponerse en contacto con un usuario que se encuentra en una reunión es mediante correo electrónico.
    
- **Conferencias de audio y vídeo**
    
    La característica de conferencia de audio y vídeo permite realizar este tipo de conferencias en tiempo real.
    
- **Conferencias de acceso telefónico local**
    
    La conferencia de acceso telefónico local permite a los usuarios unirse a una conferencia de audio y vídeo desde un teléfono en la RTC. La conferencia de acceso telefónico local requiere la implementación de las aplicaciones Operador de conferencia y Servicio de anuncio de conferencia.
    
- **Conferencia web**
    
    La conferencia web permite a los usuarios de empresa dentro y fuera del firewall crear y unirse a conferencias en tiempo real hospedadas en los servidores internos.
    
- **Chat persistente**
    
    El chat persistente permite que varios usuarios participen en conversaciones en las que publican y obtienen acceso a contenido de temas específicos, incluidos texto, vínculos y archivos. Aunque los usuarios se pueden comunicar en tiempo real durante una sesión, el contenido de cada sesión es persistente, lo que significa que sigue disponible después de que finaliza la sesión.
    
### <a name="users"></a>Usuarios

 **Usuarios** contiene las siguientes opciones:
  
- **Organización interna**
    
- **Federación con otras organizaciones**
    
- **Federación con versiones anteriores**
    
- **Federación con proveedores de servicios de mensajería instantánea pública**. Permite a los usuarios de la organización establecer una comunicación con proveedores de servicios de mensajería instantánea pública, como MSN, Yahoo! y AOL. Se requiere una licencia independiente para establecer la federación con redes de mensajería instantánea pública.
    
- **Federación con proveedores de servicios basados en XMPP**
    
    Skype para Business Server 2015 presenta un proxy XMPP totalmente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP implementado en los servidores Front-End. Puede implementar agregar y configurar al proxy XMPP y puerta de enlace XMPP permitirá su Skype para los usuarios de Business Server 2015 agregar contactos de presencia y socios basados en XMPP para la mensajería instantánea (IM).

> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype para Business Server 2015, pero ya no se admiten en Skype para Business Server 2019. Para obtener más información, vea [la federación XMPP migrar](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
    
- **Movilidad**
    
    Al implementar el Skype para servicio de movilidad de Business Server 2015, los usuarios pueden utilizar compatibles Apple iOS, Android, Windows Phone o dispositivos móviles Nokia para realizar dichas actividades como enviar y recibir mensajes instantáneos, ver contactos y visualización de la presencia.
    
- **Buzón de correo de W15 Exchange**
    
    Skype para Business Server 2015 permite que los mensajes de correo de voz almacenados en Exchange mensajería unificada (UM); los mensajes de correo de voz, a continuación, se mostrará como mensajes de correo electrónico en las bandejas de entrada de los usuarios.
    
### <a name="voice"></a>Voz

 **Voz** contiene las siguientes opciones:
  
- **Telefonía IP empresarial**
    
    Enterprise voice es la solución de VoIP basada en software de Microsoft. Enterprise voice permite a los usuarios usar Skype para la empresa para realizar una llamada telefónica desde su equipo.
    
- **Mensajería unificada de Exchange**
    
    Correo de voz de mensajería unificada de Exchange (UM) combina y correo electrónico en una sola infraestructura de mensajería. Skype para Business Server 2015 mensajería unificada de Exchange usa para proporcionar el contestador automático, acceso de suscriptor, notificación de llamadas y servicios de operador automático. Si utiliza estos servicios, debe integrar la mensajería unificada de Exchange y Skype para Business Server en una topología de Active Directory compartida.
    
### <a name="additional-deployment-options"></a>Opciones de implementación adicionales

 **Opciones de implementación adicionales** contiene las siguientes opciones:
  
- **Alta disponibilidad**
    
    La alta disponibilidad habilita la compatibilidad de los servidores en espera con la conmutación por error.
    
- **Recuperación ante desastres**
    
    Medidas de recuperación ante desastres permiten a los grupos de servidores Front-End de par que se encuentra en dos centros de datos.
    
- **Supervisión**
    
    La supervisión captura registros de detalles de llamadas relacionados con las sesiones de comunicación. También recopila métricas de sesiones de audio y vídeo en los puntos de conexión de los participantes. El servidor de supervisión proporciona las estadísticas de uso, las tendencias y estadísticas de calidad media.
    
- **Archivado**
    
    El archivado almacena conferencias y conversaciones de mensajería instantánea.
    
- **Integración de archivado de Exchange**
    
    Si tiene usuarios que están hospedados en Exchange 2013 y sus buzones de correo se almacenaron en suspensión en contexto, puede seleccionar la opción de integrar Skype para el almacenamiento de Business Server 2015 con el almacenamiento de Exchange.
    
- **IPv4**
    
    Las direcciones IPv4 son direcciones de 32 bits que permiten a los equipos comunicarse a través de Internet. Debido al cada vez mayor número de dispositivos en todo el mundo, las direcciones IPv4 disponibles se han agotado. Por ello, muchos dispositivos nuevos están pasando a usar direcciones IPv6.
    
- **IPv6**
    
    Las direcciones IPv6 cumplen la misma función que las direcciones IPv4 (con algunas características adicionales), pero en lugar de usar solo 32 bits, usan 128 bits. Esto no solo proporciona un nuevo conjunto de direcciones, sino también un número mucho más elevado de ellas.
    
- **Servicio web de actualización de dispositivos**
    
    El servicio Web de actualización de dispositivo proporciona una forma automatizada de actualizar todos los dispositivos, como Skype para profesionales de Windows Phone, que se han implementado fuera de la organización.
    
### <a name="server-applications"></a>Aplicaciones de servidor

 **Aplicaciones de servidor** contiene las siguientes opciones:
  
- **Grupo de respuesta**
    
    La aplicación de grupo de respuesta contesta a y distribuye las llamadas a un agente de departamento de soporte técnico disponibles automáticamente.
    
- **Anuncio**
    
    Si planea implementar Enterprise Voice, es posible que desee poder configurar la forma en que se administran las llamadas telefónicas si el número marcado es válido pero no asignado a un área común del usuario. Los administradores pueden configurar el servicio de anuncio para que estas llamadas se transfieran a un destino predeterminado (número de teléfono o URI de SIP) o para que se reproduzca un anuncio de audio, o bien para que se lleven a cabo ambas acciones. Con el servicio de anuncio, se evita la situación en la que el autor de una llamada marca el número de forma incorrecta y escucha un tono de línea ocupada o el cliente SIP recibe un mensaje de error. La funcionalidad del servicio de anuncio es una característica típica de PBX. 
    
- **Estacionamiento de llamadas**
    
    Permite de aplicación de estacionamiento de llamadas un usuario de Enterprise Voice para poner una llamada en espera de uno de teléfono y, a continuación, recibe la llamada desde otro teléfono sin consumir recursos en el teléfono que recibió la llamada. Aplicación estacionamiento de llamadas es útil cuando un usuario necesita para transferir una llamada, pero el destinatario específico es desconocido. 
    
- **Operador de conferencia**
    
    Aplicación operador de conferencia proporciona capacidades de conferencia de audio a los usuarios de teléfonos sin el servicio de un proveedor de conferencia de audio de terceros.
    
- **Anuncio de conferencia**
    
    Anuncio de conferencia aplicación genera tonos que señalan cuándo los usuarios o la abandonan una conferencia, así como notificaciones a los usuarios de teléfonos cuando se ha desactivado o reactivados.
    
- **Control de admisión de llamadas**
    
    El servicio de control de admisión de llamadas, también llamado administración de ancho de banda de la WAN, ayuda a evitar que los usuarios experimenten una calidad deficiente en las redes congestionadas, ya que determina si se permitirá que se establezcan nuevas sesiones de comunicación en tiempo real según el ancho de banda disponible. 
    
    > [!NOTE]
    > El servicio de control de admisión de llamadas solo controla el tráfico en tiempo real y no afecta al tráfico de datos. 
  
    Si una sesión de vídeo o voz nueva supera los límites de ancho de banda que se han asignado en una WAN, la sesión se bloquea o (solo para llamadas telefónicas) se desvía a la RTC.
    

