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
description: En este artículo, obtendrá información sobre los informes de Teams que están disponibles en el Centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0891b9267039d8c07d437cb8e67eb2b982a0016
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883553"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Análisis e informes de Microsoft Teams

En el Centro de administración de Microsoft Teams hay disponible una nueva experiencia de análisis e informes para Microsoft Teams. Puede ejecutar diferentes informes para obtener información sobre cómo los usuarios de su organización usan Teams. Por ejemplo, puede ver cuántos usuarios se comunican a través de mensajes de canal y chat, así como los tipos de dispositivos que usan para conectarse a Teams. Su organización puede usar la información de los informes para comprender mejor los patrones de uso, ayudar a tomar decisiones empresariales e informar sobre los esfuerzos de aprendizaje y comunicación.

## <a name="how-to-access-the-reports"></a>Cómo obtener acceso a los informes

Para acceder a los informes, debe ser administrador global de Microsoft 365 u Office 365, lector global de Microsoft 365 u Office 365, administrador del servicio de Teams o administrador de Skype Empresarial. Para obtener más información sobre los roles de administrador de Teams y a qué informes puede acceder cada rol de administrador, consulte [Usar roles de administrador de Teams para administrar Teams](../using-admin-roles.md).

Vaya al Centro de administración de Microsoft Teams, en el panel de navegación izquierdo, seleccione **Análisis & informes** y, a continuación, en **Ver informes**, elija el informe que desea ejecutar.

> [!NOTE]
> Los informes del Centro de administración de Microsoft Teams son independientes de los informes de actividad de Teams que forman parte de los informes de Microsoft 365 en el Centro de administración de Microsoft 365. Para obtener más información sobre los informes de actividades en el Centro de administración de Microsoft 365, vea [Informes de actividad de Teams en el Centro de administración de Microsoft 365](../teams-activity-reports.md).

## <a name="teams-reporting-reference"></a>Referencia de informes de Teams

Esta es una lista de los informes de Teams disponibles en el Centro de administración de Microsoft Teams y una descripción general de parte de la información disponible en cada informe.

Mejoramos continuamente la experiencia de creación de informes de Teams y agregamos características y funcionalidades. Con el tiempo, crearemos capacidades adicionales en los informes y agregaremos nuevos informes en el Centro de administración de Microsoft Teams.

|Informe  |¿Qué se mide? |
|---------|---------|
|[Informes de uso de Teams](teams-usage-report.md)  |  Usuarios activos<br/>Usuarios activos en equipos y canales<br/>Canales activos<br/>Mensajes<br/>Configuración de privacidad de teams<br/>Invitados de un equipo   |
|[Informe de actividad de usuario de Teams](user-activity-report.md)  | Mensajes que un usuario publicó en un chat de equipo<br/>Mensajes que un usuario publicó en un chat privado<br/>  1:1 llama a un usuario en el que ha participado<br/> Número de reuniones organizadas por el usuario <br/>Número de reuniones en las que el usuario ha participado<br/>Audio, vídeo y tiempo de uso compartido de pantalla de reuniones<br/>   Fecha de la última actividad de un usuario     |
|[Informe de uso de dispositivos de Teams](device-usage-report.md)   |  Usuarios de Windows<br/>Usuarios de Mac<br/>Usuarios de iOS<br/>Usuarios de teléfonos Android     |
|[Informe de uso de eventos en directo de Teams](teams-live-event-usage-report.md)   |  Vistas totales<br>Hora de inicio<br>Estado del evento<br>Organizador<br>Presentador<br>Productor<br>Configuración de la grabación<br>Tipo de producción    |
|[Informe de usuarios bloqueados de RTC de Teams](pstn-blocked-users-report.md)   |  Nombre para mostrar<br>Número de teléfono<br>Motivo<br>Tipo de acción<br>Fecha y hora de la acción   |
|[Informe de grupos de minutos de RTC de Teams](pstn-minute-pools-report.md) |  País o región<br>Funcionalidad (licencia) <br>Minutos totales<br>Minutos usados<br>Minutos disponibles|
|[Informe de uso de RTC de Teams: Planes de llamadas](pstn-usage-report.md#calling-plans)|  Marca de tiempo<br>Nombre de usuario<br>Número de teléfono<br>Tipo de llamada <br>Llamado a<br>País o región <br>Se ha llamado desde <br>Desde el país o la región<br>Cargo<br>Moneda<br>Duración<br>Nacional e internacional<br>Id. de llamada<br>Tipo de número<br>País o región<br>Id. de conferencia<br>Funcionalidad (licencia)|
|[Informe de uso de RTC de Teams: enrutamiento directo](pstn-usage-report.md#direct-routing)  |  Marca de tiempo<br>Nombre para mostrar<br>Dirección SIP<br>Número de teléfono <br>Tipo de llamada<br>Llamado a<br>Hora de inicio<br>Hora de invitación<br>Tiempo de error<br>Hora de finalización<br>Duración<br>Tipo de número<br>Omisión de medios<br>SBC FQDN<br>Región de Azure<br>Tipo de evento<br>Código SIP final<br>Subcódigo final de Microsoft<br>Frase SIP final<br>Id. de correlación  |
|[Informe de licencia de protección de la información de Teams](information-protection-license-report.md)  | <br>Si los usuarios tienen licencias válidas para enviar sus mensajes a través de notificaciones de cambio</br><br>Número total de eventos de notificación de cambios desencadenados por un usuario<br><br>Qué aplicaciones escuchan los eventos de notificación de cambios de toda la organización<br>|
|[Informe de uso de visitas virtuales de Teams](virtual-visits-usage-report.md)  | Número de citas virtuales<br>Número de citas de Bookings<br>Número de citas integradas con registros electrónicos de salud (EHR) de Teams<br>Duración media de una cita<br>Promedio de tiempo de espera en la sala de espera de los asistentes<br>Hora de inicio<br>Id. de reunión<br>Tiempo de espera en la sala de espera<br>Duración<br>Estado<br>Tipo de producto<br>Asistentes<br>SMS enviados
|[Informe citas virtuales del conector EHR de Teams](../expand-teams-across-your-org/healthcare/ehr-admin-reports.md) | Hora de inicio<br>Duración<br>Principal (nombre del organizador de la reunión)<br>Correo electrónico del principal (correo electrónico del organizador de la reunión)<br>Departamento<br>Asistentes<br>Tiempo de espera en la sala de espera<br>Si la cita está dentro del límite de asignación
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Establecer que los datos específicos del usuario sean anónimos

Para que los datos de la actividad de los usuarios de Teams y el informe de uso de dispositivos de Teams sean anónimos, debe ser administrador global. Esto ocultará la información identificable, como el nombre para mostrar, el correo electrónico y el id. de Microsoft Azure Active Directory en los informes y sus exportaciones.

1. En el Centro de administración de Microsoft 365, vaya a **Configuración** \> de la organización **y, en** la pestaña **Servicios** , elija **Informes**.
    
2. Seleccione **Informes** y, a continuación, elija **Mostrar nombres de usuario, grupo y sitio ocultos en todos los informes**. Esta configuración se aplica tanto a los informes de uso del Centro de administración de Microsoft 365 como al Centro de administración de Teams.
  
3. Seleccione **Guardar cambios**.

> [!NOTE]
> Si habilita esta opción, se despersonalizará la información en el [informe de actividad de los usuarios de Teams](user-activity-report.md) y en los informes [de uso de dispositivos de Teams](device-usage-report.md) . No afectará a otros informes de uso disponibles en el Centro de administración de Teams.
> Esta configuración también se aplica a los informes de uso de Microsoft 365 en el Centro de administración de Microsoft 365, Microsoft Graph y Power BI.
