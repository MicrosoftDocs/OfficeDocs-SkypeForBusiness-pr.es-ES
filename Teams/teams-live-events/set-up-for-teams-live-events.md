---
title: Configure los eventos en directo en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Configure los eventos en directo de Teams, incluyendo la configuración de su red, la asignación de las licencias, la habilitación de las funciones y la programación de los eventos en directo, además de las soluciones de distribución de vídeo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0e2d35152ae8a840a6e0c0943144380e7169fe8b
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203943"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configure los eventos en directo en Microsoft Teams

Debe realizar varios pasos para configurar los eventos en directo.

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>Paso 1: configurar la red para los eventos en directo de Teams

Los eventos en directo creados en Teams requieren de la [preparación de la red de su organización para usar Teams](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener las licencias y asignarlas

Asegúrese de disponer de las asignaciones de licencia correctas para determinar [qué usuarios pueden crear y programar eventos en directo](plan-for-teams-live-events.md#who-can-attend-create-and-schedule-live-events) y [quién podrá verlos](plan-for-teams-live-events.md#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Paso 3: configurar las directivas de los eventos en directo

Las directivas de los eventos en directo se usan para controlar qué usuarios de la organización pueden realizar eventos en directo y las características disponibles en los eventos que creen. Puede usar la directiva predeterminada o crear una o más directivas personalizadas para los eventos en directo. Después de crear una directiva personalizada, asígnela a un usuario o a grupos de usuarios de su organización.

> [!NOTE]
> Los usuarios de la organización obtendrán la directiva global (opción predeterminada para toda la organización) a menos que cree y asigne una directiva personalizada. En la directiva global, la programación de eventos en directo está habilitada para los usuarios de equipo de forma predeterminada, al igual que los subtítulos en directo y los subtítulos (transcripción) está desactivada, todas las personas de la organización pueden unirse a los eventos en directo y la configuración de la grabación está establecida para grabar siempre.

### <a name="create-or-edit-a-live-events-policy"></a>Cree o edite una directiva de eventos en directo

<a name="bkcreatepolicy"> </a>

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Meetings**  >  **directivas de eventos en directo**de reuniones.
2. Realice una de las siguientes acciones:

    - Si desea editar la directiva predeterminada actual, elija **Global (predeterminado para toda la organización)**.
    - Si desea crear una nueva directiva personalizada, elija **Agregar**.
    - Si desea editar una directiva personalizada, selecciónela y, a continuación, elija **Editar**.

    Puede cambiar estas opciones de configuración para satisfacer las necesidades de su organización.

    ![Captura de pantalla de la configuración de los eventos en directo de Teams](../media/teams-live-events-policies.png "Captura de pantalla de la configuración de la directiva de eventos en directo en el centro de administración de Microsoft Teams")

|Setting  |Descripción  |
|---------|---------|
|**Title**     |Este es el título de la directiva que aparecerá en la página directivas de los eventos en directo. No puede contener caracteres especiales ni tener más de 64 caracteres.          |
|**Descripción**    |Use esta para agregar una descripción detallada sobre la directiva.         |
|**Permitir la programación**     |Al habilitar esta opción le permite a los usuarios de la organización crear y programar eventos en directo de Teams. Es importante que tenga en cuenta que, si quiere que los usuarios programen un evento en directo creado con una aplicación o dispositivo externo, debe realizar algunos pasos adicionales. Para obtener más información, vea [permitir que los usuarios programen eventos creados con una aplicación o un dispositivo externo](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).     |
|**Permitir la transcripción para los asistentes** |Esta configuración solo se puede aplicar en los eventos creados en Teams. Al activar esto, los asistentes del evento podrán ver los subtítulos en directo durante el evento.         |
|**Quién puede unirse a eventos en directo programados**    |Elija una de las siguientes opciones:<br><br>**Todos** los usuarios pueden crear eventos en directo para que todos los usuarios, incluidas las personas de fuera de la organización, puedan asistir. Esta configuración habilita el tipo de permiso **público** para equipos cuando un usuario programa un evento en directo a través de Teams.<br> **Todos los usuarios de la organización** Los usuarios pueden crear eventos en directo a los que puedan asistir las personas de la organización, incluyendo los [usuarios invitados](../add-guests.md) que hayan sido añadidos a la organización. Los usuarios no pueden crear eventos en directo a los que puedan asistir los usuarios anónimos. Esta configuración habilita el tipo de permiso **Toda la organización** cuando un usuario programa un evento en directo a través de Teams.<br> **Usuarios o grupos específicos** Los usuarios pueden crear eventos en directo a los que solo puedan asistir los usuarios o grupos específicos de su organización. Los usuarios no pueden crear eventos en directo a los que asistan tanto los usuarios anónimos como todos los de su organización. Esta configuración habilita el tipo de permiso de **usuarios y grupos** cuando un usuario programa un evento en directo a través de Teams.       |
|**Configuración de la grabación**  <br>     | Esta configuración solo se puede aplicar en los eventos creados en Teams. Elija una de las siguientes opciones: <br><br> **Grabar siempre** Los eventos en directo creados por los usuarios siempre serán grabados. Después de que el evento termine, los miembros del equipo del evento podrán descargar la grabación, y los asistentes también podrán ver el evento. <br> **Nunca grabar** Los eventos en directo creados por los usuarios nunca serán grabados. <br>**El organizador puede grabar o no** Los usuarios podrán decidir si quieren grabar el evento en directo. Si es grabado, entonces, después de que el evento termine los miembros del equipo del evento podrán descargar la grabación, y los asistentes también podrán ver el evento.      

También puede hacerlo mediante Windows PowerShell. Para obtener más información, vea [Usar PowerShell para establecer las directivas de eventos en directo en Microsoft Teams](set-teams-live-events-policies-using-powershell.md) 

### <a name="assign-a-live-events-policy-to-users"></a>Asignar una directiva de eventos en directo a los usuarios

Si ha creado una directiva personalizada de eventos en directo, asígnesela a los usuarios para que la directiva esté activa. <br><br>[!INCLUDE [assign-policy](../includes/assign-policy.md)]

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>Permitir que los usuarios programen eventos creados con una aplicación o un dispositivo externo

Los usuarios que programen eventos creados con una aplicación o un dispositivo, también deben hacer lo siguiente:

1. Habilitar Microsoft Stream para los usuarios de la organización Stream está disponible como parte de suscripciones de Microsoft 365 o de Office 365 válidos o como un servicio independiente. Stream no está incluido en los planes de Empresa Esenciales o Empresa Premium. Para obtener más información, vea [Información general sobre licencias de Stream](https://docs.microsoft.com/stream/license-overview)

>[!Note]
> El cambio de usar Microsoft Stream a [OneDrive para la empresa y SharePoint para las grabaciones](../tmr-meeting-recording-change.md) de la reunión será un enfoque por fases. En el lanzamiento podrá optar por esta experiencia, en noviembre tendrá que optar por no participar si desea seguir usando la secuencia y, a principios de 2021, necesitaremos que todos los clientes usen OneDrive para la empresa y SharePoint para nuevas grabaciones de reunión.

      Learn more about how you can [assign licenses to users](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) so that users can access Stream. Ensure Stream isn't blocked for the users as defined in [this article](https://docs.microsoft.com/stream/disable-user-organization).

2. Asegúrese de que los usuarios tengan los permisos de creación de eventos en directo de Stream Los administradores pueden crear eventos de forma predeterminada, con una aplicación o dispositivo externo El administrador de Stream puede [permitir que los usuarios adicionales puedan crear eventos en directo](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) en Stream.  

3. Asegúrese de que los organizadores de los eventos en directo hayan consentido la directiva de empresa establecida por el administrador de Stream. Si un administrador de Stream tiene que [configurar la directiva de directrices de la empresa](https://docs.microsoft.com/stream/company-policy-and-consent) y necesita que los empleados acepten esta directiva antes de guardar el contenido, los usuarios deberán hacerlo antes de crear un evento en directo (con una aplicación o dispositivo externo) en Teams. Antes de que implemente la función de eventos en directo en la organización, asegúrese de que los usuarios que van a crear estos eventos en directo hayan consentido la directiva. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Paso 4: Configurar una solución para la distribución de los vídeos de los eventos en directo de Teams

La reproducción de vídeos de eventos en directo usa el streaming con velocidad de bits adaptable (ABR), aunque se trata de una secuencia de unidifusión, lo cual significa que cada espectador recibe su propia secuencia de video a través de Internet. Para los eventos o vídeos en directo de su organización, podría haber una cantidad significativa de ancho de banda de Internet consumido por los espectadores. Las soluciones para las organizaciones que desean reducir este tráfico de Internet en los evento en directo deben integrarse con los partners de entrega de vídeo de confianza de Microsoft, los cuales ofrecen redes definidas por software (SDN) o redes de entrega de contenido empresarial (eCDN). Estas plataformas de SDN y eCDN permiten que las organizaciones optimicen el ancho de banda de la red sin sacrificar la experiencia final de visualización del usuario. Nuestros socios le pueden ayudar a habilitar una distribución de vídeo más eficaz y escalable a través de la red empresarial.

**Comprar y configurar la solución fuera de Teams** obtenga asistencia experta para ampliar la distribución de vídeo aprovechando los partners de confianza de Microsoft para la entrega de vídeo. Antes de poder habilitar un proveedor de entrega de vídeo para usar en Teams, debe comprar y configurar la solución de SDN y eCDN fuera y por separado de Teams.

Las siguientes soluciones de SDN y eCDN están preintegradas y pueden ser configuradas para usarse en Stream.

- **Hive Streaming** proporciona una solución eficaz y sencilla para la distribución de vídeo empresarial en directo y a petición. Hive es una solución basada en software que no requiere un hardware o ancho de banda adicional y proporciona una forma segura para permitir que miles de espectadores simultáneos de vídeo sin afectar a su red. Para los clientes que buscan entender el impacto que tiene el vídeo en su red antes de comprar una solución de SDN y eCDN, Hive Streaming también proporciona una solución de análisis basada en el explorador para los clientes de Microsoft. [Más información](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** es una plataforma en la nube con un emparejamiento inteligente que aprovecha la infraestructura de red existente para ofrecer contenidos en muchos formatos (vídeo de transmisión en directo, vídeo bajo demanda, actualizaciones de software, correcciones de seguridad, etc.) de manera más rápida y confiable, y con menos ancho de banda. Nuestra plataforma segura cuenta con la confianza de las instituciones financieras más grandes del mundo y, sin hardware adicional, es fácil de configurar y mantener. [Más información](https://kollective.com/microsoft-pilot/).
 
- **Tabla OmniCache** proporciona una distribución en red de nueva generación y garantiza una entrega de contenido de vídeo sin problemas a través de las redes WAN globales, ayudando a los productores de eventos a optimizar el ancho de banda de la red y el soporte de difusión de eventos en directo y las transmisiones a petición. La compatibilidad de la tabla OmniCache con los eventos en directo creados de Teams estará disponible próximamente. [Más información](https://rampecdn.com). 

- **Riverbed**, el estándar de la industria en la optimización de red, está extendiendo sus soluciones de aceleración a Microsoft Teams y streaming.  Ahora, los clientes de Microsoft 365 pueden acelerar el tráfico 365, incluidos los equipos y la transmisión, junto con una amplia variedad de servicios líderes de SaaS empresarial para aumentar la productividad del personal desde cualquier lugar. Los equipos y la aceleración de la transmisión por secuencias se pueden habilitar mediante una configuración sin esfuerzo, que incluye toda la seguridad del soporte de primer nivel de Riverbed y de la inversión continua.
 
> [!NOTE] 
> La solución de SDN y eCDN elegida estará sujeta a los **términos de servicio y a la directiva de privacidad del proveedor de terceros** y controlará el uso de la solución del proveedor. El uso de la solución del proveedor no estará sujeto a los términos de la licencia por volumen de Microsoft ni a los términos de servicios en línea. Si no está de acuerdo con los**términos del proveedor de terceros**, entonces no necesita habilitar la solución en Teams. 

Después de configurar la solución de SDN y eCDN, estará listo para configurar el proveedor de eventos en directo de Teams. 

## <a name="next-steps"></a>Siguientes pasos

Vaya a [Establecer la configuración de eventos en directo de Microsoft Teams](configure-teams-live-events.md)

### <a name="related-topics"></a>Temas relacionados

- [¿Qué son los eventos en directo en Teams?](what-are-teams-live-events.md)
- [Planear eventos en directo en Teams](plan-for-teams-live-events.md)
- [Establecer la configuración de eventos en directo de Microsoft Teams](configure-teams-live-events.md)
