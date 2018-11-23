---
title: Administrar la configuración de reunión en Microsoft Teams
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
f1keywords: ms.teamsadmincenter.meetingsettings.overview
MS.collection: Teams_ITAdmin_Help
description: Obtenga información sobre cómo administrar la configuración para las reuniones de los equipos que los usuarios programar en la organización.
ms.openlocfilehash: bf7350d94f61fcbaff60dacb161d5096b8f549e7
ms.sourcegitcommit: 72afa227b917f9fabd278fc7bea9d515b5d53def
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2018
ms.locfileid: "26671043"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Administrar la configuración de reunión en Microsoft Teams

Como administrador, usa la configuración de las reuniones de los equipos para controlar si los usuarios anónimos pueden participar en las reuniones de los equipos, personalizar las invitaciones a reuniones y si desea habilitar la calidad de servicio (QoS), definir puertos para el tráfico en tiempo real. Esta configuración aplica a todas las reuniones de los equipos que programación a los usuarios de la organización. Administrar estas opciones de configuración de **reuniones** > **configuración de reunión** en Microsoft Teams & Skype para el centro de administración de negocio. 

## <a name="allow-anonymous-users-to-join-meetings"></a>Permitir a los usuarios anónimos unirse a reuniones

Unión anónima, cualquier usuario puede unirse a la reunión como un usuario anónimo haciendo clic en el vínculo en la invitación a la reunión. 

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) Uso de la Microsoft equipos & Skype para el centro de administración de negocio
1. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de reunión**. 
2. En **los participantes**, activar **los usuarios anónimos pueden unirse a una reunión**. 

    ![reunión-configuración-participants.png] (media/meeting-settings-participants.png "Captura de pantalla de configuración de los participantes de las reuniones de los equipos en los equipos de Microsoft & Skype para el centro de administración de negocio")

Si no desea que los usuarios anónimos a participar en reuniones programadas por los usuarios de su organización, desactive esta opción. 
## <a name="customize-meeting-invitations"></a>Personalizar invitaciones a reuniones

Puede personalizar las invitaciones a reuniones de los equipos para satisfacer las necesidades de su organización. Puede agregar el logotipo de su organización e incluye información útil, como vínculos a su sitio Web de soporte técnico y renuncia de responsabilidad legal y un pie de página de sólo texto. 

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Sugerencias para la creación de un logotipo para las invitaciones a reuniones  

1. Crear una imagen que es no más de 188 píxeles de ancho por 30 píxeles de alto (es bastante pequeña). 
2. Guarde la imagen en formato JPG. 
3. Almacenar la imagen en una ubicación central que todas las personas de su organización pueden tener acceso, como un recurso compartido de red. 

### <a name="customize-your-meeting-invitations"></a>Personalizar las invitaciones de reunión

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) Uso de la Microsoft equipos & Skype para el centro de administración de negocio

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de reunión**.
2. En la **invitación por correo electrónico**, haga lo siguiente: 

    ![reunión-configuración-invitation.png] (media/meeting-settings-invitation.png "Captura de pantalla de la reunión configuración de invitación que se puede personalizar para las reuniones de los equipos") 

    - **Dirección URL del logotipo** Escriba la dirección URL donde está almacenado el logotipo. 
    - **Dirección URL legal** Si su organización tiene un sitio Web legal que desea que las personas para ir a si tiene alguna duda legal, escriba la dirección URL aquí. 
    - **Dirección URL de ayuda** Si su organización tiene un sitio Web de soporte técnico que desea que las personas para ir a si se ejecutan en problemas, escriba la dirección URL aquí.
    - **Pie de página** Escriba el texto que desea incluir como un pie de página. 
3. Tiempo de espera una hora o lo propagar los cambios. A continuación, programar una reunión de los equipos para ver qué aspecto tiene la invitación a la reunión.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings-coming-soon"></a>Establecer cómo desea controlar el tráfico de medios en tiempo real para las reuniones de los equipos (próximamente) 
Si se usa la calidad de servicio (QoS) para dar prioridad al tráfico de red, puede habilitar QoS marcadores y puede establecer los intervalos de puertos para cada tipo de tráfico de medios. 

 ![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) Uso de la Microsoft Teams & Skype para el centro de administración de negocio

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de reunión**. 
2. En la **red**, haga lo siguiente:

    ![reunión-configuración-network.png] (media/meeting-settings-network.png "Captura de pantalla de la configuración de red para las reuniones de los equipos en los equipos de Microsoft & Skype para el centro de administración de negocio")

    - Para habilitar QoS marcadores, activar **marcadores de insertar calidad de servicio (QoS) para el tráfico de medios en tiempo real**.
    - Para especificar intervalos de puertos, junto al **Seleccionar un rango de puerto para cada tipo de tráfico de medios en tiempo real**, seleccione **especificar intervalos de puertos**y, a continuación, escriba los puertos inicial y final de audio, vídeo y uso compartido de la pantalla. 
    
        Si selecciona **utilizar automáticamente los puertos disponibles**, disponibles puertos entre 1024 y 65535 se usan. 

 ### <a name="related-topics"></a>Temas relacionados
- [Calidad de servicio (QoS) en los equipos](qos-in-teams.md)

