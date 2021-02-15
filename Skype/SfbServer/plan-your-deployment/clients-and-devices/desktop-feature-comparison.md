---
title: Comparación de características de cliente de escritorio para Skype Empresarial Server 2015
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Resumen: los administradores de Skype Empresarial Server 2015 o Skype Empresarial Online pueden usar estas tablas para comprender qué características se admiten en qué clientes.'
ms.openlocfilehash: 5ee4546e62593ca61e9833bbdf1c09efeef4ce13
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832190"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2015"></a>Comparación de características de cliente de escritorio para Skype Empresarial Server 2015

**Resumen:** Los administradores de Skype Empresarial Server 2015 o Skype Empresarial Online pueden usar estas tablas para comprender qué características se admiten en qué clientes.
  
 Antes de implementar o actualizar a Skype Empresarial, compruebe qué clientes ya están en uso en su organización. Use las tablas siguientes para comprender el impacto de la compatibilidad de características en esos clientes. Esto puede ayudarle a comunicar los cambios a los usuarios, al ritmo del proceso de implementación y a comprender perfectamente las ventajas de actualizar al cliente más reciente.
  
Some features available with Skype for Business Server 2015 are not available in Skype for Business Online, see [Online or Hybrid user account limitations](desktop-feature-comparison.md#Online-Hybrid) for specifics. Es posible que los administradores de Skype Empresarial Online quieran consultar la descripción del servicio Skype Empresarial [Online](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) para obtener información sobre los diferentes planes disponibles para ellos.

Vea la comparación de características de cliente [de escritorio para Skype Empresarial 2019](../../../SfBServer2019/plan/feature-comparison.md) para obtener soporte para clientes en Skype Empresarial Server 2019.
  
En las tablas siguientes se muestran las características disponibles con cada cliente que funciona con Skype Empresarial Server 2015 o Skype Empresarial Online. También puede hacer referencia a la comparación de características de cliente móvil para [Skype Empresarial](mobile-feature-comparison.md) para comparaciones de características de cliente de tabletas y teléfonos inteligentes. La licencia de acceso de cliente o la licencia de suscripción de usuario que compra su organización también tendrán un impacto en las características que están disponibles para los usuarios. La implementación del cliente completo o básico para los usuarios depende de la licencia o del plan que la organización decida comprar. Consulta la [Guía de licencias](https://products.office.com/skype-for-business/it-pros) para obtener más información.
  
> [!IMPORTANT]
> Skype Empresarial Server 2015 y Skype Empresarial Online admiten los siguientes clientes publicados anteriormente: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Phone Edition y Lync 2010 Attendant. Para obtener información acerca de estos clientes cuando se usan con otros servidores, consulte las tablas de comparación de clientes para [Lync Server 2013](https://technet.microsoft.com/library/gg425836%28v=ocs.15%29.aspx) y las tablas de comparación de clientes para [Lync Server 2010.](https://technet.microsoft.com/library/gg425836%28v=ocs.14%29.aspx)

> [!NOTE]
> El **cliente de Lync 2010 Attendant** no es compatible con Skype Empresarial Online.

> [!NOTE]
> El cliente de explorador de Skype Empresarial Web App y la aplicación de Reuniones de Skype para Windows 10 solo proporcionan [compatibilidad con reuniones.](desktop-feature-comparison.md#BKMK_Conferencing) Consulte [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md) para obtener más información sobre estos clientes.
  
## <a name="enhanced-presence-support"></a>Compatibilidad con presencia mejorada

<a name="BKMK_EnhancedPresence"> </a>

En esta tabla se tratan las características de presencia mejorada que se extienden más allá de una simple indicación de si un usuario está conectado, sin conexión, ocupado, etc.
  
|Característica/funcionalidad|Cliente de Skype Empresarial 2015 o 2016|Skype Empresarial en Mac|Cliente de Lync 2013|Aplicación de la Tienda Windows de Lync|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator for Mac 2011|Lync para Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Estado de publicación |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|Ver estado   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ver notas de estado y mensajes Fuera de la oficina |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar una ubicación personalizada |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Agregar una nota personalizada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Usar una foto de cualquier sitio público para Mi imagen (no disponible en Skype Empresarial Online) |&#x2714;||&#x2714;|||||||

 &#x2776; no admite el estado de publicación en función de la información de disponibilidad del calendario.
  
## <a name="contacts-and-contact-groups-support"></a>Compatibilidad con contactos y grupos de contactos

<a name="BKMK_Contacts"> </a>

En esta tabla se tratan las características relacionadas con la administración de contactos de mensajería instantánea y presencia.

|Característica/funcionalidad|Cliente de Skype Empresarial 2015 o 2016|Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Lista de contactos rellenada previamente |&#x2714;|||||||||
|Ver y modificar lista de contactos |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Etiqueta de contacto para alertas de cambio de estado |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|Controlar las relaciones de privacidad |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Buscar en la libreta de direcciones de la compañía |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Buscar en los contactos de Microsoft Outlook |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar los grupos de contactos |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Expandir grupos de distribución y Grupos de Microsoft 365 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Buscar los grupos de respuesta  <br/> (no disponible en Skype Empresarial Online) |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Mostrar el grupo de contactos reciente |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Mostrar el grupo de conversaciones actuales |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|Mostrar vistas de contactos alternativas (por ejemplo, mosaico) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Ordenar contactos por grupo, relación o nuevo (personas que le han agregado a su lista de contactos) |&#x2714;||&#x2714;|Ordenar por grupo |&#x2714;|&#x2714;||||
|Ordenar contactos por estado (disponibilidad) |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Buscar y agregar contactos de Exchange |&#x2714;||&#x2714;||||||&#x2714;|

## <a name="im-support"></a>Compatibilidad con mensajería instantánea

<a name="BKMK_IMSupport"> </a>

En esta tabla se tratan las características relacionadas con la compatibilidad con mensajería instantánea.

|Característica/funcionalidad | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensajería instantánea con o correo electrónico a un contacto |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Navegar entre varias conversaciones de mensajería instantánea/Realizar un seguimiento de varias conversaciones en una sola ventana con pestañas |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Registrar las conversaciones de mensajería instantánea en Outlook |&#x2714;|&#x2714;Si el historial de conversaciones del lado servidor está activado  |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Se guardan en Communicator para Mac |Se guardan en Lync para Mac |
|Usar las plantillas de conversación preparadas |||||&#x2714;|&#x2714;||||
|Revisar la ortografía |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Búsqueda de aptitudes (con integración de SharePoint Server)  <br/> (Skype Empresarial Server local y SharePoint 2013 local son necesarios para la búsqueda de aptitudes). |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|Integración de chat persistente (chat en grupo)  <br/> (no disponible para Skype Empresarial Online) |&#x2714;||&#x2714;|||||||
|Escalar un salón de chat persistente a una reunión de Skype Empresarial con un solo clic  <br/> (no disponible para Skype Empresarial Online) |&#x2714;||&#x2714;|||||||
|Imágenes en línea del remitente y el receptor en la ventana de mensajería instantánea |&#x2714;||&#x2714;|&#x2714;||||||
|Enviar mensajes de entrada de lápiz ||||&#x2714;||||||
|Recibir mensajes de entrada de lápiz |&#x2714;||&#x2714;|&#x2714;||||||
|Establecer mensajes de mensajería instantánea como de importancia alta |&#x2714;||&#x2714;|||||||
|Transferir archivos en conversaciones de mensajería instantánea punto a punto |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|

## <a name="meetings-support"></a>Compatibilidad con reuniones

<a name="BKMK_Conferencing"> </a>

En esta tabla se tratan las características relacionadas con la compatibilidad con reuniones.
  
> [!NOTE]
> Las características de reuniones de Skype Empresarial no están disponibles en el Plan independiente 1 de Skype Empresarial Online.  El plan 1 se [está retirando.](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement)

En las sesiones de Skype a Skype, un usuario del Plan 1 de Skype Empresarial Online puede participar en el uso compartido de escritorio y en el uso compartido de aplicaciones si lo invita un usuario que tiene acceso a las características de uso compartido.
Para obtener más información, consulte la [descripción del servicio de Skype Empresarial Online.](https://technet.microsoft.com/library/jj822172.aspx)
  
|Característica/funcionalidad | Cliente de Skype Empresarial 2016 | Skype Empresarial en Mac | Aplicación web de Skype Empresarial | Cliente de Skype Empresarial 2015 | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Agregar audio de equipo |&#x2714;|&#x2714;|&#x2714;(requiere complemento) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agregar vídeo |&#x2714;|&#x2714;|&#x2714;(requiere complemento) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|Ver vídeo entre varias entidades (vista galería) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Uso compartido de la pantalla basado en el vídeo |&#x2714;|&#x2714;|&#x2714;solo vista |||||||||
|Usar controles de moderador de reunión |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Obtener acceso a lista de reuniones detallada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Participar en mensajería instantánea con varios participantes |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Compartir el escritorio (si se habilita) |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (requiere complemento) |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|Compartir un programa (si se habilita) |&#x2714;|Ver solamente   |&#x2714;(requiere complemento) |&#x2714;|&#x2714;||&#x2714;||||Ver solamente |
|Agregar participantes anónimos (si se habilita) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Usar reuniones de audio de acceso telefónico |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|Iniciar una reunión reunirse ahora |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Agregar y presentar archivos de Microsoft PowerPoint |&#x2714;| &#x2778; anotaciones no disponibles |&#x2714;|&#x2714;|&#x2714;|Solo presente |&#x2714;|||| &#x2778; solo vista, las anotaciones no están disponibles |
|Navegar por archivos de Microsoft PowerPoint |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Agregar y editar notas de reunión de OneNote |&#x2714;||Solo edición (no agregar) |&#x2714;|&#x2714;|||||||
|Usar una pizarra |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Realizar sondeos |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Cargar archivos para compartirlos con otros usuarios |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Programar una conferencia o reunión |Programador web de Outlook o Skype Empresarial |Programador web de Outlook o Skype Empresarial |Programador web de Skype Empresarial |Programador web de Outlook o Skype Empresarial |Programador de Outlook o Lync Web |Programador de Outlook o Lync Web |Outlook ||||Outlook |
|Administrador &amp; de preguntas y respuestas |&#x2714;|||||||||||
|Deshabilitar vídeo de asistente|&#x2714;||&#x2714;|||||||||
 | |Deshabilitar mensajería instantánea de reunión  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|Silenciar audiencia   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Convertir a todos en asistentes |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Producir Difusión de reunión de Skype  |&#x2714;|||||||||||
|El delegado puede programar una reunión en nombre del delegador  |&#x2714;|&#x2714;|&#x2714;|||||||||
|Sincronizar delegados entre Skype Empresarial y Outlook |&#x2714;||&#x2714;|||||||||
|Establecer contenido destacado de vídeo (bloquear vídeo) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Dar o tomar el control del uso compartido de pantalla |&#x2714;||&#x2714;|||||||||

 &#x2776; participantes no pueden controlar escritorios compartidos por Skype Empresarial en Mac, Lync para Mac 2011 o Communicator para usuarios de Mac 2011. Los usuarios de Skype Empresarial en Mac, Lync para Mac 2011 y Communicator para Mac 2011 no pueden controlar los escritorios compartidos por los usuarios de Windows. Esto tampoco funcionará para Skype Empresarial Web App en Max OSX.
  
 &#x2777; Skype Empresarial Online, esta característica requiere conferencias RTC de Microsoft, mensajería unificada de Exchange o un proveedor de audioconferencia de terceros.
  
 &#x2778; el cliente de Lync para Mac 2011 no puede ver presentaciones de PowerPoint de Microsoft Office 2013 cuando la aplicación web de Skype Empresarial las ha compartido en una conferencia.
  
## <a name="voice-telephony-support"></a>Compatibilidad con voz (telefonía)

<a name="BKMK_Telephony"> </a>

En esta tabla se tratan las características relacionadas con la compatibilidad con servicios de voz.
  
> [!NOTE]
> Las características de Skype Empresarial Voice (telefonía) están limitadas a determinados planes de suscripción de Skype Empresarial Online. Para obtener más información, consulte la [descripción del servicio de Skype Empresarial Online.](https://technet.microsoft.com/library/jj822172.aspx)
  
| Característica/funcionalidad | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar una llamada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Hacer clic para llamar a un contacto  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir una llamada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar la transferencia de llamadas |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar la configuración de llamada de equipo |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Administrar delegados |&#x2714;|&#x2714;requiere Skype Empresarial Server 2015 CU4 o posterior |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|Iniciar una llamada a un grupo de respuesta |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Soporte de servicios de emergencia (E-911)  |&#x2714;|&#x2714;requiere Skype Empresarial Server 2015 CU6 o posterior |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notificación de mensajería instantánea a URI de SIP para llamada E-911 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notificación de mensajería instantánea a la lista de distribución para la llamada E-911 |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Conectarse al correo de voz, configurar o cambiar el saludo |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Notificación de llamada perdida |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Realizar llamadas en nombre de otro contacto (escenario de administrador/delegado) |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|Administrar las llamadas de otro contacto si se está configurado como delegado |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|Administrar volúmenes altos de llamadas |||||&#x2714;|&#x2714;||||
|Estacionamiento de llamadas  |&#x2714;||&#x2714; &#x2776; |||||||
|Recogida de llamada de grupo  |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|Enrutamiento basado en la ubicación  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Administrar grupo de respuesta/grupo de llamadas de equipo |&#x2714;||&#x2714;|||||||
|Responder llamada de operador automático |&#x2714;||&#x2714;|||||||

&#x2776; Esta característica no está disponible en Skype Empresarial Online.
  
## <a name="external-users-support"></a>Compatibilidad con usuarios externos

<a name="BKMK_ExternalUsers"> </a>

En esta tabla se tratan las características relacionadas con la compatibilidad con usuarios externos que están en la RTC.

|Característica/funcionalidad | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensajería instantánea con un contacto público  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Iniciar mensajería instantánea con un contacto asociado externo |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Realizar llamadas de dos o más participantes con usuarios externos  <br/> (no disponible en Skype Empresarial Online) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

## <a name="recording-support"></a>Compatibilidad con grabaciones

<a name="BKMK_Recording"> </a>

En esta tabla se tratan las características relacionadas con la compatibilidad con la grabación de reuniones.
  
| Futuro/capacidad** | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Grabación del lado cliente de audio, vídeo, uso compartido de aplicaciones, uso compartido de escritorio y contenido cargado |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Registro del lado cliente de transferencias de archivos, páginas compartidas de OneNote y anotaciones de PowerPoint |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|Seleccionar resolución de grabación preferida |&#x2714;||&#x2714;|||||||

 &#x2776; grabación no está disponible en determinados planes independientes de Skype Empresarial Online. La grabación requiere derechos completos de cliente de Skype Empresarial.
  
 &#x2777; registro de transferencias de archivos, páginas compartidas de OneNote y anotaciones de PowerPoint no está disponible en Skype Empresarial Online.
  
## <a name="modern-authentication"></a>Autenticación moderna

<a name="BKMK_Recording"> </a>

En esta tabla se tratan las características que requieren compatibilidad con la autenticación moderna.
  
La autenticación moderna también requiere una topología descrita en las topologías de [Skype Empresarial compatibles con la autenticación moderna.](../../plan-your-deployment/modern-authentication/topologies-supported.md)

| Característica/funcionalidad | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticación moderna |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticación multifactor  |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticación basada en certificados  |&#x2714;(solo dispositivo unido a un dominio)| &#x2714;|&#x2714;(solo dispositivo unido a un dominio)  |||||||
|Autenticación Kerberos |&#x2714;||&#x2714;|||||||

## <a name="archiving-compliance-and-logging-support"></a>Compatibilidad con archivado, cumplimiento y registro

<a name="BKMK_Archiving"> </a>

En esta tabla se tratan las características relacionadas con la compatibilidad con las funciones de archivado y registro.

| Característica/funcionalidad | Cliente de Skype Empresarial 2015 o 2016 | Skype Empresarial en Mac | Cliente de Lync 2013 | Aplicación de la Tienda Windows de Lync | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator for Mac 2011** | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Archivado de conversaciones de mensajería instantánea en el historial de conversaciones de Outlook |&#x2714; &#x2776; |&#x2714;Si el historial de conversaciones del lado servidor está habilitado |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Se guardan en Communicator para Mac |Se guardan en Lync para Mac |
|Archivado del lado cliente de audio, vídeo, uso compartido de aplicaciones, uso compartido de escritorio y contenido cargado |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Archivado del lado cliente de transferencias de archivos, páginas compartidas de OneNote y anotaciones de PowerPoint  <br/> (no disponible en Skype Empresarial Online)|&#x2714;||&#x2714;||&#x2714;|||||
|Acceder a los registros de inicio de sesión desde el icono de Skype Empresarial en la barra de tareas |&#x2714;||&#x2714;|||||||

 &#x2776; Para los usuarios de Skype Empresarial Online, esta característica requiere Exchange Online y se controla mediante el atributo de retención de In-Place buzón de Correo de Exchange del usuario.
  
## <a name="client-limitations"></a>Limitaciones del cliente

<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Limitaciones de cliente básico

<a name="Full-Basic"> </a>

Las siguientes características están disponibles con el cliente completo y no están disponibles con el cliente básico:

- Administrar la configuración de llamada de equipo
- Administrar delegados
- Administrar las llamadas de otro contacto si se está configurado como delegado
- Administrar un volumen alto de llamadas
- Iniciar una llamada a un grupo de respuesta
- Estacionamiento de llamadas
- Cambiar saludo
- Recogida de llamada de grupo
- Los correos electrónicos de notificación de llamadas perdidas no se generan cuando el estado de un usuario está deshabilitado y usan un cliente de Outlook heredado (2013 o versiones anteriores)

### <a name="online-or-hybrid-user-account-limitations"></a>Limitaciones de la cuenta de usuario híbrida o en línea

<a name="Online-Hybrid"> </a>

Las cuentas de usuario pueden existir en línea o de forma local, lo que afectará a las características disponibles para ese usuario. Los usuarios con cuentas en Skype Empresarial Online no tendrán acceso a las siguientes características, incluso con el cliente completo:
  
- Presencia mejorada: usar una foto de cualquier sitio público para Mi imagen
- Contactos: buscar grupos de respuesta
- Compatibilidad con mensajería instantánea: integración de chat persistente (chat en grupo)
- Soporte de mensajería instantánea: escalar un salón de chat persistente a una reunión de Skype Empresarial con un solo clic
- Usuarios externos: realizar llamadas entre dos o varias entidades con usuarios externos

## <a name="see-also"></a>Vea también

<a name="Types"> </a>

[Planeación de clientes y dispositivos](clients-and-devices.md)

[Actualizaciones más recientes para las versiones de Skype Empresarial que usan Windows Installer (MSI)](../../sfb-client-updates.md)
