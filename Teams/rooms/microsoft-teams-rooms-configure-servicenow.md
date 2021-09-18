---
title: Configurar ServiceNow para Salas de Teams
author: cazawideh
ms.author: czawideh
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Obtenga información sobre cómo configurar ServiceNow en el Salas de Teams Premium web
f1keywords: ''
ms.openlocfilehash: a8f1e43ca52ee9fa155115fb911f88221cb6fdd0
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432712"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Configurar ServiceNow para Salas de Teams

En este artículo se describen los requisitos previos y los pasos para configurar el entorno de ServiceNow en Salas de Teams Premium portal.

## <a name="before-you-begin"></a>Antes de empezar

### <a name="teams-rooms-prerequisites"></a>Salas de Teams requisitos previos

- Debe tener un rol de administrador de servicio asignado. Para obtener más información, vea Control de acceso basado en roles [con Salas de Microsoft Teams Servicios administrados.](microsoft-teams-rooms-premium-rbac.md)

### <a name="servicenow-prerequisites"></a>Requisitos previos de ServiceNow

- Un inicio de sesión de autorización básica o un inicio de sesión de OAuth. Para obtener más información, vea [Crear credenciales en](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) ServiceNow.
- Una instancia de ServiceNow y el nombre de host de la instancia y el URI de la API
- Un rol de incident_manager o superior
- Una versión de software de ServiceNow compatible con Table API

## <a name="configure-your-environment"></a>Configurar el entorno

La configuración de su entorno es altamente personalizable y dependerá de las necesidades de su organización. A continuación se explica cómo copiar la configuración existente en ServiceNow en el portal Salas de Teams Premium usuario.

1. Abra la instancia de ServiceNow que desea copiar. Tendrá que hacer referencia a esto a medida que complete el formulario de configuración en el Salas de Teams Premium web.
2. En una nueva pestaña del explorador, vaya al [portal Salas de Teams Premium y](https://portal.rooms.microsoft.com/) vaya a **Configuración**. Después, seleccione **ServiceNow en** el menú de navegación izquierdo para abrir el formulario de configuración.
3. Seleccione un método de autenticación para iniciar sesión y escribir el Host de instancia de ServiceNow y el URI de la API.
4. Todos los elementos necesarios en la columna Campo de ServiceNow de la sección Asignación de campos deben rellenarse previamente. La tabla siguiente contiene cada campo ServiceNow y sus correspondientes Salas de Microsoft Teams campo. Complete la acción de cada fila de la sección Asignación de campos. Para obtener definiciones de cada campo de ServiceNow, vea [Definiciones de campo de ServiceNow](#servicenow-field-definitions).

| Campo ServiceNow | Salas de Microsoft Teams campo | Action |
| --- | --- | --- |
| short_description | Descripción del incidente | No se necesita ninguna acción. El Salas de Teams se rellena automáticamente. |
| descripción | Primer mensaje | No se necesita ninguna acción. El Salas de Teams se rellena automáticamente. |
| assignment_group | Grupo sala | Copie el assignment_group en la instancia de ServiceNow y péguelo en el campo de valor ServiceNow del formulario de configuración. Si tiene más de una assignment_group, seleccione Agregar grupo **de sala** para cada valor personalizado adicional. |
| gravedad | Anillos | Gravedad es un valor personalizado en ServiceNow. Es el cuarto elemento de la segunda columna de la instancia de ServiceNow. Copie el valor y péguelo en el campo de valor ServiceNow del formulario de configuración. Si tiene más de un valor de gravedad, seleccione **Agregar anillo** para cada valor personalizado adicional. |
| Comentarios (opcional) | Valor personalizado* | Para agregar un campo de comentarios al formulario de configuración, seleccione **Agregar** en la parte superior de la sección de asignación de campos. Copie el valor del comentario en la instancia de ServiceNow y péguelo en el campo ServiceNow del formulario de configuración. Asígnele un Microsoft Teams de sala desde el menú desplegable y copie y pegue el valor ServiceNow. |
| estado (resuelto) | Valor personalizado* | Copie el estado de resolución de su instancia de ServiceNow y péguelo en el campo de valor ServiceNow del formulario de configuración. |
| close_code | Valor personalizado* | En la **pestaña Información de** resolución de la instancia de ServiceNow, copie el código de cierre y péguelo en el campo de valor ServiceNow en el formulario de configuración. |

*Seleccionar valores personalizados en el menú desplegable

>[!NOTE]
>Si no puede localizar los valores personalizados, póngase en contacto con el administrador de ServiceNow.

Para agregar campos necesarios adicionales a la sección Resolver incidente, seleccione **Agregar**.

## <a name="test-and-enable"></a>Probar y habilitar

Después de completar el formulario de configuración, seleccione **Probar** en la parte inferior de la página. Las pruebas son necesarias para enviar la configuración.

Una vez que la prueba se haya realizado correctamente, seleccione **Enviar** para guardar los cambios. Una vez que esté listo para habilitar ServiceNow para su organización, cambie el botón de alternancia ¿Desea habilitar **ServiceNow?** a **Activar**.

## <a name="servicenow-field-definitions"></a>Definiciones de campo de ServiceNow

- **short_description:** el campo de descripción breve de ServiceNow es un breve valor alfanumérico de 160 caracteres que proporciona un resumen del incidente. La descripción breve equivale a la descripción del incidente en Salas de Teams Premium portal.

- **descripción:** el campo de descripción de ServiceNow es el primer valor en el historial de conversaciones de un incidente de ServiceNow. La descripción equivale a Primer mensaje en el portal Salas de Teams Premium usuario.

- **assignment_group:** el campo de grupo de tareas de ServiceNow se usa para organizar incidentes. El grupo de asignaciones es equivalente a los grupos de salón en el Salas de Teams Premium de tareas. De forma predeterminada, hay un grupo de salón y se pueden agregar más. Puede decidir cuántos grupos hay y cómo agrupar los incidentes. Por ejemplo, es posible que elija organizar los incidentes por ubicación.

- **gravedad:** el campo de gravedad de ServiceNow se usa para organizar incidentes por prioridad. Los valores que designan prioridad se pueden personalizar. La gravedad es equivalente al campo Anillo del Salas de Teams Premium portal. Para personalizar los anillos en el Salas de Teams Premium, vaya a **Actualizaciones** en el menú de navegación izquierdo. A continuación, vaya a la **pestaña Anillos** y seleccione **Agregar anillo.**

- **comentarios:** Comentarios es un campo opcional en ServiceNow que se usa para incluir campos obligatorios personalizados de la instancia de ServiceNow en la configuración del portal Salas de Teams Premium usuario. El equivalente de los comentarios es un valor personalizado en el portal Salas de Teams Premium usuario.

- **estado (resuelto):** el campo estado (resuelto) de ServiceNow se usa para designar cómo se resolvió un incidente y se requiere para cerrar un incidente. El valor de estado (resuelto) se puede personalizar. El equivalente de estado (resuelto) es un valor personalizado en Salas de Teams Premium portal.

- **close_code:** se debe asignar un código de cierre a un incidente una vez que se haya resuelto por completo. Este valor se puede personalizar en ServiceNow. El equivalente a código de cierre es un valor personalizado en el portal Salas de Teams Premium datos.
