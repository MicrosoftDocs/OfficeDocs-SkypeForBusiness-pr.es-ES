---
title: Informe de uso de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Aprenda a usar el informe de uso de Teams en el centro de administración de Microsoft Teams para obtener información general sobre la actividad de Teams en su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3e280a32c765c989ef5d6081388ad76701be6ab1
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033798"
---
# <a name="microsoft-teams-usage-report"></a>Informe de uso de Microsoft Teams

El informe de uso de Teams en el centro de administración de Microsoft Teams proporciona información general sobre la actividad de uso en Teams, como el número de usuarios y canales activos, para que pueda ver rápidamente cuántos usuarios en su organización usan Teams para comunicarse y colaborar. Puede ver información sobre el uso para equipos, como el número de canales y usuarios activos, invitados y mensajes en cada equipo.

Con más información acerca de los usuarios internos y externos, ahora puede medir la colaboración en [los canales compartidos](/Teams/shared-channels.md) internos y externos de un equipo. Por ejemplo, las métricas como los canales compartidos activos y los usuarios activos externos de un equipo ayudarán al administrador a medir la colaboración entre canales compartidos dentro de un equipo.

## <a name="view-the-usage-report"></a>Ver el informe de uso

Para ver los informes en el Centro de administración de Teams, debe ser administrador global, lector global o administrador del servicio de Teams. Consulte [Usar los roles de administrador de Teams para administrar Teams](../using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Análisis & informes** > **de uso**. En la pestaña **Ver informes** , en **Informe**, seleccione **Uso de Teams**.
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**.

    ![Captura de pantalla del informe de uso de Teams en el Centro de administración de Teams con globos.](../media/teams-reports-teams-usage-with-callouts2.png "Captura de pantalla del informe de uso de Teams en el Centro de administración de Teams con globos")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe Actividad de uso de Teams para ver las tendencias de los últimos 7, 30, 90 y 180 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Los informes suelen reflejar una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |<ul><li>En el gráfico, el eje X es el intervalo de fechas seleccionado para el informe específico.</li> <li> El eje Y es el número de elementos activos o actividad.</li> </ul>Mueva el puntero sobre el punto que representa un elemento o actividad en una fecha determinada para ver el número de instancias de ese elemento o actividad en esa fecha.|
|**4**   |Puede filtrar lo que aparece en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haga clic en  **Usuarios activos internos**, **Invitados activos**,  **Canales activos**, **Publicaciones**, etc. para ver solo la información relacionada con cada uno de ellos. Al cambiar esta selección no se cambia la información de la tabla. |
|**5**   |La tabla le proporciona un desglose del uso por equipo. <ul><li>**Nombre del equipo** es el nombre para mostrar del equipo. Puede hacer clic en el nombre del equipo para ir a la página de configuración del equipo en el Centro de administración de Microsoft Teams. </li> <li>**Id. de** equipo es el identificador único del equipo. </li> <li>**Tipo** hace referencia a si el equipo es un equipo privado o público.</li> <li>**Usuarios internos activos** es el número de usuarios activos, incluidos los invitados que realizan una acción en ese equipo en el período de tiempo especificado. <br/>Los usuarios internos y los invitados residen en el mismo espacio empresarial, pero no son iguales.</li><li>**Invitados activos** es el número de invitados que realizan una acción en ese equipo en el período de tiempo especificado.</li> <li>**Usuarios activos externos** (nuevo) es el número de usuarios activos de organizaciones externas que realizan una acción en ese equipo en un recurso, como un canal compartido en un equipo. <br/> Los usuarios externos tienen sus propias identidades en espacios empresariales diferentes y no son lo mismo que una cuenta de invitado.</li><li>**Canales activos** es el número de canales del equipo que tiene al menos un usuario activo en el período de tiempo especificado. Esto incluye canales privados, públicos y compartidos. </li><li>**Canales compartidos activos** (nuevo) es el número de canales compartidos en un equipo que tiene al menos un usuario interno o externo activo en el período de tiempo especificado. </li> <li>**El total de reuniones organizadas** es la suma de reuniones programadas, periódicas, no planeadas y sin clasificar organizadas por un usuario durante el período de tiempo especificado. </li><li>**Publicaciones** es el número de todos los mensajes publicados en canales en el período de tiempo especificado.</li> <li>**Respuestas** es el número de todos los mensajes de respuesta en canales en el período de tiempo especificado.</li> <li>**Menciones** es el número de todas las menciones usadas en los mensajes en el período de tiempo especificado.</li><li>**Reacciones** es el número de todas las reacciones a los mensajes en el período de tiempo especificado.</li><li>**Mensajes urgentes** es el número de todos los mensajes urgentes en el período de tiempo especificado.</li><li>**Mensajes de canal** es el número de mensajes únicos que los usuarios del equipo publicaron en los chats del equipo durante el período de tiempo especificado.</li> </li> </ul>Tenga en cuenta que si ya no existe un equipo, el nombre se mostrará como "--" en la tabla. <br><br>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**7**   |Exporte el informe a un archivo CSV para analizarlo sin conexión. Seleccione el icono **Exportar a Excel** y el informe se descargará en el explorador.|
|**8** |Los datos de series temporales representados en el gráfico superior muestran métricas de uso diferentes agregadas para todo el espacio empresarial|
|**9** |Los datos tabulares representados en la mitad inferior muestran las distintas métricas de uso agregadas por equipo|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]


## <a name="make-the-user-specific-data-anonymous"></a>Establecer que los datos específicos del usuario sean anónimos

Para que los datos del informe de actividad de los usuarios de Teams sean anónimos, debe ser administrador global. El administrador global puede ocultar la información identificable (con hash MD5) como el nombre para mostrar, el nombre del grupo, el correo electrónico y el id. de AAD en el informe y su exportación.

1. En Centro de administración de Microsoft 365, vaya a **Configuración** >  de la organización y, en la pestaña **Servicios**, elija **Informes**.
    
2. Seleccione **Informes** y, a continuación **, elija Mostrar nombres de usuario, grupo y sitio ocultos en todos los informes**. Esta configuración se aplica tanto a los informes de uso de Centro de administración de Microsoft 365 como al Centro de administración de Teams.
  
3. Seleccione **Guardar cambios**.

> [!NOTE]
> Si habilita esta opción, se despersonalizará la información de usuario, grupo y nombre del sitio en el [informe de actividad de los usuarios de Teams](user-activity-report.md), el informe de [uso de dispositivos de Teams](device-usage-report.md) y el [informe de uso de Teams](teams-usage-report.md). A partir del 1 de septiembre de 2021, esta configuración está habilitada de forma predeterminada para todos los usuarios como parte de nuestro compromiso continuo de ayudar a proteger información importante y permitir que las empresas apoyen sus leyes de privacidad local. 
>
>Esta configuración también se aplica a los informes de uso de Microsoft 365 en Centro de administración de Microsoft 365, Microsoft Graph y Power BI.

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
