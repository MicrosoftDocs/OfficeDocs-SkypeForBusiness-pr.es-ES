---
title: Comparación de características de cliente móvil de Skype para la empresa
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Resumen: Revise la compatibilidad con la característica para el cliente móvil durante la planeación de Skype para Business Server.'
ms.openlocfilehash: f04d0162113db68e2507930e827904110b69066f
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965751"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Comparación de características de cliente móvil de Skype para la empresa
 
**Resumen:** Revise la compatibilidad con la característica para el cliente móvil durante la planeación de Skype para Business Server.
  
En este artículo se comparan las características y la funcionalidad entre Skype para clientes móviles de negocio y la Skype para el cliente de escritorio de negocio en las siguientes categorías:
  
- Inicio de sesión, notificaciones de inserción y características generales
    
- Presencia mejorada
    
- Contactos y grupos de contactos
    
- Mensajería instantánea (MI)
    
- Skype para la empresa a Skype para profesionales audio y vídeo
    
- Conferencia
    
- Telefonía
    
- Usuarios externos
    
- Archivado y cumplimiento
    
-  Autenticación moderna
    
En las tablas siguientes se enumeran las características que están disponibles para Skype para los usuarios de negocio en una implementación local de Skype para Business Server. Las mismas características también están disponibles para Skype para los usuarios en línea de negocio y de Microsoft Office 365, a menos que se indique lo contrario en las notas al pie de tabla.
  
> [!NOTE]
> Para obtener ayuda en pantalla y recursos para los usuarios finales, vea [Detectar Skype para la empresa](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Para comparar las características disponibles en otro Skype para clientes empresariales, vea [comparación de características de cliente de escritorio de Skype para la empresa](desktop-feature-comparison.md). 

> [!NOTE]
> Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos. Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Inicio de sesión, notificaciones de inserción y características generales

 
 | Característica/función  | Skype para el cliente de escritorio empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype para la sesión de negocio permanece iniciada  <br/> |& #x 2714;|& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |& #x 2714;|
|Compatibilidad con notificaciones de inserción  <br/> |& #x 2714; & #x 2778; |& #x 2714;|& #x 2714;|& #x 2714;|
|La información de cuenta para varios usuarios se puede almacenar en caché en el mismo dispositivo  <br/> |& #x 2714;||||
|Lector de pantalla/nota de voz  <br/> |& #x 2714;|& #x 2714; & #x 2777;           Solo en inglés  <br/> |& #x 2714;|& #x 2714;|
|Usar un teclado externo para accesibilidad  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|
|Compatibilidad con el Programa para la mejora de la experiencia del usuario de Microsoft  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
   
 & #x 2776;  En Windows Phone, Skype para la empresa cierra automáticamente después de un período de inactividad, como se indica a continuación:
  
- Si el usuario ha habilitado las notificaciones de inserción, Skype para la empresa cierra sesión después de 10 días de inactividad.
    
- Si el usuario no ha habilitado las notificaciones de inserción, Skype para la empresa cierra sesión tan pronto como el usuario sale de la aplicación.
    
En dispositivos iOS, Skype para la empresa cierra la sesión automáticamente después de que el cliente móvil no ha establecido contacto con el servidor para 10 días debido a la pérdida de conectividad de red u otros problemas.
  
 & #x 2777;  En la aplicación solo.
  
 & #x 2778;  Las notificaciones están disponibles cuando la aplicación se ejecuta en segundo plano.
  
## <a name="enhanced-presence-support"></a>Compatibilidad con presencia mejorada


 | Característica/función  | Skype para el cliente de escritorio empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publicar y ver estado  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Ver estado según la información de disponibilidad del calendario  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Ver notas de estado y mensajes de Fuera de la oficina  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Agregar una ubicación personalizada  <br/> |& #x 2714;||||
|Agregar una nota personalizada  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Publicar el estado según la información de disponibilidad del calendario   <br/> |& #x 2714; & #x 2776; ||||
|Definir el estado de presencia manual (como Ocupado, No molestar, etc.)  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
   
 & #x 2776;  Skype para clientes móviles de negocio no actualiza la presencia de un usuario según la información de disponibilidad de calendario del usuario. Si también ha iniciado sesión un usuario de cliente móvil a la Skype para el cliente de escritorio de negocios, el cliente de escritorio actualiza la presencia del usuario según la información de disponibilidad de calendario del usuario. Si el usuario ha iniciado sesión en un cliente móvil sólo, la presencia del usuario no actualiza en función de libre/ocupado información del calendario.
  
## <a name="contacts-and-contact-groups-support"></a>Compatibilidad con contactos y grupos de contactos


 | Característica/función  | Skype para el cliente de escritorio empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Ver lista de contactos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Ver grupos de contactos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Ver grupo de contactos frecuentes  <br/> |& #x 2714;||||
|Modificar lista de contactos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Marcar contactos para alertas de cambio de estado  <br/> |& #x 2714;||||
|Controlar las relaciones de privacidad  <br/> |& #x 2714;||||
|Buscar en la libreta de direcciones corporativa  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Buscar en la lista de contactos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Administrar grupos de contactos  <br/> |& #x 2714;|||& #x 2714;|
|Expandir grupos de distribución  <br/> |& #x 2714;|& #x 2714;||& #x 2714;|
|Buscar grupos de respuesta  <br/> |& #x 2714; & #x 2776; |& #x 2714;||& #x 2714;|
|Mostrar u ocultar fotos de contactos  <br/> |& #x 2714;|& #x 2714;|||
|Anclar un contacto en la pantalla de inicio  <br/> ||& #x 2714;|||
   
 & #x 2776;  No disponible para Skype para los usuarios de negocio en línea o de Office 365.
  
## <a name="instant-messaging-support"></a>Asistencia de mensajería instantánea


 | Característica/función  | Skype para el cliente de escritorio empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensajería instantánea (MI) con un contacto  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Participar en mensajería instantánea para varios participantes  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Invitar a otros usuarios desde la ventana de conversación  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Mostrar conversaciones actuales  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Navegar entre varias conversaciones de mensajería instantánea  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Registrar automáticamente conversaciones de MI en Exchange  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Enviar una conversación de MI como mensaje de correo electrónico  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Empezar un correo electrónico para un contacto  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Ver invitaciones de MI perdidas  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Vibración con mensaje instantáneo entrante  <br/> ||& #x 2714; & #x 2776; |& #x 2714;|& #x 2714;|
   
 & #x 2776;  Este dispositivo vibra cada vez que se recibe un mensaje instantáneo aunque se muestre el mensaje actual en la conversación de mensajería instantánea
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype para la empresa a Skype para profesionales audio y vídeo


 | Característica / función  | Skype para el cliente de escritorio empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype para profesionales de Skype para voz empresarial  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Skype para profesionales de Skype para vídeo de negocio  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
   
> [!NOTE]
> El vídeo en un dispositivo móvil requiere una conexión WiFi de forma predeterminada.  
  
## <a name="conferencing-support"></a>Compatibilidad con conferencias


 | Característica/función  | Skype para el cliente de escritorio empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Hacer clic en un vínculo del recordatorio de reunión para unirse a una reunión VoIP o en vídeo  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Participar en mensajería instantánea para varios participantes  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Usar la conferencia saliente (el servidor llama al dispositivo móvil)  <br/> |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |
|Usar audioconferencia de acceso telefónico  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Ver vídeo de la reunión  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Ver un vídeo entre varios participantes (vista de galería)  <br/> |& #x 2714;||||
|Esperar en la sala de espera de la reunión  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Usar los controles de moderador en la reunión  <br/> |& #x 2714;||||
|Obtener acceso a la lista detallada de la reunión para audioconferencias  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Obtener acceso a la lista detallada de la reunión para conferencias de MI  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Compartir escritorio o programa  <br/> |& #x 2714;||||
|Ver el escritorio compartido o programa (VbSS o RDP)  <br/> |& #x 2714;|& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |
|Ver archivos de PowerPoint compartidos  <br/> |& #x 2714;|& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |
|Cargar y presentar archivos de PowerPoint  <br/> |& #x 2714;||& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |
|Usar herramientas de la reunión (usar la pizarra, realizar sondeos, compartir archivos)  <br/> |& #x 2714;||||
|Navegar por una lista de reuniones personales  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Unirse a una reunión, incluso si no tienen un Skype para la cuenta de empresa  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Ver más información sobre los participantes de la reunión  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Iniciar una conversación grupal no programada con varios participantes directamente desde su cliente o dispositivo   <br/> |& #x 2714;|& #x 2714;|& #x 2714;||
   
 & #x 2776;  Para los usuarios de Office 365, esta característica requiere Enterprise Voice, que forma parte de la licencia de E5.
  
 & #x 2777;  Requiere una conexión WiFi de forma predeterminada.
  
## <a name="telephony-support"></a>Compatibilidad con funciones de telefonía


 | Característica/función  | Skype para el cliente de escritorio empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|En Skype para la empresa, puntee en el icono de llamada para llamar a un contacto  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Transferir una llamada  <br/> |& #x 2714;|& #x 2714;|& #x 2714;||
|Transferencia consultiva  <br/> |& #x 2714; & #x 2778; ||||
|Administrar el desvío de llamadas  <br/> |& #x 2714; & #x 2776; |& #x 2714;|& #x 2714;|& #x 2714;|
|Administrar la configuración de llamada de equipo  <br/> |& #x 2714; & #x 2776; ||||
|Administrar delegados  <br/> |& #x 2714; & #x 2776; ||||
|Empezar una llamada a un grupo de respuesta  <br/> |& #x 2714; & #x 2776; ||||
|Admitir servicios de emergencia  <br/> |& #x 2714; & #x 2777; ||||
|Realizar llamadas en nombre de otro contacto (escenario de administrador/delegado)  <br/> |& #x 2714; & #x 2776; ||||
|Administrar llamadas de otro contacto, si se configura como delegado  <br/> |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |
|Llamar a través de la cuenta del trabajo  <br/> |& #x 2714; & #x 2776; |& #x 2714;|& #x 2714;||
|Obtener acceso a correo de voz  <br/> |& #x 2714;|& #x 2714;|& #x 2714;||
|Usar el teclado en Skype para la empresa  <br/> |& #x 2714; & #x 2776; |& #x 2714;|& #x 2714;||
   
 & #x 2776;  Disponible para Skype para los usuarios empresariales Online o Office 365 E5, y los usuarios alojados en Skype para Business Server o Lync Server 2013 con Enterprise Voice está habilitado.
  
 & #x 2777;  Para Skype para los usuarios empresariales Online y Office 365, esta característica es compatible con los socios de Microsoft.
  
 & #x 2778;  Cliente de escritorio de Windows.
  
## <a name="external-user-support"></a>Compatibilidad con usuarios externos


 | Característica/función  | Skype para el cliente de escritorio empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensajería instantánea con un contacto público  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Iniciar mensajería instantánea con un contacto federado  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Realizar llamadas de dos participantes con usuarios externos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Realizar llamadas de varios participantes con usuarios externos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Usar vía trabajo para contactar con un contacto federado en su teléfono móvil mediante una llamada a su número del trabajo publicado & #x 2776;            <br/> ||& #x 2714;|& #x 2714;|& #x 2714;|
   
 & #x 2776;  De forma predeterminada, los usuarios federados se asignan la relación de privacidad contactos externos. Para comunicarse con un contacto federado en su teléfono móvil llamando a su número del trabajo publicado, el contacto federado debe asignar manualmente la relación de privacidad Compañeros al autor de la llamada.
  
## <a name="address-book-integration"></a>Integración de la Libreta de direcciones


 | Característica/función  | Skype para el cliente de escritorio empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Llamar a los contactos de la libreta de direcciones  <br/> ||& #x 2714;|& #x 2714;|& #x 2714;|
|Asegúrese de Skype para llamadas de trabajo a los contactos directamente desde la libreta de direcciones de dispositivo  <br/> ||||& #x 2714;|
   
## <a name="archiving-and-compliance-support"></a>Compatibilidad con archivado y cumplimiento


 | Característica/función  | Skype para el cliente de escritorio empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Proporcionar archivado del lado cliente  <br/> |& #x 2714;||||
|Proporcionar registro del lado cliente  <br/> |& #x 2714; & #x 2776; ||||
   
 & #x 2776;  No disponible para Skype para los usuarios de negocio en línea o de Office 365.
  
## <a name="modern-authentication"></a>Autenticación moderna

Esta tabla reúne las características que requieren soporte para la autenticación moderna.
  
Autenticación moderna también requiere una topología que se describen en [Skype para topologías empresariales compatibles con autenticación moderno](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Característica / función  | Skype para el cliente de escritorio empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticación moderna  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Autenticación multifactor  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Autenticación basada en certificados  <br/> |& #x 2714; (sólo dispositivo unido a un dominio)  <br/> ||& #x 2714;|& #x 2714;|
|Administración de aplicaciones móviles (a través de Intune)  <br/> |||& #x 2714;|& #x 2714;|
   

