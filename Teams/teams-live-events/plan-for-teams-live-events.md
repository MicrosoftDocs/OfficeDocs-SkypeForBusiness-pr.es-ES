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
localization_priority: Priority
ms.collection:
- M365-collaboration
search.appverid: MET150
description: En este artículo encontrará información sobre los factores que debe tener en cuenta antes de configurar eventos en vivo en Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2258103e73b13a22965e0fbf7749d012e09ed485
ms.sourcegitcommit: 491c44b6a9b30faaf4d73394969f4a0587362830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "47820494"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Plan para eventos en directo en Microsoft Teams

Cuando planee a los equipos eventos para tener reuniones grandes en la organización, debe tener en cuenta varios factores antes de empezar a configurarlo.

 > [!Note]
> Para obtener más información sobre los eventos en directo de Teams en las distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="who-can-attend-create-and-schedule-live-events"></a>¿Quién puede crear, asistir y programar eventos en directo?

Cualquiera puede asistir a un evento en directo sin una licencia. Lea [Inicio rápido para administradores: reuniones y eventos en vivo](../quick-start-meetings-live-events.md).

Para que el usuario programe un evento en directo de Teams se requieren los siguientes requisitos previos.

Estas son las licencias que debe asignar para producir o presentar un evento de Teams en directo:  

- Una licencia de Microsoft o de Office 365 Enterprise E1, E3 o E5 o una licencia de Office 365 Educación A3 o A5.
- Una licencia de Microsoft Teams. - esta se incluye en las licencias anteriores. 
- Se requiere una licencia de Microsoft Stream si tiene previsto compartir el contenido en una aplicación o dispositivo externo. Consulte [licencias de Microsoft Stream](https://docs.microsoft.com/stream/license-overview). 

  Los usuarios no necesitarán una licencia de Microsoft Stream asignada si quiere que los usuarios solo graben y descarguen las grabaciones. Esto significará que las grabaciones no se almacenan en Microsoft Stream, sino que se almacenan en Azure Media Services (AMS) con un límite de 30 días antes de que se eliminen. En este momento, no es algo que un administrador pueda controlar o administrar, incluida la capacidad de eliminarlo.

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

Para que un invitado pueda presentar en un evento en directo, haga lo siguiente:

1. [Agregue el usuario como invitado a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Pida al usuario que acepte la invitación y se una al equipo.
3. [Programe el evento en directo y agregue el invitado al grupo de eventos](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

Recomendamos que cree un canal para los productores y moderadores del evento en directo para que puedan chatear y compartir información antes del evento. Los invitados que no dispongan de credenciales de Microsoft 365 no podrán ver el calendario en Teams. Para que sea más fácil para ellos unirse al evento, los productores pueden publicar el vínculo del evento en el canal. Los moderadores pueden abrir Teams, ir al canal y, después, hacer clic en el vínculo para unirse al evento. 

## <a name="who-can-watch-live-events"></a>¿Quién puede ver los eventos en directo?

|**Visibilidad del asistente**       |**Producción de Teams**  |**Producción de dispositivos o aplicaciones externos**  |
|------------------------------|-----------------|----------------------|
|Público (Usuarios anónimos)      |  Sí            |  No                  |
|Usuarios invitados                   |  Sí            |  No                  |
|Todos los usuarios de la empresa de acceso externo (federaciones) |  Sí<sup>1</sup>|  No                  |
|Todas los usuarios de la empresa           |  Sí            |  Sí                 |
|Grupos específicos / personas      |  Sí            |  Sí                 |

<sup>1 </sup>solo se pueden invitar a un solo asistente de acceso externo (federación) por usuarios y grupo <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Eventos y Difusión de reunión de Skype en Teams

En la siguiente tabla, se resaltan las funciones y características principales ofrecidas en los eventos en directo y cómo estas se diferencian de la Difusión de reunión de Skype.

> [!IMPORTANT]
> **Aumentamos el límite de eventos en directo de Microsoft 365**
> 
> Para ayudar a los clientes a cumplir con unas necesidades de comunicación que cambian cada día, los eventos en directo de Microsoft 365 Live elevarán temporalmente sus límites predeterminados hasta el 1 de julio de 2020 para eventos en directo alojados en Teams. A finales de abril de 2020 se comenzaron a elevar los siguientes límites:
> - Límite de asistentes: los eventos pueden dar cabida a hasta 20 000 asistentes.
> - Eventos simultáneos: 50 eventos se pueden hospedar de forma simultánea en un espacio empresarial.
> - Duración del evento: se ha aumentado la duración del evento hasta a 16 horas por difusión.

|**Función**   |**Difusión de reunión de Skype** |**Eventos producidos en Teams** |**Eventos producidos en las aplicaciones o dispositivos externos** |
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
|Soporte técnico eCDN Partner |&#x2714; (Kollective, Hive) |&#x2714; (Kollective, Hive) |&#x2714; (Hive, Kollective, Ramp) |
|Informe de asistencia posterior a la difusión para los productores |&#x2714; |&#x2714; |&#x274C; |
|Análisis de opiniones de los asistentes: votación y sondeos en directo |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> Los límites establecidos pueden ser modificados. Compruebe[ Los límites y las especificaciones de los Teams](../limits-specifications-teams.md)<br/>
<sup>2</sup> Puede tener hasta 250 moderadores y productores en un evento en directo, pero solo se muestran en la lista los últimos 10 que habló.

## <a name="regional-availability"></a>Disponibilidad regional

Puede usar los eventos en directo de Teams en varias regiones a través de todo el mundo. La siguiente información muestra la disponibilidad de los miembros del equipo y los asistentes al evento.

> [!IMPORTANT]
> La región para el evento se selecciona automáticamente dependiendo del organizador y la ubicación del inquilino de Microsoft 365.

**Disponible en estos centros de datos regionales **

- Norteamérica
- Centroamérica
- Sudamérica
- Asia Pacífico
- Europa / África

**Ubicación de los datos para estos países y regiones (compatibles)**
- Australia
- Canada
- India
- Japón
- Reino Unido

**Estos países o regiones y estas nubes no son compatibles**
- Alemania
- Francia
- Noruega
- Sudáfrica
- Corea del Sur
- Suiza
- EMIRATOS ÁRABES UNIDOS
- Government Community Cloud (GCC)-H
- REQUISITODOD

**Exclusiones y permisos**

- **Ubicación de datos:** las ubicaciones de datos de Teams, excepto las que se enumeraron anteriormente, no son compatibles en estos momentos.
- **China:** los participantes y los miembros del equipo no podrán usar los eventos en directo de Teams, ya que no se puede obtener acceso a Microsoft Azure Content Delivery Network en China. Una forma de evitar el problema es usar una conexión VPN corporativa, que mantiene al cliente conectado a la red CDN a través de la red corporativa.

## <a name="next-steps"></a>Siguientes pasos

Vaya a [Configuración de eventos en directo de Teams](set-up-for-teams-live-events.md)

### <a name="related-topics"></a>Temas relacionados

- [¿Qué son los eventos en directo de Teams?](what-are-teams-live-events.md)
- [Configuración de Eventos en Directo de Teams](set-up-for-teams-live-events.md)
- [Establecer la configuración de eventos en directo de Microsoft Teams](configure-teams-live-events.md)
