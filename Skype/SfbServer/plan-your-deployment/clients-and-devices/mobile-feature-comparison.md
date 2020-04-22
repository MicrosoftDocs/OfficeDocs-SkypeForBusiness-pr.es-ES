---
title: Comparación de características de cliente móvil para Skype empresarial
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Resumen: Revise la compatibilidad de características para el cliente móvil mientras planea Skype empresarial Server.'
ms.openlocfilehash: 36ae93e796e4142a9ae3b5fb85ac806c9a38cdca
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777775"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Comparación de características de cliente móvil para Skype empresarial
 
**Resumen:** Revise la compatibilidad de características para el cliente móvil al planificar Skype empresarial Server.
  
En este artículo se comparan las características y capacidades entre los clientes móviles de Skype empresarial y el cliente de escritorio de Skype empresarial en las siguientes categorías:
  
- Inicio de sesión, notificaciones de inserción y características generales
    
- Presencia ampliada
    
- Contactos y grupos de contactos
    
- Mensajería instantánea
    
- Skype empresarial para audio y vídeo de Skype empresarial
    
- Conferencia
    
- Telefonía
    
- Usuarios externos
    
- Archivado y cumplimiento
    
-  Autenticación moderna
    
En las tablas siguientes se enumeran las características que están disponibles para los usuarios de Skype empresarial en una implementación local de Skype empresarial Server. Las mismas características también están disponibles para los usuarios de Skype empresarial online y Microsoft 365 o Office 365, a menos que se indique lo contrario en las notas al pie de la tabla.
  
> [!NOTE]
> Para obtener ayuda en línea y recursos para usuarios finales, vea [Descubra Skype empresarial](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Para comparar las características disponibles en otros clientes de Skype empresarial, consulte [comparación de características de cliente de escritorio para Skype empresarial](desktop-feature-comparison.md). 

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (mi), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Inicio de sesión, notificaciones de inserción y características generales

 
 | Característica/funcionalidad  | Cliente de escritorio de Skype empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|La sesión de Skype empresarial continúa con la sesión iniciada  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Compatibilidad con notificaciones de inserción  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|La información de cuenta para varios usuarios se puede almacenar en caché en el mismo dispositivo  <br/> |&#x2714;||||
|Lector de pantalla/voz sobre  <br/> |&#x2714;|Solo &#x2714; &#x2777;  inglés  <br/> |&#x2714;|&#x2714;|
|Usar un teclado externo para accesibilidad  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Soporte del programa para la mejora de la experiencia del usuario de Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; en Windows Phone, Skype empresarial cierra la sesión automáticamente tras un período de inactividad, como se indica a continuación:
  
- Si el usuario ha habilitado las notificaciones de inserción, Skype empresarial cerrará la sesión después de 10 días de inactividad.
    
- Si el usuario no ha habilitado las notificaciones de inserción, Skype empresarial cerrará la sesión en cuanto el usuario abandone la aplicación.
    
En dispositivos iOS, Skype empresarial cierra sesión automáticamente después de que el cliente móvil no haya contactado con el servidor durante 10 días debido a la pérdida de conectividad de red u otros problemas.
  
 &#x2777; solo en la aplicación.
  
 Las notificaciones de &#x2778; están disponibles cuando la aplicación se está ejecutando en segundo plano.
 
 &#x2779; los servicios de notificación móvil de Google/Android/GCNS y Apple/APNS usan el cifrado de HTTPS/TLS para la entrega de notificaciones. La carga de la notificación se controla en texto sin formato mientras el proveedor de notificaciones la procesa.
 
-   Skype empresarial para Android recibe notificaciones simples (entregadas a través de GCNS) sin datos de clientes.
-   Skype empresarial para iOS recibe notificaciones (entregadas mediante APNS) que pueden incluir datos de clientes para la llamada o el mensaje.
 
  
## <a name="enhanced-presence-support"></a>Compatibilidad con presencia mejorada


 | Característica/funcionalidad  | Cliente de escritorio de Skype empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publicar y ver el estado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver estado según la información de disponibilidad del calendario  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver notas de estado y mensajes Fuera de la oficina  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar una ubicación personalizada  <br/> |&#x2714;||||
|Agregar una nota personalizada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Publicar el estado según la información de disponibilidad del calendario  <br/> |&#x2714; &#x2776; ||||
|Establecer el estado de presencia manual (como ocupado, no molestar, etc.)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; clientes móviles de Skype empresarial no actualizan la presencia de un usuario en función de la información del calendario de disponibilidad del usuario. Si un usuario de cliente móvil también ha iniciado sesión en el cliente de escritorio de Skype empresarial, el cliente de escritorio actualiza la presencia del usuario en función de la información del calendario de disponibilidad del usuario. Si el usuario ha iniciado sesión en un solo cliente móvil, la presencia del usuario no se actualiza en función de la información de disponibilidad del calendario.
  
## <a name="contacts-and-contact-groups-support"></a>Compatibilidad con contactos y grupos de contactos


 | Característica/funcionalidad  | Cliente de escritorio de Skype empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Ver la lista de contactos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver grupos de contactos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver grupo de contactos frecuentes  <br/> |&#x2714;||||
|Modificar la lista de contactos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Etiqueta de contacto para alertas de cambio de estado  <br/> |&#x2714;||||
|Controlar las relaciones de privacidad  <br/> |&#x2714;||||
|Buscar en la libreta de direcciones de la compañía  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Buscar en la lista de contactos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Administrar los grupos de contactos  <br/> |&#x2714;|||&#x2714;|
|Expandir los grupos de distribución  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Buscar los grupos de respuesta  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Mostrar u ocultar fotos de contactos  <br/> |&#x2714;|&#x2714;|||
|Anclar un contacto a la pantalla de inicio  <br/> ||&#x2714;|||
   
 &#x2776; no disponible para los usuarios de Skype empresarial online o Microsoft 365 o Office 365.
  
## <a name="instant-messaging-support"></a>Compatibilidad con mensajería instantánea


 | Característica/funcionalidad  | Cliente de escritorio de Skype empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar la mensajería instantánea (mi) con un contacto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar en mensajería instantánea con varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitar a otros usuarios desde la ventana de conversación  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mostrar conversaciones actuales  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navegar entre varias conversaciones de mensajería instantánea  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Registrar automáticamente conversaciones de MI en Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Enviar una conversación de MI como mensaje de correo electrónico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar un correo electrónico para un contacto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver invitaciones de MI perdidas  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibración con mensaje instantáneo entrante  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776; este dispositivo vibra cada vez que se recibe un mensaje instantáneo aunque se muestre el mensaje actual en la conversación de mensajería instantánea
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype empresarial para audio y vídeo de Skype empresarial


 | Característica/funcionalidad  | Cliente de escritorio de Skype empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Voz de Skype empresarial a Skype empresarial  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vídeo de Skype empresarial a Skype empresarial  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> El vídeo en un dispositivo móvil requiere una conexión WiFi de forma predeterminada. 
  
## <a name="conferencing-support"></a>Compatibilidad con conferencias


 | Característica/funcionalidad  | Cliente de escritorio de Skype empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Haga clic en un vínculo del aviso de reunión para unirse a una reunión de vídeo o VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar en mensajería instantánea con varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar la conferencia saliente (el servidor llama al dispositivo móvil)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usar conferencias de audio de acceso telefónico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver vídeo de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver vídeo entre varias partes (vista de galería)  <br/> |&#x2714;||||
|Esperar en la sala de espera de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar controles de moderador de reunión  <br/> |&#x2714;||||
|Obtener acceso a la lista detallada de la reunión para audioconferencias  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Obtener acceso a la lista detallada de la reunión para conferencias de MI  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartir escritorio o programa  <br/> |&#x2714;||||
|Ver un programa o escritorio compartido (VbSS o RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Ver archivos compartidos de PowerPoint  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Cargar y presentar archivos de PowerPoint  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Usar las herramientas de reuniones (usar la pizarra, realizar sondeos, compartir archivos)  <br/> |&#x2714;||||
|Navegar por una lista de reuniones personales  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Unirse a una reunión incluso si no tiene una cuenta de Skype empresarial  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver más información sobre los participantes de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar una conversación de grupo no programado con varios participantes directamente desde su cliente o dispositivo  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; para los usuarios de Microsoft 365 u Office 365, esta característica requiere la telefonía IP empresarial, que forma parte de la licencia E5.
  
 &#x2777; requiere una conexión WiFi de forma predeterminada.
 
 No se admite &#x2778; ver vídeo insertado en presentaciones de PowerPoint.
  
## <a name="telephony-support"></a>Compatibilidad con telefonía


 | Característica/funcionalidad  | Cliente de escritorio de Skype empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|En Skype empresarial, pulse el icono de llamada para llamar a un contacto.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir una llamada  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Transferencia Consultiva  <br/> |&#x2714; &#x2778; ||||
|Administrar la transferencia de llamadas  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Administrar la configuración de llamada de equipo  <br/> |&#x2714; &#x2776; ||||
|Administrar delegados  <br/> |&#x2714; &#x2776; ||||
|Iniciar una llamada a un grupo de respuesta  <br/> |&#x2714; &#x2776; ||||
|Admitir servicios de emergencia  <br/> |&#x2714; &#x2777; ||||
|Realizar llamadas en nombre de otro contacto (escenario de administrador/delegado)  <br/> |&#x2714; &#x2776; ||||
|Administrar las llamadas de otro contacto, si está configurado como delegado  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usar la llamada vía trabajo  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Obtener acceso al correo de voz  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Usar el teclado en Skype empresarial  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; disponible para los usuarios de Skype empresarial online o de Office 365 E5, y los usuarios alojados en Skype empresarial Server o Lync Server 2013 con Enterprise Voice habilitado.
  
 &#x2777; para los usuarios de Skype empresarial online o Microsoft 365 u Office 365, esta característica es compatible con los socios de Microsoft.
  
 &#x2778; solo cliente de escritorio de Windows.
  
## <a name="external-user-support"></a>Compatibilidad con usuarios externos


 | Característica/funcionalidad  | Cliente de escritorio de Skype empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensajería instantánea con un contacto público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar mensajería instantánea con un contacto asociado externo  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Realizar llamadas de dos participantes con usuarios externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Realizar llamadas de varios participantes con usuarios externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use llamar a través del trabajo para llegar a un contacto federado en su teléfono móvil llamando a su número de trabajo publicado &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; de forma predeterminada, los usuarios federados tienen asignada la relación de privacidad contactos externos. Para poder llegar a un contacto federado en su teléfono móvil llamando a su número de trabajo publicado, el contacto federado debe asignar manualmente la relación de privacidad compañeros.
  
## <a name="address-book-integration"></a>Integración de la libreta de direcciones


 | Característica/funcionalidad  | Cliente de escritorio de Skype empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Llamar a los contactos de la libreta de direcciones del dispositivo  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Realizar llamadas de Skype empresarial a los contactos directamente desde la libreta de direcciones del dispositivo  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Soporte de archivado y cumplimiento


 | Característica/funcionalidad  | Cliente de escritorio de Skype empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Proporcionar archivado del cliente  <br/> |&#x2714;||||
|Proporcionar grabación del cliente  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; no disponible para los usuarios de Skype empresarial online o Microsoft 365 o Office 365.
  
## <a name="modern-authentication"></a>Autenticación moderna

En esta tabla se describen las características que requieren soporte para la autenticación moderna.
  
La autenticación moderna también requiere una topología descrita en las [topologías de Skype empresarial compatibles con la autenticación moderna](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Característica/funcionalidad  | Cliente de escritorio de Skype empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticación moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticación multifactor  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticación basada en certificados  <br/> |&#x2714; (sólo dispositivos Unidos a un dominio)  <br/> ||&#x2714;|&#x2714;|
|Administración de aplicaciones móviles (a través de Intune)  <br/> |||&#x2714;|&#x2714;|
   

