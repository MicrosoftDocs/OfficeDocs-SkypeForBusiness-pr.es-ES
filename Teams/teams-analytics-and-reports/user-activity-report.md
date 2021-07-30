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
description: Obtenga información sobre cómo usar el informe Teams actividad del usuario en el centro de administración de Microsoft Teams para ver cómo usan los usuarios de su organización Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13d2d261358fc5c373304c46b48684d1f116fc06
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646061"
---
# <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El Teams actividad de usuario proporciona información sobre los tipos de actividades que los usuarios de su organización hacen en Teams. Puede ver cuántos usuarios se comunican de forma no planificada a través de reuniones no programadas (1:1 y llamadas grupales). Vea cuántas reuniones ha organizado Teams usuario y las reuniones en las que ha participado Teams usuario. Vea detalles sobre minutos de pantalla, vídeo y audio, y estadísticas de comunicación de chat, como cuántos usuarios responden y publican mensajes del canal, y cuántos usuarios participan en mensajes de chat grupales o de 1:1.

> [!NOTE]
> La capacidad de programar un informe de actividad de usuario no está disponible en este momento.

## <a name="view-the-user-activity-report"></a>Ver el informe de actividad del usuario

Debe ser administrador de servicio de Teams para poder realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams](../using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. En el panel de navegación izquierdo del Microsoft Teams de administración, seleccione **Análisis & informes de**  >  **uso.** En la **pestaña Ver informes,** en **Informe,** **seleccione Teams de usuario.**
2. En **Intervalo de fechas,** seleccione un rango y, a continuación, seleccione **Ejecutar informe.**

    ![Captura de pantalla del Teams actividad del usuario en el Teams de administración con llamadas](../media/teams-reports-user-activity-with-callouts.png "Captura de pantalla del Teams actividad del usuario en el Teams de administración con llamadas")

## <a name="interpret-the-report"></a>Interpretar el informe

| Globo |Descripción  |
|--------|-------------|
|**1**   |El Teams de actividad del usuario se puede ver para ver las tendencias de los últimos 7 días, 30 o 90 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Los informes suelen reflejar una latencia de 24 horas desde el momento de la actividad. |
|**3**   |Los puntos de datos de series de tiempo en el gráfico muestran métricas de uso diferentes agregadas en el espacio empresarial. |
|**4**   |Los datos tabulares representaron métricas de uso diferentes agregadas por usuario. |
|**5**   |<ul><li>En el gráfico, el eje X es el intervalo de fechas seleccionado para el informe específico.</li> <li> El eje Y es el número de elementos activos o actividad.</li> </ul>Mueva el puntero sobre el punto que representa un elemento o actividad en una fecha determinada para ver el número de instancias de ese elemento o actividad en esa fecha.|
|**6**   | Cada una de las métricas representadas en el gráfico a nivel de inquilino. Filtre lo que ve en el gráfico seleccionando un elemento de la leyenda. Seleccione **Mensajes de canal,** **Mensajes de respuesta,**  **Mensajes de chat** o **Reuniones organizadas** para ver información relacionada con cada uno de ellos. Al cambiar esta selección no se cambia la información de la tabla. |
|**7**   |La tabla le proporciona un desglose del uso por usuario.   <ul><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Seleccione el nombre para mostrar para ir a la página de detalles del usuario en el Microsoft Teams de administración.</li><li>**Los mensajes de** canal son el número de mensajes únicos que el usuario publicó en un canal de grupo durante el período de tiempo especificado.</li><li>**Responder mensajes** es el número de mensajes de respuesta únicos que el usuario publicó en un canal de grupo durante el período de tiempo especificado.</li> <li>**Publicar mensajes** es el número de mensajes de publicación únicos que el usuario publicó en un canal de grupo durante el período de tiempo especificado.</li><li>**Mensajes de chat** es el número de mensajes únicos que el usuario ha publicado en un chat privado durante el período de tiempo especificado.</li><li>**Mensajes urgentes** es el número de mensajes urgentes que el usuario publicó en un chat durante el período de tiempo especificado.</li><li>Total de reuniones organizadas es la suma de reuniones **programadas, periódicas,** no planeadas y <em>sin</em> clasificar de una vez que un usuario organizó durante el período de tiempo especificado.</li><li>**Reuniones organizadas una** vez es el número de reuniones programadas una vez que un usuario organizó durante el período de tiempo especificado.</li><li>**Reuniones organizadas periódicamente es** el número de reuniones periódicas que un usuario organizó durante el período de tiempo especificado.</li><li>**Reuniones organizadas adhoc** es el número de reuniones no planeadas que un usuario organizó durante el período de tiempo especificado.</li><li>Total de reuniones participadas es la suma de las reuniones **programadas** de una sola vez, periódicas, no planeadas y <em>sin</em> clasificar en las que participó un usuario durante el período de tiempo especificado.</li><li>**Las reuniones que han participado una** vez programadas es el número de las reuniones programadas de una vez en las que participó un usuario durante el período de tiempo especificado.</li><li>**Las reuniones en las que ha** participado periódicamente es el número de reuniones periódicas en las que participó un usuario durante el período de tiempo especificado.</li><li>Reuniones en las que ha participado **adhoc** es el número de reuniones no planeadas en las que participó un usuario durante el período de tiempo especificado.</li><li>**Las llamadas 1:1** son el número de llamadas 1:1 en las que el usuario participó durante el período de tiempo especificado.</li><li>**El tiempo de** audio es el tiempo total de audio (minutos) en el que el usuario participó durante el período de tiempo especificado.</li><li>**El tiempo de** vídeo es el tiempo total de vídeo (minutos) en el que el usuario participó durante el período de tiempo especificado.</li><li>**El tiempo de uso compartido de** pantalla es el tiempo total de uso compartido de pantalla (minutos) en el que el usuario participó durante el período de tiempo especificado.</li>  <li>**La última actividad** es la última fecha (UTC) en la que el usuario participó en una Teams actividad.</li><li>**Otra actividad** realiza un seguimiento cuando el usuario se considera activo, pero tiene un valor de cero para los mensajes de chat, las llamadas de 1:1, los mensajes de canal, el total de reuniones y las reuniones organizadas. Ejemplos de acciones son cuando un usuario abre una entrada de mensaje de canal, pero no responde a ella o cuando un usuario recibe un mensaje privado y lo lee, pero no responde a él.</li> <li>**Las reuniones sin clasificar** son aquellas que no se pueden clasificar como programadas, periódicas o no planeadas. Son un número corto y, en su mayoría, no se pueden identificar debido a la información de telemetría manipulada</li> </ul>**Las llamadas grupales** se han sustituido por **reuniones organizadas y** reuniones **participadas adhoc.** La suma de estos dos valores es igual a lo que se ha medido mediante **llamadas grupales.**
|**8**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**9**   |Exporte el informe a un archivo CSV para analizarlo sin conexión. Seleccione **Exportar a Excel** y, a continuación, en la pestaña **Descargas,** seleccione Descargar **para** descargar el informe cuando esté listo.<br><br>![Captura de pantalla de la pestaña Descargas que muestra los informes exportados para descargar](../media/teams-reports-export-to-csv.png) <br>Al ver el informe en Excel, también verá una columna **Id.** que representa el Id. de usuario. Un id. de usuario suele ser una cadena alfanumérica. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Convertir los datos específicos del usuario en anónimos

Para que los datos de Teams de actividad de usuario sean anónimos, debe ser administrador global. Esto ocultará información identificable, como el nombre para mostrar, el correo electrónico y el id. de AAD en el informe y su exportación.

1. En Centro de administración de Microsoft 365, vaya a  la Configuración de Configuración y, en la pestaña \> Servicios, elija **Informes.** 
    
2. Seleccione **Informes** y, a continuación, **elija Mostrar identificadores anónimos.** Esta configuración se aplica tanto a los informes de uso de Centro de administración de Microsoft 365 como Teams de administración.
  
3. Seleccione **Guardar cambios**.

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
