---
title: Comparación de características de cliente de escritorio para Skype empresarial Server 2015
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Resumen: Skype empresarial Server 2015 o los administradores de Skype empresarial online pueden usar estas tablas para comprender qué características son compatibles con los clientes.'
ms.openlocfilehash: b2a5bd1f0544713501bfce2fc0dffc9776ec64e2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803680"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2015"></a>Comparación de características de cliente de escritorio para Skype empresarial Server 2015

**Resumen:** Skype empresarial Server 2015 o los administradores de Skype empresarial online pueden usar estas tablas para comprender qué características son compatibles con cada cliente.
  
 Antes de implementar o actualizar a Skype empresarial, compruebe qué clientes ya están en uso en su organización. Use las tablas siguientes para comprender el impacto en el soporte técnico de las características de esos clientes. Esto puede ayudarle a comunicar los cambios a los usuarios, decidir el ritmo del proceso de lanzamiento y conocer en profundidad las ventajas que tiene actualizar al cliente más reciente.
  
Algunas de las características disponibles en Skype empresarial Server 2015 no están disponibles en Skype empresarial online, consulte [limitaciones de cuentas de usuario híbridas o en línea](desktop-feature-comparison.md#Online-Hybrid) para determinados aspectos. Es posible que los administradores de Skype empresarial online deseen consultar la [Descripción del servicio de Skype empresarial online](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) para obtener información sobre los distintos planes disponibles para ellos.

Consulte [comparación de características de cliente de escritorio de Skype empresarial 2019](../../../SfBServer2019/plan/feature-comparison.md) para compatibilidad con clientes en Skype empresarial Server 2019.
  
En las tablas siguientes se muestran las características que están disponibles con cada cliente que funciona con Skype empresarial Server 2015 o Skype empresarial online. Es posible que también desee consultar la [comparación de características de los clientes móviles](mobile-feature-comparison.md) para las comparaciones de características de Skype empresarial para smartphones y tabletas. La licencia de acceso de cliente o la licencia de suscripción de usuario que adquiera su organización también influirá en qué características están disponibles para sus usuarios. La decisión de implementar el cliente completo o el básico en los usuarios depende de la licencia o el plan que su organización decida comprar. Para obtener más información, consulte la [Guía de licencias](https://products.office.com/en-us/skype-for-business/it-pros) .
  
> [!IMPORTANT]
> Skype empresarial Server 2015 y Skype empresarial online son compatibles con los siguientes clientes lanzados anteriormente: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Phone Edition y el operador de Lync 2010. Para obtener información sobre estos clientes cuando se usan con otros servidores, vea las [tablas de comparación de clientes para Lync server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) y [las tablas de comparación de clientes para Lync Server 2010](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.14%29.aspx).

> [!NOTE]
> El cliente del **operador de Lync 2010** no es compatible con Skype empresarial online.

> [!NOTE]
> El cliente del explorador de la aplicación Web de Skype empresarial y la aplicación reuniones de Skype 10 solo proporcionan [soporte técnico para reuniones](desktop-feature-comparison.md#BKMK_Conferencing). Para obtener más información sobre estos clientes [, consulte planear para clientes de reuniones (aplicación web y aplicación de reuniones)](meetings-clients.md) .
  
## <a name="enhanced-presence-support"></a>Compatibilidad con presencia mejorada

<a name="BKMK_EnhancedPresence"> </a>

En esta tabla se presentan las características de presencia mejorada que implican algo más que una simple indicación de que un usuario está en línea, sin conexión, ocupado, etc.
  
|Característica/función|Cliente de Skype Empresarial 2015 o 2016|Skype Empresarial en Mac|Cliente de Lync 2013|Aplicación de la Tienda Windows de Lync|Lync 2010 | Operador de Lync 2010|Lync Phone Edition|Communicator para Mac 2011|Lync para Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Publicar estado |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|Ver estado   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver notas de estado y mensajes Fuera de la oficina |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar una ubicación personalizada |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Agregar una nota personalizada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Usar una foto de cualquier sitio público para mi foto (no disponible en Skype empresarial online) |&#x2714;||&#x2714;|||||||

 &#x2776; no admite el estado de publicación en función de la información de disponibilidad del calendario.
  
## <a name="contacts-and-contact-groups-support"></a>Compatibilidad con contactos y grupos de contactos

<a name="BKMK_Contacts"> </a>

En esta tabla se presentan las características relacionadas con la administración de contactos de presencia y mensajería instantánea.

|Característica / función|Cliente de Skype Empresarial 2015 o 2016|Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Lync 2010 | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Lista de contactos rellenada anteriormente |&#x2714;|||||||||
|Ver y modificar la lista de contactos |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Marcar contactos para alertas de cambio de estado |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|Controlar relaciones de privacidad |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Buscar en la libreta de direcciones corporativa |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Buscar en los contactos de Microsoft Outlook |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar grupos de contactos |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Expandir grupos de distribución y grupos de Office 365 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Buscar grupos de respuesta  <br/> (no disponible en Skype empresarial online) |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Mostrar el grupo de contactos reciente |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Mostrar el grupo de conversaciones actuales |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|Mostrar vistas de contactos alternativas (por ejemplo, mosaico) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Ordenar contactos por grupo, relación o nuevo (personas que le han agregado a su lista de contactos) |&#x2714;||&#x2714;|Ordenar por grupo |&#x2714;|&#x2714;||||
|Ordenar contactos por Estado (disponibilidad) |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Buscar y agregar contactos de Exchange |&#x2714;||&#x2714;||||||&#x2714;|

## <a name="im-support"></a>Compatibilidad con la mensajería instantánea

<a name="BKMK_IMSupport"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con mensajería instantánea.

|Característica / función | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Lync 2010 | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar la mensajería instantánea con un contacto o enviarle un correo electrónico |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Navegar entre varias conversaciones de mensajería instantánea o realizar un seguimiento de varias conversaciones en una ventana de única pestaña |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Registrar las conversaciones de mensajería instantánea en Outlook |&#x2714;|&#x2714;si el historial de conversaciones del lado del servidor está activado  |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Se guardan en Communicator para Mac |Se guardan en Skype Empresarial Mac |
|Usar las plantillas de conversación preparadas |||||&#x2714;|&#x2714;||||
|Revisar la ortografía |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Búsqueda de aptitudes (con integración con SharePoint Server)   <br/> (Los servidores locales de Skype empresarial y los de SharePoint 2013 son necesarios para la búsqueda de aptitudes). |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|Integración de sistemas de chat en grupo o chat persistente  <br/> (no disponible para Skype empresarial online) |&#x2714;||&#x2714;|||||||
|Escalar un salón de chat persistente a una reunión de Skype Empresarial con un solo clic   <br/> (no disponible para Skype empresarial online) |&#x2714;||&#x2714;|||||||
|Imágenes entre líneas del remitente y el receptor en la ventana de mensajería instantánea |&#x2714;||&#x2714;|&#x2714;||||||
|Enviar mensajes manuscritos ||||&#x2714;||||||
|Recibir mensajes manuscritos |&#x2714;||&#x2714;|&#x2714;||||||
|Establecer mensajes de mensajería instantánea como de importancia alta |&#x2714;||&#x2714;|||||||
|Transferir archivos en conversaciones de mensajería instantánea de punto a punto |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|

## <a name="meetings-support"></a>Compatibilidad con reuniones

<a name="BKMK_Conferencing"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con reuniones.
  
> [!NOTE]
> Las funciones de reunión de Skype empresarial no están disponibles en el plan independiente 1 de Skype empresarial online.  El plan 1 se va a [retirar](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement).

En sesiones de Skype a Skype, los usuarios del plan 1 de Skype Empresarial Online pueden participar en el uso compartido del escritorio y de aplicaciones si les invita un usuario que tiene acceso a las características de uso compartido.
Para obtener más información, consulte la [Descripción del servicio de Skype empresarial online](https://technet.microsoft.com/library/jj822172.aspx).
  
|Característica/función | Cliente de Skype empresarial 2016 | Skype Empresarial en Mac | Aplicación web de Skype Empresarial | Cliente de Skype empresarial 2015 | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Lync 2010 | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Agregar audio de equipo |&#x2714;|&#x2714;|&#x2714; (requiere complemento) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar vídeo |&#x2714;|&#x2714;|&#x2714; (requiere complemento) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|Ver un vídeo entre varias partes (vista de galería) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Pantalla compartida basada en vídeo |&#x2714;|&#x2714;|&#x2714;solo lectura |||||||||
|Usar los controles de moderador en la reunión |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Obtener acceso a lista de reuniones detallada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Participar en mensajería instantánea para varios participantes |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Compartir el escritorio (si se habilita) |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776;  (requiere complemento) |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|Compartir un programa (si se habilita) |&#x2714;|Ver solamente   |&#x2714; (requiere complemento) |&#x2714;|&#x2714;||&#x2714;||||Ver solamente |
|Agregar participantes anónimos (si se habilita) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Usar reuniones de audio de acceso telefónico local |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|Empezar una reunión de tipo Reunirse ahora |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Agregar y presentar archivos de Microsoft PowerPoint |&#x2714;| &#x2778; anotaciones no disponibles |&#x2714;|&#x2714;|&#x2714;|Presentar solamente |&#x2714;|||| Solo vista de &#x2778;, anotaciones no disponibles |
|Explorar archivos de Microsoft PowerPoint |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Agregar y editar las notas de reunión de OneNote |&#x2714;||Solo editar (no agregar) |&#x2714;|&#x2714;|||||||
|Usar una pizarra |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Realizar sondeos |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Cargar archivos para compartir con otros usuarios |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Programar una reunión o conferencia |Programador web de Outlook o Skype empresarial |Programador web de Outlook o Skype empresarial |Programador web de Skype empresarial |Programador web de Outlook o Skype empresarial |Programador web de Outlook o Lync |Programador web de Outlook o Lync |Outlook ||||Outlook |
|Un&amp;administrador de preguntas y respuestas |&#x2714;|||||||||||
|Deshabilitar vídeo de asistentes|&#x2714;||&#x2714;|||||||||
 | |Deshabilitar la mensajería instantánea de la reunión  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|Desactivar audio de la audiencia   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Convertir a todos en asistentes |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Producir difusión de reunión de Skype  |&#x2714;|||||||||||
|El delegado puede programar una reunión en nombre del delegador  |&#x2714;|&#x2714;|&#x2714;|||||||||
|Sincronizar delegados entre Skype Empresarial y Outlook |&#x2714;||&#x2714;|||||||||
|Establecer el primer plano del vídeo (bloquear vídeo) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Ceder/tomar el control de la pantalla compartida |&#x2714;||&#x2714;|||||||||

 &#x2776; los participantes no pueden controlar los escritorios compartidos por usuarios de Skype empresarial en Mac, Lync para Mac 2011 o Communicator para Mac 2011. Skype empresarial en Mac, Lync para Mac 2011 y Communicator para Mac 2011 los usuarios no pueden controlar los escritorios compartidos por usuarios de Windows. Esto tampoco funcionará en la aplicación Web de Skype empresarial en Max OSX.
  
 &#x2777; para Skype empresarial online, esta característica requiere conferencias RTC de Microsoft, mensajería unificada de Exchange o un proveedor de servicios de audioconferencia de terceros.
  
 &#x2778; el cliente de Lync para Mac 2011 no puede ver presentaciones de PowerPoint de Microsoft Office 2013 cuando se han compartido en una conferencia desde la aplicación Web de Skype empresarial.
  
## <a name="voice-telephony-support"></a>Compatibilidad con voz (telefonía)

<a name="BKMK_Telephony"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con servicios de voz.
  
> [!NOTE]
> Las características de voz (telefonía) de Skype empresarial se limitan a determinados planes de suscripción de Skype empresarial online. > para obtener más información, consulte la [Descripción del servicio de Skype empresarial online](https://technet.microsoft.com/library/jj822172.aspx).
  
| Característica / función | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Lync 2010 | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar una llamada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Hacer clic para llamar a un contacto  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir una llamada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar el desvío de llamadas |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar la configuración de llamada de equipo |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Administrar delegados |&#x2714;|&#x2714;requiere Skype empresarial Server 2015 CU4 o posterior |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|Empezar una llamada a un grupo de respuesta |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Compatibilidad con servicios de emergencia (E-911)  |&#x2714;|&#x2714;requiere Skype empresarial Server 2015 CU6 o posterior |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notificación de mi a URI de SIP para llamada E-911 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notificación de mensajería instantánea a la lista de distribución para llamadas E-911 |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Conectar a correo de voz, configurar o cambiar saludo |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Notificación de llamada perdida |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Realizar llamadas en nombre de otro contacto (escenario de administrador/delegado) |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|Administrar llamadas de otro usuario si se configura como delegado |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|Administrar volúmenes altos de llamadas |||||&#x2714;|&#x2714;||||
|Estacionar llamada  |&#x2714;||&#x2714; &#x2776; |||||||
|Atender llamada grupal  |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|Enrutamiento basado en ubicación  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar el grupo de llamada de equipo/grupo de respuesta |&#x2714;||&#x2714;|||||||

 &#x2776; esta característica no está disponible en Skype empresarial online.
  
## <a name="external-users-support"></a>Compatibilidad con usuarios externos

<a name="BKMK_ExternalUsers"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con usuarios externos alojados en RTC.

|Característica / función | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Lync 2010 | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensajería instantánea con un contacto público  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Iniciar mensajería instantánea con un contacto federado |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Realizar llamadas de dos o más participantes con usuarios externos  <br/> (no disponible en Skype empresarial online) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

## <a name="recording-support"></a>Compatibilidad con grabaciones

<a name="BKMK_Recording"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con la grabación de reuniones.
  
| Futuro/capacidad * * | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Lync 2010 | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Grabación del lado cliente de audio, vídeo, uso compartido de aplicaciones, uso compartido de escritorio y contenido cargado |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Grabación del lado cliente de transferencias de archivos, páginas compartidas de OneNote y anotaciones de PowerPoint |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|Seleccionar la resolución preferida para la grabación |&#x2714;||&#x2714;|||||||

 &#x2776; grabación no está disponible en determinados planes independientes de Skype empresarial online. La grabación requiere derechos de cliente completos de Skype Empresarial.
  
 &#x2777; grabación de transferencias de archivos, páginas de OneNote compartidas y anotaciones de PowerPoint no está disponible en Skype empresarial online.
  
## <a name="modern-authentication"></a>Autenticación moderna

<a name="BKMK_Recording"> </a>

Esta tabla reúne las características que requieren soporte para la autenticación moderna.
  
La autenticación moderna también requiere una topología descrita en las [topologías de Skype empresarial compatibles con la autenticación moderna](../../plan-your-deployment/modern-authentication/topologies-supported.md).

| Característica / función | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Lync 2010 | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticación moderna |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticación multifactor  |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticación basada en certificado  |&#x2714; (solo dispositivo unido al dominio)| &#x2714;|&#x2714; (solo dispositivo unido al dominio)  |||||||
|Autenticación Kerberos |&#x2714;||&#x2714;|||||||

## <a name="archiving-compliance-and-logging-support"></a>Compatibilidad con archivado, cumplimiento y registro

<a name="BKMK_Archiving"> </a>

En esta tabla se presentan las características relacionadas con la compatibilidad con archivado y registro.

| Característica/función | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Operador de Lync 2010 | Lync Phone Edition | **Communicator para Mac 2011** | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Archivado de conversaciones de mensajería instantánea en el Historial de conversaciones de Outlook |&#x2714; &#x2776; |&#x2714;si el historial de conversaciones del lado servidor está habilitado |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Se guardan en Communicator para Mac |Se guardan en Skype Empresarial Mac |
|Archivado del lado cliente de audio, vídeo, uso compartido de aplicaciones, uso compartido de escritorio y contenido cargado |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Archivado del lado cliente de transferencias de archivos, páginas compartidas de OneNote y anotaciones de PowerPoint  <br/> (no disponible en Skype empresarial online)|&#x2714;||&#x2714;||&#x2714;|||||
|Acceder a los registros de inicio de sesión desde el icono de Skype empresarial en la barra de tareas |&#x2714;||&#x2714;|||||||

 &#x2776; para los usuarios de Skype empresarial online, esta característica requiere Exchange Online y está controlada por el atributo de conservación local del buzón del usuario de Exchange.
  
## <a name="client-limitations"></a>Limitaciones de cliente 

<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Limitaciones del cliente básico

<a name="Full-Basic"> </a>

Las características que figuran a continuación están disponibles con el cliente completo y no con el cliente básico: 

- Administrar la configuración de llamada de equipo
- Administrar delegados
- Administrar llamadas de otro usuario si se configura como delegado
- Administrar un gran volumen de llamadas
- Empezar una llamada a un grupo de respuesta
- Estacionar llamada
- Cambiar saludo
- Atender llamada grupal
- Los correos electrónicos de notificación de llamadas perdidas no se generan cuando el estado de un usuario es UM deshabilitado y están usando un cliente heredado de Outlook (2013 o versiones anteriores)

### <a name="online-or-hybrid-user-account-limitations"></a>Limitaciones de las cuentas de usuario en línea o híbridas

<a name="Online-Hybrid"> </a>

Las cuentas de usuario pueden existir en línea o en local, y esto puede influir en las características que estén disponibles para el usuario. Los usuarios con cuentas en Skype empresarial online no tendrán acceso a las siguientes características, incluso con el cliente completo:
  
- Presencia mejorada: usar una fotografía de cualquier sitio público para Mi imagen
- Contactos: buscar grupos de respuesta
- Compatibilidad con la mensajería instantánea: integración de chat persistente (chat grupal)
- Soporte técnico de mensajería instantánea: escalar un salón de chat persistente a una reunión de Skype empresarial con un solo clic
- Usuarios externos: realizar llamadas de dos o más participantes con usuarios externos

## <a name="see-also"></a>Vea también

<a name="Types"> </a>

[Planificar los clientes y los dispositivos](clients-and-devices.md)

[Actualizaciones más recientes de las versiones de Skype Empresarial que usan Windows Installer (MSI)](../../sfb-client-updates.md)
