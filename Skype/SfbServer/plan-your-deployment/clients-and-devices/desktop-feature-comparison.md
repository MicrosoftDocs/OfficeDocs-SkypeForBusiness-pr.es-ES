---
title: Desktop client feature comparison for Skype for Business
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Summary: Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.'
ms.openlocfilehash: 0ce6457bea83c775ca5cf9373a5724f95785ddb1
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="desktop-client-feature-comparison-for-skype-for-business"></a>Desktop client feature comparison for Skype for Business
 
**Summary:** Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.
  
 Before you deploy or upgrade to Skype for Business, check which clients are already in use in your organization. Use the tables below to understand the feature support impact on those clients. Esto puede ayudarle a comunicar los cambios a los usuarios, decidir el ritmo del proceso de lanzamiento y conocer en profundidad las ventajas que tiene actualizar al cliente más reciente.
  
Some features available with Skype for Business Server 2015 are not available in Skype for Business Online, see [Online or Hybrid user account limitations](desktop-feature-comparison.md#Online-Hybrid) for specifics. Skype for Business Online Admins may want to refer to [Skype for Business Online Service Description](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) for information on the different plans available to them.
  
The following tables show the features that are available with each client that works with Skype for Business Server 2015 or Skype for Business Online. You may also want to refer to [Mobile client feature comparison for Skype for Business](mobile-feature-comparison.md) for smart phone and tablet client feature comparisons. La licencia de acceso de cliente o la licencia de suscripción de usuario que adquiera su organización también influirá en qué características están disponibles para sus usuarios. La decisión de implementar el cliente completo o el básico en los usuarios depende de la licencia o el plan que su organización decida comprar. See the [Licensing Guide](https://products.office.com/en-us/skype-for-business/it-pros) for more details.
  
> [!IMPORTANT]
> Skype for Business Server 2015 and Skype for Business Online support the following previously released clients: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Phone Edition, and Lync 2010 Attendant. For information about these clients when used with other servers, see the [Client comparison tables for Lync Server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) and [Client comparison tables for Lync Server 2010](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.14%29.aspx). 
  
> [!NOTE]
> The **Lync 2010 Attendant** client is not supported in Skype for Business Online.
  
> [!NOTE]
> The Skype for Business Web App browser client and Skype Meetings App Windows 10 app only provide [Meetings support](desktop-feature-comparison.md#BKMK_Conferencing). Refer to [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md) for more about these clients.
  
## <a name="enhanced-presence-support"></a>Compatibilidad con presencia mejorada
<a name="BKMK_EnhancedPresence"> </a>

En esta tabla se presentan las características de presencia mejorada que implican algo más que una simple indicación de que un usuario está en línea, sin conexión, ocupado, etc. 
  
|Característica / función|Cliente de Skype Empresarial 2015 o 2016|Skype Empresarial en Mac|Lync 2013 client|Aplicación de la Tienda Windows de Lync|Lync 2010 | Operador de Skype Empresarial|Lync Phone Edition|Communicator para Mac 2011|Lync para Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Publicar estado  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|Ver estado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver notas de estado y mensajes de Fuera de la oficina  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar una ubicación personalizada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Agregar una nota personalizada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Usar una fotografía de cualquier sitio público para Mi imagen  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||

 &#x2776;  Does not support publishing status based on calendar free/busy information.
  
## <a name="contacts-and-contact-groups-support"></a>Compatibilidad con contactos y grupos de contactos
<a name="BKMK_Contacts"> </a>

En esta tabla se presentan las características relacionadas con la administración de contactos de presencia y mensajería instantánea. 
  

|Característica / función|Cliente de Skype Empresarial 2015 o 2016|Skype Empresarial en Mac | Lync 2013 client | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Skype Empresarial | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Lista de contactos rellenada anteriormente  <br/> |&#x2714;|||||||||
|Ver y modificar la lista de contactos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Marcar contactos para alertas de cambio de estado  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|Controlar las relaciones de privacidad  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Buscar en la libreta de direcciones corporativa  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Buscar en los contactos de Microsoft Outlook  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar grupos de contactos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Expandir grupos de distribución y grupos de Office 365  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Buscar grupos de respuesta  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Mostrar el grupo de contactos recientes  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Mostrar el grupo de conversaciones actuales  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|Mostrar vistas de contactos alternativas (por ejemplo, mosaico)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Sort contacts by Group, Relationship, or New (people who've added you to their Contacts list)  <br/> |&#x2714;||&#x2714;|Ordenar por grupo  <br/> |&#x2714;|&#x2714;||||
|Ordenar contactos por Estado (disponibilidad)  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Buscar y agregar contactos de Exchange  <br/> |&#x2714;||&#x2714;||||||&#x2714;|
   
## <a name="im-support"></a>Compatibilidad con mensajería instantánea
<a name="BKMK_IMSupport"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con mensajería instantánea.
  

|Característica / función | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Lync 2013 client | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Skype Empresarial | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar la mensajería instantánea con un contacto o enviarle un correo electrónico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Desplazarse por varias conversaciones de mensajería instantánea o realizar un seguimiento de varias conversaciones en una única ventana con pestañas  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Registrar las conversaciones de mensajería instantánea en Outlook  <br/> |&#x2714;|&#x2714;If server side conversation history is turned on  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Se guardan en Communicator para Mac  <br/> |Se guardan en Skype Empresarial Mac  <br/> |
|Usar las plantillas de conversación preparadas  <br/> |||||&#x2714;|&#x2714;||||
|Revisar la ortografía  <br/> |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Skill search (with SharePoint Server integration)  <br/> (On-premises Skype for Business Server and on-premises SharePoint 2013 are required for skill search.)  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|Integración de sistemas de chat en grupo o chat persistente  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|Escalate a Persistent Chat room to a Skype for Business Meeting with one click  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|Imágenes entre líneas del remitente y el destinatario en la ventana de mensajería instantánea  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|Enviar mensajes de lápiz  <br/> ||||&#x2714;||||||
|Recibir mensajes de lápiz  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|Establecer mensajes de mensajería instantánea como de importancia alta  <br/> |&#x2714;||&#x2714;|||||||
   
## <a name="meetings-support"></a>Compatibilidad con reuniones
<a name="BKMK_Conferencing"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con reuniones.
  
> [!NOTE]
>  Skype for Business meeting features aren't available in Skype for Business Online Standalone Plan 1.

En sesiones de Skype a Skype, los usuarios del plan 1 de Skype Empresarial Online pueden participar en el uso compartido del escritorio y de aplicaciones si les invita un usuario que tiene acceso a las características de uso compartido.   
For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
|Característica / función | Skype for Business 2016 client | Skype Empresarial en Mac | Aplicación web de Skype Empresarial | Skype for Business 2015 client | Lync 2013 client | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Skype Empresarial | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Agregar audio de equipo  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar vídeo  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|Ver un vídeo entre varios participantes (vista de galería)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Pantalla compartida basada en vídeo  <br/> |&#x2714;|&#x2714;Only for users homed on Skype for Business Online  <br/> |&#x2714;View-only  <br/> |||||||||
|Usar los controles de moderador en la reunión  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Acceder a la lista de reuniones detallada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Participar en mensajería instantánea para varios participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Compartir el escritorio (si se habilita)  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|Compartir un programa (si se habilita)  <br/> |&#x2714;|Ver solamente  <br/> |&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;||||Ver solamente  <br/> |
|Agregar participantes anónimos (si se habilita)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Usar reuniones de audio de acceso telefónico local  <br/> |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|Empezar una reunión de tipo Reunirse ahora  <br/> |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Agregar y presentar archivos de Microsoft PowerPoint  <br/> |&#x2714;| &#x2778; View only, annotations not available  <br/> |&#x2714;|&#x2714;|&#x2714;|Presentar solamente  <br/> |&#x2714;|||| &#x2778; View only, annotations not available  <br/> |
|Explorar archivos de Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Agregar y editar las notas de reunión de OneNote  <br/> |&#x2714;||Solo editar (no agregar)  <br/> |&#x2714;|&#x2714;|||||||
|Usar una pizarra  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Realizar sondeos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Cargar archivos para compartirlos con otros usuarios  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Programar una reunión o conferencia  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook  <br/> ||||Outlook  <br/> |
|Q&amp;A Manager  <br/> |&#x2714;|||||||||||
|Deshabilitar el vídeo de asistentes  <br/> |&#x2714;||&#x2714;|||||||||
|Deshabilitar la mensajería instantánea de la reunión  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|Desactivar el audio del público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Convertir a todos en asistentes  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Producir difusión de reunión de Skype  <br/> |&#x2714;|||||||||||
|El delegado puede programar una reunión en nombre del delegador  <br/> |&#x2714;|Solo Skype Empresarial Online <br/>|&#x2714;|||||||||
|Sincronizar delegados entre Skype Empresarial y Outlook  <br/> |&#x2714;||&#x2714;|||||||||
|Pantalla compartida basada en vídeo  <br/> |&#x2714;| Solo Skype Empresarial Online <br/> |&#x2714;||&#x2714;|||||||
|Establecer el primer plano del vídeo (bloquear vídeo)  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Ceder y tomar el control de la pantalla compartida  <br/> |&#x2714;||&#x2714;|||||||||
   
 &#x2776;  Participants can't control desktops that are shared by Skype for Business on Mac, Lync for Mac 2011, or Communicator for Mac 2011 users. Skype for Business on Mac, Lync for Mac 2011 and Communicator for Mac 2011 users can't control desktops shared by Windows users. Esto tampoco funcionará con la aplicación web de Skype Empresarial en Mac OS X.
  
 &#x2777;  For Skype for Business Online, this feature requires Microsoft PSTN Conferencing, Exchange Unified Messaging, or a 3rd party audio conferencing provider.
  
 &#x2778;  The Lync for Mac 2011 client cannot view Microsoft Office 2013 PowerPoint presentations when they have been shared in a conference by the Skype for Business Web App.
  
## <a name="voice-telephony-support"></a>Compatibilidad con voz (telefonía)
<a name="BKMK_Telephony"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con servicios de voz.
  
> [!NOTE]
> Skype for Business Voice (Telephony) features are limited to certain Skype for Business Online subscription plans. > For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
 | Característica / función | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Lync 2013 client | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Skype Empresarial | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar una llamada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Hacer clic para llamar a un contacto  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir una llamada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar el desvío de llamadas  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar la configuración de llamada de equipo  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Administrar delegados  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU4 or later  <br/> |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|Empezar una llamada a un grupo de respuesta  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Compatibilidad con servicios de emergencia (E-911)  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU6 or later  <br/> |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|IM notification to SIP URI(s) for E-911 call  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|IM notification to distribution list for E-911 call  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Conectar con el correo de voz, configurar o cambiar el saludo  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Notificación de llamada perdida  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Realizar llamadas en nombre de otro contacto (escenario de administrador/delegado)  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|Administrar llamadas de otro usuario si se configura como delegado  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|Administrar volúmenes altos de llamadas  <br/> |||||&#x2714;|&#x2714;||||
|Estacionar llamada  <br/> |&#x2714;||&#x2714; &#x2776; |||||||
|Atender llamada grupal  <br/> |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|Enrutamiento basado en ubicación  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar el grupo de llamada de equipo/grupo de respuesta  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  This feature isn't available in Skype for Business Online.
  
## <a name="external-users-support"></a>Compatibilidad con usuarios externos
<a name="BKMK_ExternalUsers"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con usuarios externos alojados en RTC.
  

|Característica / función | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Lync 2013 client | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Skype Empresarial | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensajería instantánea con un contacto público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Iniciar mensajería instantánea con un contacto federado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Realizar llamadas de dos o más participantes con usuarios externos  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
## <a name="recording-support"></a>Compatibilidad con grabaciones
<a name="BKMK_Recording"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con la grabación de reuniones.
  
| Future/capability** | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Lync 2013 client | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Skype Empresarial | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Grabación del lado cliente de audio, vídeo, uso compartido de aplicaciones, uso compartido de escritorio y contenido cargado  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Grabación del lado cliente de transferencias de archivos, páginas compartidas de OneNote y anotaciones de PowerPoint  <br/> |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|Seleccionar la resolución preferida para la grabación  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  Recording is unavailable in certain Skype for Business Online standalone plans. La grabación requiere derechos de cliente completos de Skype Empresarial.
  
 &#x2777;  Recording of file transfers, shared OneNote pages, and PowerPoint annotations is unavailable in Skype for Business Online.
  
## <a name="modern-authentication"></a>Autenticación moderna
<a name="BKMK_Recording"> </a>

Esta tabla reúne las características que requieren soporte para la autenticación moderna. 
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Característica / función | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Lync 2013 client | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Skype Empresarial | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticación moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticación multifactor  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticación basada en certificados  <br/> |&#x2714;(Domain-joined device only)  <br/> |&#x2714;|&#x2714;(Domain-joined device only)  <br/> |||||||
   
## <a name="archiving-compliance-and-logging-support"></a>Compatibilidad con archivado, cumplimiento y registro
<a name="BKMK_Archiving"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con archivado y registro.
  

 | Característica / función | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Lync 2013 client | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Skype Empresarial | Lync Phone Edition | **Communicator para Mac 2011** | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Archivado de conversaciones de mensajería instantánea en el Historial de conversaciones de Outlook  <br/> |&#x2714; &#x2776; |&#x2714;If server side conversation history is turned on  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Se guardan en Communicator para Mac  <br/> |Se guardan en Skype Empresarial Mac  <br/> |
|Archivado del lado cliente de audio, vídeo, uso compartido de aplicaciones, uso compartido de escritorio y contenido cargado  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Archivado del lado cliente de transferencias de archivos, páginas compartidas de OneNote y anotaciones de PowerPoint  <br/> (unavailable in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|||||
|Access sign-in logs from Skype for Business icon in the task bar  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  For Skype for Business Online users, this feature requires Exchange Online and is controlled by the user's Exchange mailbox In-Place Hold attribute.
  
## <a name="client-limitations"></a>Limitaciones de cliente 
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Limitaciones del cliente básico
<a name="Full-Basic"> </a>

Las características que figuran a continuación están disponibles con el cliente completo y no con el cliente básico:  
  
- Administrar la configuración de llamada de equipo
    
- Administrar delegados
    
- Realizar llamadas en nombre de otro contacto (escenario de administrador/delegado)
    
- Administrar llamadas de otro usuario si se configura como delegado
    
- Administrar un gran volumen de llamadas
    
- Empezar una llamada a un grupo de respuesta
    
- Estacionar llamada
    
- Change greeting
    
- Atender llamada grupal
    
### <a name="online-or-hybrid-user-account-limitations"></a>Limitaciones de las cuentas de usuario en línea o híbridas
<a name="Online-Hybrid"> </a>

Las cuentas de usuario pueden existir en línea o en local, y esto puede influir en las características que estén disponibles para el usuario. Users with accounts on Skype for Business Online will not have access to the following features, even with the Full client: 
  
- Presencia mejorada: usar una fotografía de cualquier sitio público para Mi imagen
    
- Contactos: buscar grupos de respuesta
    
- Compatibilidad con la mensajería instantánea: integración de chat persistente (chat grupal)
    
- IM Support: Escalate a Persistent Chat room to a Skype for Business Meeting with one click
    
- Usuarios externos: realizar llamadas de dos o más participantes con usuarios externos
    
## <a name="see-also"></a>Vea también
<a name="Types"> </a>

[Plan for clients and devices](clients-and-devices.md)

