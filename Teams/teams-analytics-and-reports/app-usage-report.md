---
title: Informe de uso de aplicaciones de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.date: 09/27/2022
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de uso de aplicaciones de Teams en el Centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c437676df215ead9b588091f2cb58c19d1e136fd
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532270"
---
# <a name="microsoft-teams-app-usage-report"></a>Informe de uso de aplicaciones de Microsoft Teams

El informe de uso de aplicaciones de Teams en el Centro de administración de Microsoft Teams le proporciona información sobre qué aplicaciones usan los usuarios en Teams. Puede obtener información sobre la actividad de las aplicaciones de su organización para diferentes aplicaciones de Microsoft (aprendizaje Viva, Turnos, etc.), de terceros (Polly, Trello, etc.) & De línea de negocio (LOB).   

Puede usar este informe para comprender dónde se usan exactamente diferentes aplicaciones y profundizar en los datos de uso de cada aplicación.

Los datos representados en este informe proporcionan respuestas a las siguientes preguntas:

-  ¿Cuántas aplicaciones instaladas tienen los usuarios de su entorno?
-  ¿Cuántas aplicaciones tienen al menos un usuario activo en su entorno en función del tipo (Microsoft, de terceros y LOB)?
-  ¿Cuántas aplicaciones se usan por plataforma (Windows, Mac, web o móvil)?
-  ¿Cuántos usuarios activos y equipos activos usan una aplicación?

> [!NOTE]
> El uso de aplicaciones lob **cargadas en paralelo** no se incluye en este informe.

En este artículo se explica cómo acceder al informe y ver e interpretar las distintas métricas del informe. 

## <a name="view-the-app-usage-report"></a>Ver el informe de uso de aplicaciones

Debe ser administrador global, lector global o administrador del servicio de Teams para poder ver los informes en el Centro de administración de Microsoft Teams. Consulte [Usar los roles de administrador de Teams para administrar Teams](../using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Análisis & informes** > **Informes de uso**. En la pestaña **Ver informes** , en **Informe**, seleccione **Uso de aplicaciones**.

2. En **Intervalo de fechas**, seleccione un intervalo y, a continuación, seleccione **Ejecutar informe**.

:::image type="content" alt-text="Captura de pantalla del informe de uso de aplicaciones de Teams en el Centro de administración de Teams con globos." source="media/app-usage2-report10.png" lightbox="media/app-usage2-report10.png":::

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de uso de aplicaciones para ver las tendencias de los últimos 7, 30, 90 y 180 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Los informes suelen reflejar una latencia de 24 a 48 horas desde el momento en que se usó una aplicación. Por ejemplo, los datos del 10 de enero deberían aparecer en el informe alrededor del 12 de enero. |
|**3**   |<ul><li>En el gráfico, el eje X es el intervalo de fechas seleccionado para el informe específico.</li> <li> El eje Y es el recuento de elementos.</li> </ul>Desplace el puntero sobre el punto que representa un elemento en una fecha determinada para ver el número de instancias de ese elemento en esa fecha determinada.|
|**4**   |Puede filtrar lo que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, selecciona **Aplicaciones activas de Microsoft**, **Total de aplicaciones instaladas** y mucho más para ver solo la información relacionada con cada una de ellas. Al cambiar esta selección no se cambia la información de la tabla. <ul><li>**Aplicaciones activas de Microsoft** es el número de aplicaciones de Microsoft (por ejemplo, aprendizaje Viva) que se usan en toda la organización. </li> <li>**Aplicaciones de terceros activas** es el número de aplicaciones de terceros (por ejemplo, Polly) que se usan en toda la organización.  </li> <li>**Aplicaciones de LÍNEA de negocio activas** es el número de aplicaciones de línea de negocio que se usan en toda la organización. </li><li>**El número total de aplicaciones activas** es el número total de aplicaciones que se usan en toda la organización. </li><li>**El total de aplicaciones inactivas** es el número de aplicaciones que no se usan en su organización. </li><li>**El total de aplicaciones instaladas** es el número total de aplicaciones instaladas en su organización. La fecha de inicio de todas las métricas de instalación es octubre de 2021. Solo se contarán las aplicaciones instaladas después de esa fecha.</li></ul> El gráfico muestra las métricas agregadas en toda la organización en cada día dentro de un período seleccionado. Por ejemplo, si selecciona el 28 de enero y la métrica **Aplicaciones de terceros activas**, el gráfico le mostrará el número total de aplicaciones de terceros usadas el 28 de enero en su organización.  |
|**5**   |La tabla ofrece un desglose del uso de cada aplicación. <ul><li>**Id. de** aplicación es el identificador de aplicación externo presente en el manifiesto de la aplicación. <br/>Puede encontrar más información sobre la aplicación en la [sección Administrar aplicaciones del Centro de administración de Teams](/microsoftteams/manage-apps) haciendo referencia a ella con este id. de aplicación externo.</li> <li>**Nombre de** la aplicación es el nombre de esta aplicación tal y como está presente en el manifiesto de la aplicación. </li> <li>**Publisher** es el editor de esta aplicación tal y como está presente en el manifiesto de la aplicación. Esto solo está disponible para las aplicaciones publicadas en la Store global.</li> <li>**Equipos que usan esta aplicación** es el número de equipos distintos de Teams que tienen al menos un usuario usando esta aplicación. </li><li>**Los usuarios que usan esta aplicación** son el número de usuarios distintos de su organización que usan esta aplicación.</li> <li>**Usado en Windows** indica si esa aplicación ha sido usada en Windows por al menos un usuario de la organización.</li><li>**Usado en Mac** indica si esa aplicación se ha usado en MAC por al menos un usuario de su organización.</li><li>**Usado en la Web** indica si esa aplicación ha sido usada en la Web por al menos un usuario de su organización. </li> <li>**La fecha de último uso** es la fecha en que cualquier persona de la organización usó la aplicación por última vez. </li></ul> |
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**7**   |Exporte el informe a un archivo CSV para analizarlo sin conexión. Seleccione el icono **Exportar a Excel** y el informe se descargará en el explorador.|
|**8** |Los datos de series temporales representados en el gráfico superior muestran distintas métricas de uso agregadas para todo el espacio empresarial.|
|**9** |Los datos tabulares representados en la mitad inferior muestran diferentes métricas de uso agregadas por equipo.|


## <a name="managing-apps-in-the-microsoft-teams-admin-center"></a>Administrar aplicaciones en el Centro de administración de Microsoft Teams

Para obtener más información sobre cómo administrar las aplicaciones de Teams, consulte [Acerca de las aplicaciones en Microsoft Teams](/microsoftteams/deploy-apps-microsoft-teams-landing-page.md).

Para vincular una aplicación de este informe a la experiencia Administrar aplicaciones del Centro de administración de Microsoft Teams, puede usar lo siguiente:

- Nombre de aplicación
- Id. de aplicación externa

Los identificadores de aplicación externos equivalen al identificador de la página Administrar aplicaciones de las aplicaciones de la Store. Para las aplicaciones de LOB, la columna **Id. de aplicación externa**  se puede habilitar en la [sección Administrar aplicaciones de](/microsoftteams/manage-apps) la configuración de la columna del Centro de administración de Teams. También puedes verlo en la página de detalles de la aplicación de una aplicación lob personalizada.

## <a name="related-articles"></a>Artículos relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
