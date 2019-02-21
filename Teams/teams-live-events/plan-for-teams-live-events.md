---
title: Plan para eventos en directo en Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Obtenga información sobre los factores a tener en cuenta antes de configurar los eventos en directo en Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cee30cc853043b4424a9a30c1ad785f77ea05f70
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2019
ms.locfileid: "30120927"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Plan para eventos en directo en Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Al planear los equipos eventos en directo para incluir grandes reuniones de la organización, hay varios factores que debe tener en cuenta antes de empezar a establecerla Subir todo. 

## <a name="who-can-create-and-schedule-live-events"></a>¿Quién puede crear y programar eventos en directo? 
Los siguientes requisitos previos son necesarios para el usuario programar un evento en directo los equipos.

Estas son las licencias que se deben asignar:  
- Una licencia de Office 365 Enterprise E3 o E5 o una licencia de Office 365 A3 o A5. 
- Un Microsoft Teams, Skype para la empresa y la licencia de Microsoft Stream.

Es importante saber que se requiere una licencia de Office 365 para participar en un evento en directo como un usuario autenticado, pero esto depende del método de producción usado:

- **Producción de inicio para rápido**  El usuario debe estar asignado a una licencia de Microsoft Teams.
- **Producción de codificador para externo** El usuario debe estar asignado a una licencia de Microsoft Stream.

Para obtener más información acerca de las licencias, vea [licencias de complemento de equipos de Microsoft](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

El usuario debe tener:
- Programación de reunión privada en los equipos habilitados (*AllowPrivateMeetingScheduling - TeamsMeetingPolicy el parámetro = True*).
- Live programación de eventos en los equipos habilitados (*AllowBroadcastScheduling - TeamsMeetingBroadcastPolicy el parámetro = True*).
- Permisos para crear eventos en directo en Microsoft Stream (para [producción codificador externo](#production)).

> [!IMPORTANT]
> Invitados de Office 365, los usuarios federados y anónimos no pueden ser invitados como productores o moderadores en los equipos eventos en directo. Invitado de Office 365 y los usuarios federados pueden sólo verla eventos en directo forma anónima. 
 
## <a name="who-can-watch-live-events"></a>¿Quién puede ver los eventos en directo?

|**Visibilidad de ATTENDEE**       |**Guía de inicio rápido**  |**Codificador externo**  |
|------------------------------|-----------------|----------------------|
|Público (usuarios anónimos)      |  Sí            |  No                  |
|Usuarios invitados                   |  No hay<sup>1</sup> |  No                  |
|Todos los usuarios de empresa federada |  No hay<sup>1</sup> |  No                  |
|Todos los usuarios de empresa           |  Sí            |  Sí                 |
|Específicos de grupos o de personas      |  Sí            |  Sí                 |

<sup>1</sup> solo puede ver eventos en directo como los usuarios anónimos.

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Los equipos de live Meeting Difundir presentación de Skype y eventos
En la siguiente tabla resalta las principales características y funciones ofrecidas en eventos en directo y cómo se diferencian de Difundir presentación de reunión de Skype. 

|**Capacidad**   |**Difusión de reunión de Skype** |**Los equipos live eventos (Guía de inicio rápido)** |**Eventos de los equipos en directo (codificador externo)** |
|---------|---------|---------|---------|
|Tamaño máximo de la audiencia |asistentes de 10.000 |10.000 asistentes * |10.000 asistentes * |
|Duración máxima de live (evento) |4 horas |4 horas |4 horas |
|Creación de Live (evento) |   Portal de difusión de la reunión de Skype |Los equipos, Yammer a través de los equipos | Los equipos, Yammer a través de los equipos, secuencia |
|Compromiso de audiencia – Yammer |& #x 2714; |& #x 2714; (experiencia integrada) |& #x 2714; (experiencia integrada) |
|Compromiso de audiencia – Q moderan & A |& #x 2714;  |& #x 2714; |& #x 2714; |
|Cliente de productor en Windows |& #x 2714; (Skype para la empresa) |& #x 2714; (Equipos) |& #x 2714; (Secuencia, los equipos a través de secuencia incrustar) |
|Cliente de productor en Mac |X  | & #x 2714; (Equipos) |& #x 2714; (Secuencia, los equipos a través de secuencia incrustar) |
|Recuento de ATTENDEE de la interfaz de usuario de productor |X  |& #x 2714; (Equipos) |& #x 2714; (Secuencia, los equipos a través de secuencia incrustar) |
|Permite que varios moderadores |& #x 2714; (Skype para la empresa) |& #x 2714; (Equipos) |N/D  |
Invitar a un moderador durante la reunión |& #x 2714; (Skype para la empresa) |X |N/D |
|Combinación de moderador en Web y Mobile |& #x 2714; (Skype para la empresa)  |X |N/D |
|Moderador: acceso de RTC |X |& #x 2714; (Equipos) |N/D |
|Presentar una pantalla |X |& #x 2714; (Equipos) |N/D |
|Presentar un archivo de PowerPoint (uso compartido de PPT) |& #x 2714; |X (mitigado mediante el uso compartido de la pantalla) |N/D |
|Grabación de la reunión en función de la nube |& #x 2714; |& #x 2714; |& #x 2714; |
|Publicación automática de grabación en secuencia de Microsoft |X |X |& #x 2714; |
|Traducción y títulos de tiempo Real |& #x 2714; |& #x 2714; (próximamente) |X |
|Títulos en grabaciones de live (evento) |& #x 2714; |& #x 2714; (próximamente) |& #x 2714; |
|Controles DVR ATTENDEE (pausa, retroceso) |& #x 2714; |& #x 2714; |& #x 2714; |
|Socio eCDN soporte técnico |& #x 2714; (Subárbol, Kollective, mejorar) |& #x 2714; (Subárbol, Kollective, mejorar) |& #x 2714; (Subárbol, Kollective, mejorar) |
|Informe de asistencia posteriores a la difusión de productores |& #x 2714; |& #x 2714; |X |
|Análisis de opinión de los clientes de audiencia – Live sondeos & votación |& #x 2714; (Impulsos de Microsoft) |X |X |

> [!IMPORTANT]
> Es posible que se puede cambiar los límites que se han establecido.

## <a name="regional-availability"></a>Disponibilidad regional
Puede usar los eventos de los equipos live en varias regiones en todo el mundo. La información siguiente muestra la disponibilidad de los asistentes y los miembros del equipo (evento). 

> [!IMPORTANT]
> La región para el evento se selecciona automáticamente según el organizador y la organización de Office 365.

**Disponible en estas áreas**
- América
- Europa y África
- Asia Pacífico
- Vaya a Canadá Local

**Exclusiones y consideraciones**
- **Vaya variables locales:** Reino Unido, India y otras variables locales vaya de los equipos de Microsoft no son compatibles actualmente.
- **China:** Los asistentes y los miembros del equipo de evento no podrá usar los eventos de live de los equipos debido a que no es accesible en China CDN de Azure. Una solución alternativa consiste en usar una conexión VPN, que obtiene el cliente conectado a CDN a través de la red corporativa del cliente de empresa.

## <a name="next-steps"></a>Pasos siguientes
Vaya a [configurar para los equipos eventos en directo](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Temas relacionados
- [¿Cuáles son los equipos de eventos en directo?](what-are-teams-live-events.md)
- [Configurar para los equipos de eventos en directo](set-up-for-teams-live-events.md)
- [Establecer la configuración de eventos en directo en los equipos](configure-teams-live-events.md)

