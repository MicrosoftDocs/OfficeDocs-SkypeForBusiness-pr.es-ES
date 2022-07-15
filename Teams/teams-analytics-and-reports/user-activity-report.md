---
title: Informe de actividad de usuario de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de actividad de los usuarios de Teams en el Centro de administración de Microsoft Teams para ver cómo los usuarios de su organización usan Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 88eb4f56c6891643bd862f425821327d14b95cb4
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825714"
---
# <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe de actividad de los usuarios de Teams proporciona información sobre los tipos de actividades que realizan los usuarios de su organización en Teams. Puede ver cuántos usuarios se comunican de forma no planeada a través de reuniones no programadas (1:1 y llamadas de grupo). Vea cuántas reuniones ha organizado un usuario de Teams y las reuniones en las que ha participado un usuario de Teams. Vea los detalles sobre los minutos de audio, vídeo y pantalla, y las estadísticas de comunicación de chat, como cuántos usuarios responden y publican mensajes del canal, y cuántos usuarios participan en mensajes de chat individuales o grupales.

> [!NOTE]
> La capacidad de programar un informe de actividad de usuario no está disponible en este momento.

## <a name="view-the-user-activity-report"></a>Ver el informe de actividad de usuario

Debe ser administrador de servicio de Teams para poder realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams](../using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Análisis & informes** > **Informes de uso**. En la pestaña **Ver informes** , en **Informe**, seleccione **Actividad de usuario de Teams**.
2. En **Intervalo de fechas**, seleccione un intervalo y, a continuación, seleccione **Ejecutar informe**.

    ![Captura de pantalla del informe de actividad de los usuarios de Teams en el Centro de administración de Teams con globos.](../media/teams-reports-user-activity-with-callouts.png "Captura de pantalla del informe de actividad de los usuarios de Teams en el Centro de administración de Teams con globos")

## <a name="interpret-the-report"></a>Interpretar el informe

| Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe actividad de los usuarios de Teams para ver las tendencias de los últimos 7 días, 30 o 90 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Los informes suelen reflejar una latencia de 24 horas desde el momento de la actividad. |
|**3**   |Los puntos de datos de series temporales en el gráfico muestran distintas métricas de uso agregadas en el espacio empresarial. |
|**4**   |Los datos tabulares representaban métricas de uso diferentes agregadas por usuario. |
|**5**   |<ul><li>En el gráfico, el eje X es el intervalo de fechas seleccionado para el informe específico.</li> <li> El eje Y es el número de elementos activos o actividad.</li> </ul>Mueva el puntero sobre el punto que representa un elemento o actividad en una fecha determinada para ver el número de instancias de ese elemento o actividad en esa fecha.|
|**6**   | Cada una de las métricas representadas en el gráfico a nivel de inquilino. Filtre lo que ve en el gráfico seleccionando un elemento de la leyenda. Seleccione **Mensajes de canal**, **Mensajes de respuesta**,  **Mensajes de chat** o **Reuniones organizadas** para ver información relacionada con cada uno de ellos. Al cambiar esta selección no se cambia la información de la tabla. |
|**7**   |La tabla proporciona un desglose del uso por usuario.   <ul><li>**Nombre para** mostrar es el nombre para mostrar del usuario. Seleccione el nombre para mostrar para ir a la página de detalles del usuario en el Centro de administración de Microsoft Teams.</li><li>**Mensajes de canal** es el número de mensajes únicos que el usuario publicó en un canal de equipo durante el período de tiempo especificado.</li><li>**Mensajes de respuesta** es el número de mensajes de respuesta únicos que el usuario publicó en un canal de equipo durante el período de tiempo especificado.</li> <li>**Mensajes de publicación** es el número de mensajes de publicación únicos que el usuario publicó en un canal de equipo durante el período de tiempo especificado.</li><li>**Mensajes de chat** es el número de mensajes únicos que el usuario ha publicado en un chat privado durante el período de tiempo especificado.</li><li>**Mensajes urgentes** es el número de mensajes urgentes que el usuario publicó en un chat durante el período de tiempo especificado.</li><li>**Total de reuniones organizadas** es la suma de reuniones programadas, periódicas, no planeadas y <em>sin clasificar organizadas</em> por un usuario durante el período de tiempo especificado.</li><li>**Reuniones organizadas una sola vez es** el número de reuniones programadas por una vez que un usuario organizó durante el período de tiempo especificado.</li><li>**Reuniones periódicas organizadas periódicamente** es el número de reuniones periódicas que un usuario ha organizado durante el período de tiempo especificado.</li><li>**Reuniones organizadas adhoc** es el número de reuniones no planeadas organizadas por un usuario durante el período de tiempo especificado.</li><li>**El total de reuniones en las que se ha participado** es la suma de las reuniones programadas, periódicas, no planeadas y <em>sin clasificar</em> en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Reuniones en las que ha participado programadas una sola vez** es el número de reuniones programadas de una sola vez en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Las reuniones en las que se ha participado periódicamente** es el número de reuniones periódicas en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Reuniones en las que se ha participado** es el número de reuniones no planeadas en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Las llamadas 1:1** son el número de llamadas individuales en las que el usuario ha participado durante el período de tiempo especificado.</li><li>**Tiempo de** audio es el tiempo total de audio (minutos) en el que el usuario ha participado durante el período de tiempo especificado.</li><li>**Tiempo de vídeo** es el tiempo total de vídeo (minutos) en el que el usuario ha participado durante el período de tiempo especificado.</li><li>**Tiempo de uso compartido** de la pantalla es el tiempo total de uso compartido de la pantalla (minutos) en el que el usuario ha participado durante el período de tiempo especificado.</li>  <li>**Última actividad** es la última fecha (UTC) en la que el usuario ha participado en una actividad de Teams.</li><li>**Otras actividades** realiza un seguimiento cuando el usuario se considera activo pero tiene un valor cero para los mensajes de chat, las llamadas uno a uno, los mensajes de canal, el total de reuniones y las reuniones organizadas. Las acciones de ejemplo son cuando un usuario abre una publicación de mensaje de canal pero no responde o cuando un usuario recibe un mensaje privado y lo lee, pero no responde.</li> <li>**Las reuniones sin clasificar son aquellas** que no se pueden identificar como programadas, periódicas o no planeadas. Son pocos en número y a menudo no se pueden identificar debido a información de telemetría imperfecta.</li> </ul>**Las llamadas de** grupo han sido sustituidas por **Reuniones organizadas** y **Reuniones en las que han participado**. La suma de estos dos valores es igual a la que midieron **las llamadas de grupo**.
|**8**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**9**   |Exporte el informe a un archivo CSV para analizarlo sin conexión. Seleccione **Exportar a Excel** y, después, en la pestaña **Descargas** , seleccione **Descargar** para descargar el informe cuando esté listo.<br><br>![Captura de pantalla de la pestaña Descargas que muestra los informes exportados para descargar.](../media/teams-reports-export-to-csv.png) <br>Cuando vea el informe en Excel, también verá una columna **Id.** , que representa el id. de usuario. Un id. de usuario es normalmente una cadena alfanumérica. |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Establecer que los datos específicos del usuario sean anónimos

Para que los datos del informe de actividad de los usuarios de Teams sean anónimos, debe ser administrador global. Esto ocultará la información identificable (con hash MD5), como el nombre para mostrar, el correo electrónico y el id. de AAD en el informe y su exportación.

1. En Centro de administración de Microsoft 365, vaya a **Configuración** \> **de** la organización y, en la pestaña **Servicios**, elija **Informes**.
    
2. Seleccione **Informes** y, a continuación, elija **Mostrar nombres de usuario, grupo y sitio ocultos en todos los informes**. Esta configuración se aplica tanto a los informes de uso de Centro de administración de Microsoft 365 como al Centro de administración de Teams.
  
3. Seleccione **Guardar cambios**.

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
