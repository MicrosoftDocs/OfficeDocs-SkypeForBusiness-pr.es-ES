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
ms.openlocfilehash: 3bd00dd9cf05adea6d37ad07c1a22c3000d78e94
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532390"
---
# <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe de actividad de los usuarios de Teams proporciona información sobre los tipos de actividades que realizan los usuarios de su organización en Teams. Puede ver cuántos usuarios se comunican de forma no planeada a través de reuniones no programadas (1:1 y llamadas de grupo). Vea cuántas reuniones ha organizado un usuario de Teams y las reuniones en las que ha participado un usuario de Teams. Vea los detalles sobre los minutos de audio, vídeo y pantalla, y las estadísticas de comunicación de chat, como cuántos usuarios responden y publican mensajes del canal, y cuántos usuarios participan en mensajes de chat individuales o grupales.

Con más información acerca de los usuarios internos y externos, ahora puede medir la interacción de los usuarios en [canales compartidos](/Teams/shared-channels.md) internos y externos, por ejemplo, métricas como el nombre del inquilino al que pertenece el usuario, los nombres de inquilinos externos donde interactúa el usuario y si el usuario es externo al inquilino ayudará a los administradores a medir la inacción de los usuarios a través de las características del canal compartido. 

> [!NOTE]
> La capacidad de programar un informe de actividad de usuario no está disponible en este momento.

## <a name="view-the-user-activity-report"></a>Ver el informe de actividad de usuario

Para ver el informe en el Centro de administración de Microsoft Teams, debe ser administrador global, lector global o administrador del servicio de Teams. Consulte [Usar los roles de administrador de Teams para administrar Teams](../using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Análisis & informes** > **Informes de uso**. En la pestaña **Ver informes** , en **Informe**, seleccione **Actividad de usuario de Teams**.
2. En **Intervalo de fechas**, seleccione un intervalo y, a continuación, seleccione **Ejecutar informe**.

    ![Captura de pantalla del informe de actividad de los usuarios de Teams en el Centro de administración de Teams con globos.](../media/teams-reports-user-activity-with-callouts2.png "Captura de pantalla del informe de actividad de los usuarios de Teams en el Centro de administración de Teams con globos")

## <a name="interpret-the-report"></a>Interpretar el informe

| **Globo** |**Descripción**  |
|--------|-------------|
|**1**   |Puede visualizar el informe actividad de los usuarios de Teams para ver las tendencias de los últimos 7, 30, 90 o 180 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Los informes suelen reflejar una latencia de 24 a 48 horas desde el momento de la actividad. |
|**3**   |Los datos de series temporales representados en el gráfico superior muestran distintas métricas de uso agregadas para todo el espacio empresarial. |
|**4**   |Los datos tabulares representados en la mitad inferior muestran distintas métricas de uso agregadas por usuario. |
|**5**   |<ul><li>En el gráfico, el eje X es el intervalo de fechas seleccionado para el informe específico.</li> <li> El eje Y es el número de elementos activos o actividad.</li> </ul>Mueva el puntero sobre el punto que representa un elemento o actividad en una fecha determinada para ver el número de instancias de ese elemento o actividad en esa fecha.|
|**6**   | Cada una de las métricas se representa en el gráfico en el nivel de inquilino. Filtre lo que ve en el gráfico seleccionando un elemento de la leyenda. Seleccione **Mensajes de canal**, **Mensajes de respuesta**,  **Mensajes de chat** o **Reuniones organizadas** y mucho más para ver información relacionada con cada uno de ellos. Al cambiar esta selección no se cambia la información de la tabla. |
|**7**   |La tabla proporciona un desglose del uso por usuario.   <ul><li>**Nombre de usuario** es la dirección de correo electrónico del usuario. Consulte [la siguiente sección](#make-the-user-specific-data-anonymous) para obtener instrucciones sobre cómo anonimizarlo.  Seleccione el nombre de usuario para ir a la página de detalles del usuario.</li><li>**Nombre del inquilino** (nuevo) es el nombre de un inquilino interno o externo al que pertenece un usuario. Si un usuario pertenece a un inquilino externo, se calculan distintas métricas de uso (por ejemplo, publicar mensajes, mensajes de respuesta, etc.) en función de sus interacciones en uno o más canales compartidos del inquilino del administrador. Las interacciones realizadas por un usuario externo en su propio inquilino no se tienen en cuenta para el informe de uso de administrador de un inquilino determinado.  </li><li>**Nombres de inquilino de canal compartido** (nuevo) son los nombres de inquilinos internos o externos en los que el usuario ha participado como parte de un canal compartido.</li><li>**Mensajes de canal** es el número de mensajes únicos que el usuario publicó en un canal de equipo durante el período de tiempo especificado.</li><li>**Respuestas** es el número de mensajes de respuesta únicos que el usuario publicó en un canal de equipo durante el período de tiempo especificado.</li> <li>**Publicaciones** es el número de mensajes de publicación únicos que el usuario publicó en un canal de equipo durante el período de tiempo especificado.</li><li>**Mensajes de chat** es el número de mensajes únicos que el usuario ha publicado en un chat privado durante el período de tiempo especificado.</li><li>**Mensajes urgentes** es el número de mensajes urgentes que el usuario publicó en un chat durante el período de tiempo especificado.</li><li>**Total de reuniones organizadas** es la suma de reuniones programadas, periódicas, no planeadas y sin clasificar organizadas por un usuario durante el período de tiempo especificado.</li><li>**Reuniones organizadas una sola vez es** el número de reuniones programadas por una sola vez que un usuario organizó durante el período de tiempo especificado.</li><li>**Reuniones periódicas organizadas periódicamente** es el número de reuniones periódicas que un usuario ha organizado durante el período de tiempo especificado.</li><li>**Reuniones organizadas adhoc** es el número de reuniones no planeadas organizadas por un usuario durante el período de tiempo especificado.</li><li>**Total de reuniones en las que se ha participado** es la suma de las reuniones programadas, periódicas, no planeadas y sin clasificar en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Reuniones en las que ha participado programadas una sola vez** es el número de reuniones programadas de una sola vez en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Las reuniones en las que se ha participado periódicamente** es el número de reuniones periódicas en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Reuniones en las que se ha participado** es el número de reuniones no planeadas en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Llamadas** individuales es el número de llamadas individuales en las que el usuario ha participado durante el período de tiempo especificado.</li><li>**Tiempo de audio** es el tiempo total de audio (en minutos) en el que el usuario ha participado durante el período de tiempo especificado.</li><li>**Tiempo de vídeo** es el tiempo total de vídeo (en minutos) en el que el usuario ha participado durante el período de tiempo especificado.</li><li>**Tiempo de uso compartido** de la pantalla es el tiempo total de uso compartido de la pantalla (minutos) en el que el usuario ha participado durante el período de tiempo especificado.</li>  <li>**Última actividad** es la última fecha (UTC) en la que el usuario ha participado en una actividad de Teams.</li><li>**Otras actividades** realiza un seguimiento cuando el usuario se considera activo pero tiene un valor cero para los mensajes de chat, las llamadas uno a uno, los mensajes de canal, el total de reuniones y las reuniones organizadas. Ejemplos de acciones son cuando un usuario cambia el estado de Teams o el mensaje de estado de Teams, cuando un usuario abre una publicación de mensaje de canal pero no responde, o cuando un usuario recibe un mensaje privado y lo lee pero no responde.</li> </ul> **Las reuniones sin clasificar son aquellas** que no se pueden identificar como programadas, periódicas o no planeadas. Son pocos en número y a menudo no se pueden identificar debido a información de telemetría imperfecta.<br><br>**Las llamadas de** grupo han sido sustituidas por **Reuniones organizadas** y **Reuniones en las que han participado**. La suma de estos dos valores es igual a la que midieron **las llamadas de grupo**. <br/><br/>Tenga en cuenta que si ya no existe un usuario, el nombre se mostrará como "--" en la tabla.
|**8**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
**9**   |Exporte el informe a un archivo CSV para analizarlo sin conexión. Seleccione **Exportar a Excel** y el informe se descargará en el explorador. <br>Cuando vea el informe en Excel, también verá una columna id. de **usuario** , que representa el id. de usuario. Un id. de usuario es normalmente una cadena alfanumérica. |


[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Establecer que los datos específicos del usuario sean anónimos

Para que los datos del informe de actividad de los usuarios de Teams sean anónimos, debe ser administrador global. La Administrador global puede ocultar información de identificación (con hash MD5), como el nombre para mostrar, el nombre del grupo, el correo electrónico y el id. de AAD en los informes y su exportación.

1. En Centro de administración de Microsoft 365, vaya a **Configuración** \> **de** la organización y, en la pestaña **Servicios**, elija **Informes**.
    
2. Seleccione **Informes** y, a continuación, elija **Mostrar nombres de usuario, grupo y sitio ocultos en todos los informes**. Esta configuración se aplica tanto a los informes de uso de Centro de administración de Microsoft 365 como al Centro de administración de Teams.
  
3. Seleccione **Guardar cambios**.


> [!NOTE]
> Si habilita esta opción, se despersonalizará la información de usuario, grupo y nombre del sitio en el [informe de actividad de los usuarios de Teams](user-activity-report.md), el informe de [uso de dispositivos de Teams](device-usage-report.md) y el [informe de uso de Teams](teams-usage-report.md) . A partir del 1 de septiembre de 2021, esta configuración está habilitada de forma predeterminada para todos los usuarios como parte de nuestro compromiso continuo de ayudar a proteger información importante y permitir que las empresas apoyen sus leyes de privacidad local. Esta configuración también se aplica a los informes de uso de Microsoft 365 en la Centro de administración de Microsoft 365, Microsoft Graph y Power BI.
## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
