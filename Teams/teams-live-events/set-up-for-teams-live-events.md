---
title: Definir eventos en directo en Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre los pasos necesarios para configurar los eventos en Teams, incluida la preparación de la red, la asignación de licencias, el uso de directivas para habilitar las características de eventos en vivo y la programación de usuarios, y la configuración de un proveedor de distribución de terceros.
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7f69f036e01c86dd02eabf7f229a80f0c51c520
ms.sourcegitcommit: 9d9376c6e5e6d79e33ba54fb8ce87509a2f57754
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2019
ms.locfileid: "35013000"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Definir eventos en directo en Microsoft Teams

Cuando está configurando para eventos en vivo, debe realizar varios pasos:

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>Paso 1: configurar la red para eventos en directo en Teams
Los eventos en directo generados en Teams requieren que [Prepare la red de su organización para Teams](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener licencias y asignarlas
Asegúrese de que tiene las asignaciones de licencia correctas para [quién puede crear y programar eventos en vivo](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events) y [quién puede ver los eventos en directo](plan-for-teams-live-events.md#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Paso 3: configurar directivas de eventos en directo
Las directivas de eventos en directo se usan para controlar qué usuarios de su organización pueden mantener eventos en vivo y las características que están disponibles en los eventos que crean. Puede usar la directiva predeterminada o crear una o más directivas de eventos en directo personalizados. Después de crear una directiva personalizada, asígnela a un usuario o a un grupo de usuarios de la organización.

> [!NOTE]
> Los usuarios de la organización obtendrán la directiva global a menos que cree y asigne una directiva personalizada. De forma predeterminada, en la directiva global, la programación de eventos en directo está habilitada para los usuarios de Teams, la transcripción está desactivada, todas las personas de la organización pueden unirse a eventos en vivo y la configuración de la grabación está establecida en grabar siempre. 

### <a name="create-or-edit-a-live-events-policy"></a>Crear o editar una directiva de eventos en directo
<a name="bkcreatepolicy"> </a>

**![Un icono que muestra el logotipo](../media/teams-logo-30x30.png) de Microsoft Teams con el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, vaya a**directivas de eventos en directo**de **reuniones** > . 
2. Siga uno de estos pasos:
- Si desea modificar la directiva predeterminada existente, elija **global (opción predeterminada para toda la organización)**. 
- Si desea crear una nueva directiva personalizada, elija **nueva Directiva**. 
- Si desea editar una directiva personalizada, selecciónela y, a continuación, elija **Editar**. 

    A continuación se muestran las opciones de configuración que puede cambiar para adaptarse a las necesidades de su organización.

    ![Captura de pantalla de la configuración de directiva de eventos en directo] (../media/teams-live-events-policies.png "Captura de pantalla de la configuración de directiva de eventos en directo en el centro de administración de Microsoft Teams") 

|Configuración  |Descripción  |
|---------|---------|
|**Nombre.**     |Este es el nombre de la Directiva que aparece en la página de directivas de eventos en directo. No puede tener más de 64 caracteres ni caracteres especiales.          |
|**Descripción**    |Use esta para agregar una descripción detallada a la Directiva.         |
|**Permitir la programación**     |Activar esta opción permite a los usuarios de la organización crear y programar eventos en vivo en Teams. Es importante saber que si desea que los usuarios programen un evento en directo producido con una aplicación o dispositivo externo, hay pasos adicionales que debe realizar. Para obtener más información, vea [permitir a los usuarios programar eventos generados con una aplicación o un dispositivo externo](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).     |
|**Permitir la transcripción para los asistentes** (próximamente) |Esta configuración solo se puede aplicar a eventos generados en Teams. Activar esta habilitación permite a los asistentes de eventos en directo ver los subtítulos y la traducción en tiempo real durante el evento.         |
|**Quién puede unirse a eventos en directo programados**    |Elija una de las opciones siguientes.<br><br>**Todos los usuarios** Los usuarios pueden crear eventos en vivo que todos, incluidas las personas de fuera de su organización, pueden asistir. Esta configuración habilita el tipo de permiso **público** en Teams cuando un usuario programa un evento en vivo.<br> **Todas las personas de la organización** Los usuarios pueden crear eventos en vivo que solo pueden asistir las personas de su organización. Los usuarios no pueden crear eventos en vivo atendidos por usuarios anónimos. Esta configuración habilita el tipo de permiso de **toda la organización** en Teams cuando un usuario programa un evento en vivo.<br> **Usuarios o grupos específicos** Los usuarios pueden crear eventos en vivo que solo pueden asistir a usuarios o grupos específicos de su organización. Los usuarios no pueden crear eventos en vivo atendidos por todos los usuarios de su organización o por usuarios anónimos. Esta opción habilita el tipo de permiso **personas y grupos** en Teams cuando un usuario programa un evento en vivo.       |
|**Configuración de grabación**  <br>     | Esta configuración solo se puede aplicar a eventos generados en Teams. Elija una de las opciones siguientes. <br><br> **Grabar siempre** Los eventos en directo creados por los usuarios siempre se graban. Después de que el evento haya finalizado, los miembros del equipo del evento pueden descargar la grabación y los asistentes pueden ver el evento. <br> No **grabar nunca** Los eventos en directo creados por los usuarios nunca se graban. <br>**Organizador puede grabar o no** Los usuarios pueden decidir si deseas grabar el evento en vivo. Si se graba, después de que el evento haya finalizado, los miembros del equipo del evento pueden descargar la grabación y los asistentes pueden ver el evento.      

También puede hacerlo con Windows PowerShell. Para obtener más información, vea [usar PowerShell para configurar directivas de eventos en vivo en Teams](set-teams-live-events-policies-using-powershell.md). 

### <a name="assign-a-live-events-policy-to-users"></a>Asignar una directiva de eventos en directo a los usuarios 

Si ha creado una directiva de eventos en directo personalizada, asígnela a los usuarios para que la Directiva esté activa. 

![Un icono que muestra el logotipo de Microsoft Teams](../media/teams-logo-30x30.png) Usar el centro de administración de Microsoft Teams

1. En el navegación de la izquierda, vaya a **usuarios**y, después, seleccione el usuario.
2. Junto a **directivas asignadas**, elija **Editar**. 
3. Seleccione la Directiva de eventos en vivo que desea asignar y, a continuación, elija **Guardar**. 

También puede asignar una directiva de eventos en vivo a uno o más usuarios de la siguiente manera:

![Un icono que muestra el logotipo de Microsoft Teams](../media/teams-logo-30x30.png) Usar el centro de administración de Microsoft Teams

1. Vaya a **** > **las directivas eventos en directo**de reuniones.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva.
3. Seleccione **administrar usuarios**.
4. En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **Guardar**.
 

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>Permitir a los usuarios programar eventos generados con una aplicación o un dispositivo externo

Para que los usuarios puedan programar eventos producidos con una aplicación o dispositivo externo, también debe hacer lo siguiente:

1. Habilite Microsoft Stream para los usuarios de su organización. Stream está disponible como parte de suscripciones de Office 365 válidas o como un servicio independiente. La secuencia no se incluye en los planes de Business Essentials o Business Premium. Para obtener más información, vea [información general sobre las licencias de secuencias](https://docs.microsoft.com/stream/license-overview) .

      Obtenga más información sobre cómo puede [asignar licencias a usuarios en Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que los usuarios puedan obtener acceso a la secuencia. Asegúrese de que la secuencia no está bloqueada para los usuarios, tal y como se define en [este artículo](https://docs.microsoft.com/stream/disable-user-organization).

2. Asegúrese de que los usuarios tienen permisos de creación de eventos en directo en Stream. De forma predeterminada, los administradores pueden crear eventos con una aplicación o un dispositivo externo. El administrador de la transmisión puede [Habilitar usuarios adicionales para la creación de eventos en directo](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) en Stream.  

3. Asegúrese de que los organizadores de eventos en vivo hayan respondido a la Directiva de la empresa establecida por el administrador de la transmisión. Si un administrador de la secuencia ha [configurado una política de directrices](https://docs.microsoft.com/stream/company-policy-and-consent) de la empresa y requiere que los empleados acepten esta Directiva antes de guardar el contenido, los usuarios deben hacerlo antes de crear un evento en vivo (con una aplicación o dispositivo externo) en Teams. Antes de implementar la característica eventos en directo en la organización, asegúrese de que los usuarios que vayan a crear estos eventos en directo han remitido a la Directiva. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Paso 4: configurar una solución de distribución de vídeo para eventos en directo en Teams
La reproducción de vídeos de eventos en vivo usa la transmisión por secuencias de bits adaptativa (ABR), pero es una secuencia de unidifusión, lo que significa que cada visor está recibiendo su propia secuencia de vídeo de Internet. En el caso de eventos en directo o vídeos enviados a grandes partes de su organización, puede haber una cantidad considerable de ancho de banda de Internet consumido por los visores. Para las organizaciones que desean reducir este tráfico de Internet para eventos en directo, las soluciones de eventos en vivo se integran con los socios de entrega de vídeo de Microsoft que ofrecen redes definidas por software (SDNs) o redes de entrega de contenido empresarial (eCDNs). Estas plataformas SDN/eCDN permiten a las organizaciones optimizar el ancho de banda de la red sin sacrificar las experiencias de visualización del usuario final. Nuestros socios pueden ayudar a habilitar una distribución de video más eficaz y escalable en toda la red de la empresa.

**Comprar y configurar su solución fuera de Teams** Obtén ayuda de expertos con el escalado de la distribución de video aprovechando los socios de entrega de video de confianza de Microsoft. Antes de poder habilitar un proveedor de entrega de video para usarlo con equipos, debe comprar y configurar la solución SDN/eCDN fuera y separada de Teams.

Las siguientes soluciones de SDN/eCDN están preintegradas y se pueden configurar para usarlas con secuencias.

- La **transmisión por subárbol** ofrece una solución simple y eficaz para la distribución de video empresarial en vivo y a petición. Hive es una solución basada en software que no requiere hardware adicional ni ancho de banda y proporciona una manera segura de habilitar a miles de visores de vídeo simultáneos sin afectar a la red. Para los clientes que desean comprender el impacto que tiene el vídeo en su red antes de comprar una solución SDN/eCDN, la transmisión por secuencias de Hive también proporciona una solución de análisis basada en explorador para clientes de Microsoft. [Más información](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** es una plataforma de distribución de emparejamiento inteligente, basada en la nube, que aprovecha la infraestructura de red existente para ofrecer contenido, en muchos formatos (video de transmisión en vivo, video a petición, actualizaciones de software, revisiones de seguridad, etc.) más rápido, más confiable y con menos ancho de banda. Nuestra plataforma segura es de confianza para las instituciones financieras más grandes del mundo, sin necesidad de hardware, configuración y mantenimiento adicionales. [Más información](http://www.kollective.com).
 
- La **rampa OmniCache** ofrece una distribución de red de próxima generación y garantiza la entrega transparente de contenido de video en redes WAN internacionales, ayudando a los productores de eventos a optimizar el ancho de banda de la red y las difusiones de eventos en vivo exitosas y a petición transmiti. La compatibilidad con la rampa OmniCache para eventos en directo producidos en Teams estará disponible próximamente. [Más información](http://www.ramp.com). 
 
> [!NOTE] 
> La solución SDN o eCDN elegida está sujeta a las **condiciones de servicio y la política de privacidad del proveedor de terceros**seleccionado, que controlará el uso que usted hará de la solución del proveedor. El uso de la solución del proveedor no estará sujeto a los términos de licencias por volumen de Microsoft ni a las condiciones de los servicios en línea. Si no acepta las **condiciones del proveedor de terceros**, no habilite la solución en Teams. 

Después de configurar el SDN o la solución eCDN, está listo para configurar el proveedor de eventos en directo de Teams. 

## <a name="next-steps"></a>Pasos siguientes
Vaya a [configuración de eventos en directo en Teams](configure-teams-live-events.md).

### <a name="related-topics"></a>Temas relacionados
- [¿Qué son los eventos en directo en Teams?](what-are-teams-live-events.md)
- [Planear eventos en directo en Teams](plan-for-teams-live-events.md)
- [Configurar los eventos en directo en Teams](configure-teams-live-events.md)

