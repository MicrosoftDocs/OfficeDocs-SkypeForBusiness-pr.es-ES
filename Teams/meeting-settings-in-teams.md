---
title: Administrar configuración de reuniones
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo administrar la configuración de las reuniones de teams que los usuarios programan en su organización.
ms.openlocfilehash: b1513e80028137c909f5fc0f854666b1770299c8
ms.sourcegitcommit: c169b091a630ff78c233a2a2824da122184635d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2019
ms.locfileid: "36404608"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Administrar la configuración de reuniones en Microsoft Teams

Como administrador, debe usar la configuración de reuniones de Teams para controlar si los usuarios anónimos pueden unirse a reuniones de Teams, personalizar las invitaciones a reuniones y, si desea habilitar la calidad de servicio (QoS), establecer intervalos de puertos para el tráfico en tiempo real. Esta configuración se aplica a todas las reuniones de teams que los usuarios programan en su organización. Esta configuración se administra desde la**configuración** de las reuniones de las **reuniones** > en el centro de administración de Microsoft Teams.

## <a name="allow-anonymous-users-to-join-meetings"></a>Permitir que usuarios anónimos se unan a reuniones

Con la combinación anónima, cualquier persona puede unirse a la reunión como un usuario anónimo haciendo clic en el vínculo de la invitación a la reunión.

![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, vaya a**configuración de reunión**de **reuniones** > .
2. En **participantes**, Active **usuarios anónimos pueden unirse a una reunión**.

    ![Captura de pantalla de la configuración de participantes para reuniones en el centro de administración] (media/meeting-settings-participants.png "Captura de pantalla de la configuración de participantes de las reuniones de Teams en el centro de administración de Microsoft Teams")

Si no desea que los usuarios anónimos se unan a las reuniones programadas por los usuarios de su organización, desactive esta configuración.

## <a name="customize-meeting-invitations"></a>Personalizar invitaciones a reuniones

Puede personalizar las invitaciones a reuniones de Teams para satisfacer las necesidades de su organización. Puede Agregar el logotipo de su organización e incluir información útil, como vínculos a su sitio web de soporte técnico y renuncia legal, y un pie de página de solo texto.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Sugerencias para crear un logotipo para invitaciones a reuniones  

1. Crear una imagen que no supere los 188 píxeles de ancho por 30 píxeles de alto (es bastante pequeño).
2. Guarde la imagen en formato JPG o PNG.
3. Almacene la imagen en una ubicación central a la que tengan acceso todos los miembros de su organización, como un recurso compartido de red.

    Ahora puede agregarlo a las invitaciones a reuniones. Consulte los pasos siguientes.

### <a name="customize-your-meeting-invitations"></a>Personalizar las invitaciones a reuniones

![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, vaya a**configuración de reunión**de **reuniones** > .
2. En **invitación por correo electrónico**, haga lo siguiente:

    ![Captura de pantalla de la configuración de la invitación a la reunión que puede personalizar] (media/meeting-settings-invitation.png "Captura de pantalla de la configuración de la invitación a la reunión que puede personalizar para las reuniones de Teams")

    - **Dirección URL del logotipo** Escriba la dirección URL donde se encuentra almacenado el logotipo.
    - **Dirección URL legal** Si su organización tiene un sitio web legal al que desea que se vean los problemas legales, escriba la dirección URL aquí.
    - **Dirección URL de ayuda** Si su organización tiene un sitio web de soporte al que quiere que los demás usuarios tengan problemas, escriba la dirección URL aquí.
    - **Pie de página** Escriba el texto que desee incluir como pie de página.
3. Espere una hora o para que los cambios se propaguen. Después, programe una reunión de Teams para ver el aspecto de la invitación a la reunión.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Establezca cómo desea controlar el tráfico de medios en tiempo real de las reuniones de Teams

<a name="bknetwork"> </a>

Si está usando la calidad de servicio [(QoS)](qos-in-teams.md) para priorizar el tráfico de red, puede habilitar marcadores de QoS y establecer intervalos de puertos para cada tipo de tráfico de medios. La configuración de intervalos de puertos para diferentes tipos de tráfico es un único paso para controlar los medios en tiempo real; para obtener más información [, consulta calidad de servicio (QoS) en Teams](qos-in-teams.md) .

> [!IMPORTANT]
> Si habilita QoS o cambia la configuración en el centro de administración de Microsoft Teams para el servicio Microsoft Teams, también tendrá que [aplicar la configuración correspondiente a todos los dispositivos de usuario](QoS-in-Teams-clients.md) y todos los dispositivos de red internos para implementar por completo los cambios en QoS en Teams.

 ![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, vaya a**configuración de reunión**de **reuniones** > .
2. En **red**, haga lo siguiente:

    ![Captura de pantalla de la configuración de red para las reuniones en el centro de administración] (media/meeting-settings-network.png "Captura de pantalla de la configuración de red de las reuniones de Teams en el centro de administración de Microsoft Teams")

    - Para permitir que los marcadores de DSCP se usen para QoS, Active **insertar marcadores de calidad de servicio (QoS) para el tráfico de medios en tiempo real**. Solo tiene la opción de usar marcadores o no. no puede establecer marcadores personalizados para cada tipo de tráfico. Para obtener más información sobre los marcadores de DSCP, vea [seleccionar un método de implementación de QoS](QoS-in-Teams.md#select-a-qos-implementation-method) .
    - Para especificar intervalos de puertos, junto a **seleccionar un intervalo de puertos para cada tipo de tráfico de medios en tiempo real**, seleccione **especificar intervalos de puertos**y, a continuación, escriba los puertos de inicio y de finalización para el audio, el vídeo y la pantalla compartida. Es necesario seleccionar esta opción para implementar QoS.
    > [!IMPORTANT]
    > Si selecciona **usar automáticamente cualquiera de los puertos disponibles**, se usan los puertos disponibles entre 1024 y 65535. Use esta opción solo si no implementa QoS.
    >
    > Si seleccionas un intervalo de puertos demasiado estrecho, dará lugar a llamadas perdidas y a una mala calidad de las llamadas. Las siguientes recomendaciones deben ser un mínimo.

Si no está seguro de qué intervalos de puertos usar en su entorno, la configuración siguiente es un buen punto de partida. Para obtener más información, lea [implementar calidad de servicio (QoS) en Microsoft Teams](QoS-in-Teams.md). Estas son las marcas de DSCP necesarias y los intervalos de puertos de medios correspondientes sugeridos que usan tanto Teams como ExpressRoute.

_Intervalos de puertos y marcas de DSCP_

Tipo de tráfico multimedia| Intervalo de puertos de origen del cliente\* |Protocolo|Valor de DSCP|Clase de DSCP|
|:---             |:---                         |:---    |:---      |:---      |
|Audio            | 50000 – 50019               |TCP/UDP |46        |Desvío rápido (EF)|
|Vídeo            | 50,020–50,039               |TCP/UDP |34        |Desvío garantizado (AF41)|
|Aplicación/pantalla compartida| 50,040–50,059      |TCP/UDP |18        |Reenvío asegurado (AF21)|
| | | | |

\*Los intervalos de puertos que asigne no se pueden superponer y deben estar unos al lado de otros.

Después de que se haya utilizado QoS durante un tiempo, tendrá información de uso sobre la demanda para cada una de estas tres cargas de trabajo y podrá elegir qué cambios se deben realizar en función de las necesidades específicas. El [Panel de calidad de llamadas](turning-on-and-using-call-quality-dashboard.md) te ayudará a hacerlo.
