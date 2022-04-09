---
title: Supervisión y alertas de dispositivos Microsoft Teams
author: cazawideh
ms.author: czawideh
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar las capacidades de supervisión y alertas de Teams en el centro de administración de Microsoft Teams para supervisar de forma proactiva el estado de los dispositivos Teams
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 22b67a0c046c3abb0643503948d67b77abb0e690
ms.sourcegitcommit: f3c380f745af4c3aaa2720234860b45696a0c333
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2022
ms.locfileid: "64737607"
---
# <a name="microsoft-teams-device-health-monitoring"></a>supervisión del estado del dispositivo Microsoft Teams

La supervisión del estado del dispositivo en el centro de administración de Microsoft Teams le ofrece la posibilidad de supervisar de forma proactiva el estado de varios dispositivos Teams. Supervise el estado sin conexión de un dispositivo y reciba alertas en tiempo real si el dispositivo supervisado de su organización se desconecta.  

Antes de empezar, necesitará los permisos de creación de canales o equipos en su inquilino. [Más información](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).

## <a name="configure-device-state-rule"></a>Configurar la regla de estado del dispositivo

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **Notificaciones &** **alertasRules** > .

   ![Sección Reglas del Centro de administración.](../media/select-rules.png)

2. En la página **Reglas** , selecciona **Regla de estado de dispositivo**.

3. Seleccione el dispositivo para configurar la regla de estado para habilitar las alertas.

    ![página Teams regla de estado de dispositivos.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpretar la configuración de la regla


|Campo |Descripción  |
|--------|-------------|
|**Tipo de regla**   |La regla de estado del dispositivo te ayuda a administrar de forma eficaz. Teams dispositivos y se clasifica como un tipo de administración de dispositivos. En el futuro, habrá disponibles más reglas de tipo de administración de dispositivos para supervisar otras funcionalidades relacionadas (algunos ejemplos pueden ser: dispositivo en mal estado y estado de inicio de sesión del dispositivo).|
|**Condición**   |Puedes supervisar el estado de los dispositivos si se desconectan. [Obtenga más información](../devices/device-management.md) sobre la administración de dispositivos en Teams centro de administración. |
|**Ámbito**   |Puede especificar la frecuencia con la que desea supervisar el estado del dispositivo mencionando la frecuencia de evaluación de reglas. De forma predeterminada, los dispositivos de los equipos se supervisarán en casi tiempo real si se desconectan. |
|**Usuarios de dispositivos**   |Puedes especificar qué dispositivos necesitan supervisión proactiva de estatuas sin conexión seleccionándolas en función de los usuarios con sesión iniciada. Consulte [Seleccionar dispositivos para la configuración](#select-devices-for-configuration) para obtener más detalles. |
|**Acciones** >  **Alerta de canal**   |En la sección Acciones, puede especificar los canales de los equipos para los que desea recibir alertas. Actualmente, se creará un equipo predeterminado denominado **Alertas y notificaciones de administrador** y un canal denominado **MonitoringAlerts** donde se entregarán las notificaciones. <BR/> <BR/> Los administradores globales y los administradores de Teams de su inquilino se agregarán automáticamente a este equipo predeterminado.|
|**Acciones** >  **Webhook**   |También puede recibir notificaciones con un webhook externo (opcional). Especifique una dirección URL de webhook público externo en la sección webhook donde se enviará una carga de notificación JSON. <BR/> <BR/>  La carga de notificaciones, a través de webhooks, se puede integrar con otros sistemas de su organización para crear flujos de trabajo personalizados.<br/><br/> 

**Esquema de carga json para webhook:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **Carga de JSON de ejemplo**:<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         "DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": "Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Seleccionar dispositivos para la configuración

1. Puedes seleccionar Teams dispositivos que quieras supervisar seleccionando usuarios que hayan iniciado sesión en esos dispositivos. Selecciona **Agregar** en la sección **Usuarios de dispositivos** .

2. Seleccione uno o más usuarios para los que desea supervisar el estado del dispositivo

   ![agregar usuario en la regla de estado de estado del dispositivo.](../media/select-device-users.png )

   La lista seleccionada de usuarios se muestra en la sección **Usuarios de dispositivos** . Puede modificar esta lista agregando o quitando usuarios.

Se supervisará el estado sin conexión de todos los dispositivos de inicio de sesión usados por la lista de usuarios seleccionada.

## <a name="notifications-in-teams-client"></a>Notificaciones en Teams cliente

Las notificaciones se entregan en el canal **MonitoringAlerts** creado automáticamente del equipo **de alertas y notificaciones del administrador** . Recibirás una alerta en un plazo de 15 minutos desde que el dispositivo se esté desconectando. 

Una notificación sin conexión del dispositivo puede incluir la siguiente información:

- El nombre del dispositivo sin conexión.
- El usuario del dispositivo sin conexión.
- ¿A qué hora se quedó sin conexión el dispositivo? (Actualmente, la hora se presenta en UTC).
- El tipo de regla que ha elevado la alerta.
- Por qué se eleva una alerta.
