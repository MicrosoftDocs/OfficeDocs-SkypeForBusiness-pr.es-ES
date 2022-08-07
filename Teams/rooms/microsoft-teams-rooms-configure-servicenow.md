---
title: Configurar ServiceNow para Salas de Teams
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ronmart
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Más información sobre cómo configurar ServiceNow en el portal de Salas de Teams Premium
f1keywords: ''
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
ms.openlocfilehash: 920d31a350914115623a83f018815d8bebe94f6a
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272385"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Configurar ServiceNow para Salas de Teams

En este artículo se describen los requisitos previos y los pasos para configurar el entorno de ServiceNow en el portal de Salas de Teams Premium.

## <a name="watch-microsoft-teams-rooms--managed-services-service-now-integration"></a>Vea: Salas de Microsoft Teams: Integración de Servicios administrados ahora

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ZK4B]


### <a name="teams-rooms-prerequisites"></a>Salas de Teams requisitos previos

- Debe tener asignado un rol de administrador de servicios. Para obtener más información, vea [Control de acceso basado en roles con los servicios administrados de Salas de Microsoft Teams](microsoft-teams-rooms-premium-rbac.md).

### <a name="servicenow-prerequisites"></a>Requisitos previos de ServiceNow

- Un inicio de sesión de autorización básica O un inicio de sesión de [OAuth](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) . Para obtener más información, vea [Creación de credenciales](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) en ServiceNow.
- Una instancia de ServiceNow y su nombre de host de instancia y URI de API
- Un rol de incident_manager o superior
- Una versión de software de ServiceNow que admite table API

## <a name="configure-your-environment"></a>Configurar el entorno

La configuración del entorno es muy personalizable y dependerá de las necesidades de su organización. En los pasos siguientes se explica cómo copiar la configuración existente en ServiceNow al portal de Salas de Teams Premium.

1. Abra la instancia de ServiceNow que quiera copiar. Tendrás que hacer referencia a esto cuando completes el formulario de configuración en el portal de Salas de Teams Premium.
2. En una nueva pestaña del explorador, ve a la [Salas de Teams portal Premium](https://portal.rooms.microsoft.com/) y ve a **Configuración**. Después, seleccione **ServiceNow** en el menú de navegación izquierdo para abrir el formulario de configuración.
3. Seleccione un método de autenticación para iniciar sesión y escriba el host de instancia de ServiceNow y el URI de LA API.
4. Todos los elementos necesarios en la columna Campo de ServiceNow de la sección Asignación de campos deben rellenarse previamente. La tabla siguiente contiene cada campo de ServiceNow y su correspondiente campo de Salas de Microsoft Teams. Complete la acción para cada fila de la sección Asignación de campos. Para las definiciones de cada campo de ServiceNow, vea [Definiciones de campo de ServiceNow](#servicenow-field-definitions).

| Campo ServiceNow | campo Salas de Microsoft Teams | Acción |
| --- | --- | --- |
| short_description | Descripción del incidente | No es necesario realizar ninguna acción. El campo Salas de Teams se rellena automáticamente. |
| Descripción | Primer mensaje | No es necesario realizar ninguna acción. El campo Salas de Teams se rellena automáticamente. |
| assignment_group | Grupo de salas | Copie el valor de assignment_group en la instancia de ServiceNow y péguelo en el campo de valor ServiceNow del formulario de configuración. Si tiene más de una assignment_group, seleccione **Agregar grupo de salones** por cada valor personalizado adicional. |
| Severidad | Anillos | La gravedad es un valor personalizado en ServiceNow. Es el cuarto elemento de la segunda columna de su instancia de ServiceNow. Copie el valor y péguelo en el campo de valor ServiceNow del formulario de configuración. Si tiene más de un valor de gravedad, seleccione **Agregar anillo** para cada valor personalizado adicional. |
| Comentarios (opcional) | Valor personalizado* | Para agregar un campo de comentarios al formulario de configuración, seleccione **Agregar** en la parte superior de la sección de asignación de campos. Copie el valor del comentario en su instancia de ServiceNow y péguelo en el campo ServiceNow del formulario de configuración. Asígnele un campo sala de Microsoft Teams en el menú desplegable y copie y pegue el valor de ServiceNow. |
| estado (resuelto) | Valor personalizado* | Copie el estado de resolución de la instancia de ServiceNow y péguelo en el campo de valor ServiceNow del formulario de configuración. |
| close_code | Valor personalizado* | En la pestaña **Información de resolución** de la instancia de ServiceNow, copie el código de cierre y péguelo en el campo de valor ServiceNow en el formulario de configuración. |

*Seleccionar valores personalizados en el menú desplegable

>[!NOTE]
>Si no puede encontrar los valores personalizados, póngase en contacto con el administrador de ServiceNow.

Para agregar otros campos obligatorios a la sección Resolver incidencia, seleccione **Agregar**.

## <a name="test-and-enable"></a>Probar y habilitar

Después de completar el formulario de configuración, seleccione **Probar** en la parte inferior de la página. Es necesario realizar pruebas para enviar la configuración.

Una vez que la prueba se supere correctamente, selecciona **Enviar** para guardar los cambios. Cuando esté listo para habilitar ServiceNow para su organización, cambie el botón de alternancia **¿Desea habilitar ServiceNow?** a **Activado**.

## <a name="servicenow-field-definitions"></a>Definiciones de campo de ServiceNow

- **short_description**: El campo de descripción breve de ServiceNow es un valor alfanumérico breve de 160 caracteres que proporciona un resumen del incidente. La descripción breve equivale a la descripción del incidente en el portal de Salas de Teams Premium.

- **descripción**: El campo de descripción de ServiceNow es el primer valor del historial de conversaciones de un incidente de ServiceNow. Descripción equivale al primer mensaje del portal de Salas de Teams Premium.

- **assignment_group**: El campo de grupo de asignaciones de ServiceNow se usa para organizar incidentes. Los grupos de asignaciones son equivalentes a los grupos de salas en el portal de Salas de Teams Premium. De forma predeterminada, hay un grupo de salas y se pueden agregar más. Usted decide cuántos grupos hay y cómo agrupar sus incidentes. Por ejemplo, puede optar por organizar los incidentes por ubicación.

- **gravedad**: el campo de gravedad de ServiceNow se usa para organizar los incidentes por prioridad. Los valores que designan prioridad se pueden personalizar. La gravedad es equivalente al campo Anillo del portal de Salas de Teams Premium. Para personalizar los anillos en el portal de Salas de Teams Premium, vaya a **Novedades** en el menú de navegación izquierdo. A continuación, vaya a la pestaña **Anillos** y seleccione **Agregar anillo**.

- comentarios: Comentarios es un campo opcional de ServiceNow que se usa para incluir campos **obligatorios personalizados** de la instancia de ServiceNow en la configuración del portal de Salas de Teams Premium. El equivalente de los comentarios es un valor personalizado en el portal de Salas de Teams Premium.

- **estado (resuelto)**: el campo estado (resuelto) de ServiceNow se usa para designar cómo se resolvió un incidente y se requiere para cerrar un incidente. El valor de estado (resuelto) se puede personalizar. El equivalente del estado (resuelto) es un valor personalizado en el portal de Salas de Teams Premium.

- **close_code**: debe asignarse un código de cierre a un incidente una vez que se haya resuelto por completo. Este valor se puede personalizar en ServiceNow. El equivalente de cerrar código es un valor personalizado en el portal de Salas de Teams Premium.
