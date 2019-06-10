---
title: Plan para eventos en directo en Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Obtenga más información sobre los factores que hay que tener en cuenta antes de configurar eventos en Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0093bafdf59c1d18c578f8e8edfaed3ab4c26381
ms.sourcegitcommit: 8305fd00f6f9e302653fb383e4ac8d38490644c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "34428756"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Plan para eventos en directo en Microsoft Teams

Cuando planea eventos en vivo de Teams para mantener reuniones grandes de su organización, hay varios factores que debe tener en cuenta antes de empezar a configurarlo. 

## <a name="who-can-create-and-schedule-live-events"></a>¿Quién puede crear y programar eventos en vivo? 
Los siguientes requisitos previos son necesarios para que el usuario programe un evento de Teams Live.

Estas son las licencias que deben asignarse:  
- Una licencia de Office 365 Enterprise E1, E3 o E5 o una licencia de Office 365 a3 o a5. 
- Una licencia de Microsoft Teams y Microsoft Stream.

> [!IMPORTANT]
> El usuario que crea y programa un evento en vivo debe tener un buzón de correo de Exchange Online.

Es importante saber que se necesita una licencia de Office 365 para participar en un evento en vivo como usuario autenticado, pero esto depende del método de producción utilizado:

- **Para la producción de inicio rápido**  El usuario debe tener asignada una licencia de Microsoft Teams.
- **Para la producción de codificador externo** El usuario debe tener asignada una licencia de Microsoft Stream.

Para obtener más información sobre las licencias, vea [licencias complementarias de Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

El usuario debe tener:
- Programación de reuniones privadas en Teams habilitado (*el TeamsMeetingPolicy-AllowPrivateMeetingScheduling Parameter = true*).
- El uso compartido de vídeos está habilitado en las reuniones de Teams (*el TeamsMeetingPolicy-AllowIPVideo Parameter = true*).
- Pantalla compartida habilitada en reuniones de Teams (*el TeamsMeetingPolicy-ScreenSharingMode Parameter = EntireScreen*).
- Programación de eventos en directo en Teams habilitado (*el TeamsMeetingBroadcastPolicy-AllowBroadcastScheduling Parameter = true*).
- Permisos para crear eventos en directo de Microsoft Stream (para la producción de codificador externo).

> [!IMPORTANT]
> Los invitados de Office 365, los federados y los usuarios anónimos no pueden ser invitados como productores o moderadores en eventos de Teams Live. Los usuarios federados y invitados de Office 365 solo pueden ver los eventos en directo de forma anónima. 
 
## <a name="who-can-watch-live-events"></a>¿Quién puede ver eventos en directo?

|**Visibilidad de los asistentes**       |**Inicio rápido**  |**Codificador externo**  |
|------------------------------|-----------------|----------------------|
|Público (usuarios anónimos)      |  Sí            |  No                  |
|Usuarios invitados                   |  No<sup>1</sup> |  No                  |
|Todas las personas de la empresa federada |  No<sup>1</sup> |  No                  |
|Todas las personas de la empresa           |  Sí             |  Sí                 |
|Grupos o personas específicos      |  Sí             |  Sí                 |

<sup>1</sup> solo puede ver eventos en vivo como usuarios anónimos.

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventos de Teams Live y difusión de reunión de Skype
En la siguiente tabla se resaltan las funciones principales y las características que se ofrecen en eventos en directo y cómo se diferencian de la difusión de reunión de Skype. 

|**Capacidades**   |**Difusión de reunión de Skype** |**Eventos producidos en Microsoft Teams** |**Eventos producidos en una aplicación o dispositivo externo** |
|---------|---------|---------|---------|
|Tamaño máximo de audiencia |10.000 asistentes |10.000 asistentes * |10.000 asistentes * |
|Duración máxima del evento en directo |4 horas |4 horas |4 horas |
|Número máximo de eventos dinámicos simultáneos por inquilino de Office 365 |4,5  | 4,5  | 4,5  |
|Creación de eventos en directo |   Portal de difusión de reunión de Skype |Teams, Yammer a través de Teams | Teams, Yammer a través de Teams, streaming |
|Compromiso de audiencias: Yammer |&#x2714; |&#x2714; (experiencia integrada) |&#x2714; (experiencia integrada) |
|Compromiso de audiencia: moderador Q & A |&#x2714;  |&#x2714; |&#x2714; |
|Cliente productor en Windows |&#x2714; (Skype empresarial) |&#x2714; (Teams) |&#x2714; (Stream, Teams a través de Stream embed) |
|Cliente productor en Mac |X  | &#x2714; (Teams) |&#x2714; (Stream, Teams a través de Stream embed) |
|Número de asistentes en la interfaz de usuario del productor |X  |&#x2714; (Teams) |&#x2714; (Stream, Teams a través de Stream embed) |
|Permite varios moderadores |&#x2714; (Skype empresarial) |&#x2714; (Teams) |N/D  |
|Invitar a un moderador durante la reunión |&#x2714; (Skype empresarial) |X |N/D |
|Unirse al moderador en la web y en el móvil |&#x2714; (Skype empresarial)  |X |N/D |
|Moderadores y asistentes de invitados de & federado |&#x2714; (Skype empresarial)  | (próximamente) |N/D |
|Moderador: acceso a la RTC |X |&#x2714; (Teams) |N/D |
|Presentar una pantalla |X |&#x2714; (Teams) |N/D |
|Presentar un PowerPoint (uso compartido de PPT) |&#x2714; |X (mitigado a través de pantalla compartida) |N/D |
|Grabación de reuniones basada en la nube |&#x2714; |&#x2714; |&#x2714; |
|Publicar automáticamente la grabación en Microsoft Stream |X |X |&#x2714; |
|Traducción y subtítulos en tiempo real |&#x2714; |&#x2714; (próximamente) |X |
|Subtítulos en grabaciones de eventos en directo |&#x2714; |&#x2714; (próximamente) |&#x2714; |
|Los controles de asistentes DVR (pausar, rebobinar) |&#x2714; |&#x2714; |&#x2714; |
|Soporte técnico eCDN |&#x2714; (Hive, Kollective, rampa) |&#x2714; (Hive, Kollective, rampa) |&#x2714; (Hive, Kollective, rampa) |
|Informe de asistencia posterior a la difusión para los productores |&#x2714; |&#x2714; |X |
|Análisis de la opinión de la audiencia: votación en vivo & sondeos |&#x2714; (Microsoft Pulse) |X |X |

> [!IMPORTANT]
> Los límites establecidos pueden cambiarse.

## <a name="regional-availability"></a>Disponibilidad regional
Puede usar eventos de Teams Live en varias regiones de todo el mundo. La siguiente información muestra la disponibilidad para miembros del equipo del evento y los asistentes. 

> [!IMPORTANT]
> La región del evento se selecciona automáticamente según el organizador y la organización de Office 365.

**Disponible en estas regiones**
- Americano
- Europa/África
- Asia Pacífico
- Ir a Canadá local

**Exclusiones y consideraciones**
- **Ir a locales:** Actualmente no se admiten las variables locales de Reino Unido, India, Australia, Japón y otras personas de Microsoft Teams go.
- **China:** Los miembros del equipo del evento y los asistentes no podrán usar los eventos en directo de Teams porque no se puede obtener acceso a la CDN de Azure en China. Una solución es usar una conexión VPN corporativa, que obtiene el cliente conectado a CDN a través de la red corporativa del cliente.

## <a name="next-steps"></a>Pasos siguientes
Vaya a [configuración de eventos de Teams Live](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Temas relacionados
- [¿Qué son los eventos en directo en Teams?](what-are-teams-live-events.md)
- [Configuración de eventos en directo en Teams](set-up-for-teams-live-events.md)
- [Configurar los eventos en directo en Teams](configure-teams-live-events.md)

