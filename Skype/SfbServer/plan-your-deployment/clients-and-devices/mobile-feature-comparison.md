---
title: Mobile client feature comparison for Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Summary: Review the feature support for the mobile client while planning for Skype for Business Server 2015.'
ms.openlocfilehash: 4287c5baf0642fab9d55d291470b2352f3da5932
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Mobile client feature comparison for Skype for Business
 
**Summary:** Review the feature support for the mobile client while planning for Skype for Business Server 2015.
  
This article compares the features and capabilities among Skype for Business mobile clients and the Skype for Business desktop client in the following categories:
  
- Inicio de sesión, notificaciones de inserción y características generales
    
- Presencia mejorada
    
- Contactos y grupos de contactos
    
- Mensajería instantánea (MI)
    
- Skype for Business to Skype for Business audio and video
    
- Conferencia
    
- Telefonía
    
- Usuarios externos
    
- Archivado y cumplimiento
    
-  Autenticación moderna
    
The following tables list the features that are available to Skype for Business users in an on-premises deployment of Skype for Business Server 2015. The same features are also available to Skype for Business Online and Microsoft Office 365 users, unless otherwise indicated in the table footnotes.
  
> [!NOTE]
> For online help and resources for end users, see [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> To compare the features available in other Skype for Business clients, see [Desktop client feature comparison for Skype for Business](desktop-feature-comparison.md). 
  
## <a name="sign-in-push-notifications-and-general-features"></a>Inicio de sesión, notificaciones de inserción y características generales

 
 | Característica/función  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business session remains signed in  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Compatibilidad con notificaciones de inserción  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714;|&#x2714;|
|La información de cuenta para varios usuarios se puede almacenar en caché en el mismo dispositivo  <br/> |&#x2714;||||
|Lector de pantalla/nota de voz  <br/> |&#x2714;|&#x2714; &#x2777;           English only  <br/> |&#x2714;|&#x2714;|
|Usar un teclado externo para accesibilidad  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Compatibilidad con el Programa para la mejora de la experiencia del usuario de Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  On Windows Phone, Skype for Business signs out automatically after a period of inactivity, as follows:
  
- If the user has enabled push notifications, Skype for Business signs out after 10 days of inactivity.
    
- If the user has not enabled push notifications, Skype for Business signs out as soon as the user leaves the app.
    
On iOS devices, Skype for Business signs out automatically after the mobile client has not contacted the server for 10 days due to loss of network connectivity or other issues.
  
 &#x2777;  In app only.
  
 &#x2778;  Notifications are available when the app is running in the background.
  
## <a name="enhanced-presence-support"></a>Compatibilidad con presencia mejorada


 | Característica/función  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publicar y ver estado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver estado según la información de disponibilidad del calendario  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver notas de estado y mensajes de Fuera de la oficina  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar una ubicación personalizada  <br/> |&#x2714;||||
|Agregar una nota personalizada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Publicar el estado según la información de disponibilidad del calendario   <br/> |&#x2714; &#x2776; ||||
|Definir el estado de presencia manual (como Ocupado, No molestar, etc.)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  Skype for Business mobile clients do not update a user's presence based on the user's free/busy calendar information. If a mobile client user is also signed in to the Skype for Business desktop client, the desktop client updates the user's presence based on the user's free/busy calendar information. If the user is signed in to a mobile client only, the user's presence does not update based on free/busy calendar information.
  
## <a name="contacts-and-contact-groups-support"></a>Compatibilidad con contactos y grupos de contactos


 | Característica/función  | Skype for Business Lync 2013 desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Ver lista de contactos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver grupos de contactos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver grupo de contactos frecuentes  <br/> |&#x2714;||||
|Modificar lista de contactos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Marcar contactos para alertas de cambio de estado  <br/> |&#x2714;||||
|Controlar las relaciones de privacidad  <br/> |&#x2714;||||
|Buscar en la libreta de direcciones corporativa  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Buscar en la lista de contactos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Administrar grupos de contactos  <br/> |&#x2714;|||&#x2714;|
|Expandir grupos de distribución  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Buscar grupos de respuesta  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Mostrar u ocultar fotos de contactos  <br/> |&#x2714;|&#x2714;|||
|Anclar un contacto en la pantalla de inicio  <br/> ||&#x2714;|||
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="instant-messaging-support"></a>Asistencia de mensajería instantánea


 | Característica/función  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensajería instantánea (MI) con un contacto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar en mensajería instantánea para varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitar a otros usuarios desde la ventana de conversación  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mostrar conversaciones actuales  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navegar entre varias conversaciones de mensajería instantánea  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Registrar automáticamente conversaciones de MI en Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Enviar una conversación de MI como mensaje de correo electrónico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Empezar un correo electrónico para un contacto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver invitaciones de MI perdidas  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibración con mensaje instantáneo entrante  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776;  This device vibrates every time an IM is received even if the current message in the IM conversation is displayed
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business to Skype for Business audio and video


 | Característica / función  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-to-Skype for Business voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business-to-Skype for Business video  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> El vídeo en un dispositivo móvil requiere una conexión WiFi de forma predeterminada.  
  
## <a name="conferencing-support"></a>Compatibilidad con conferencias


 | Característica/función  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Hacer clic en un vínculo del recordatorio de reunión para unirse a una reunión VoIP o en vídeo  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar en mensajería instantánea para varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar la conferencia saliente (el servidor llama al dispositivo móvil)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usar audioconferencia de acceso telefónico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver vídeo de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver un vídeo entre varios participantes (vista de galería)  <br/> |&#x2714;||||
|Esperar en la sala de espera de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar los controles de moderador en la reunión  <br/> |&#x2714;||||
|Obtener acceso a la lista detallada de la reunión para audioconferencias  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Obtener acceso a la lista detallada de la reunión para conferencias de MI  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartir escritorio o programa  <br/> |&#x2714;||||
|View shared desktop or program (VbSS or RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Ver archivos de PowerPoint compartidos  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Cargar y presentar archivos de PowerPoint  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Usar herramientas de la reunión (usar la pizarra, realizar sondeos, compartir archivos)  <br/> |&#x2714;||||
|Navegar por una lista de reuniones personales  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Join a meeting even if you don't have a Skype for Business account  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver más información sobre los participantes de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar una conversación grupal no programada con varios participantes directamente desde su cliente o dispositivo   <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  For Office 365 users, this feature requires Enterprise Voice, which is part of the E5 license.
  
 &#x2777;  Requires a WiFi connection by default.
  
## <a name="telephony-support"></a>Compatibilidad con funciones de telefonía


 | Característica/función  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|In Skype for Business, tap the call icon to call a contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir una llamada  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Transferencia consultiva  <br/> |&#x2714; &#x2778; ||||
|Administrar el desvío de llamadas  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Administrar la configuración de llamada de equipo  <br/> |&#x2714; &#x2776; ||||
|Administrar delegados  <br/> |&#x2714; &#x2776; ||||
|Empezar una llamada a un grupo de respuesta  <br/> |&#x2714; &#x2776; ||||
|Admitir servicios de emergencia  <br/> |&#x2714; &#x2777; ||||
|Realizar llamadas en nombre de otro contacto (escenario de administrador/delegado)  <br/> |&#x2714; &#x2776; ||||
|Handle another contact's calls, if configured as a delegate  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Llamar a través de la cuenta del trabajo  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Obtener acceso a correo de voz  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Use the keypad in Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776;  Available to Skype for Business Online and/or Office 365 E5 users, and users homed on Skype for Business Server 2015 or Lync 2013 with Enterprise Voice enabled.
  
 &#x2777;  For Skype for Business Online and/or Office 365 users, this feature is supported by Microsoft partners.
  
 &#x2778;  Windows Desktop client only.
  
## <a name="external-user-support"></a>Compatibilidad con usuarios externos


 | Característica/función  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensajería instantánea con un contacto público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar mensajería instantánea con un contacto federado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Realizar llamadas de dos participantes con usuarios externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Realizar llamadas de varios participantes con usuarios externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use Call via Work to reach a federated contact on their mobile phone by calling their published work number  &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  By default, federated users are assigned the External Contacts privacy relationship. Para comunicarse con un contacto federado en su teléfono móvil llamando a su número del trabajo publicado, el contacto federado debe asignar manualmente la relación de privacidad Compañeros al autor de la llamada.
  
## <a name="address-book-integration"></a>Integración de la Libreta de direcciones


 | Característica/función  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Llamar a los contactos de la libreta de direcciones  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Make Skype for Business calls to contacts directly from device address book  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Compatibilidad con archivado y cumplimiento


 | Característica/función  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Proporcionar archivado del lado cliente  <br/> |&#x2714;||||
|Proporcionar registro del lado cliente  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="modern-authentication"></a>Autenticación moderna

Esta tabla reúne las características que requieren soporte para la autenticación moderna.
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Característica / función  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticación moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticación multifactor  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticación basada en certificados  <br/> |&#x2714;(Domain-joined device only)  <br/> ||&#x2714;|&#x2714;|
|Mobile Application Management (via Intune)  <br/> |||&#x2714;|&#x2714;|
   

