---
title: Administrar la configuración de las reuniones
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: high
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
ms.openlocfilehash: a4a2eea55336639925d8c07c00ded4057456e1ff
ms.sourcegitcommit: 95c7603b47fcd5fba8f762a4590693ee9f026328
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61153313"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Administrar la configuración de las reuniones en Microsoft Teams

Como administrador, usted utiliza la configuración de las reuniones de Teams para controlar si los usuarios anónimos pueden unirse a las reuniones de Teams, personalice las invitaciones a las reuniones, y si desea habilitar la calidad de servicio (QoS), establecer intervalos de puertos para el tráfico en tiempo real. Estas configuraciones se aplican a todas las reuniones de Teams que los usuarios programen en su organización. Usted administra estos ajustes desde **Reuniones** > **Configuración de reunión** en el centro de administración de Microsoft Teams.

A través de una configuración de directiva por organizador, los administradores ahora pueden controlar si determinados usuarios o grupos de usuarios pueden permitir que los usuarios anónimos se unan a las reuniones que organizan. Tanto la configuración de directiva por organizador como la de toda la organización controlan la unión anónima y la más restrictiva es la que tiene efecto.

> [!Important]
 > **-DisableAnonymousJoin** es la configuración de directiva de toda la organización. Quedará en desuso en el futuro y, a continuación, la directiva por organizador será la única manera de controlar la unión anónima.

## <a name="allow-anonymous-users-to-join-meetings"></a>Permitir que los usuarios anónimos se unan a las reuniones

Con la unión anónima, cualquiera puede unirse a la reunión como usuario anónimo haciendo clic en el enlace de la invitación a la reunión. Para más información, consulte[Únase a una reunión sin una cuenta de Teams](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508). Puede controlar la capacidad de los usuarios anónimos para unirse a reuniones a nivel de organización o por organizador de reuniones mediante dos configuraciones de directiva diferentes.

 ### <a name="using-the-microsoft-teams-admin-center-to-configure-organization-wide-policy"></a>Usar el Centro de administración de Microsoft Teams para configurar la directiva de toda la organización

Debe ser administrador de Teams para realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams](./using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. Vaya al [Centro de administración de Teams](https://admin.teams.microsoft.net).

2. En la navegación izquierda, diríjase a **Reuniones** > **Configuración de la reunión**.

3. En **Participantes**, Active **Usuarios anónimos pueden unirse a una reunión**.

    ![Captura de pantalla de la configuración de los participantes para las reuniones en el centro de administración.](media/meeting-settings-participants.png "Captura de pantalla de la configuración de los participantes para las reuniones de Teams en el centro de administración de Microsoft Teams.")

> [!CAUTION]
> Si no desea que los usuarios anónimos se unan a las reuniones programadas por los usuarios de su organización, desactive esta opción.

### <a name="using-powershell-to-configure-per-organizer-policy"></a>Usar PowerShell para configurar la directiva por organizador

Los administradores ahora pueden controlar si determinados usuarios o grupos de usuarios pueden permitir que usuarios anónimos se unan a las reuniones que organicen. Esta nueva directiva por organizador se controla mediante el parámetro **-AllowAnonymousUsersToJoinMeeting** en [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps). Esto viene con la versión 2.6.0 y posteriores de PowerShell de Teams.

Puede usar cualquiera de las dos directivas, es decir, para toda la organización o por organizador, para administrar la unión de usuarios anónimos. Se recomienda implementar la directiva por organizador. La configuración de directiva para toda la organización quedará en desuso en el futuro y la directiva por organizador será la única para controlar la unión de usuarios anónimos.

Puesto que tanto las directivas para toda la organización como las directivas por organizador controlan la unión de usuarios anónimos, la configuración más restrictiva será la que se aplique. Por ejemplo, si no se permite la unión de usuarios anónimos a nivel de la organización, esa será la directiva que prevalezca independientemente de lo que se configure para la directiva por organizador. Por lo tanto, para permitir que los usuarios anónimos se unan a reuniones, se deben configurar ambas directivas para permitir este tipo de unión estableciendo los siguientes valores:

- **-DisableAnonymousJoin** establecido en **$false**
- **-AllowAnonymousUsersToJoinMeeting** establecido en **$true**

Cualquier otra combinación de valores impedirá que los usuarios anónimos se unan a las reuniones.
> [!NOTE]
> Para usar la directiva por organizador para las organizaciones con unión de usuarios anónimos desactivada por organización, los administradores deberán crear una directiva y asignarla a los usuarios. Para obtener información sobre cómo hacerlo, vea [Administrar directivas de reunión en Microsoft Teams](/microsoftteams/meeting-policies-overview).


## <a name="allow-anonymous-users-to-interact-with-apps-in-meetings"></a>Permitir que los usuarios anónimos interactúen con las aplicaciones en las reuniones

Los usuarios anónimos ahora heredarán la directiva de permisos globales predeterminados del nivel de usuario. Este control permite a los usuarios anónimos interactuar con las aplicaciones en las reuniones de Teams siempre que la directiva de permisos del nivel de usuario haya habilitado la aplicación. Tenga en cuenta que los usuarios anónimos solo podrán interactuar con las aplicaciones que ya estén disponibles en una reunión y no podrán adquirir o administrar dichas aplicaciones. 

> [!IMPORTANT]
> De forma predeterminada, la configuración para permitir que los usuarios anónimos interactúen con las aplicaciones en las reuniones está habilitada.

 **Usar el Centro de administración de Microsoft Teams**

Debe ser un administrador de servicio de Teams para tener acceso a esta configuración. Consulte [Usar los roles de administrador de Teams para administrar Teams](./using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. Vaya al Centro de administración.

2. En la navegación izquierda, diríjase a **Reuniones** > **Configuración de la reunión**.

3. En **Participantes**, el ajuste de **Los usuarios anónimos pueden interactuar con las aplicaciones en las reuniones** se puede cambiar.

> [!CAUTION]
> Si no desea que usuarios anónimos se unan a las reuniones programadas por los usuarios en su organización, desactive esta opción.

## <a name="customize-meeting-invitations"></a>Personalice las invitaciones a reuniones

Puede personalizar las invitaciones a la reunión de Teams para cumplir con las necesidades de su organización. Puede agregar el logotipo de su organización e incluir información útil, como enlaces a su sitio web de apoyo y renuncia a la responsabilidad legal, y un pie de página sólo de texto.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Consejos para crear un logotipo para las invitaciones a reuniones  

1. Crear una imagen que no tenga más de 188 píxeles de ancho por 30 píxeles de alto (es bastante pequeña).
2. Guarde la imagen en formato JPG o PNG.
3. Almacene la imagen en un lugar en el que todos los que reciban la invitación puedan acceder, como un sitio web público.

    Ahora puede añadirlo a sus invitaciones a reuniones. Vea los pasos siguientes.

### <a name="customize-your-meeting-invitations"></a>Personalice sus invitaciones a reuniones

 **Usar el Centro de administración de Microsoft Teams**

1. Vaya al Centro de administración.
2. En la navegación izquierda, diríjase a **Reuniones** > **Configuración de la reunión**.
3. En **Invitación por correo electrónico**, haga lo siguiente:

    ![Captura de pantalla de la configuración de invitaciones a las reuniones que puede personalizar.](media/meeting-settings-invitation.png "Captura de pantalla de la configuración de la invitación a la reunión que puede personalizar para las reuniones de Teams")

    - **URL del logotipo** escriba la dirección URL en donde esté almacenado el logotipo.
    - **URL jurídica** si su organización tiene un sitio web legal al que quiere que la gente vaya para cualquier asunto legal, introduzca la URL aquí.
    - **URL de ayuda** si su organización tiene un sitio web de apoyo al que quiere que la gente vaya si se encuentra con problemas, introduzca la URL aquí.
    - **Pie de página** escriba el texto que quiera incluir como pie de página.
4. Haga clic en **Vista previa de invitación** para ver una vista previa de su invitación a reunión.
5. Cuando haya terminado, haga clic en **Guardar**.
6. Espere una hora más o menos para que los cambios se propaguen. Luego programe una reunión de Teams para ver cual es el aspecto de la invitación a reunión.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Establezca cómo quiere manejar el tráfico de medios en tiempo real para las reuniones de Teams

<a name="bknetwork"> </a>

Si utiliza la Calidad de servicio (QoS) para priorizar el tráfico de la red, puede habilitar los marcadores de QoS y establecer intervalos de puertos para cada tipo de tráfico de medios. Establecer los intervalos de puertos para los diferentes tipos de tráfico es sólo un paso en el manejo de los medios en tiempo real; consulte [Calidad de Servicio (QoS) en Teams](qos-in-teams.md) para más detalles.

> [!IMPORTANT]
> Sistemas basados en Apple: la única instancia que sabemos en que los dispositivos basados en Apple establecen realmente el valor DSCP es si se cumplen todas las condiciones siguientes:
> - iOS
> - Red Wi-Fi.
> - Conmutadores Cisco.
> - El administrador de red ha agregado la aplicación a la lista aprobada.
>
> Sistemas basados en Android: no hay limitaciones conocidas.
>
> Si habilita la QoS o cambia la configuración en el Centro de administración de Microsoft Teams para el servicio de Teams, también deberá [aplicar la configuración correspondiente a todos los dispositivos de usuario](QoS-in-Teams-clients.md) y a todos los dispositivos de la red interna para implementar completamente los cambios en la QoS en Teams.

  **Usar el Centro de administración de Microsoft Teams**
1. Vaya al Centro de administración.
2. En la navegación izquierda, diríjase a **Reuniones** > **Configuración de la reunión**.
3. En **Red**, haga lo siguiente:

    ![Captura de pantalla de la configuración de red para las reuniones en el centro de administración.](media/meeting-settings-network.png "Captura de pantalla de la configuración de la red para las reuniones de Teams en el centro de administración de Microsoft Teams")

    - Para permitir que las marcas de DSCP se utilicen para QoS, Active **Insertar marcadores de calidad de servicio (QoS) para el tráfico de medios en tiempo real**. Sólo tienes la opción de usar marcadores o no; no puedes establecer marcadores personalizados para cada tipo de tráfico. Consulte [Seleccionar un método de implementación de QoS ](QoS-in-Teams.md#select-a-qos-implementation-method) para más información sobre los marcadores DSCP.

        > [!IMPORTANT]
        > Tenga en cuenta que la habilitación de QoS solo se realiza en los puntos de conexión para etiquetar paquetes que salen del cliente. Se recomienda aplicar reglas de QoS coincidentes en todos los dispositivos de red internos para el tráfico entrante.
        
        > [!NOTE]
        > El etiquetado DSCP normalmente se realiza a través de los puertos de origen y el tráfico UDP se redirigirá a retransmisión de transporte con el puerto de destino 3478 como valor predeterminado. Si su empresa necesita etiquetado en los puertos de destino, contacte al servicio de soporte técnico para habilitar la comunicación a la retransmisión de transporte con los puertos UDP 3479 (Audio), 3480 (Vídeo) y 3481 (Uso compartido).
    - Para especificar los intervalos de los puertos, junto a **Seleccione un rango de puertos para cada tipo de tráfico de medios en tiempo real**, seleccione **Especificar rangos de puertos** y luego introduzca los puertos inicial y final para compartir audio, video y pantalla. La selección de esta opción es necesaria para implementar la QoS. 
        > [!Note]
        > Si la opción **Marcadores de Calidad del servicio (QoS) para tráfico multimedia en tiempo real** está activada, deberá administrar la configuración del puerto. No se puede administrar automáticamente.
        
        > [!IMPORTANT]
        > Si usted selecciona **Utilizar automáticamente cualquier puerto disponible**, se utilizan los puertos disponibles entre 1024 y 65535. Use esta opción sólo cuando no implemente la QoS.
        >
        > Si se selecciona un rango de puertos demasiado estrecho, se producirán caídas y una mala calidad en las llamadas. Las recomendaciones que figuran a continuación deben ser en lo mínimo.

Si no está seguro de los rangos de puertos a utilizar en su entorno, los siguientes ajustes son un buen punto de partida. Para obtener más información, consulte[Implementar la Calidad de servicio (QoS) en Microsoft Teams](QoS-in-Teams.md). Estas son las marcas DSCP requeridas y los rangos de puertos de medios correspondientes sugeridos utilizados tanto por Teams como por ExpressRoute.

### <a name="port-ranges-and-dscp-markings"></a>Intervalos de puertos y marcas de DSCP

Tipo de tráfico de medios | Rango de puertos de origen del cliente \* |Protocolo|Valor de DSCP|Clase DSCP|
|:---             |:---                         |:---    |:---      |:---      |
|Audio            | 50 000 – 50 019               |TCP/UDP |46        |Desvío rápido (EF)|
|Vídeo            | 50 020 – 50 039               |TCP/UDP |34        |Desvío garantizado (AF41)|
|Aplicación/Compartir pantalla| 50 040 – 50 059      |TCP/UDP |18        |Desvío garantizado (AF21)|
| | | | |

\* Los rangos del puerto asignados no deben superponerse y deben ser adyacentes entre sí.

Después de que la QoS se haya utilizado durante un tiempo, tendrá información de uso sobre la demanda de cada una de estas tres cargas de trabajo, y podrá elegir qué cambios realizar en función de sus necesidades específicas. El [Panel de calidad de llamadas](turning-on-and-using-call-quality-dashboard.md) será de gran ayuda con eso.
