---
title: Administrar configuración de reuniones
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo administrar la configuración para las reuniones de los equipos que los usuarios programar en la organización.
ms.openlocfilehash: 4ded26dae69b5afef1d9fafb4819a73475c44898
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231903"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Administrar la configuración de reuniones en Microsoft Teams

Como administrador, usa la configuración de las reuniones de los equipos para controlar si los usuarios anónimos pueden participar en las reuniones de los equipos, personalizar las invitaciones a reuniones y si desea habilitar la calidad de servicio (QoS), establecer los intervalos de puertos para el tráfico en tiempo real. Esta configuración aplica a todas las reuniones de los equipos que programación a los usuarios de la organización. Administrar estas opciones de configuración de **reuniones** > **configuración de reunión** en el centro de administración de Microsoft Teams.

## <a name="allow-anonymous-users-to-join-meetings"></a>Permitir a los usuarios anónimos unirse a reuniones

Unión anónima, cualquier usuario puede unirse a la reunión como un usuario anónimo haciendo clic en el vínculo en la invitación a la reunión.

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de reunión**.
2. En **los participantes**, activar **los usuarios anónimos pueden unirse a una reunión**.

    ![reunión-configuración-participants.png] (media/meeting-settings-participants.png "Captura de pantalla de configuración de los participantes de las reuniones de los equipos en el centro de administración de equipos de Microsoft")

Si no desea que los usuarios anónimos a participar en reuniones programadas por los usuarios de su organización, desactive esta opción.

## <a name="customize-meeting-invitations"></a>Personalizar invitaciones a reuniones

Puede personalizar las invitaciones a reuniones de los equipos para satisfacer las necesidades de su organización. Puede agregar el logotipo de su organización e incluye información útil, como vínculos a su sitio Web de soporte técnico y renuncia de responsabilidad legal y un pie de página de sólo texto.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Sugerencias para la creación de un logotipo para las invitaciones a reuniones  

1. Crear una imagen que es no más de 188 píxeles de ancho por 30 píxeles de alto (es bastante pequeña).
2. Guarde la imagen en formato JPG.
3. Almacenar la imagen en una ubicación central que todas las personas de su organización pueden tener acceso, como un recurso compartido de red.

### <a name="customize-your-meeting-invitations"></a>Personalizar las invitaciones de reunión

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de reunión**.
2. En la **invitación por correo electrónico**, haga lo siguiente:

    ![reunión-configuración-invitation.png] (media/meeting-settings-invitation.png "Captura de pantalla de la reunión configuración de invitación que se puede personalizar para las reuniones de los equipos")

    - **Dirección URL del logotipo** Escriba la dirección URL donde está almacenado el logotipo.
    - **Dirección URL legal** Si su organización tiene un sitio Web legal que desea que las personas para ir a si tiene alguna duda legal, escriba la dirección URL aquí.
    - **Dirección URL de ayuda** Si su organización tiene un sitio Web de soporte técnico que desea que las personas para ir a si se ejecutan en problemas, escriba la dirección URL aquí.
    - **Pie de página** Escriba el texto que desea incluir como un pie de página.
3. Tiempo de espera una hora o lo propagar los cambios. A continuación, programar una reunión de los equipos para ver qué aspecto tiene la invitación a la reunión.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Establecer cómo desea controlar el tráfico de medios en tiempo real para las reuniones de los equipos

<a name="bknetwork"> </a>

Si está utilizando de calidad de servicio [(QoS)](qos-in-teams.md) para dar prioridad al tráfico de red, puede habilitar QoS marcadores y puede establecer los intervalos de puertos para cada tipo de tráfico de medios.

 ![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de reunión**.
2. En la **red**, haga lo siguiente:

    ![reunión-configuración-network.png] (media/meeting-settings-network.png "Captura de pantalla de la configuración de red para las reuniones de los equipos en el centro de administración de equipos de Microsoft")

    - Para permitir que los marcados de DSCP que se usará para QoS, activar **marcadores de insertar calidad de servicio (QoS) para el tráfico de medios en tiempo real**. Sólo tienen la opción de utilizar marcadores o no; no se puede establecer marcadores personalizados para cada tipo de tráfico. Para obtener más marcadores DSCP en, consulte [Seleccionar un método de implementación de QoS](QoS-in-Teams.md#select-a-qos-implementation-method) .
    - Para especificar intervalos de puertos, junto al **Seleccionar un rango de puerto para cada tipo de tráfico de medios en tiempo real**, seleccione **especificar intervalos de puertos**y, a continuación, escriba los puertos inicial y final de audio, vídeo y uso compartido de la pantalla. Si selecciona esta opción es necesario para implementar QoS.
    > [!IMPORTANT]
    > Si selecciona **utilizar automáticamente los puertos disponibles**, disponibles puertos entre 1024 y 65535 se usan. Use esta opción sólo cuando no la implementación de QoS.
    >
    > Selección de un intervalo de puertos que es demasiado estrecho llevará a llamadas interrumpidas y calidad de llamadas deficientes. Las siguientes recomendaciones deben ser mínimo.

 Si no está seguro de qué puerto rangos para usar en su entorno, las siguientes opciones son un buen punto de partida. Para obtener más información, lea [Implementar calidad de servicio (QoS) en los equipos de Microsoft](QoS-in-Teams.md). Estos son las marcas DSCP necesarias y utilizadas por los equipos y ExpressRoute de intervalos de puertos de los medios correspondientes sugeridos.

_Intervalos de puertos y marcados de DSCP_

Tipo de tráfico de medios| Intervalo de puertos de origen de cliente\* |Protocolo|Valor de DSCP|Clase de DSCP|
|:---             |:---                         |:---    |:---      |:---      |
|Audio            | 50.000 – 50,019               |TCP/UDP |46        |Desvío rápido (EF)|
|Vídeo            | 50,020 – 50,039               |TCP/UDP |34        |Desvío garantizado (AF41)|
|Uso compartido de aplicaciones o pantalla| 50,040 – 50,059      |TCP/UDP |18        |Reenvío (AF21) asegurado|
| | | | |

\*Los intervalos de puertos que asigna no se pueden superponer y deben ser adyacentes entre sí.

Establecer los intervalos de puertos para tipos de tráfico diferentes es sólo un paso en el control multimedia en tiempo real; vea [Calidad de servicio (QoS) en los equipos](qos-in-teams.md) para mucho más detalle. Si habilita o cambiar la configuración en el centro de administración de Microsoft Teams, necesitará para [aplicar la configuración correspondiente a todos los dispositivos de usuario](QoS-in-Teams-clients.md) y los dispositivos de la red interna para implementar completamente los cambios realizados en QoS en los equipos.

Después de haber QoS en uso durante un tiempo, tendrá la información sobre el uso de la demanda de cada una de estas tres cargas de trabajo, y puede elegir qué cambios hacer según sus necesidades concretas. [Panel de calidad de llamadas](turning-on-and-using-call-quality-dashboard.md) le serán útiles con eso.
