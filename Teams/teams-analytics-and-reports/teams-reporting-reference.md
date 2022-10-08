---
title: Análisis e informes de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: b08e62a7ddee8298ff38846d8d254d10d3d6f681
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033838"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Análisis e informes de Microsoft Teams

En el Centro de administración de Microsoft Teams hay disponible una nueva experiencia de análisis e informes para Microsoft Teams. Puede ejecutar diferentes informes para obtener información sobre cómo los usuarios de su organización usan Teams. Por ejemplo, puede ver cuántos usuarios se comunican a través de mensajes de canal y chat, así como los tipos de dispositivos que usan para conectarse a Teams. Su organización puede usar la información de los informes para comprender mejor los patrones de uso, ayudar a tomar decisiones empresariales e informar sobre los esfuerzos de aprendizaje y comunicación.

## <a name="how-to-access-the-reports"></a>Cómo obtener acceso a los informes

Para acceder a los informes, debe ser administrador global de Microsoft 365 o Office 365, lector global de Microsoft 365 o Office 365, administrador del servicio de Teams o administrador de Skype Empresarial. Para obtener más información sobre los roles de administrador de Teams y a qué informes puede acceder cada rol de administrador, consulte [Usar roles de administrador de Teams para administrar Teams](../using-admin-roles.md).

Vaya al Centro de administración de Microsoft Teams, en el panel de navegación izquierdo, seleccione **Análisis & informes** y, a continuación, en **Ver informes**, elija el informe que desea ejecutar.

> [!NOTE]
> Los informes del Centro de administración de Microsoft Teams son independientes de los informes de actividad de Teams que forman parte de los informes de Microsoft 365 de la Centro de administración de Microsoft 365. Para obtener más información sobre los informes de actividad en el Centro de administración de Microsoft 365, vea [Informes de Microsoft 365 en el Centro de administración](/microsoft-365/admin/activity-reports/activity-reports).

## <a name="teams-reporting-reference"></a>Referencia de informes de Teams

Esta es una lista de los informes de Teams disponibles en el Centro de administración de Microsoft Teams en diferentes entornos y una descripción general de parte de la información disponible en cada informe.

Mejoramos continuamente la experiencia de creación de informes de Teams y agregamos características y funcionalidades. Con el tiempo, crearemos capacidades adicionales en los informes y agregaremos nuevos informes en el Centro de administración de Microsoft Teams.

|Informe  |Público |Gcc |GCCH |Dod |¿Qué se mide? |
|---------|---------|---------|---------|---------|---------|
|[Informes de uso de Teams](teams-usage-report.md)  |Sí|Sí|Sí|Sí|  Usuarios activos<br/>Usuarios activos en equipos y canales<br/>Canales activos<br/>Mensajes<br/>Configuración de privacidad de teams<br/>Invitados activos en un equipo  <br/>Usuarios externos activos (en canales compartidos)<br/>Detalles específicos del canal compartido en un equipo (nuevo)|
|[Informe de actividad de usuario de Teams](user-activity-report.md)  |Sí|Sí|Sí|Sí|Usuarios activos internos y externos (en canales compartidos)<br/> Mensajes que un usuario publicó en un chat de equipo<br/>Mensajes que un usuario publicó en un chat privado<br/>  1:1 llama a un usuario en el que ha participado<br/> Número de reuniones organizadas por el usuario <br/>Número de reuniones en las que el usuario ha participado<br/>Audio, vídeo y tiempo de uso compartido de pantalla de reuniones<br/>   Fecha de la última actividad de un usuario  <br>Interacciones de canal compartidas de un usuario (nuevo)</br>   |
|[Informe de uso de dispositivos de Teams](device-usage-report.md)   |Sí|Sí|Sí|Sí|  Usuarios de Windows<br/>Usuarios de Mac<br/>Usuarios de iOS<br/>Usuarios de teléfonos Android     |
|[Informe de uso de aplicaciones de Teams (nuevo)](app-usage-report.md)   |Sí|Sí|No|No|  Total de usuarios activos de la aplicación<br/>Total de equipos activos que usan la aplicación<br/>Total de aplicaciones instaladas (nuevas)<br/>Total de aplicaciones inactivas <br/>Uso total de aplicaciones de 1P frente a 3P frente a lob (nuevo)     |
|[Informe de uso de eventos en directo de Teams](teams-live-event-usage-report.md)   |Sí|Sí|No|No|  Vistas totales<br>Hora de inicio<br>Estado del evento<br>Organizador<br>Presentador<br>Productor<br>Configuración de la grabación<br>Tipo de producción    |
|[Informe de usuarios bloqueados de RTC de Teams](pstn-blocked-users-report.md)   |Sí|Sí|No|No|  Nombre para mostrar<br>Número de teléfono<br>Motivo<br>Tipo de acción<br>Fecha y hora de la acción   |
|[Informe de grupos de minutos de RTC de Teams](pstn-minute-pools-report.md) |Sí|Sí|No|No|  País o región<br>Funcionalidad (licencia) <br>Minutos totales<br>Minutos usados<br>Minutos disponibles|
|[Informe de uso de RTC de Teams: Planes de llamadas](pstn-usage-report.md#calling-plans)|Sí|Sí|No|No|  Marca de tiempo<br>Nombre de usuario<br>Número de teléfono<br>Tipo de llamada <br>Llamado a<br>País o región <br>Se ha llamado desde <br>Desde el país o la región<br>Cargo<br>Moneda<br>Duración<br>Nacional e internacional<br>Id. de llamada<br>Tipo de número<br>País o región<br>Id. de conferencia<br>Funcionalidad (licencia)|
|[Informe de uso de RTC de Teams: enrutamiento directo](pstn-usage-report.md#direct-routing)  |Sí|Sí|No|No|  Marca de tiempo<br>Nombre para mostrar<br>Dirección SIP<br>Número de teléfono <br>Tipo de llamada<br>Llamado a<br>Hora de inicio<br>Hora de invitación<br>Tiempo de error<br>Hora de finalización<br>Duración<br>Tipo de número<br>Omisión de medios<br>SBC FQDN<br>Región de Azure<br>Tipo de evento<br>Código SIP final<br>Subcódigo final de Microsoft<br>Frase SIP final<br>Id. de correlación  |
|[Informe de licencia de protección de la información de Teams](information-protection-license-report.md)  |Sí|Sí|No|No| <br>Si los usuarios tienen licencias válidas para enviar sus mensajes a través de notificaciones de cambio</br><br>Número total de eventos de notificación de cambios desencadenados por un usuario<br><br>Qué aplicaciones escuchan los eventos de notificación de cambios de toda la organización<br>|
|[Informe de uso de visitas virtuales de Teams](/microsoft-365/frontline/virtual-visits-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)  |Sí|Sí|No|No| Número de citas virtuales<br>Número de citas de Bookings<br>Número de citas integradas con registros electrónicos de salud (EHR) de Teams<br>Duración media de una cita<br>Promedio de tiempo de espera en la sala de espera de los asistentes<br>Hora de inicio<br>Id. de reunión<br>Tiempo de espera en la sala de espera<br>Duración<br>Estado<br>Tipo de producto<br>Asistentes<br>SMS enviados
|[Informe de Citas virtuales del conector EHR de Teams](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |Sí|Sí|No|No| Hora de inicio<br>Duración<br>Principal (nombre del organizador de la reunión)<br>Correo electrónico del principal (correo electrónico del organizador de la reunión)<br>Departamento<br>Asistentes<br>Tiempo de espera en la sala de espera<br>Si la cita está dentro del límite de asignación|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Establecer que los datos específicos del usuario sean anónimos

Para que los datos del informe de actividad de los usuarios de Teams sean anónimos, debe ser administrador global. El administrador global puede ocultar la información identificable (con hash MD5) como el nombre para mostrar, el nombre del grupo, el correo electrónico y el id. de AAD en el informe y su exportación.

1. En Centro de administración de Microsoft 365, vaya a **Configuración** \> **de** la organización y, en la pestaña **Servicios**, elija **Informes**.
    
2. Seleccione **Informes** y, a continuación, elija **Mostrar nombres de usuario, grupo y sitio ocultos en todos los informes**. Esta configuración se aplica tanto a los informes de uso de Centro de administración de Microsoft 365 como al Centro de administración de Teams.
  
3. Seleccione **Guardar cambios**.

> [!NOTE]
> Si habilita esta opción, se despersonalizará la información de usuario, grupo y nombre del sitio en el [informe de actividad de los usuarios de Teams](user-activity-report.md), el informe de [uso de dispositivos de Teams](device-usage-report.md) y el [informe de uso de Teams](teams-usage-report.md). A partir del 1 de septiembre de 2021, esta configuración está habilitada de forma predeterminada para todos los usuarios como parte de nuestro compromiso continuo de ayudar a proteger información importante y permitir que las empresas apoyen sus leyes de privacidad local. 
>
>Esta configuración también se aplica a los informes de uso de Microsoft 365 en Centro de administración de Microsoft 365, Microsoft Graph y Power BI.
