---
title: Introducción a las características (herramienta de planeación)
ms.author: heidip
author: microsoftheidi
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
ms.openlocfilehash: 8d35b9babe99b4899cda51804f40dd6e3302feeb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="feature-overview-planning-tool"></a>Introducción a las características (herramienta de planeación)
 
Herramienta de planeación de Skype Empresarial Server 2015
  
Puede utilizar la página de **Los sitios centrales** de la herramienta de planeación para diseñar el Skype para la implementación de Business Server. Puede crear una implementación distribuida o centralizada. Una implementación centralizada sólo tiene un sitio central, que aloje todos Skype para usuarios profesionales de su organización. Una implementación distribuida tiene más de un sitio central. Si implementa Skype para Business Server en varios sitios centrales, se especifique el número de usuarios en cada sitio central en la herramienta de planeación.
  
Para completar la definición del sitio central, primero debe proporcionar la siguiente información:
  
- **Nombre del sitio** Escriba el nombre del sitio central.
    
- **Número de usuarios** Escriba el número de usuarios, incluidos los usuarios de sitios de sucursal alojados en el sitio central.
    
- **Nube de usuarios alojados** Escriba el número de usuarios alojados en el sitio central de Skype para los negocios en línea.
    
## <a name="ui-elements"></a>Elementos de la interfaz de usuario

Los elementos restantes se rellenaron con las respuestas proporcionadas a las preguntas presentadas en el Asistente para **introducción** o, si omitió el asistente, se rellenaron automáticamente con la herramienta de planeación.
  
### <a name="online-collaboration"></a>Colaboración en línea

 **Colaboración en línea** contiene las siguientes opciones:
  
- **Mensajería instantánea (MI) y presencia**
    
    La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos mediante mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. La presencia proporciona información a los usuarios acerca del estado de los otros usuarios en la red. Estado de presencia del usuario proporciona información para ayudar a otros a determinar si el usuario está conectado y cómo mejor póngase en contacto con el usuario. Por ejemplo, la mejor forma de ponerse en contacto con un usuario que se encuentra en una reunión es mediante correo electrónico.
    
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
    
    Skype para Business Server 2015 presenta un proxy XMPP completamente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP implementados en los servidores frontales. Agregar y configurar al servidor proxy XMPP puede implementar y gateway XMPP permitirá su Skype para los usuarios de Business Server 2015 agregar contactos de presencia y socios basado en XMPP para mensajería instantánea (IM).
    
- **Movilidad**
    
    Al implementar el Skype para servicio de movilidad de 2015 Business Server, los usuarios pueden utilizar para realizar actividades tales como enviar y recibir mensajes instantáneos, ver contactos y ver la presencia compatibles Apple iOS, Android, Windows Phone o dispositivos móviles Nokia.
    
- **Buzón de correo de W15 Exchange**
    
    Skype para el año 2015 de servidor empresarial permite que los mensajes de correo de voz almacenados en Exchange Unified Messaging (UM); los mensajes de correo de voz aparecerá como mensajes de correo electrónico en las bandejas de entrada de los usuarios.
    
### <a name="voice"></a>Voz

 **Voz** contiene las siguientes opciones:
  
- **Telefonía IP empresarial**
    
    Telefonía IP empresarial es la solución de VoIP con tecnología de software de Microsoft. Telefonía IP empresarial permite a los usuarios utilizar Skype para empresas para realizar una llamada telefónica desde su equipo.
    
- **Mensajería unificada de Exchange**
    
    Correo de voz de Exchange Unified Messaging (UM) combina y correo electrónico en una única infraestructura de mensajería. Skype para Business Server 2015 mensajería unificada de Exchange utiliza para proporcionar contestación de llamadas, acceso de suscriptor, las notificaciones de llamadas y servicios de operador automático. Si utiliza estos servicios, debe integrar mensajería unificada de Exchange y Skype para Business Server en una topología de Active Directory compartida.
    
### <a name="additional-deployment-options"></a>Opciones de implementación adicionales

 **Opciones de implementación adicionales** contiene las siguientes opciones:
  
- **Alta disponibilidad**
    
    La alta disponibilidad habilita la compatibilidad de los servidores en espera con la conmutación por error.
    
- **Recuperación ante desastres**
    
    Las medidas de recuperación ante desastres permiten pools de Front-End de par ubicados en dos centros de datos.
    
- **Supervisión**
    
    La supervisión captura registros de detalles de llamadas relacionados con las sesiones de comunicación. También recopila métricas de sesiones de audio y vídeo en los puntos de conexión de los participantes. Servidor de supervisión proporciona estadísticas de uso, tendencias y estadísticas de calidad media.
    
- **Archivado**
    
    El archivado almacena conferencias y conversaciones de mensajería instantánea.
    
- **Integración de archivado de Exchange**
    
    Si tiene usuarios que están alojados en 2013 de Exchange y sus buzones se han puesto en posesión en el lugar, puede seleccionar la opción integrar Skype para el almacenamiento de Business Server 2015 con almacenamiento de información de Exchange.
    
- **IPv4**
    
    Las direcciones IPv4 son direcciones de 32 bits que permiten a los equipos comunicarse a través de Internet. Debido al cada vez mayor número de dispositivos en todo el mundo, las direcciones IPv4 disponibles se han agotado. Por ello, muchos dispositivos nuevos están pasando a usar direcciones IPv6.
    
- **IPv6**
    
    Las direcciones IPv6 cumplen la misma función que las direcciones IPv4 (con algunas características adicionales), pero en lugar de usar solo 32 bits, usan 128 bits. Esto no solo proporciona un nuevo conjunto de direcciones, sino también un número mucho más elevado de ellas.
    
- **Servicio web de actualización de dispositivos**
    
    El servicio Web de actualización de dispositivo proporciona una forma automatizada para actualizar todos los dispositivos, como Skype para negocios para Windows Phone, que se implementan fuera de la organización.
    
### <a name="server-applications"></a>Aplicaciones de servidor

 **Aplicaciones de servidor** contiene las siguientes opciones:
  
- **Grupo de respuesta**
    
    La aplicación de grupo de respuesta automáticamente respuestas y distribuye llamadas a un agente de asistencia técnica disponible.
    
- **Anuncio**
    
    Si planea implementar la Telefonía IP empresarial, desea poder configurar cómo se controlan las llamadas de teléfono si el número marcado es válido pero no asignado a un área común del usuario. Los administradores pueden configurar el servicio de anuncio para que estas llamadas se transfieran a un destino predeterminado (número de teléfono o URI de SIP) o para que se reproduzca un anuncio de audio, o bien para que se lleven a cabo ambas acciones. Con el servicio de anuncio, se evita la situación en la que el autor de una llamada marca el número de forma incorrecta y escucha un tono de línea ocupada o el cliente SIP recibe un mensaje de error. La funcionalidad del servicio de anuncio es una característica típica de PBX. 
    
- **Estacionamiento de llamadas**
    
    Habilita aplicaciones de llamada parque mantenga un usuario de Telefonía IP empresarial para poner una llamada en una teléfono y, a continuación, recibe la llamada desde otro teléfono sin consumir recursos en el teléfono que recibió la llamada. Aplicación llamada Park es útil cuando necesita transferir una llamada a un usuario, pero se desconoce el destinatario específico. 
    
- **Operador de conferencia**
    
    Aplicación de conferencia operador proporciona capacidades de conferencia de audio para los usuarios de teléfono sin el servicio de un proveedor de conferencia de audio de terceros.
    
- **Anuncio de conferencia**
    
    Anuncio de conferencias aplicación genera tonos que cuando los usuarios entren o salgan de una conferencia, así como notificaciones a los usuarios de teléfonos cuando se silencian o desactivar el silencio de señal.
    
- **Control de admisión de llamadas**
    
    El servicio de control de admisión de llamadas, también llamado administración de ancho de banda de la WAN, ayuda a evitar que los usuarios experimenten una calidad deficiente en las redes congestionadas, ya que determina si se permitirá que se establezcan nuevas sesiones de comunicación en tiempo real según el ancho de banda disponible. 
    
    > [!NOTE]
    > El servicio de control de admisión de llamadas solo controla el tráfico en tiempo real y no afecta al tráfico de datos. 
  
    Si una sesión de vídeo o voz nueva supera los límites de ancho de banda que se han asignado en una WAN, la sesión se bloquea o (solo para llamadas telefónicas) se desvía a la RTC.
    

