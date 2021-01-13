---
title: Administrar la configuración de las reuniones
author: cichur
ms.author: v-cichur
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Aprenda como administrar la configuración de las reuniones de Teams que los usuarios programan en su organización.
ms.openlocfilehash: 447aa83af836eefb854f3917738020badee2f33c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806220"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Administrar la configuración de las reuniones en Microsoft Teams

Como administrador, usted utiliza la configuración de las reuniones de Teams para controlar si los usuarios anónimos pueden unirse a las reuniones de Teams, personalice las invitaciones a las reuniones, y si desea habilitar la calidad de servicio (QoS), establecer intervalos de puertos para el tráfico en tiempo real. Estas configuraciones se aplican a todas las reuniones de Teams que los usuarios programen en su organización. Usted administra estos ajustes desde **Reuniones** > **Configuración de reunión** en el centro de administración de Microsoft Teams.

## <a name="allow-anonymous-users-to-join-meetings"></a>Permitir que los usuarios anónimos se unan a las reuniones

Con la unión anónima, cualquiera puede unirse a la reunión como usuario anónimo haciendo clic en el enlace de la invitación a la reunión. Para más información, consulte[Únase a una reunión sin una cuenta de Teams](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

Debe ser administrador del servicio de Teams para realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams y](https://docs.microsoft.com/microsoftteams/using-admin-roles) obtener información sobre cómo obtener permisos y roles de administrador.

1. Vaya al centro de administración.

2. En la navegación izquierda, diríjase a **Reuniones** > **Configuración de reunión**.

3. En **Participantes**, Active **Usuarios anónimos pueden unirse a una reunión**.

    ![Captura de pantalla de la configuración de los participantes para las reuniones en el centro de administración](media/meeting-settings-participants.png "Captura de pantalla de la configuración de los participantes para las reuniones de Teams en el centro de administración de Microsoft Teams.")

> [!CAUTION]
> Si no desea que los usuarios anónimos se unan a las reuniones programadas por los usuarios de su organización, desactive esta opción.

## <a name="customize-meeting-invitations"></a>Personalice las invitaciones a reuniones

Puede personalizar las invitaciones a reuniones de Teams para satisfacer las necesidades de su organización. Puede agregar el logotipo de su organización e incluir información útil, como enlaces a su sitio web de apoyo y renuncia a la responsabilidad legal, y un pie de página sólo de texto.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Consejos para crear un logotipo para las invitaciones a reuniones  

1. Crear una imagen que no tenga más de 188 píxeles de ancho por 30 píxeles de alto (es bastante pequeña).
2. Guarde la imagen en formato JPG o PNG.
3. Almacene la imagen en un lugar en el que todos los que reciban la invitación puedan acceder, como un sitio web público.

    Ahora puede añadirlo a sus invitaciones a reuniones. Vea los siguientes pasos.

### <a name="customize-your-meeting-invitations"></a>Personalice sus invitaciones a reuniones

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. Vaya al centro de administración.
2. En la navegación izquierda, diríjase a **Reuniones** > **Configuración de reunión**.
3. En **Invitación por correo electrónico**, haga lo siguiente:

    ![Captura de pantalla de la configuración de la invitación a reunión que puede personalizar](media/meeting-settings-invitation.png "Captura de pantalla de la configuración de la invitación a la reunión que puede personalizar para las reuniones de Teams")

    - **URL del logotipo** escriba la dirección URL en donde esté almacenado el logotipo.
    - **URL jurídica** si su organización tiene un sitio web legal al que quiere que la gente vaya para cualquier asunto legal, introduzca la URL aquí.
    - **URL de ayuda** si su organización tiene un sitio web de apoyo al que quiere que la gente vaya si se encuentra con problemas, introduzca la URL aquí.
    - **Pie de página** escriba el texto que quiera incluir como pie de página.
4. Haga clic en **Vista previa de invitación** para ver una vista previa de su invitación a reunión.
5. Cuando haya terminado, haga clic en **Guardar**.
6. Espere una hora más o menos para que los cambios se propaguen. Luego programe una reunión de Teams para ver cual es el aspecto de la invitación a reunión.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Establezca cómo quiere manejar el tráfico de medios en tiempo real para las reuniones de Teams

<a name="bknetwork"> </a>

Si usa Calidad de servicio (QoS) para priorizar el tráfico de red, puede habilitar los marcadores de QoS y establecer intervalos de puertos para cada tipo de tráfico multimedia. Establecer los intervalos de puertos para los diferentes tipos de tráfico es sólo un paso en el manejo de los medios en tiempo real; consulte [Calidad de Servicio (QoS) en Teams](qos-in-teams.md) para más detalles.

> [!IMPORTANT]
> Si habilita QoS o cambia la configuración en el centro de administración [](QoS-in-Teams-clients.md) de Microsoft Teams para el servicio Teams, también deberá aplicar la configuración de coincidencia a todos los dispositivos de usuario y a todos los dispositivos de la red interna para implementar completamente los cambios en QoS en Teams.

 ![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**
1. Vaya al centro de administración.
2. En la navegación izquierda, diríjase a **Reuniones** > **Configuración de reunión**.
3. En **Red**, haga lo siguiente:

    ![Captura de pantalla de la configuración de la red para las reuniones en el centro de administración](media/meeting-settings-network.png "Captura de pantalla de la configuración de la red para las reuniones de Teams en el centro de administración de Microsoft Teams")

    - Para permitir que las marcas de DSCP se utilicen para QoS, Active **Insertar marcadores de calidad de servicio (QoS) para el tráfico de medios en tiempo real**. Sólo tienes la opción de usar marcadores o no; no puedes establecer marcadores personalizados para cada tipo de tráfico. Consulte [Seleccionar un método de implementación de QoS ](QoS-in-Teams.md#select-a-qos-implementation-method) para más información sobre los marcadores DSCP.
        > [!NOTE]
        > El etiquetado de DSCP normalmente se realiza a través de puertos de origen y el tráfico UDP se enruta a retransmisión de transporte con el puerto de destino del 3478 de forma predeterminada. Si su empresa requiere etiquetado en puertos de destino, póngase en contacto con el soporte técnico para habilitar la comunicación con la retransmisión de transporte con los puertos UDP 3479 (Audio), 3480 (vídeo) y 3481 (uso compartido).
    - Para especificar los intervalos de los puertos, junto a **Seleccione un rango de puertos para cada tipo de tráfico de medios en tiempo real**, seleccione **Especificar rangos de puertos** y luego, introducir los puertos inicial y final para compartir audio, video y pantalla. La selección de esta opción es necesaria para implementar la QoS. 
        > [!Note]
        > Si los marcadores de Calidad de servicio **(QoS)** para el tráfico multimedia en tiempo real están activas, tendrá que administrar la configuración de puertos. No se administran automáticamente.
        
        > [!IMPORTANT]
        > Si usted selecciona **Utilizar automáticamente cualquier puerto disponible**, se utilizan los puertos disponibles entre 1024 y 65535. Use esta opción sólo cuando no implemente la QoS.
        >
        > Si se selecciona un rango de puertos demasiado estrecho, se producirán caídas y una mala calidad en las llamadas. Las recomendaciones que figuran a continuación deben ser en lo mínimo.

Si no está seguro de los rangos de puertos a utilizar en su entorno, los siguientes ajustes son un buen punto de partida. Para obtener más información, consulte[Implementar la Calidad de servicio (QoS) en Microsoft Teams](QoS-in-Teams.md). Estas son las marcas DSCP requeridas y los rangos de puertos de medios correspondientes sugeridos utilizados tanto por Teams como por ExpressRoute.

### <a name="port-ranges-and-dscp-markings"></a>Intervalos de puertos y marcas DSCP

Tipo de tráfico de medios | Rango de puertos de origen del cliente \* |Protocolo|Valor de DSCP|Clase DSCP|
|:---             |:---                         |:---    |:---      |:---      |
|Audio            | 50 000 – 50 019               |TCP/UDP |46        |Desvío rápido (EF)|
|Vídeo            | 50 020 – 50 039               |TCP/UDP |34        |Desvío garantizado (AF41)|
|Aplicación/Compartir pantalla| 50 040 – 50 059      |TCP/UDP |18        |Desvío garantizado (AF21)|
| | | | |

\* Los intervalos de puertos asignados no se pueden superponer y deben ser adyacentes.

Después de que la QoS se haya utilizado durante un tiempo, tendrá información de uso sobre la demanda de cada una de estas tres cargas de trabajo, y podrá elegir qué cambios realizar en función de sus necesidades específicas. [Panel de calidad de llamadas](turning-on-and-using-call-quality-dashboard.md)será de gran ayuda con eso.
