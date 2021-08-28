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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Resumen: revise la compatibilidad de características para el cliente móvil mientras planea la Skype Empresarial Server.'
ms.openlocfilehash: 576947499c506052c5204d4826489ae9a2a60037
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614130"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Comparación de características de cliente móvil para Skype Empresarial
 
**Resumen:** Revise la compatibilidad con características para el cliente móvil mientras planea la Skype Empresarial Server.
  
En este artículo se comparan las características y capacidades entre Skype Empresarial móviles y el Skype Empresarial de escritorio en las siguientes categorías:
  
- Inicio de sesión, notificaciones de inserción y características generales
    
- Presencia ampliada
    
- Contactos y grupos de contactos
    
- Mensajería instantánea
    
- Skype Empresarial para Skype Empresarial audio y vídeo
    
- Conferencias
    
- Telefonía
    
- Usuarios externos
    
- Archivado y cumplimiento
    
-  Autenticación moderna
    
En las tablas siguientes se muestran las características que están disponibles para los Skype Empresarial en una implementación local de Skype Empresarial Server. Las mismas características también están disponibles para los usuarios Skype Empresarial Online y Microsoft 365 o Office 365, a menos que se indique lo contrario en las notas al pie de la tabla.
  
> [!NOTE]
> Para obtener ayuda en línea y recursos para usuarios finales, vea [Discover Skype Empresarial](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Para comparar las características disponibles en otros Skype Empresarial cliente, consulte Comparación de características de cliente de escritorio [para Skype Empresarial](desktop-feature-comparison.md). 

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes Skype Empresarial móviles ya usan la API web de comunicaciones unificadas (UCWA) para admitir mensajería instantánea (MI), presencia y contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Inicio de sesión, notificaciones de inserción y características generales

 
 | Característica/funcionalidad  | Skype Empresarial cliente de escritorio  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype Empresarial sesión permanece abierta  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Compatibilidad con notificaciones de inserción  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|La información de cuenta para varios usuarios se puede almacenar en caché en el mismo dispositivo  <br/> |&#x2714;||||
|Lector de pantalla/voz en over  <br/> |&#x2714;|&#x2714; &#x2777;           solo inglés  <br/> |&#x2714;|&#x2714;|
|Usar un teclado externo para accesibilidad  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Soporte técnico del Programa de mejora de la experiencia del cliente de Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; On Windows Phone, Skype Empresarial cierra sesión automáticamente después de un período de inactividad, como se muestra a continuación:
  
- Si el usuario ha habilitado las notificaciones de inserción, Skype Empresarial cierra sesión después de 10 días de inactividad.
    
- Si el usuario no ha habilitado las notificaciones de inserción, Skype Empresarial cierra sesión en cuanto el usuario abandona la aplicación.
    
En dispositivos iOS, Skype Empresarial cierra sesión automáticamente después de que el cliente móvil no se haya puesto en contacto con el servidor durante 10 días debido a la pérdida de conectividad de red u otros problemas.
  
 &#x2777; solo en la aplicación.
  
 &#x2778; notificaciones están disponibles cuando la aplicación se ejecuta en segundo plano.
 
 &#x2779; los servicios de notificaciones móviles de Google/Android/GCNS y Apple/APNS usan cifrado HTTPS/TLS para la entrega de notificaciones. La carga de notificación se controla en texto sin formato mientras la procesa el proveedor de notificaciones.
 
-   Skype Empresarial para Android recibe notificaciones sencillas (entregadas a través de GCNS) sin datos de clientes.
-   Skype Empresarial para iOS recibe notificaciones (entregadas a través de APNS) que pueden incluir datos de clientes para la llamada o el mensaje.
 
  
## <a name="enhanced-presence-support"></a>Compatibilidad con presencia mejorada


 | Característica/funcionalidad  | Skype Empresarial cliente de escritorio  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publicar y ver el estado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver estado según la información de disponibilidad del calendario  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver notas de estado y mensajes Fuera de la oficina  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar una ubicación personalizada  <br/> |&#x2714;||||
|Agregar una nota personalizada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Publicar el estado según la información de disponibilidad del calendario  <br/> |&#x2714; &#x2776; ||||
|Establecer el estado de presencia manual (como Ocupado, No molestar, y así sucesivamente)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Skype Empresarial los clientes móviles no actualizan la presencia de un usuario en función de la información de calendario de disponibilidad del usuario. Si un usuario cliente móvil también ha iniciado sesión en el cliente de escritorio de Skype Empresarial, el cliente de escritorio actualiza la presencia del usuario en función de la información del calendario de disponibilidad del usuario. Si el usuario ha iniciado sesión solo en un cliente móvil, la presencia del usuario no se actualiza en función de la información del calendario de disponibilidad.
  
## <a name="contacts-and-contact-groups-support"></a>Compatibilidad con contactos y grupos de contactos


 | Característica/funcionalidad  | Skype Empresarial cliente de escritorio  | Windows Phone  | iOS  | Android |
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
   
 &#x2776; no está disponible para Skype Empresarial online y/o Microsoft 365 o Office 365 usuarios.
  
## <a name="instant-messaging-support"></a>Compatibilidad con mensajería instantánea


 | Característica/funcionalidad  | Skype Empresarial cliente de escritorio  | Windows Phone  | iOS  | Android |
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
   
 &#x2776; Este dispositivo vibra cada vez que se recibe una mensajería instantánea, incluso si se muestra el mensaje actual en la conversación de mensajería instantánea
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype Empresarial para Skype Empresarial audio y vídeo


 | Característica/funcionalidad  | Skype Empresarial cliente de escritorio  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype Empresarial a voz Skype Empresarial voz  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype Empresarial vídeo de Skype Empresarial vídeo  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> El vídeo en un dispositivo móvil requiere una conexión WiFi de forma predeterminada. 
  
## <a name="conferencing-support"></a>Compatibilidad con conferencias


 | Característica/funcionalidad  | Skype Empresarial cliente de escritorio  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Haga clic en un vínculo en el aviso de la reunión para unirse a una reunión de vídeo o VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar en mensajería instantánea con varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar la conferencia saliente (el servidor llama al dispositivo móvil)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usar conferencias de audio de acceso telefónico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver vídeo de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver vídeo multiparte (vista galería)  <br/> |&#x2714;||||
|Esperar en la sala de espera de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar controles de moderador de reunión  <br/> |&#x2714;||||
|Obtener acceso a la lista detallada de la reunión para audioconferencias  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Obtener acceso a la lista detallada de la reunión para conferencias de MI  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartir escritorio o programa  <br/> |&#x2714;||||
|Ver programa o escritorio compartido (VbSS o RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Ver archivos PowerPoint compartidos  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Upload y presentar PowerPoint archivos  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Usar herramientas de reunión (usar pizarra, realizar sondeos, compartir archivos)  <br/> |&#x2714;||||
|Navegar por una lista de reuniones personales  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Unirse a una reunión incluso si no tiene una Skype Empresarial cuenta  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver más información sobre los participantes de la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar una conversación de grupo no programada con varios participantes directamente desde el cliente o el dispositivo  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; Para Microsoft 365 o Office 365 usuarios, esta característica requiere Telefonía IP empresarial, que forma parte de la licencia de E5.
  
 &#x2777; requiere una conexión WiFi de forma predeterminada.
 
 &#x2778; no se admite la visualización de vídeo incrustado PowerPoint presentaciones.
  
## <a name="telephony-support"></a>Compatibilidad con telefonía


 | Característica/funcionalidad  | Skype Empresarial cliente de escritorio  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|En Skype Empresarial, pulse el icono de llamada para llamar a un contacto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir una llamada  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Transferencia consultiva  <br/> |&#x2714; &#x2778; ||||
|Administrar la transferencia de llamadas  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Administrar la configuración de llamada de equipo  <br/> |&#x2714; &#x2776; ||||
|Administrar delegados  <br/> |&#x2714; &#x2776; ||||
|Iniciar una llamada a un grupo de respuesta  <br/> |&#x2714; &#x2776; ||||
|Admitir servicios de emergencia  <br/> |&#x2714; &#x2777; ||||
|Realizar llamadas en nombre de otro contacto (escenario de administrador/delegado)  <br/> |&#x2714; &#x2776; ||||
|Controlar las llamadas de otro contacto, si está configurado como delegado  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usar llamada a través del trabajo  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Obtener acceso al correo de voz  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Use el teclado en Skype Empresarial  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; Disponible para Skype Empresarial Online y/o Office 365 E5 y usuarios que se encuentran en Skype Empresarial Server o Lync Server 2013 con Telefonía IP empresarial habilitado.
  
 &#x2777; Para Skype Empresarial online y/o Microsoft 365 o Office 365 usuarios, esta característica es compatible con partners de Microsoft.
  
 &#x2778; Windows cliente de escritorio.
  
## <a name="external-user-support"></a>Compatibilidad con usuarios externos


 | Característica/funcionalidad  | Skype Empresarial cliente de escritorio  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensajería instantánea con un contacto público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar mensajería instantánea con un contacto asociado externo  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Realizar llamadas de dos participantes con usuarios externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Realizar llamadas de varios participantes con usuarios externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use Llamar a través del trabajo para ponerse en contacto con un contacto federado en su teléfono móvil llamando a su número de trabajo publicado &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; De forma predeterminada, a los usuarios federados se les asigna la relación de privacidad Contactos externos. Para poder llegar a un contacto federado en su teléfono móvil llamando a su número de trabajo publicado, el contacto federado debe asignarle manualmente la relación de privacidad compañeros.
  
## <a name="address-book-integration"></a>Integración de libreta de direcciones


 | Característica/funcionalidad  | Skype Empresarial cliente de escritorio  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Llamar a contactos de la libreta de direcciones de dispositivos  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Realizar Skype Empresarial llamadas a contactos directamente desde la libreta de direcciones del dispositivo  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Soporte técnico de archivado y cumplimiento


 | Característica/funcionalidad  | Skype Empresarial cliente de escritorio  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Proporcionar archivado del cliente  <br/> |&#x2714;||||
|Proporcionar grabación del cliente  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; no está disponible para Skype Empresarial online y/o Microsoft 365 o Office 365 usuarios.
  
## <a name="modern-authentication"></a>Autenticación moderna

En esta tabla se tratan las características que requieren compatibilidad con la autenticación moderna.
  
La autenticación moderna también requiere una topología descrita en [Skype Empresarial topologías compatibles con la autenticación moderna.](../../plan-your-deployment/modern-authentication/topologies-supported.md)
  

 | Característica/funcionalidad  | Skype Empresarial cliente de escritorio  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticación moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticación multifactor  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticación basada en certificados  <br/> |&#x2714;(solo dispositivo unido a dominio)  <br/> ||&#x2714;|&#x2714;|
|Administración de aplicaciones móviles (a través de Intune)  <br/> |||&#x2714;|&#x2714;|
   

