---
title: Configure los eventos en directo en Microsoft Teams
author: serdarsoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: Configure eventos en directo en Teams, incluida la configuración de su red, la asignación de licencias, la habilitación de características y programación de eventos en directo y las soluciones de distribución de vídeo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a2e7061252afc5c485da01c3c1c30e9625bd07cc
ms.sourcegitcommit: 3f046142c40b3b776165e964f2b8718e2fe55df3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65661671"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configure los eventos en directo en Microsoft Teams

Debe realizar varios pasos para configurar los eventos en directo.

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>Paso 1: configurar la red para los eventos en directo de Teams

Los eventos en directo creados en Teams requieren de la [preparación de la red de su organización para usar Teams](../prepare-network.md).  

## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener las licencias y asignarlas

Asegúrese de disponer de las asignaciones de licencia correctas para determinar [qué usuarios pueden crear y programar eventos en directo](plan-for-teams-live-events.md#who-can-attend-create-and-schedule-live-events) y [quién podrá verlos](plan-for-teams-live-events.md#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Paso 3: configurar las directivas de los eventos en directo

Las directivas de los eventos en directo se usan para controlar qué usuarios de la organización pueden realizar eventos en directo y las características disponibles en los eventos que creen. Puede usar la directiva predeterminada o crear una o más directivas personalizadas para los eventos en directo. Después de crear una directiva personalizada, asígnela a un usuario o a grupos de usuarios de su organización.

> [!NOTE]
> Los usuarios de su organización obtendrán la directiva global (predeterminada para toda la organización), a menos que cree y asigne una directiva personalizada. En la directiva global, la programación de eventos en directo está habilitada para los usuarios de equipo de forma predeterminada, al igual que los subtítulos en directo y los subtítulos (transcripción) está desactivada, todas las personas de la organización pueden unirse a los eventos en directo y la configuración de la grabación está establecida para grabar siempre.

### <a name="create-or-edit-a-live-events-policy"></a>Cree o edite una directiva de eventos en directo

<a name="bkcreatepolicy"> </a>

1. En el panel de navegación izquierdo del Microsoft Teams centro de administración, vaya a la pestaña **Directivas de administración** de **directivas** >  de **eventos** >  en directo de Reuniones.
2. Realice una de las siguientes opciones:

    - Si desea editar la directiva predeterminada actual, elija **Global (predeterminado para toda la organización)**.
    - Si desea crear una nueva directiva personalizada, elija **+Agregar**.
    - Si desea editar una directiva personalizada, selecciónela y, a continuación, elija **Editar**.

    Puede cambiar estas opciones de configuración para satisfacer las necesidades de su organización.

    ![Captura de pantalla de la configuración de directiva de eventos en directo.](../media/teams-live-events-policies-new.png "Captura de pantalla de la configuración de la directiva de eventos en directo en el centro de administración de Microsoft Teams")

|Setting  |Descripción  |
|---------|---------|
|**Title**     |Este es el título de la directiva que aparecerá en la página directivas de los eventos en directo. No puede contener caracteres especiales ni tener más de 64 caracteres.          |
|**Descripción**    |Use esta para agregar una descripción detallada sobre la directiva.         |
|**Programación de eventos en directo**     |Al habilitar esta opción le permite a los usuarios de la organización crear y programar eventos en directo de Teams. Es importante que tenga en cuenta que, si quiere que los usuarios programen un evento en directo creado con una aplicación o dispositivo externo, debe realizar algunos pasos adicionales. Para obtener más información, vea [permitir que los usuarios programen eventos creados con una aplicación o un dispositivo externo](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).     |
|**Transcripción para los asistentes** |Esta configuración solo se puede aplicar en los eventos creados en Teams. Al activar esto, los asistentes del evento podrán ver los subtítulos en directo durante el evento.         |
|**Quién puede unirse a eventos en directo programados**    |Elija una de las siguientes opciones:<br><br>**Todos** los usuarios pueden crear eventos en directo para que todos los usuarios, incluidas las personas de fuera de la organización, puedan asistir. Esta configuración habilita el tipo de permiso **público** para equipos cuando un usuario programa un evento en directo a través de Teams.<br> **Todos los usuarios de la organización** Los usuarios pueden crear eventos en directo a los que puedan asistir las personas de la organización, incluyendo los [usuarios invitados](../add-guests.md) que hayan sido añadidos a la organización. Los usuarios no pueden crear eventos en directo a los que puedan asistir los usuarios anónimos. Esta configuración habilita el tipo de permiso **Toda la organización** cuando un usuario programa un evento en directo a través de Teams.<br> **Usuarios o grupos específicos** Los usuarios pueden crear eventos en directo a los que solo puedan asistir los usuarios o grupos específicos de su organización. Los usuarios no pueden crear eventos en directo a los que asistan tanto los usuarios anónimos como todos los de su organización. Esta configuración habilita el tipo de permiso de **usuarios y grupos** cuando un usuario programa un evento en directo a través de Teams.       |
|**Configuración de la grabación**  <br>     | Esta configuración solo se puede aplicar en los eventos creados en Teams. Elija una de las siguientes opciones: <br><br> **Grabar siempre** Los eventos en directo creados por los usuarios siempre serán grabados. Después de que el evento termine, los miembros del equipo del evento podrán descargar la grabación, y los asistentes también podrán ver el evento. <br> **Nunca grabar** Los eventos en directo creados por los usuarios nunca serán grabados. <br>**El organizador puede grabar o no** Los usuarios podrán decidir si quieren grabar el evento en directo. Si es grabado, entonces, después de que el evento termine los miembros del equipo del evento podrán descargar la grabación, y los asistentes también podrán ver el evento.

También puede hacerlo usando Windows PowerShell y, actualmente, los clientes de GCC Alto y DD deben usar este método. Para obtener más información, vea [Usar PowerShell para establecer las directivas de eventos en directo en Microsoft Teams](set-teams-live-events-policies-using-powershell.md)

### <a name="assign-a-live-events-policy-to-users"></a>Asignar una directiva de eventos en directo a los usuarios

Si ha creado una directiva personalizada de eventos en directo, asígnesela a los usuarios para que la directiva esté activa. <br><br>[!INCLUDE [assign-policy](../includes/assign-policy.md)]

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>Permitir que los usuarios programen eventos creados con una aplicación o un dispositivo externo

Para que los usuarios programen eventos producidos con una aplicación o dispositivo externo, también debe realizar los pasos siguientes:

1. Habilitar Microsoft Stream para los usuarios de la organización Stream está disponible como parte de las suscripciones de Microsoft 365 o Office 365 válidas o como un servicio independiente. Stream no está incluido en los planes de Empresa Esenciales o Empresa Premium. Para obtener más información, vea [Información general sobre licencias de Stream](/stream/license-overview)

   >[!Note]
   > El cambio del uso de Microsoft Stream a [OneDrive para la Empresa y SharePoint para grabaciones de reuniones](../tmr-meeting-recording-change.md) estará basado en fases. Durante el lanzamiento podrá participar en esta experiencia, pero en noviembre tendrá que optar por no participar si quiere continuar usando Stream y, en algún momento, a principios de 2021, les pediremos a todos los clientes que usen OneDrive para la Empresa y SharePoint para grabar sus nuevas reuniones. Obtenga más información sobre cómo [**asignar licencias a los usuarios para**](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) que los usuarios puedan acceder a Stream. Asegúrese de que Stream no está bloqueado para los usuarios, como se define en [**este artículo**](/stream/disable-user-organization).

2. Asegúrese de que los usuarios tengan los permisos de creación de eventos en directo de Stream Los administradores pueden crear eventos de forma predeterminada, con una aplicación o dispositivo externo El administrador de Stream puede [permitir que los usuarios adicionales puedan crear eventos en directo](/stream/live-event-administration#restrict-who-can-create-events) en Stream.

3. Asegúrese de que los organizadores de los eventos en directo hayan consentido la directiva de empresa establecida por el administrador de Stream. Si un administrador de Stream tiene que [configurar la directiva de directrices de la empresa](/stream/company-policy-and-consent) y necesita que los empleados acepten esta directiva antes de guardar el contenido, los usuarios deberán hacerlo antes de crear un evento en directo (con una aplicación o dispositivo externo) en Teams. Antes de que implemente la función de eventos en directo en la organización, asegúrese de que los usuarios que van a crear estos eventos en directo hayan consentido la directiva.

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Paso 4: Configurar una solución para la distribución de los vídeos de los eventos en directo de Teams

La reproducción de vídeos de eventos en directo usa el streaming con velocidad de bits adaptable (ABR), aunque se trata de una secuencia de unidifusión, lo cual significa que cada espectador recibe su propia secuencia de video a través de Internet. Para los eventos o vídeos en directo de su organización, podría haber una cantidad significativa de ancho de banda de Internet consumido por los espectadores. Las soluciones para las organizaciones que desean reducir este tráfico de Internet en los evento en directo deben integrarse con los partners de entrega de vídeo de confianza de Microsoft, los cuales ofrecen redes definidas por software (SDN) o redes de entrega de contenido empresarial (eCDN). Estas plataformas de SDN y eCDN permiten que las organizaciones optimicen el ancho de banda de la red sin sacrificar la experiencia final de visualización del usuario. Nuestros socios le pueden ayudar a habilitar una distribución de vídeo más eficaz y escalable a través de la red empresarial.

**Comprar y configurar la solución fuera de Teams** obtenga asistencia experta para ampliar la distribución de vídeo aprovechando los partners de confianza de Microsoft para la entrega de vídeo. Antes de habilitar un proveedor de entrega de vídeo para que se use con Teams, debe comprar y configurar la solución SDN/eCDN fuera y independiente de Teams.

Las siguientes soluciones de SDN y eCDN están preintegradas y pueden ser configuradas para usarse en Stream.

- **Hive Streaming** proporciona una solución eficaz y sencilla para la distribución de vídeo empresarial en directo y a petición. Hive es una solución basada en software que no requiere un hardware o ancho de banda adicional y proporciona una forma segura para permitir que miles de espectadores simultáneos de vídeo sin afectar a su red. Para los clientes que buscan entender el impacto que tiene el vídeo en su red antes de comprar una solución de SDN y eCDN, Hive Streaming también proporciona una solución de análisis basada en el explorador para los clientes de Microsoft. [Más información](https://www.hivestreaming.com/partners/integration-partners/microsoft/).

- **Kollective** es una plataforma de distribución de emparejamiento inteligente basada en la nube que aprovecha su infraestructura de red existente para entregar contenido de muchas formas (vídeo en streaming en directo, vídeo bajo demanda, actualizaciones de software, revisiones de seguridad, etc.) de forma más rápida, confiable y con menos ancho de banda. Nuestra plataforma segura cuenta con la confianza de las instituciones financieras más grandes del mundo y, sin hardware adicional, es fácil de configurar y mantener. [Más información](https://kollective.com/microsoft-pilot/).

- **Tabla OmniCache** proporciona una distribución en red de nueva generación y garantiza una entrega de contenido de vídeo sin problemas a través de las redes WAN globales, ayudando a los productores de eventos a optimizar el ancho de banda de la red y el soporte de difusión de eventos en directo y las transmisiones a petición. La compatibilidad de la tabla OmniCache con los eventos en directo creados de Teams estará disponible próximamente. [Más información](https://rampecdn.com).

- **Riverbed**, el estándar del sector en optimización de red, está ampliando sus soluciones de aceleración a Microsoft Teams y Stream.  Ahora, Microsoft 365 clientes pueden acelerar con confianza el tráfico de 365, incluidos Teams y Stream, junto con una gran cantidad de otros servicios SaaS empresariales líderes para aumentar la productividad de la fuerza de trabajo desde cualquier lugar. Teams y la aceleración de Stream se pueden habilitar a través de una configuración sin esfuerzo que viene con toda la garantía del apoyo y la inversión continua de Riverbed de primera clase.

> [!NOTE]
> La solución de SDN y eCDN elegida estará sujeta a los **términos de servicio y a la directiva de privacidad del proveedor de terceros** y controlará el uso de la solución del proveedor. El uso de la solución del proveedor no estará sujeto a los términos de la licencia por volumen de Microsoft ni a los términos de servicios en línea. Si no está de acuerdo con los **términos del proveedor de terceros**, entonces no necesita habilitar la solución en Teams.

Después de configurar la solución de SDN y eCDN, estará listo para configurar el proveedor de eventos en directo de Teams.

## <a name="next-steps"></a>Siguientes pasos

Vaya a [Establecer la configuración de eventos en directo de Microsoft Teams](configure-teams-live-events.md)

### <a name="related-topics"></a>Temas relacionados

- [¿Qué son los eventos en directo de Teams?](what-are-teams-live-events.md)
- [Planear eventos en directo en Teams](plan-for-teams-live-events.md)
- [Establecer la configuración de eventos en directo de Microsoft Teams](configure-teams-live-events.md)
