---
title: Configurar para eventos en directo en Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Aprenda los pasos para configurar live para los eventos de los equipos, incluida la preparación de su red, asignación de licencias, uso de directivas para habilitar las características de evento en directo y programación para los usuarios y configurar un proveedor de distribución de terceros.
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: a92f227b7f625da02e003622c8ff87e744206443
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532666"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configurar para eventos en directo en Microsoft Teams

> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Cuando se está estableciendo para eventos en directo, hay varios pasos que debe seguir:

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Paso 1: Configurar la red para eventos en directo en Microsoft Teams
Eventos en directo de inicio rápido requieren para [Preparar la red de su organización para que los equipos de Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener licencias y asignarlas
Asegúrese de que tiene asignaciones de licencia correcta para [quién puede crear y programar eventos en directo?](#who-can-create-and-schedule-live-events) y [quién puede ver los eventos en directo?](#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Paso 3: Configurar las directivas de eventos en directo
Las directivas se utilizan para controlar quién en la organización puede contener eventos en directo y las características que están disponibles en los eventos que se crean de eventos en directo. Puede usar la directiva predeterminada o crear uno o más personalizado live directivas de eventos. Después de crear una directiva personalizada, asignar a un usuario o grupos de usuarios de la organización.

> [!NOTE]
> Los usuarios de su organización obtendrá la directiva global, a menos que se cree y asigne una directiva personalizada. De forma predeterminada en la directiva global, la programación de evento en directo está habilitada para los usuarios de los equipos, transcripción está desactivada, todas las personas de la organización pueden unir a eventos en directo y la configuración de grabación se establece para registrar siempre. 

### <a name="create-or-edit-a-live-events-policy"></a>Crear o editar una directiva de eventos en directo

**![los equipos-logotipo-30x30.png](../media/teams-logo-30x30.png) utilizando el Microsoft Teams & Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **las directivas de eventos en directo**. 
2. Siga uno de estos pasos:
- Si desea editar la directiva predeterminada existente, elija **Global (valor predeterminado de toda la organización)**. 
- Si desea crear una nueva directiva personalizada, elija **nueva directiva**. 
- Si desea editar una directiva personalizada, seleccione la directiva y, a continuación, elija **Editar**. 

    Estos son los valores que puede cambiar para ajustarse a las necesidades de su organización.

    ![Captura de pantalla de configuración de directiva de eventos de live] (../media/teams-live-events-policies.png "Captura de pantalla de configuración de directiva de eventos en los equipos de Microsoft & Skype para el centro de administración de negocio de live") 

|Configuración  |Descripción  |
|---------|---------|
|**Nombre.**     |Esto es el nombre de la directiva que aparece en la página de directivas de eventos en directo. No puede superar los 64 caracteres o tienen todos los caracteres especiales.          |
|**Descripción**    |Se usa para agregar una descripción simplificada de la directiva.         |
|**Permitir la programación**     |Activar Esto permite a los usuarios de su organización crear y programar eventos en directo en los equipos. Es importante saber que, si desea que los usuarios programen eventos en directo codificador externo, existen pasos adicionales que debe realizar. Para obtener más información, vea [Permitir a los usuarios programar eventos codificador externo](#enable-users-to-schedule-external-encoder-events).     |
|**Transcripción de permitir para los asistentes** (próximamente) |Esta configuración solo se puede aplicar a los eventos de inicio rápido. Activar Esto permite a los asistentes de evento en directo ver los títulos en tiempo real y traducción durante el evento.         |
|**Que pueden unir a eventos en directo programados**    |Elija una de las siguientes opciones.<br> <br> **Todos los usuarios** Los usuarios pueden crear eventos en directo que todos, incluidas las personas fuera de la organización, pueden asistir a. <br> **Todas las personas de la organización** Los usuarios pueden crear eventos en directo que pueden asistir sólo las personas de su organización. Los usuarios no pueden crear eventos en directo que se asistieron a los usuarios anónimos. <br> **Usuarios o grupos específicos** Los usuarios pueden crear eventos en directo que sólo determinados usuarios o grupos de la organización pueden asistir a. Los usuarios no pueden crear eventos en directo que se ha atendido por todas las personas de su organización o por los usuarios anónimos.        |
|**Configuración de grabación**  <br>     | Esta configuración solo se puede aplicar a los eventos de inicio rápido. Elija una de las siguientes opciones. <br><br> **Registrar siempre** Siempre se registran eventos en directo creados por los usuarios. Después de que el evento es a través de, los miembros del equipo de evento pueden descargar la grabación y los asistentes pueden verla el evento. <br> **Nunca registrar** Nunca se registran eventos en directo creados por los usuarios. <br>**Puede registrar el organizador o no** Los usuarios pueden decidir si va a registrar el evento en directo. Si está registrado, después de que el evento es a través de, los miembros del equipo de evento pueden descargar la grabación y los asistentes pueden verla el evento.      

También puede hacerlo mediante el uso de Windows PowerShell. Para obtener más información, vea [Uso de PowerShell para establecer las directivas de eventos en directo de los equipos](set-teams-live-events-policies-using-powershell.md). 

### <a name="assign-a-live-events-policy-to-users"></a>Asignar una directiva de eventos en directo a los usuarios 

Si ha creado una directiva personalizada eventos en directo, asignar a los usuarios para la directiva para estar activa. 

![los equipos-logotipo-30x30.png](../media/teams-logo-30x30.png) Uso de la Microsoft Teams & Skype para el centro de administración de negocio

1. En el panel de navegación izquierdo, vaya a **los usuarios**y, a continuación, seleccione el usuario.
2. Junto a **las directivas asignadas**, elija **Editar**. 
3. Seleccione la directiva de eventos en directo que desea asignar y, a continuación, elija **Guardar**. 

### <a name="enable-users-to-schedule-external-encoder-events"></a>Permitir a los usuarios programar eventos externos codificador

Para que los usuarios programar eventos codificador externo, también debe hacer lo siguiente:

1. Habilitar Microsoft Stream para los usuarios de su organización. Microsoft Stream está disponible como parte de suscripciones a Office 365 optan o como un servicio independiente. Microsoft Stream no está incluido en los planes de negocio Essentials o Business Premium. Para obtener más información, vea [información general sobre licencias de secuencia](https://docs.microsoft.com/stream/license-overview) .

      Obtenga más información acerca de cómo se pueden [asignar licencias a los usuarios de Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que los usuarios pueden tener acceso a Microsoft Stream. Asegúrese de que no se bloquea Microsoft Stream para los usuarios tal como se define en [este artículo](https://docs.microsoft.com/stream/disable-user-organization).

2. Asegúrese de que los usuarios tienen permiso de creación de evento en directo en Microsoft Stream. De forma predeterminada, los administradores pueden crear codificador externo eventos en directo. Administrador de Microsoft Stream puede [Permitir que los usuarios adicionales para la creación de evento en directo](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) en secuencia.  

3. Asegúrese de evento en directo han dado su consentimiento los organizadores de la directiva de empresa establecida por el Administrador de secuencia. Si un administrador de Microsoft Stream tiene que [Configurar una directiva de instrucciones de la compañía](https://docs.microsoft.com/stream/company-policy-and-consent) y requiere que los empleados Aceptar esta directiva antes de guardar el contenido, a continuación, los usuarios deben hacerlo antes de crear un evento en directo (con producción codificador externo) en los equipos. Antes de desplegar la característica de eventos en directo en la organización, asegúrese de que los usuarios que vayan a crear estos eventos en directo han dado su consentimiento a la directiva. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Paso 4: Configurar una solución de distribución de vídeo para eventos en directo en los equipos
Reproducción de vídeos de evento en directo usa adaptable velocidad de bits de transmisión por secuencias (ABR) pero es una secuencia de unidifusión, lo que significa que cada visor obtiene su propia secuencia de vídeo de internet. Para eventos en directo o los vídeos que se envía al gran parte de su organización, podría ser una cantidad considerable de ancho de banda de internet que consume los visores. Para las organizaciones que desean reducir este tráfico de internet para eventos en directo, eventos en directo soluciones se integran con de Microsoft de confianza definen de socios de entrega de vídeo que ofrecen software redes (SDNs) o redes de entrega de contenido empresarial (eCDNs). Estas plataformas SDN/eCDN permiten a las organizaciones a optimizar el ancho de banda de red sin sacrificar usuario final experiencias de visualización. Nuestros socios pueden ayudar a permitir una distribución de vídeo más escalable y eficaz a través de la red de la empresa.

**Compra y configurar la solución fuera de los equipos** Obtenga ayuda de expertos con ajuste de escala entrega vídeo mediante el aprovechamiento de los socios de entrega de vídeo de confianza de Microsoft. Para poder habilitar un proveedor de entrega de vídeo ser utilizados con los equipos que debe adquirir y configurar la solución SDN/eCDN externa e independiente de los equipos.

Las siguientes soluciones SDN/eCDN previamente están integradas y se pueden configurar para usarse con Microsoft Stream.

- **Subárbol de transmisión por secuencias** proporciona una solución sencilla y eficaz para la distribución de vídeo en directo y a petición enterprise. Subárbol es una solución basada en software que no requiere ningún hardware adicional o el ancho de banda y proporciona un modo seguro para habilitar miles de visores de vídeo simultáneos sin afectar a la red. Para clientes que desean para comprender el vídeo de impacto que tiene en su red antes de adquirir una solución de SDN/eCDN, también subárbol de transmisión por secuencias proporciona una solución de análisis basada en explorador para los clientes de Microsoft. [Más información](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** es una basada en la nube, smart interconexión distribución plataforma que aprovecha la infraestructura de red existente para entregar contenido, en muchas formas, (live transmisiones de vídeo, vídeo y a petición, las actualizaciones de software, las revisiones de seguridad, etc.) con mayor rapidez, confiable y con menos ancho de banda. Nuestra plataforma segura es de confianza por las instituciones financieras más grandes del mundo y sin hardware adicional y, a continuación, el programa de instalación y mantenimiento son fáciles. [Más información](http://www.kollective.com).
 
- **Mejorar OmniCache** proporciona la distribución de red de próxima generación y garantiza la entrega perfecta de contenido de vídeo a través de WAN global, ayudar a los productores de evento optimizar el ancho de banda de red y admitir las difusiones de evento correcta en directo y a petición transmisión por secuencias. La compatibilidad para mejorar OmniCache para eventos en directo inicio rápido estará disponible próximamente.  [Más información](http://www.ramp.com). 
 
> [!NOTE] 
> La solución SDN o eCDN elegida está sujeto a la seleccionado **términos 3ª del proveedor de servicio y política de privacidad**, donde se regula el uso de la solución del proveedor. El uso de la solución del proveedor no estará sujeto a los términos de licencia por volumen de Microsoft o los términos de servicios en línea. Si no acepta los **términos de 3ª del proveedor**, a continuación, no habilite la solución en los equipos. 

Después de configurar la solución SDN o eCDN, estará listo configurar el proveedor para eventos en directo en los equipos. 

## <a name="next-steps"></a>Pasos siguientes
Vaya a [Configurar live configuración de eventos en los equipos](configure-teams-live-events.md).

### <a name="related-topics"></a>Temas relacionados
- [¿Cuáles son los equipos de eventos en directo?](what-are-teams-live-events.md)
- [Plan para los equipos eventos en directo](plan-for-teams-live-events.md)
- [Configurar live configuración de eventos en los equipos](configure-teams-live-events.md)

