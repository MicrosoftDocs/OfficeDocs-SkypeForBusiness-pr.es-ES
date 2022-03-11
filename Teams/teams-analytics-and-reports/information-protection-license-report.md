---
title: Microsoft Teams de licencia de protección de información
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
description: Obtenga información sobre cómo usar el informe Teams licencia de protección de la información en el Centro de administración de Microsoft Teams para ver cómo las aplicaciones de su organización usan las API de suscripción de eventos de notificación de cambio.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73ce4b5720c42cdb4e468182d6290912baf95d7e
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435864"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams de licencia de protección de información


Teams de licencia de protección de la información proporciona información sobre el uso de la API de [Microsoft Graph API que tienen requisitos de licencia y pago](/graph/teams-licenses). Este informe resalta todas las aplicaciones que usan estas API en [model=A](/graph/teams-licenses#modela-requirements). No muestra el uso cuando las API se usan en [model=B o](/graph/teams-licenses#modelb-requirements) [en modo de evaluación](/graph/teams-licenses#evaluation-mode-default-requirements). 


## <a name="view-the-information-protection-license-report"></a>Ver el informe de licencia de protección de información

Debe ser administrador de servicio de Teams para poder realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams](../using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. En el panel de navegación izquierdo del centro Microsoft Teams administración, seleccione **Análisis &** **informesUsar** >  informes. En la pestaña **Ver informes** , en **Informe**, seleccione **Licencia de protección de información**.
2. En **Intervalo de fechas**, seleccione un rango.
3. En **Aplicaciones**, seleccione una aplicación y, a continuación, **seleccione Ejecutar informe**.

    ![Captura de pantalla de la lista desplegable Teams informe de licencia de protección de la información en el Teams de administración con llamadas.](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Captura de pantalla de la lista desplegable Teams informe de licencia de protección de la información en el Teams de administración con llamadas.")

4. Para cada categoría, se pueden ver las métricas de usuarios con licencia, usuarios sin licencia, capacidad de semilla y capacidad utilizada. 

    ![Captura de pantalla del gráfico de resumen de Teams de licencia de protección de información en el centro Teams de notificaciones de cambio con llamadas.](../media/teams-info-protection-license-report-chart-with-callouts.png "Captura de pantalla del gráfico de resumen de Teams de licencia de protección de información en el centro Teams de notificaciones de cambio con llamadas.")

5. Los datos se pueden exportar haciendo clic en el botón Exportar. Los datos de la tabla se pueden cambiar haciendo clic en las pestañas de la API de notificación de cambio Teams, la API de revisión Teams, Teams exportar API (chat) y Teams exportar API (equipos). 

    ![Captura de pantalla de las diferentes pestañas de Teams de licencia de protección de información en el centro de administración de Teams de pestañas con llamadas.](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "Captura de pantalla de las diferentes pestañas de Teams de licencia de protección de información en el centro de administración de Teams de pestañas con llamadas.")

    ![Captura de pantalla de la pestaña de notificación de Teams informe de licencia de protección de la información en el centro Teams de administración con llamadas.](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Captura de pantalla de la pestaña de notificación de Teams informe de licencia de protección de la información en el centro Teams de administración con llamadas.")


## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe de licencia de protección de información se puede ver para ver las tendencias de los últimos tres meses. |
|**2**   |El nombre de la aplicación mostrará una lista de todas las aplicaciones que han usado [la API de Microsoft Graph](/graph/teams-licenses) que tiene requisitos de licencia y pago durante el período de tiempo seleccionado.|
|**3**   |Número de usuarios que tienen [licencias válidas](/graph/teams-licenses#required-licenses-for-modela).  |
|**4**   |Número de usuarios que no tienen una licencia [válida](/graph/teams-licenses#required-licenses-for-modela).  |
|**5**   |Volumen total de llamadas de la API permitido a una aplicación más allá de la cual se cobrará una cuota de consumo por llamada de API a la aplicación. |
|**6**   |Volumen total de llamadas api usadas por la aplicación para el intervalo de fechas determinado. |
|**7**   |Exporte el informe a un archivo CSV para analizarlo sin conexión. Seleccione **Exportar a Excel** y, a continuación, la pestaña **Descargas****. Seleccione Descargar** para descargar el informe cuando esté listo. Esta exportación solo exportará la pestaña seleccionada actualmente.|
|**8**   |Seleccione cualquier etiqueta específica para mostrarla u ocultarla en un gráfico. |
|**9**   |Cada pestaña muestra el uso de un conjunto determinado de API, es decir, cambiar la [notificación, exportar](/graph/api/resources/webhooks) [API](/microsoftteams/export-teams-content) y [actualizar la API de mensajes](/graph/api/message-update). Seleccione una pestaña para ver los detalles de uso de esa API. |
|**10**   |**Cambiar el uso de la API de notificación**<li>**Nombre para mostrar** : nombre para mostrar del usuario contra el que se desencadenó una notificación de cambio.</li><li>**Licencia requerida** : si el usuario determinado tiene la licencia necesaria para enviar correctamente una notificación de cambio a la aplicación.</li><li>**Recuento intentado** : número total de notificaciones de cambio que se desencadenaron a causa de este usuario.</li><li>**Cambiar notificación enviada** : número total de notificaciones de cambio que se enviaron a la aplicación. Esto será menor que el total de notificaciones de cambio activadas si el usuario no tiene una licencia válida.</li>|
|**11**|**API de revisiones**<li>**Nombre para mostrar** : nombre para mostrar del usuario en el que se ha realizado un intento de actualizar el mensaje.</li> <li>**Licencia requerida** : si el usuario determinado tiene la licencia necesaria para que el mensaje se actualice correctamente.</li><li>**Recuento intentado** : intentos totales de actualizar mensajes.</li><li>**Mensaje parcheado** : total de mensajes que se actualizaron correctamente.</li>|
|**12**|**Uso de la API de exportación de chat**<li>**Nombre para mostrar** : nombre para mostrar del usuario en el que se ha realizado un intento de exportar el mensaje de chat del usuario.</li><li>**Licencia requerida** : si el usuario determinado tiene la licencia necesaria para que el mensaje se exporte correctamente.</li><li>**Recuento intentado** : intentos totales de exportar mensajes de chat.</li><li>**Mensaje exportado** : intentos totales en los que el mensaje de chat se exportó correctamente.</li> |
|**13**|**Uso de la API de exportación de equipo**<li>**Nombre para mostrar** : nombre para mostrar del equipo en el que se ha realizado un intento de exportar el mensaje de ese equipo.</li><li>**Recuento intentado** : intentos totales de exportar mensajes de equipo.</li><li>**Mensaje exportado** : intentos totales en los que el mensaje de equipo se exportó correctamente.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>Convertir los datos específicos del usuario en anónimos

Para que los datos del informe Teams actividad del usuario sean anónimos, debe ser administrador global. Esto ocultará información identificable, como el nombre para mostrar, el correo electrónico y el Azure AD en los informes y sus exportaciones.

1. En el Centro de administración de Microsoft 365, vaya **a Configuración** \> **organización Configuración** y, en la **pestaña Servicios,** elija **Informes**.
    
2. Seleccione **Informes** y, a continuación, **elija Mostrar identificadores anónimos**. Esta configuración se aplica tanto a los informes de uso en el Centro de administración de Microsoft 365 como en el centro Teams administración.
  
3. Seleccione **Guardar cambios**.