---
title: Plan para eventos en directo en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Obtenga más información sobre los factores que debe tener en cuenta antes de configurar eventos en Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95baeaf25600853b7d6a2b4e18c548d1998f6789
ms.sourcegitcommit: 708270f1fecab6b7b44345d57a8e12bc36d19c8b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102371"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Plan para eventos en directo en Microsoft Teams

Cuando planee a los equipos eventos para tener reuniones grandes en la organización, debe tener en cuenta varios factores antes de empezar a configurarlo. 

## <a name="who-can-create-and-schedule-live-events"></a>¿Quién puede crear y programar eventos en directo? 
Para que el usuario programe un evento en directo de Teams se requieren los siguientes requisitos previos.

Deben asignarse las siguientes licencias:  
- Una licencia de Office 365 Enterprise E1, E3 o E5 o una licencia de Office 365 a3 o A5
- Una licencia de Microsoft Teams
- Una licencia de Microsoft Stream

> [!IMPORTANT]
> El usuario que cree y programe un evento en directo debe tener un buzón de Exchange Online.

Para participar en un evento en directo como usuario autenticado se requiere una licencia de Office 365, pero este requisito depende del método de producción que se use:

- **Para eventos producidos en Teams** El usuario debe tener asignada una licencia de Teams.
- **Para eventos producidos con una aplicación o dispositivo externo** El usuario debe tener asignada una licencia de Stream.

> [!NOTE]
> Los eventos en directo de Teams Live están disponible para las organizaciones de la comunidad en la nube del gobierno (GCC) en los Estados Unidos.

Para obtener más información sobre las licencias, vea [Licencias complementarias de Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

El usuario debe tener:
- La programación de reuniones privadas habilitada en Teams (*el parámetro TeamsMeetingPolicy -AllowPrivateMeetingScheduling parameter = True*).
- El uso compartido de vídeos habilitado para las reuniones en Teams (*el parámetro TeamsMeetingPolicy -AllowIPVideo parameter = True*).
- El uso compartido de vídeos habilitado para las reuniones en Teams (*el parámetro TeamsMeetingPolicy -ScreenSharingMode = EntireScreen*).
- La programación de reuniones privadas habilitada en Teams (*el parámetro TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling = True*).
- Permisos para crear eventos en directo en Stream (para producción de dispositivos o aplicaciones externas).

> [!IMPORTANT]
> Los usuarios anónimos sin autenticar no pueden ser invitados como productores ni moderadores de los eventos en directo de Teams. 
 
## <a name="who-can-watch-live-events"></a>¿Quién puede ver los eventos en directo?

|**Visibilidad del asistente**       |**Producción de Teams**  |**Producción de dispositivos o aplicaciones externos**  |
|------------------------------|-----------------|----------------------|
|Público (Usuarios anónimos)      |  Sí            |  No                  |
|Usuarios invitados                   |  Sí            |  No                  |
|Todos los usuarios de la empresa asociada |  Sí<sup>1</sup>|  No                  |
|Todas los usuarios de la empresa           |  Sí            |  Sí                 |
|Grupos específicos / personas      |  Sí            |  Sí                 |

<sup>1</sup> solo se puede invitar a los asistentes federados a través de personas & grupo <br>


 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventos y Difusión de reunión de Skype en Teams

En la siguiente tabla, se resaltan las funciones y características principales ofrecidas en los eventos en directo y cómo estas se diferencian de la Difusión de reunión de Skype. 

|**Función**   |**Difusión de reunión de Skype** |**Eventos producidos en Teams** |**Eventos producidos en las aplicaciones o dispositivos externos** |
|---------|---------|---------|---------|
|Tamaño máximo de audiencia |10 000 asistentes |10 000 asistentes<sup>1</sup> |10 000 asistentes<sup>1</sup> |
|Duración máxima del evento en directo |4 horas |4 horas |4 horas |
|Número máximo de moderadores y productores en un evento en directo |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Cantidad máxima de eventos simultáneos en vivo por cada inquilino de Office 365 |4,5  | 4,5  | 4,5  |
|Creación de eventos en directo |   Portal de Difusión de reunión de Skype |Teams, Yammer a través de Teams | Teams, Yammer a través de Teams, Stream |
|Compromiso de audiencia: Yammer |&#x2714; |&#x2714; (experiencia integrada) |&#x2714; (experiencia integrada) |
|Negociación de audiencia: moderado por P y R |&#x2714;  |&#x2714; |&#x2714; |
|Cliente productor en Windows |&#x2714; (Skype Empresarial) |&#x2714; (Teams) |&#x2714; (Stream, Teams a través de Stream Embed) |
|Cliente productor en Mac |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream, Teams a través de Stream Embed) |
|Recuento de asistentes en la interfaz de usuario del productor |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream, Teams a través de Stream Embed) |
|Permite varios moderadores |&#x2714; (Skype Empresarial) |&#x2714; (Teams) |N/D  |
|Invitar a un moderador durante la reunión |&#x2714; (Skype Empresarial) |&#x274C; |N/D |
|El moderador se unió desde el móvil e Internet |&#x2714; (Skype Empresarial)  |&#x274C; |N/D |
|Asociados e invitados de los moderadores o asistentes |&#x2714; (Skype Empresarial)  |  &#x2714; (Teams) |N/D |
|Moderador: acceso por RTC |&#x274C; |&#x2714; (Teams) |N/D |
|Presentar en una pantalla |&#x274C; |&#x2714; (Teams) |N/D |
|Presentar un archivo de PowerPoint (uso compartido de archivos PPT) |&#x2714; |&#x274C; (mitigado a través de pantalla compartida) |N/D |
|Grabación de la reunión guardada en la nube |&#x2714; |&#x2714; |&#x2714; |
|Publicar automáticamente la grabación en Stream |&#x274C; |&#x274C; |&#x2714; |
|Subtítulos en directo y otros subtítulos |&#x2714; |&#x2714; |&#x274C; |
|Subtítulos para las grabaciones de eventos en directo |&#x2714; |&#x2714; |&#x2714; |
|Controles DVR de los asistentes (pausa, retroceso) |&#x2714; |&#x2714; |&#x2714; |
|Soporte técnico eCDN Partner |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |
|Informe de asistencia posterior a la difusión para los productores |&#x2714; |&#x2714; |&#x274C; |
|Análisis de opiniones de los asistentes: votación y sondeos en directo |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> Los límites establecidos pueden ser modificados. Comprobar los [límites y las especificaciones de Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> puede tener hasta 250 moderadores y productores en un evento en vivo, pero solo se muestran en la lista los últimos 10 usuarios.


## <a name="regional-availability"></a>Disponibilidad regional
Puede usar los eventos en directo de Teams en varias regiones a través de todo el mundo. La siguiente información muestra la disponibilidad de los miembros del equipo y los asistentes al evento. 

> [!IMPORTANT]
> La región del evento se selecciona automáticamente según el organizador y la organización de Office 365.

**Disponible en estas regiones**
- América
- Europa / África
- Asia Pacífico
- De forma local en Canada, India, Australia, Japón, Reino Unido

**Exclusiones y permisos**
- **De forma local:** Teams funcionará de forma local y no es compatible con las opciones mostradas anteriormente.
- **China:** los participantes y los miembros del equipo no podrán usar los eventos en directo de Teams, ya que no se puede obtener acceso a Microsoft Azure Content Delivery Network en China. Una forma de evitar el problema es usar una conexión VPN corporativa, que mantiene al cliente conectado a la red CDN a través de la red corporativa.

## <a name="next-steps"></a>Siguientes pasos
Vaya a [Configuración de eventos en directo de Teams](set-up-for-teams-live-events.md)

### <a name="related-topics"></a>Temas relacionados
- [¿Qué son los eventos en directo de Teams?](what-are-teams-live-events.md)
- [Configuración de Eventos en Directo de Teams](set-up-for-teams-live-events.md)
- [Establecer la configuración de eventos en directo de Microsoft Teams](configure-teams-live-events.md)

