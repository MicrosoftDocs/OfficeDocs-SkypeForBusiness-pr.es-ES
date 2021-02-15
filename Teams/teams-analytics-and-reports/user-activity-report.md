---
title: Informe de actividad de usuario de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de actividad de los usuarios de Teams en el Centro de administración de Microsoft Teams para ver cómo usan teams los usuarios de su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f02d2f8751b8059f435164158d5c97fb6766a286
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196919"
---
# <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe de actividad de los usuarios de Teams proporciona información sobre los tipos de actividades que los usuarios de su organización hacen en Teams. Puede ver cuántos usuarios se comunican de forma no planificada a través de reuniones no programadas (1:1 y llamadas grupales). Vea cuántas reuniones ha organizado un usuario de Teams y las reuniones en las que ha participado un usuario de Teams. Vea los detalles sobre la pantalla, los minutos de audio y vídeo, y las estadísticas de comunicación de chat, como cuántos usuarios responden y publican mensajes del canal, y cuántos usuarios participan en mensajes de chat grupales o uno a uno.

## <a name="view-the-user-activity-report"></a>Ver el informe de actividad de usuario

Debe ser administrador del servicio de Teams para realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams y](https://docs.microsoft.com/microsoftteams/using-admin-roles) obtener información sobre cómo obtener permisos y roles de administrador.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Analytics & informes de**  >  **uso.** En la **pestaña Ver informes,** en **Informe,** seleccione Actividad **de usuario de Teams.**
2. En **Intervalo de fechas,** seleccione un rango y, a continuación, seleccione **Ejecutar informe.**

    ![Captura de pantalla del informe de actividad de los usuarios de Teams en el centro de administración de Teams con llamadas](../media/teams-reports-user-activity-with-callouts.png "Captura de pantalla del informe de actividad de los usuarios de Teams en el centro de administración de Teams con llamadas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de actividad de los usuarios de Teams para ver las tendencias de los últimos 7, 30 o 90 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, los informes reflejan una latencia de 24 horas desde el momento de actividad. |
|**3**   |Los puntos de datos de serie temporal del gráfico muestran métricas de uso diferentes agregadas en el inquilino. |
|**4**   |Los datos tabulares representaron métricas de uso diferentes agregadas por usuario. |
|**5**   |<ul><li>En el gráfico, el eje X es el intervalo de fechas seleccionado para el informe específico.</li> <li> El eje Y es el número de elementos activos o actividad.</li> </ul>Mueva el puntero sobre el punto que representa un elemento o actividad en una fecha determinada para ver el número de instancias de ese elemento o actividad en esa fecha.|
|**6**   | Cada una de las métricas representadas en el gráfico a nivel de inquilino. Filtre lo que ve en el gráfico seleccionando un elemento en la leyenda. Seleccione **Mensajes de canal,** **Mensajes de respuesta,**  **Mensajes de chat** o Reuniones **organizadas** para ver información relacionada con cada uno de ellos. Al cambiar esta selección no se cambia la información de la tabla. |
|**7**   |La tabla proporciona un desglose del uso por usuario.   <ul><li>**Nombre para** mostrar es el nombre para mostrar del usuario. Seleccione el nombre para mostrar para ir a la página de detalles del usuario en el Centro de administración de Microsoft Teams.</li><li>**Mensajes de canal** es el número de mensajes únicos que el usuario publicó en un canal de equipo durante el período de tiempo especificado.</li><li>**Mensajes de respuesta** es el número de mensajes de respuesta única que el usuario publicó en un canal de equipo durante el período de tiempo especificado.</li> <li>**Publicar mensajes** es el número de mensajes de publicación únicos que el usuario publicó en un canal de equipo durante el período de tiempo especificado.</li><li>**Mensajes de** chat es el número de mensajes únicos que el usuario publicó en un chat privado durante el período de tiempo especificado.</li><li>**Mensajes urgentes** es el número de mensajes urgentes que el usuario publicó en un chat durante el período de tiempo especificado.</li><li>El total de reuniones organizadas es la suma de reuniones **programadas, periódicas,** no planeadas y <em>sin</em> clasificar de un usuario durante el período de tiempo especificado.</li><li>**Las reuniones organizadas una** sola vez es el número de reuniones programadas una vez que el usuario ha organizado durante el período de tiempo especificado.</li><li>**Las reuniones organizadas periódicamente** es el número de reuniones periódicas que ha organizado el usuario durante el período de tiempo especificado.</li><li>**Reuniones organizadas es el** número de reuniones no planeadas que ha organizado un usuario durante el período de tiempo especificado.</li><li>El total de reuniones en las que se ha participado es la suma de las reuniones programadas de un solo uso, **periódicas,** no planeadas y <em>sin</em> clasificar en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Las reuniones en las** que se ha participado una sola vez es el número de las reuniones programadas de una hora en las que el usuario ha participado durante el período de tiempo especificado.</li><li>**Reuniones en las que se** ha participado periódicamente es el número de reuniones periódicas en las que ha participado un usuario durante el período de tiempo especificado.</li><li>Las reuniones en las que **se ha participado** es el número de reuniones no planificadas en las que el usuario ha participado durante el período de tiempo especificado.</li><li>**Las llamadas de 1:1** son el número de llamadas de 1:1 en las que el usuario ha participado durante el período de tiempo especificado.</li><li>**El tiempo de** audio es el tiempo total de audio (minutos) en el que el usuario ha participado durante el período de tiempo especificado.</li><li>**El tiempo de** vídeo es el tiempo total de vídeo (minutos) en el que el usuario ha participado durante el período de tiempo especificado.</li><li>**El tiempo de uso compartido** de la pantalla es el tiempo total de uso compartido de la pantalla (minutos) en el que el usuario ha participado durante el período de tiempo especificado.</li>  <li>**La última** actividad es la última fecha (UTC) en la que el usuario ha participado en una actividad de Teams.</li><li>**Otra actividad** realiza un seguimiento cuando el usuario se considera activo, pero tiene un valor cero para los mensajes de chat, las llamadas uno a uno, los mensajes de canal, el total de reuniones y las reuniones organizadas. Algunos ejemplos de acciones son cuando un usuario abre una publicación de mensaje de canal pero no responde o cuando un usuario recibe un mensaje privado y lo lee pero no responde.</li> <li>**Las reuniones sin** clasificar son las que no se pueden clasificar como programadas, periódicas o no planeadas. Son un número corto y casi no se pueden identificar debido a la información de telemetría manipulada</li> </ul>**Las llamadas de** grupo se han sustituido **por reuniones organizadas** y reuniones en las que **se ha participado.** La suma de estos dos valores es igual a lo que se miden las llamadas **de grupo.**
|**8**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**9**   |Exporte el informe a un archivo CSV para analizarlo sin conexión. Seleccione **Exportar a Excel** y, después, en la pestaña **Descargas,** seleccione Descargar para descargar el informe cuando esté listo. <br><br>![Captura de pantalla de la pestaña Descargas que muestra los informes exportados para descargar](../media/teams-reports-export-to-csv.png) <br>Cuando vea el informe en Excel, también  verá una columna Id., que representa el Id. de usuario. Un id. de usuario suele ser una cadena alfanumérica. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
