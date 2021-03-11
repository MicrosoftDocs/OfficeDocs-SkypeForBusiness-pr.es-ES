---
title: Plan para eventos en directo en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Priority
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
search.appverid: MET150
description: En este artículo encontrará información sobre los factores que debe tener en cuenta antes de configurar eventos en directo en Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc05b94fd5f375133c0682d72757eec5f90ef43e
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569242"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Plan para eventos en directo en Microsoft Teams

Cuando planee eventos en directo de Teams para tener reuniones grandes en la organización, debe tener en cuenta varios factores antes de empezar la configuración.

> [!Note]
> For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.

## <a name="who-can-attend-create-and-schedule-live-events"></a>¿Quién puede crear, asistir y programar eventos en directo?

Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).

Para que el usuario programe un evento en directo de Teams se requieren los siguientes requisitos previos.

Estas son las licencias que debe asignar para organizar, producir o presentar un evento en directo de Teams:  

- **Para organizar:** una licencia de Microsoft o de Office 365 Enterprise E1, E3 o E5 **[o]** una licencia de Office 365 Educación A3 o A5. 
- **Para producir o presentar:** una licencia de Microsoft o de Office 365 Enterprise E1, E3 o E5 **[o]** una licencia de Office 365 Educación A1, A3 o A5. La excepción de este requisito es que los usuarios invitados pueden presentar sin una licencia si se cumplen los otros criterios para [usuarios invitados](plan-for-teams-live-events.md#guest-to-present).
- Una licencia de Microsoft Teams: se incluye en las licencias que aparecen en la primera y la segunda viñeta.
- Se requiere una licencia de Microsoft Stream si tiene previsto compartir el contenido en una aplicación o dispositivo externo. Consulte [licencias de Microsoft Stream](https://docs.microsoft.com/stream/license-overview).

  Los usuarios no necesitarán una licencia asignada de Microsoft Stream si desea que los usuarios únicamente graben y descarguen las grabaciones. Esto significará que las grabaciones no se almacenan en Microsoft Stream, sino que se almacenan en Azure Media Services (AMS) con un límite de 180 días antes de que se eliminen. En este punto, no es algo que un administrador pueda controlar o administrar para incluir la capacidad de eliminarlo.

>[!Note]
> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to OneDrive for Business and SharePoint for meeting recordings.

> [!NOTE]
> En este momento no hay planes de Microsoft 365 Small Business que puedan usarse para crear y mantener eventos en vivo de Teams.

Para participar en un evento en directo como usuario autenticado se requiere una licencia de Microsoft 365 u Office 365, pero este requisito depende del método de producción que se use:

- **Para eventos producidos en Teams** El usuario debe tener asignada una licencia de Teams.
- **Para eventos producidos con una aplicación o dispositivo externo** El usuario debe tener asignada una licencia de Stream.

> [!NOTE]
> Los eventos en directo de Teams Live están disponible para las organizaciones de la comunidad en la nube del gobierno (GCC) en los Estados Unidos.

Para obtener más información sobre las licencias, vea [Licencias complementarias de Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

El usuario debe tener:

- La programación de reuniones privadas habilitada en Teams (*el parámetro TeamsMeetingPolicy -AllowPrivateMeetingScheduling parameter = True*).
- El uso compartido de vídeos habilitado para las reuniones en Teams (*el parámetro TeamsMeetingPolicy -AllowIPVideo parameter = True*).
- El uso compartido de vídeos habilitado para las reuniones en Teams (*el parámetro TeamsMeetingPolicy -ScreenSharingMode = EntireScreen*).
- La programación de reuniones privadas habilitada en Teams (*el parámetro TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling = True*).
- Permisos para crear eventos en directo en Stream (para producción de dispositivos o aplicaciones externas).
- El modo de coexistencia se configuró para que pueda programar reuniones de Teams (*islas, en primer lugar, o solo Teams*).

> [!IMPORTANT]
> Los usuarios anónimos sin autenticar no pueden ser invitados como productores ni moderadores de los eventos en directo de Teams.

### <a name="guest-to-present"></a>[Invitado a presentar](#guest-to-present)

Para que un invitado pueda presentar en un evento en directo, haga lo siguiente:

1. [Agregue el usuario como invitado a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Pida al usuario que acepte la invitación y se una al equipo.
3. [Programe el evento en directo y agregue el invitado al grupo de eventos](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then click the link to join the event.

## <a name="who-can-watch-live-events"></a>¿Quién puede ver los eventos en directo?

| Visibilidad del asistente | Producción de Teams | Producción de aplicaciones o dispositivos externos |
|------------------------------|-----------------|----------------------|
|Público (usuarios anónimos)      |  Sí            |  No                  |
|Usuarios invitados                   |  Sí<sup>1</sup>            |  No                  |
|Todos los usuarios de la empresa de acceso externo (federaciones) |  Sí<sup>1</sup>|  No                  |
|Todas los usuarios de la empresa           |  Sí            |  Sí                 |
|Grupos específicos / personas      |  Sí            |  Sí                 |

<sup>1 </sup> Solo se pueden invitar a través de usuarios y grupo <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventos y Difusión de reunión de Skype en Teams

En la siguiente tabla, se resaltan las funciones y características principales ofrecidas en los eventos en directo y cómo estas se diferencian de la Difusión de reunión de Skype.

> [!IMPORTANT]
> **Aumentamos el límite de eventos en directo de Microsoft 365**
>
> **Para continuar cubriendo las necesidades de nuestros clientes, hasta el 30 de junio de 2021, extenderemos los aumentos de los límites temporales para los eventos en vivo, incluyendo**:
>
>- Soporte de eventos de hasta 20 000 asistentes
>- 50 eventos se pueden hospedar de forma simultánea en un espacio empresarial
>- Difusión de un evento de 16 horas de duración
>
> Además, los eventos en directo de hasta 100 000 asistentes pueden planificarse con el programa de asistencia para eventos en directo de Microsoft 365. El equipo evaluará cada solicitud y trabajará con usted para determinar las opciones disponibles. [Más información](https://aka.ms/Stream/Blog/LiveEventOptions). 

| Funcionalidad | Difusión de reunión de Skype | Eventos producidos en Teams | Eventos producidos en las aplicaciones o dispositivos externos |
|---------|---------|---------|---------|
|Tamaño máximo de audiencia |10 000 asistentes |10 000 asistentes<sup>1</sup> |10 000 asistentes<sup>1</sup> |
|Duración máxima del evento en directo |4 horas |4 horas |4 horas |
|Cantidad máxima de moderadores y productores en un evento en directo |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Notas de la versión para las versiones de las Aplicaciones de Microsoft 365 u Office 365 |15  | 15  | 15  |
|Creación de eventos en directo |   Portal de Difusión de reunión de Skype |Teams, Yammer a través de Teams | Teams, Yammer a través de Teams, Stream |
|Compromiso de audiencia: Yammer |&#x2714; |&#x2714; (experiencia integrada) |&#x2714; (experiencia integrada) |
|Negociación de audiencia: moderado por P y R |&#x2714;  |&#x2714; |&#x2714; |
|Cliente productor en Windows |&#x2714; (Skype Empresarial) |&#x2714; (Teams) |&#x2714; (Stream, Teams a través de Stream Embed) |
|Cliente productor en Mac |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream, Teams a través de Stream Embed) |
|Recuento de asistentes en la interfaz de usuario del productor |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream, Teams a través de Stream Embed) |
|Permite varios moderadores |&#x2714; (Skype Empresarial) |&#x2714; (Teams) |N/D  |
|Invitar a un moderador durante la reunión |&#x2714; (Skype Empresarial) |&#x274C; |N/D |
|El moderador se unió desde el móvil e Internet |&#x2714; (Skype Empresarial)  |&#x274C; |N/D |
|Acceso externo (federación) y presentadores o asistentes invitados |&#x2714; (Skype Empresarial)  |  &#x2714; (Teams) |N/D |
|Moderador: acceso por RTC |&#x274C; |&#x2714; (Teams) |N/D |
|Presentar en una pantalla |&#x274C; |&#x2714; (Teams) |N/D |
|Compartir audio del sistema en Windows (solo disponible cuando se comparte la pantalla)|&#x274C; |&#x2714; (Teams) |&#x2714; |
|Presentar un archivo de PowerPoint (uso compartido de archivos PPT) |&#x2714; |&#x274C; (atenuado a través del uso compartido de la pantalla) |N/D |
|Grabación de la reunión guardada en la nube |&#x2714; |&#x2714; |&#x2714; |
|Publicar automáticamente la grabación en Stream |&#x274C; |&#x274C; |&#x2714; |
|Subtítulos en directo y otros subtítulos |&#x2714; |&#x2714; |&#x274C; |
|Subtítulos para las grabaciones de eventos en directo |&#x2714; |&#x2714; |&#x2714; |
|Controles DVR de los asistentes (pausa, retroceso) |&#x2714; |&#x2714; |&#x2714; |
|Soporte técnico eCDN Partner |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|Informe de asistencia posterior a la difusión para los productores |&#x2714; |&#x2714; |&#x274C; |
|Análisis de opiniones de los asistentes: votación y sondeos en directo |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> Los límites establecidos pueden cambiar. Compruebe [Límites y especificaciones para Microsoft Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> Puede tener hasta 100 moderadores y productores en un evento en directo, pero solo se muestran en la lista los últimos 10 que hablaron.

## <a name="regional-availability"></a>Disponibilidad regional

You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.

> [!IMPORTANT]
> La región para el evento se selecciona automáticamente dependiendo del organizador y la ubicación del inquilino de Microsoft 365.

**Disponible en estos centros de datos regionales**

- Norteamérica
- Centroamérica
- Sudamérica
- Asia Pacífico
- Europa / África

**Ubicación de los datos para estos países y regiones (compatibles)**

- Australia
- Canada
- Alemania
- Francia
- India
- Japón
- Sudáfrica
- Corea del Sur
- Suiza
- EMIRATOS ÁRABES UNIDOS
- Reino Unido

**Estos países o regiones y estas nubes no son compatibles**

- Brasil
- Noruega
- Government Community Cloud (GCC)-H
- REQUISITODOD

**Exclusiones y permisos**

- **Ubicación de datos:** las ubicaciones de datos de Teams, excepto las que se enumeraron anteriormente, no son compatibles en estos momentos.
- **China:** Event team members and attendees will not be able to use Teams live events because Azure CDN is not accessible in China. A workaround is to use a company VPN connection, which gets the client connected to CDN via the customer's corporate network.

## <a name="next-steps"></a>Pasos siguientes

Vaya a [Configuración de eventos en directo de Teams](set-up-for-teams-live-events.md)

### <a name="related-topics"></a>Temas relacionados

- [¿Qué son los eventos en directo de Teams?](what-are-teams-live-events.md)
- [Configuración de Eventos en Directo de Teams](set-up-for-teams-live-events.md)
- [Establecer la configuración de eventos en directo de Microsoft Teams](configure-teams-live-events.md)
