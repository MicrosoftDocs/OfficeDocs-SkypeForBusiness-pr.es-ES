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
description: En este artículo, aprenderá acerca de los Teams que están disponibles en el centro Microsoft Teams administración.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6d195c90dc7e959146546dde1a75fedf0764c24a
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478350"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Análisis e informes de Microsoft Teams

Una nueva experiencia de análisis e informes para Microsoft Teams está disponible en el centro Microsoft Teams administración. Puede ejecutar diferentes informes para obtener información sobre cómo los usuarios de su organización usan Teams. Por ejemplo, puede ver cuántos usuarios se comunican a través de mensajes de canal y chat y los tipos de dispositivos que usan para conectarse a Teams. Su organización puede usar la información de los informes para comprender mejor los patrones de uso, ayudar a tomar decisiones empresariales e informar a los esfuerzos de aprendizaje y comunicación.

## <a name="how-to-access-the-reports"></a>Cómo obtener acceso a los informes

Para obtener acceso a los informes, debe ser administrador global en Microsoft 365 o Office 365, Teams de servicio o Skype Empresarial administrador. Para obtener más información sobre Teams de administrador y a qué informes puede acceder cada rol de administrador, vea Usar Teams de administrador para [administrar](../using-admin-roles.md)Teams .

Vaya al centro Microsoft Teams de administración, en el panel de navegación izquierdo, seleccione **Análisis & informes** y, a continuación, en Informe, elija el informe que desea ejecutar. 

> [!NOTE]
> Los informes del centro Microsoft Teams administración son independientes de los informes de actividades de Teams que forman parte de los informes de Microsoft 365 en el centro de administración Microsoft 365 administración. Para obtener más información sobre los informes de actividades en el centro Microsoft 365 administración, vea Teams de actividades en el [centro Microsoft 365 administración](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams referencia de informes

Esta es una lista de los Teams disponibles en el Centro de administración de Microsoft Teams y una descripción general de parte de la información disponible en cada informe.

Estamos mejorando continuamente la experiencia Teams informes y agregando características y funcionalidades. Con el tiempo, crearemos capacidades adicionales en los informes y agregaremos nuevos informes en el centro Microsoft Teams administración.

|Informe  |¿Qué se mide? |
|---------|---------|
|[Informes de uso de Teams](teams-usage-report.md)  |  Usuarios activos<br/>Usuarios activos en equipos y canales<br/>Canales activos<br/>Mensajes<br/>Configuración de privacidad de los equipos<br/>Invitados de un equipo   |
|[Informe de actividad de usuario de Teams](user-activity-report.md)  | Mensajes que un usuario publicó en un chat de grupo<br/>Mensajes que un usuario publicó en un chat privado<br/>  1:1 llamadas en las que ha participado un usuario<br/> Número de usuarios de la reunión organizados <br/>número de usuarios de la reunión que la han participado<br/>Tiempo de uso compartido de pantalla, vídeo y audio de reuniones<br/>   Última fecha de actividad de un usuario     |
|[Informe de uso de dispositivos de Teams](device-usage-report.md)   |  Usuarios de Windows<br/>Usuarios de Mac<br/>Usuarios de iOS<br/>Usuarios de teléfonos Android     |
|[Informe de uso de eventos en directo de Teams](teams-live-event-usage-report.md)   |  Vistas totales<br>Hora de inicio<br>Estado del evento<br>Organizador<br>Moderador<br>Productor<br>Configuración de la grabación<br>Tipo de producción    |
|[Teams Informe de usuarios bloqueados rtc](pstn-blocked-users-report.md)   |  Nombre para mostrar<br>Teléfono número<br>Motivo<br>Tipo de acción<br>Fecha y hora de la acción   |
|[Teams Informe de grupos de minutos RTC](pstn-minute-pools-report.md) |  País o región<br>Funcionalidad (licencia) <br>Minutos totales<br>Minutos usados<br>Minutos disponibles|
|[Teams Informe de uso de RTC: planes de llamadas](pstn-usage-report.md#calling-plans)|  Marca de tiempo<br>Nombre de usuario<br>Teléfono número<br>Tipo de llamada <br>Llamado a<br>Para país o región <br>Llamado desde <br>De país o región<br>Cargo<br>Moneda<br>Duración<br>Nacional/Internacional<br>Id. de llamada<br>Tipo de número<br>País o región<br>Id. de conferencia<br>Funcionalidad (licencia)|
|[Teams Informe de uso de RTC: enrutamiento directo](pstn-usage-report.md#direct-routing)  |  Marca de tiempo<br>Nombre para mostrar<br>Dirección SIP<br>Teléfono número <br>Tipo de llamada<br>Llamado a<br>Hora de inicio<br>Hora de invitación<br>Tiempo de error<br>Hora de finalización<br>Duración<br>Tipo de número<br>Omisión de medios<br>SBC FQDN<br>Región de Azure<br>Tipo de evento<br>Código SIP final<br>Subcódigo final de Microsoft<br>Frase sip final<br>Id. de correlación  |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Convertir en anónimos los datos específicos del usuario

Para que los datos de Teams de usuario y Teams informe de uso de dispositivos sean anónimos, debe ser administrador global. Esto ocultará información identificable, como el nombre para mostrar, el correo electrónico y el id. de AAD en los informes y sus exportaciones.

1. En Microsoft 365 centro de administración,  vaya a la Configuración organización Configuración y, en la pestaña \> Servicios, elija **Informes.** 
    
2. Seleccione **Informes** y, a continuación, **elija Mostrar identificadores anónimos.** Esta configuración se aplica tanto a los informes de uso de Microsoft 365 centro de administración como Teams centro de administración.
  
3. Seleccione **Guardar cambios**.

> [!NOTE]
> Al habilitar esta configuración, se desa [identificará](user-activity-report.md) la información Teams informe de actividad del usuario y Teams [informes de uso de dispositivos.](device-usage-report.md) No afectará a otros informes de uso disponibles en Teams de administración.
