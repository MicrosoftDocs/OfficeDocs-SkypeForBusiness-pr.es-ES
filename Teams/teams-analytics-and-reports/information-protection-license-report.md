---
title: informe de licencia de Microsoft Teams de protección de la información
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de licencia de Teams Information Protection en el Centro de administración de Microsoft Teams para ver cómo las aplicaciones de su organización usan las API de suscripción de eventos de notificación de cambio.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fade7b4d5d89061cdc1dd5eb231a80d5ee9e8938
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681541"
---
# <a name="microsoft-teams-information-protection-license-report"></a>informe de licencia de Microsoft Teams de protección de la información


Teams informe de licencias de protección de la información proporciona información sobre el uso de la API de [las API de Microsoft Graph que tienen requisitos de licencia y pago](/graph/teams-licenses). Este informe resalta todas las aplicaciones que usan estas API en [model=A](/graph/teams-licenses#modela-requirements). No muestra el uso cuando las API se usan en [model=B](/graph/teams-licenses#modelb-requirements) o [en el modo de evaluación](/graph/teams-licenses#evaluation-mode-default-requirements). 


## <a name="view-the-information-protection-license-report"></a>Ver el informe de licencia de protección de la información

Debe ser administrador de servicio de Teams para poder realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams](../using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **Análisis & informes** > **de uso**. En la pestaña **Ver informes**, en **Informe**, seleccione **Information Protection Licencia**.
2. En **Intervalo de fechas**, seleccione un intervalo.
3. En **Aplicaciones**, selecciona una aplicación y, a continuación, selecciona **Ejecutar informe**.

    ![Captura de pantalla de la lista desplegable de Teams informe de licencias de protección de información en el centro de administración de Teams con globos.](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Captura de pantalla de la lista desplegable de Teams informe de licencias de protección de información en el centro de administración de Teams con globos.")

4. Para cada categoría, se pueden ver las métricas de los usuarios con licencia, los usuarios sin licencia, la capacidad de semillas y la capacidad utilizada. 

    ![Captura de pantalla del gráfico de resumen de Teams informe de licencias de protección de la información en el centro de administración de Teams de notificaciones de cambios con llamadas.](../media/teams-info-protection-license-report-chart-with-callouts.png "Captura de pantalla del gráfico de resumen de Teams informe de licencias de protección de la información en el centro de administración de Teams de notificaciones de cambios con llamadas.")

5. Los datos se pueden exportar haciendo clic en el botón Exportar. Los datos de la tabla se pueden cambiar haciendo clic en las pestañas de Teams cambiar la API de notificación, Teams API de revisión, Teams exportar API (chat) y Teams exportar API (equipos). 

    ![Captura de pantalla de las diferentes pestañas de Teams informe de licencias de protección de la información en el centro de administración de Teams de pestañas con llamadas.](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "Captura de pantalla de las diferentes pestañas de Teams informe de licencias de protección de la información en el centro de administración de Teams de pestañas con llamadas.")

    ![Captura de pantalla de la pestaña de notificación de cambios de Teams informe de licencia de protección de la información en el centro de administración de Teams con globos.](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Captura de pantalla de la pestaña de notificación de cambios de Teams informe de licencia de protección de la información en el centro de administración de Teams con globos.")


## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe de licencia de protección de la información puede visualizarse para ver las tendencias de los últimos tres meses. |
|**2**   |El nombre de la aplicación mostrará una lista de todas las aplicaciones que han usado [Microsoft Graph API que tiene requisitos de licencia y pago](/graph/teams-licenses) durante el período de tiempo seleccionado.|
|**3**   |Número de usuarios que tienen [licencias válidas](/graph/teams-licenses#required-licenses-for-modela).  |
|**4**   |Número de usuarios que no tienen una [licencia](/graph/teams-licenses#required-licenses-for-modela) válida.  |
|**5**   |Volumen total de llamadas API permitidas a una aplicación, más allá de lo cual se cobrará una tarifa de consumo por llamada API a la aplicación. |
|**6**   |Volumen total de llamadas API que usa la aplicación para el intervalo de fechas especificado. |
|**7**   |Exporte el informe a un archivo CSV para analizarlo sin conexión. Seleccione **Exportar a Excel** y, después, la pestaña **Descargas**. Seleccione **Descargar** para descargar el informe cuando esté listo. Esta exportación exportará solo la pestaña seleccionada actualmente.|
|**8**   |Seleccione una etiqueta específica para mostrarla u ocultarla en un gráfico. |
|**9**   |Cada pestaña muestra el uso de un conjunto determinado de API, es decir, [notificaciones de cambios](/graph/api/resources/webhooks), [API de exportación](/microsoftteams/export-teams-content) y API de mensajes de [actualización](/graph/api/message-update). Selecciona una pestaña para ver los detalles de uso de esa API. |
|**10**   |**Cambiar el uso de la API de notificación**<li>**Nombre para mostrar** : nombre para mostrar del usuario en el que se activó una notificación de cambio.</li><li>**Licencia requerida** : si el usuario determinado tiene la licencia necesaria para enviar correctamente una notificación de cambio a la aplicación.</li><li>**Recuento de intentos** : número total de notificaciones de cambio que se activaron debido a este usuario.</li><li>**Notificación de cambio enviada** : número total de notificaciones de cambio que se han enviado a la aplicación. Esto será menor que el total de notificaciones de cambio desencadenadas si el usuario no tiene una licencia válida.</li>|
|**11**|**API de revisión**<li>**Nombre para mostrar** : nombre para mostrar del usuario donde se realizó un intento de actualización del mensaje.</li> <li>**Licencia requerida** : si el usuario determinado tiene la licencia necesaria para que el mensaje se actualice correctamente.</li><li>**Recuento de intentos** : total de intentos de actualización de mensajes.</li><li>**Mensaje con revisiones** : total de mensajes que se han actualizado correctamente.</li>|
|**12**|**Uso de la API de exportación de chat**<li>**Nombre para mostrar** : nombre para mostrar del usuario donde se realizó un intento de exportar el mensaje de chat del usuario.</li><li>**Licencia requerida** : si el usuario determinado tiene la licencia necesaria para que el mensaje se exporte correctamente.</li><li>**Recuento de intentos** : total de intentos de exportar mensajes de chat.</li><li>**Mensaje exportado** : total de intentos en los que el mensaje de chat se exportó correctamente.</li> |
|**13**|**Uso de la API de exportación de equipo**<li>**Nombre para mostrar** : nombre para mostrar del equipo donde se realizó un intento de exportación del mensaje de ese equipo.</li><li>**Recuento de intentos** : total de intentos de exportar mensajes del equipo.</li><li>**Mensaje exportado** : total de intentos en los que el mensaje del equipo se exportó correctamente.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>Establecer que los datos específicos del usuario sean anónimos

Para que los datos del informe de actividad de usuario Teams sean anónimos, debe ser administrador global. Esto ocultará la información identificable, como el nombre para mostrar, el correo electrónico y el id. de Azure AD, en los informes y sus exportaciones.

1. En la Centro de administración de Microsoft 365, vaya a **Configuración** \> **Configuración De** organización y, en la pestaña **Servicios**, elija **Informes**.
    
2. Seleccione **Informes** y, después, elija **Mostrar identificadores anónimos**. Esta configuración se aplica tanto a los informes de uso de la Centro de administración de Microsoft 365 como al centro de administración de Teams.
  
3. Seleccione **Guardar cambios**.