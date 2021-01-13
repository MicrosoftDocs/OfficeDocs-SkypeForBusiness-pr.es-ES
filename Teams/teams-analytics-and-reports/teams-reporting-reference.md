---
title: Análisis e informes de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: En este artículo, aprenderá acerca de los informes de Teams que están disponibles en el Centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 902320f1ea2bc9071bbb9fc2be531117dabc8eef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809280"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Análisis e informes de Microsoft Teams

Hay una nueva experiencia de análisis y generación de informes para Microsoft Teams disponible en el Centro de administración de Microsoft Teams. Puede ejecutar diferentes informes para obtener información sobre cómo usan los usuarios de su organización Teams. Por ejemplo, puede ver cuántos usuarios se comunican a través de mensajes de canal y chat, así como los tipos de dispositivos que usan para conectarse a Teams. Su organización puede usar la información de los informes para comprender mejor los patrones de uso, ayudar a tomar decisiones empresariales e informar sobre los esfuerzos de aprendizaje y comunicación.

## <a name="how-to-access-the-reports"></a>Cómo obtener acceso a los informes

Para acceder a los informes, debe ser administrador global en Microsoft 365 u Office 365, en el administrador del servicio de Teams o en el administrador de Skype Empresarial. Para obtener más información sobre los roles de administrador de Teams y qué informes pueden tener acceso a cada rol de administrador, consulte Usar los roles de administrador de [Teams para administrar Teams.](../using-admin-roles.md)

Vaya al Centro de administración de Microsoft Teams, en el panel de navegación izquierdo, seleccione Analytics **& Reports** y, a continuación, en **Informe,** elija el informe que desea ejecutar.

> [!NOTE]
> Los informes del Centro de administración de Microsoft Teams son independientes de los informes de actividad de Teams que forman parte de los informes de Microsoft 365 en el Centro de administración de Microsoft 365. Para obtener más información sobre los informes de actividades en el Centro de administración de Microsoft 365, vea Informes de actividad de Teams en el Centro de administración [de Microsoft 365.](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Referencia de informes de Teams

Aquí tiene una lista de los informes de Teams disponibles en el Centro de administración de Microsoft Teams y una descripción general de parte de la información que está disponible en cada informe.

Mejoramos continuamente la experiencia de los informes de Teams y agregamos características y funcionalidades. Con el tiempo, crearemos capacidades adicionales en los informes y agregaremos nuevos informes en el Centro de administración de Microsoft Teams.

|Informe  |¿Qué se mide? |
|---------|---------|
|[Informes de uso de Teams](teams-usage-report.md)  |  Usuarios activos<br/>Usuarios activos en equipos y canales<br/>Canales activos<br/>Mensajes<br/>Configuración de privacidad de los equipos<br/>Invitados de un equipo   |
|[Informe de actividad de usuario de Teams](user-activity-report.md)  |  Llamadas uno a uno en las que un usuario ha participado<br/>Mensajes que un usuario publicó en un chat de equipo<br/>Mensajes que un usuario publicó en un chat privado<br/>Fecha de la última actividad de un usuario     |
|[Informe de uso de dispositivos de Teams](device-usage-report.md)   |  Usuarios de Windows<br/>Usuarios de Mac<br/>Usuarios de iOS<br/>Usuarios de teléfonos Android     |
|[Informe de uso de eventos en directo de Teams](teams-live-event-usage-report.md)   |  Total de vistas<br>Hora de inicio<br>Estado del evento<br>Organizador<br>Moderador<br>Productor<br>Configuración de la grabación<br>Tipo de producción    |
|[Informe de usuarios bloqueados de RTC de Teams](pstn-blocked-users-report.md)   |  Nombre para mostrar<br>Número de teléfono<br>Motivo<br>Tipo de acción<br>Fecha y hora de la acción   |
|[Informe de grupos de minutos RTC de Teams](pstn-minute-pools-report.md) |  País o región<br>Funcionalidad (licencia) <br>Minutos totales<br>Minutos utilizados<br>Minutos disponibles|
|[Informe de uso de RTC de Teams: planes de llamadas](pstn-usage-report.md#calling-plans)|  Marca de tiempo<br>Nombre de usuario<br>Número de teléfono<br>Tipo de llamada <br>Llamado a<br>Para el país o la región <br>Llamada desde <br>Del país o la región<br>Cargar<br>Moneda<br>Duración<br>Nacional/Internacional<br>Id. de llamada<br>Tipo de número<br>País o región<br>Id. de conferencia<br>Funcionalidad (licencia)|
|[Informe de uso de RTC de Teams: enrutamiento directo](pstn-usage-report.md#direct-routing)  |  Marca de tiempo<br>Nombre para mostrar<br>Dirección SIP<br>Número de teléfono <br>Tipo de llamada<br>Llamado a<br>Hora de inicio<br>Hora de invitación<br>Tiempo de error<br>Hora de finalización<br>Duración<br>Tipo de número<br>Omisión de medios<br>SBC FQDN<br>Región de Azure<br>Tipo de evento<br>Código SIP final<br>Subcodigo final de Microsoft<br>Frase SIP final<br>Id. de correlación  |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]
