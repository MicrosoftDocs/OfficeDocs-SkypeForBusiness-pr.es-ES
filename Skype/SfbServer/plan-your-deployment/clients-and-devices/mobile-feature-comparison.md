---
title: Comparación de características de cliente móvil para Skype Empresarial
ms.author: v-cichur
author: cichur
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
description: 'Resumen: revise la compatibilidad de características para el cliente móvil mientras planea Skype Empresarial Server.'
ms.openlocfilehash: cdd6e5d5afc95fe6488ee89ed96739963b5f5ac0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826000"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Comparación de características de cliente móvil para Skype Empresarial
 
**Resumen:** Revise la compatibilidad de características para el cliente móvil al planear Skype Empresarial Server.
  
En este artículo se comparan las características y capacidades entre los clientes móviles de Skype Empresarial y el cliente de escritorio de Skype Empresarial en las siguientes categorías:
  
- Inicio de sesión, notificaciones de inserción y características generales
    
- Presencia ampliada
    
- Contactos y grupos de contactos
    
- Mensajería instantánea
    
- Audio y vídeo de Skype Empresarial a Skype Empresarial
    
- Conferencias
    
- Telefonía
    
- Usuarios externos
    
- Archivado y cumplimiento
    
-  Autenticación moderna
    
En las tablas siguientes se muestran las características disponibles para los usuarios de Skype Empresarial en una implementación local de Skype Empresarial Server. Las mismas características también están disponibles para los usuarios de Skype Empresarial Online y Microsoft 365 u Office 365, a menos que se indique lo contrario en las notas al pie de la tabla.
  
> [!NOTE]
> Para obtener ayuda en línea y recursos para los usuarios finales, consulte [Descubrir Skype Empresarial.](https://go.microsoft.com/fwlink/p/?LinkId=528686) 
  
> [!NOTE]
> Para comparar las características disponibles en otros clientes de Skype Empresarial, vea la comparación de características de cliente de [escritorio para Skype Empresarial.](desktop-feature-comparison.md) 

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Inicio de sesión, notificaciones de inserción y características generales

 
 | Característica/funcionalidad  | Cliente de escritorio de Skype Empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|La sesión de Skype Empresarial permanece con sesión firmada  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Compatibilidad con notificaciones de inserción  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|La información de cuenta para varios usuarios se puede almacenar en caché en el mismo dispositivo  <br/> |&#x2714;||||
|Lector de pantalla/voz en over  <br/> |&#x2714;|&#x2714; &#x2777;           solo inglés  <br/> |&#x2714;|&#x2714;|
|Usar un teclado externo para accesibilidad  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Soporte técnico del Programa para la mejora de la experiencia del usuario de Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; en Windows Phone, Skype Empresarial cierra sesión automáticamente después de un período de inactividad, como se muestra a continuación:
  
- Si el usuario ha habilitado las notificaciones de inserción, Skype Empresarial cierra sesión después de 10 días de inactividad.
    
- Si el usuario no ha habilitado las notificaciones de inserción, Skype Empresarial cierra sesión en cuanto el usuario abandona la aplicación.
    
En dispositivos iOS, Skype Empresarial cierra sesión automáticamente después de que el cliente móvil no se haya puesto en contacto con el servidor durante 10 días debido a la pérdida de conectividad de red u otros problemas.
  
 &#x2777; solo en la aplicación.
  
 &#x2778; notificaciones están disponibles cuando la aplicación se ejecuta en segundo plano.
 
 &#x2779; google/Android/GCNS y los servicios de notificación móvil de Apple/APNS usan cifrado HTTPS/TLS para la entrega de notificaciones. La carga de notificación se controla en texto sin formato mientras el proveedor de notificaciones lo procesa.
 
-   Skype Empresarial para Android recibe notificaciones sencillas (entregadas a través de GCNS) sin datos de clientes.
-   Skype Empresarial para iOS recibe notificaciones (entregadas a través de APNS) que pueden incluir datos de clientes para la llamada o el mensaje.
 
  
## <a name="enhanced-presence-support"></a>Compatibilidad con presencia mejorada


 | Característica/funcionalidad  | Cliente de escritorio de Skype Empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publicar y ver el estado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver estado según la información de disponibilidad del calendario  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver notas de estado y mensajes Fuera de la oficina  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar una ubicación personalizada  <br/> |&#x2714;||||
|Agregar una nota personalizada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Publicar el estado según la información de disponibilidad del calendario  <br/> |&#x2714; &#x2776; ||||
|Establecer el estado de presencia manual (por ejemplo, Ocupado, No molestar, entre otros)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; clientes móviles de Skype Empresarial no actualizan la presencia de un usuario en función de la información del calendario de disponibilidad del usuario. Si un usuario de cliente móvil también ha iniciado sesión en el cliente de escritorio de Skype Empresarial, el cliente de escritorio actualiza la presencia del usuario en función de la información del calendario de disponibilidad del usuario. Si el usuario ha iniciado sesión solo en un cliente móvil, la presencia del usuario no se actualiza en función de la información de disponibilidad del calendario.
  
## <a name="contacts-and-contact-groups-support"></a>Compatibilidad con contactos y grupos de contactos


 | Característica/funcionalidad  | Cliente de escritorio de Skype Empresarial  | Windows Phone  | iOS  | Android |
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
|Expandir grupos de distribución  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Buscar los grupos de respuesta  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Mostrar u ocultar fotos de contactos  <br/> |&#x2714;|&#x2714;|||
|Anclar un contacto a la pantalla principal  <br/> ||&#x2714;|||
   
 &#x2776; disponibles para skype empresarial online o usuarios de Microsoft 365 u Office 365.
  
## <a name="instant-messaging-support"></a>Compatibilidad con mensajería instantánea


 | Característica/funcionalidad  | Cliente de escritorio de Skype Empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar la mensajería instantánea (MI) con un contacto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar en mensajería instantánea con varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitar a otros usuarios desde la ventana de conversación  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mostrar conversaciones actuales  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navegar entre varias conversaciones de mensajería instantánea  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Registrar automáticamente conversaciones de MI en Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Enviar una conversación de MI como mensaje de correo electrónico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar un correo electrónico para un contacto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver invitaciones de MI perdidas  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibración con mensaje instantáneo entrante  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776; este dispositivo vibración cada vez que se recibe una mensajería instantánea, incluso si se muestra el mensaje actual en la conversación de mensajería instantánea
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Audio y vídeo de Skype Empresarial a Skype Empresarial


 | Característica/funcionalidad  | Cliente de escritorio de Skype Empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Voz de Skype Empresarial a Skype Empresarial  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vídeo de Skype Empresarial a Skype Empresarial  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> El vídeo en un dispositivo móvil requiere una conexión WiFi de forma predeterminada. 
  
## <a name="conferencing-support"></a>Compatibilidad con conferencias


 | Característica/funcionalidad  | Cliente de escritorio de Skype Empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Haga clic en un vínculo en el aviso de reunión para unirse a una reunión de Vídeo o VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar en mensajería instantánea con varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar la conferencia saliente (el servidor llama al dispositivo móvil)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usar conferencias de audio de acceso telefónico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver vídeo de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver vídeo entre varias entidades (vista galería)  <br/> |&#x2714;||||
|Esperar en la sala de espera de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar controles de moderador de reunión  <br/> |&#x2714;||||
|Obtener acceso a la lista detallada de la reunión para audioconferencias  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Obtener acceso a la lista detallada de la reunión para conferencias de MI  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartir escritorio o programa  <br/> |&#x2714;||||
|Ver el escritorio o programa compartido (VbSS o RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Ver archivos compartidos de PowerPoint  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Cargar y presentar archivos de PowerPoint  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Usar herramientas de reunión (usar pizarra, realizar sondeos, compartir archivos)  <br/> |&#x2714;||||
|Navegar por una lista de reuniones personales  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Unirse a una reunión incluso si no tiene una cuenta de Skype Empresarial  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver más información sobre los participantes de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar una conversación de grupo sin programar con varios participantes directamente desde el cliente o dispositivo  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; para los usuarios de Microsoft 365 u Office 365, esta característica requiere Telefonía IP empresarial, que forma parte de la licencia E5.
  
 &#x2777; requiere una conexión WiFi de forma predeterminada.
 
 &#x2778; no se admite la visualización de vídeo insertado en presentaciones de PowerPoint.
  
## <a name="telephony-support"></a>Compatibilidad con telefonía


 | Característica/funcionalidad  | Cliente de escritorio de Skype Empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|En Skype Empresarial, pulse el icono de llamada para llamar a un contacto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir una llamada  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Transferencia de consulta  <br/> |&#x2714; &#x2778; ||||
|Administrar la transferencia de llamadas  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Administrar la configuración de llamada de equipo  <br/> |&#x2714; &#x2776; ||||
|Administrar delegados  <br/> |&#x2714; &#x2776; ||||
|Iniciar una llamada a un grupo de respuesta  <br/> |&#x2714; &#x2776; ||||
|Admitir servicios de emergencia  <br/> |&#x2714; &#x2777; ||||
|Realizar llamadas en nombre de otro contacto (escenario de administrador/delegado)  <br/> |&#x2714; &#x2776; ||||
|Administrar las llamadas de otro contacto, si está configurado como delegado  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usar vía trabajo  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Obtener acceso al correo de voz  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Usar el teclado en Skype Empresarial  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; disponibles para los usuarios de Skype Empresarial Online u Office 365 E5, y los usuarios que se encuentran en Skype Empresarial Server o Lync Server 2013 con Telefonía IP empresarial habilitada.
  
 &#x2777; para skype empresarial online o usuarios de Microsoft 365 u Office 365, esta característica es compatible con partners de Microsoft.
  
 &#x2778; cliente de escritorio de Windows.
  
## <a name="external-user-support"></a>Compatibilidad con usuarios externos


 | Característica/funcionalidad  | Cliente de escritorio de Skype Empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensajería instantánea con un contacto público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar mensajería instantánea con un contacto asociado externo  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Realizar llamadas de dos participantes con usuarios externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Realizar llamadas de varios participantes con usuarios externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use Vía trabajo para contactar con un contacto federado en su teléfono móvil llamando a su número de trabajo publicado &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; De forma predeterminada, a los usuarios federados se les asigna la relación de privacidad contactos externos. Para poder contactar con un contacto federado en su teléfono móvil llamando a su número de trabajo publicado, el contacto federado debe asignarle manualmente la relación de privacidad Compañeros.
  
## <a name="address-book-integration"></a>Integración de la libreta de direcciones


 | Característica/funcionalidad  | Cliente de escritorio de Skype Empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Llamar a contactos de la libreta de direcciones del dispositivo  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Realizar llamadas de Skype Empresarial a contactos directamente desde la libreta de direcciones del dispositivo  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Compatibilidad con archivado y cumplimiento


 | Característica/funcionalidad  | Cliente de escritorio de Skype Empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Proporcionar archivado del cliente  <br/> |&#x2714;||||
|Proporcionar grabación del cliente  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; disponibles para skype empresarial online o usuarios de Microsoft 365 u Office 365.
  
## <a name="modern-authentication"></a>Autenticación moderna

En esta tabla se tratan las características que requieren compatibilidad con la autenticación moderna.
  
La autenticación moderna también requiere una topología descrita en las topologías de [Skype Empresarial compatibles con la autenticación moderna.](../../plan-your-deployment/modern-authentication/topologies-supported.md)
  

 | Característica/funcionalidad  | Cliente de escritorio de Skype Empresarial  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticación moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticación multifactor  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticación basada en certificados  <br/> |&#x2714;(solo dispositivo unido a un dominio)  <br/> ||&#x2714;|&#x2714;|
|Administración de aplicaciones móviles (a través de Intune)  <br/> |||&#x2714;|&#x2714;|
   

