---
title: Análisis e informes de Microsoft Teams
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: En este artículo, obtendrá información sobre los informes de Teams disponibles en el Centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6a3cbf42c65d054befac8ad4e1f25d8be65f286
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853041"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Análisis e informes de Microsoft Teams

En el centro de administración de Microsoft Teams hay disponible una nueva experiencia de análisis e informes para Microsoft Teams. Puede ejecutar diferentes informes para obtener información sobre cómo usan los usuarios de su organización Teams. Por ejemplo, puede ver cuántos usuarios se comunican a través de mensajes de canal y chat, así como los tipos de dispositivos que usan para conectarse a Teams. Su organización puede usar la información de los informes para comprender mejor los patrones de uso, ayudar a tomar decisiones empresariales e informar sobre los esfuerzos de aprendizaje y comunicación.

## <a name="how-to-access-the-reports"></a>Cómo obtener acceso a los informes

Para obtener acceso a los informes, debe ser administrador global de Microsoft 365 o Office 365, lector global de Microsoft 365 o Office 365, administrador del servicio Teams o administrador de Skype Empresarial. Para obtener más información sobre Teams roles de administrador y a qué informes puede acceder cada rol de administrador, vea [Usar Teams roles de administrador para administrar Teams](../using-admin-roles.md).

Vaya al centro de administración de Microsoft Teams, en el panel de navegación izquierdo, seleccione **Análisis & informes** y, a continuación, en **Ver informes**, elija el informe que desea ejecutar.

> [!NOTE]
> Los informes del centro de administración de Microsoft Teams son independientes de los informes de actividad de Teams que forman parte de los informes Microsoft 365 de la Centro de administración de Microsoft 365. Para obtener más información sobre los informes de actividad de la Centro de administración de Microsoft 365, vea [Teams informes de actividad en la Centro de administración de Microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>referencia de informes de Teams

Esta es una lista de los informes de Teams disponibles en el centro de administración de Microsoft Teams y una descripción general de parte de la información disponible en cada informe.

Mejoramos continuamente la experiencia de creación de informes Teams y agregamos características y funcionalidades. Con el tiempo, crearemos capacidades adicionales en los informes y agregaremos nuevos informes en el centro de administración de Microsoft Teams.

|Informe  |¿Qué se mide? |
|---------|---------|
|[Informes de uso de Teams](teams-usage-report.md)  |  Usuarios activos<br/>Usuarios activos en equipos y canales<br/>Canales activos<br/>Mensajes<br/>Configuración de privacidad de teams<br/>Invitados de un equipo   |
|[Informe de actividad de usuario de Teams](user-activity-report.md)  | Mensajes que un usuario publicó en un chat de equipo<br/>Mensajes que un usuario publicó en un chat privado<br/>  1:1 llama a un usuario en el que ha participado<br/> Número de reuniones organizadas por el usuario <br/>Número de reuniones en las que el usuario ha participado<br/>Audio, vídeo y tiempo de uso compartido de pantalla de reuniones<br/>   Fecha de la última actividad de un usuario     |
|[Informe de uso de dispositivos de Teams](device-usage-report.md)   |  Usuarios de Windows<br/>Usuarios de Mac<br/>Usuarios de iOS<br/>Usuarios de teléfonos Android     |
|[Informe de uso de eventos en directo de Teams](teams-live-event-usage-report.md)   |  Vistas totales<br>Hora de inicio<br>Estado del evento<br>Organizador<br>Presentador<br>Productor<br>Configuración de la grabación<br>Tipo de producción    |
|[Teams informe usuarios bloqueados de RTC](pstn-blocked-users-report.md)   |  Nombre para mostrar<br>Teléfono número<br>Motivo<br>Tipo de acción<br>Fecha y hora de la acción   |
|[Teams informe de grupos de minutos RTC](pstn-minute-pools-report.md) |  País o región<br>Funcionalidad (licencia) <br>Minutos totales<br>Minutos usados<br>Minutos disponibles|
|[Teams informe de uso de RTC: planes de llamadas](pstn-usage-report.md#calling-plans)|  Marca de tiempo<br>Nombre de usuario<br>Teléfono número<br>Tipo de llamada <br>Llamado a<br>País o región <br>Se ha llamado desde <br>Desde el país o la región<br>Cargo<br>Moneda<br>Duración<br>Nacional e internacional<br>Id. de llamada<br>Tipo de número<br>País o región<br>Id. de conferencia<br>Funcionalidad (licencia)|
|[Teams informe de uso de RTC: enrutamiento directo](pstn-usage-report.md#direct-routing)  |  Marca de tiempo<br>Nombre para mostrar<br>Dirección SIP<br>Teléfono número <br>Tipo de llamada<br>Llamado a<br>Hora de inicio<br>Hora de invitación<br>Tiempo de error<br>Hora de finalización<br>Duración<br>Tipo de número<br>Omisión de medios<br>SBC FQDN<br>Región de Azure<br>Tipo de evento<br>Código SIP final<br>Subcódigo final de Microsoft<br>Frase SIP final<br>Id. de correlación  |
|[informe de licencia de Teams protección de la información](information-protection-license-report.md)  | <br>Si los usuarios tienen licencias válidas para enviar sus mensajes a través de notificaciones de cambio</br><br>Número total de eventos de notificación de cambios desencadenados por un usuario<br><br>Qué aplicaciones escuchan los eventos de notificación de cambios de toda la organización<br>|
|[Teams informe de uso de visitas virtuales](virtual-visits-usage-report.md)  | Número de citas virtuales<br>Número de citas Bookings<br>Número de citas integradas con registros médicos electrónicos (EHR) Teams<br>Duración media de una cita<br>Promedio de tiempo de espera en la sala de espera de los asistentes<br>Hora de inicio<br>Id. de reunión<br>Tiempo de espera en la sala de espera<br>Duración<br>Estado<br>Tipo de producto<br>Asistentes<br>SMS enviados
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Establecer que los datos específicos del usuario sean anónimos

Para que los datos de Teams actividad de usuario y Teams informe de uso de dispositivos sean anónimos, debes ser administrador global. Esto ocultará la información identificable, como el nombre para mostrar, el correo electrónico y el identificador de Microsoft Azure Active Directory en los informes y sus exportaciones.

1. En Centro de administración de Microsoft 365, vaya a la **Configuración Organización Configuración** \> y, en la pestaña **Servicios**, elija **Informes**.
    
2. Seleccione **Informes** y, a continuación, elija **Mostrar nombres de usuario, grupo y sitio ocultos en todos los informes**. Esta configuración se aplica tanto a los informes de uso de Centro de administración de Microsoft 365 como al centro de administración de Teams.
  
3. Seleccione **Guardar cambios**.

> [!NOTE]
> Si habilita esta opción, se despersonalizará la información de [Teams informe de actividad del usuario](user-activity-report.md) y [Teams informe de uso del dispositivo](device-usage-report.md). No afectará a otros informes de uso disponibles en Teams centro de administración.
> Esta configuración también se aplica a los informes de uso de Microsoft 365 de Centro de administración de Microsoft 365, Microsoft Graph y Power BI.
