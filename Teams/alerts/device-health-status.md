---
title: Microsoft Teams Supervisión y alertas de dispositivos
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre cómo usar Teams de supervisión y alertas en el centro de administración de Microsoft Teams para supervisar de forma proactiva el estado de salud de Teams dispositivos
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b44b564da4e772fb3e385b03d61be6874baf11c5
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58735357"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams de estado del dispositivo

La supervisión del estado de los dispositivos Microsoft Teams centro de administración le ofrece la capacidad de supervisar proactivamente el estado de varios Teams dispositivos. Supervise el estado sin conexión de un dispositivo y reciba alertas en tiempo real si el dispositivo supervisado de su organización se desconecta.  

Antes de empezar, necesitará los permisos de creación de equipos o canales en el espacio empresarial. [Más información.](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)

## <a name="configure-device-state-rule"></a>Configurar la regla de estado del dispositivo

1. En el panel de navegación izquierdo del Microsoft Teams de administración, seleccione **Notificaciones & reglas de**  >  **alertas.**

   ![Sección Reglas del Centro de administración.](../media/select-rules.png)

2. En la **página** Reglas, seleccione **Regla de estado del dispositivo**.

3. Seleccione el dispositivo para configurar la regla de estado para habilitar alertas.

    ![Teams de estado de dispositivos.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpretar la configuración de la regla


|Campo |Descripción  |
|--------|-------------|
|**Tipo de regla**   |La regla de estado del dispositivo le ayuda a administrar de forma eficaz. Teams dispositivos y se clasifica como un tipo de administración de dispositivos. En el futuro, habrá más reglas de tipo de administración de dispositivos disponibles para supervisar otras capacidades relacionadas (algunos ejemplos pueden incluir: dispositivo en mal estado y el estado de inicio de sesión del dispositivo).|
|**Condición**   |Puede supervisar el estado de los dispositivos si se desconectan. [Obtenga más información](../devices/device-management.md) sobre la administración de dispositivos Teams centro de administración. |
|**Ámbito**   |Puede especificar la frecuencia con la que desea supervisar el estado del dispositivo mencionando la frecuencia de evaluación de la regla. De forma predeterminada, los dispositivos de equipos se supervisarán casi en tiempo real si se desconectan. |
|**Usuarios de dispositivos**   |Puede especificar qué dispositivos necesitan una supervisión proactiva de las imágenes sin conexión seleccionándolos en función de los usuarios que han iniciado sesión. Para obtener [más información, consulte Seleccionar dispositivos](#select-devices-for-configuration) para la configuración. |
|**Acciones**  >  **Alerta de canal**   |En la sección Acciones, puede especificar los canales de equipos para los que desea recibir alertas. Actualmente, se creará un equipo predeterminado denominado **Alertas** y notificaciones de administrador y un canal denominado **MonitoringAlerts** donde se entregarán las notificaciones. <BR/> <BR/> Los administradores globales y Teams de su inquilino se agregarán automáticamente a este equipo predeterminado.|
|**Acciones**  >  **Webhook**   |También puede recibir notificaciones con un webhook externo (opcional). Especifique una dirección URL de webhook pública externa en la sección webhook donde se enviará una carga de notificación JSON. <BR/> <BR/>  La carga de notificación, a través de webhooks, se puede integrar con otros sistemas de su organización para crear flujos de trabajo personalizados.<br/><br/> 

**Esquema de carga JSON para webhook:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **Carga JSON de ejemplo:**<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Seleccionar dispositivos para la configuración

1. Puede seleccionar Teams dispositivos que desea supervisar seleccionando usuarios que han iniciado sesión en esos dispositivos. Seleccione **Agregar en** la sección Usuarios de **dispositivos.**

2. Seleccione uno o varios usuarios para los que desea supervisar el estado del dispositivo

   ![agregar usuario en la regla de estado del dispositivo.](../media/select-device-users.png )

   La lista seleccionada de usuarios se muestra en **la sección Usuarios de dispositivos.** Puede modificar esta lista agregando o quitando usuarios.

Todos los dispositivos de inicio de sesión usados por la lista seleccionada de usuarios se supervisarán para el estado de mantenimiento sin conexión.

## <a name="notifications-in-teams-client"></a>Notificaciones en Teams cliente

Las notificaciones se entregan en el canal **MonitoringAlerts** creado automáticamente del equipo de notificaciones y **alertas de** administrador.

Una notificación de dispositivo sin conexión puede incluir la siguiente información:

- El nombre del dispositivo sin conexión.
- El usuario del dispositivo sin conexión.
- ¿A qué hora se ha desconectado el dispositivo? (Actualmente, la hora se presenta en UTC).
- El tipo de regla que ha elevado la alerta.
- Por qué se eleva una alerta.