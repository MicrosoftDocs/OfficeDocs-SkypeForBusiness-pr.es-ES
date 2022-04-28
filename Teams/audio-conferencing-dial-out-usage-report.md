---
title: Informe de uso de llamadas de salida de audioconferencia
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: fafan
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: Obtenga información sobre qué países y regiones tienen números de conferencias de acceso telefónico local y cómo se asignan automáticamente.
ms.openlocfilehash: 16cdae3a377d5ce87c218affc4944051f14f2631
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106452"
---
# <a name="audio-conferencing-dial-out-usage-report"></a>Informe de uso de llamadas de salida de audioconferencia

El informe de uso de llamadas de salida de audioconferencia en el centro de administración de Teams le ofrece información general sobre el uso y los dólares gastados en el servicio de llamada de salida de audioconferencia. Este informe permite a los administradores consumir datos a nivel de usuario en términos de créditos de comunicación invertidos y minutos de llamadas entrantes. Ayudará a los administradores a determinar los créditos de comunicación futuros necesarios a partir de cualquier momento en el tiempo.

## <a name="view-the-audio-conferencing-dial-out-usage-report"></a>Ver el informe de uso de llamadas de salida de Audioconferencia

En el panel de navegación izquierdo del centro de administración de Microsoft Teams,  **seleccioneAnalytics &**  **informesAdministrar** > informes. En la pestaña  **Ver informes** ,  **enInforme**, seleccione el **informe Uso de llamadas de salida de Audioconferencia**.

En  **Intervalo** de fechas, puede seleccionar un intervalo predefinido de 7 o 28 días, o establecer un intervalo personalizado.

 **EnContrio previsionado**, seleccione un país preferido o seleccione todo y, a continuación, seleccione  **Ejecutar informe**.

## <a name="report-details"></a>Detalles del informe

El informe de uso de llamadas de salida de audioconferencia tiene tres pestañas principales que mostrarán información en un formato de gráfico en función del rango seleccionado en las listas desplegables que hay encima:

- La pestaña **Costo** muestra los créditos de comunicación gastados durante el período seleccionado y la tabla siguiente proporciona detalles de nivel de usuario.
- La pestaña **Minutos de uso** muestra el total de minutos de llamadas entrantes durante el período seleccionado y la tabla siguiente proporciona detalles de nivel de usuario.
- La pestaña **Llamadas de salida** muestra el número total de llamadas entrantes durante el período seleccionado y la tabla siguiente proporciona detalles a nivel de usuario.

Cada informe tiene una fecha en la que se generó. Los informes suelen reflejar una latencia de 24 a 48 horas desde el tiempo de actividad.

> [!NOTE]
> Todos los minutos de llamadas entrantes, llamadas o créditos gastados se contarán en el organizador de la reunión. No es necesariamente la misma persona que marcó.

### <a name="cost-tab"></a>Pestaña Costo

En la parte superior de esta sección de pestaña hay un gráfico que muestra una línea que muestra información de costo sobre el intervalo de fechas y para el país o los países seleccionados.

Hay una sección **Costo** debajo del gráfico que muestra un precio, que es el costo total por minuto de llamadas dentro del intervalo de tiempo seleccionado.

### <a name="minutes-of-use-tab"></a>Ficha Minutos de uso

En la parte superior de esta sección de pestaña hay un gráfico que muestra una línea que muestra los minutos de uso en el intervalo de fechas y para el país o los países seleccionados.

Hay una sección **Minutos de uso debajo del** gráfico que muestra el total de minutos de llamadas usadas dentro del intervalo de tiempo seleccionado.

### <a name="dial-out-calls"></a>Llamadas entrantes

En la parte superior de esta sección de pestaña hay un gráfico que muestra una línea que muestra llamadas de acceso telefónico local en el intervalo de fechas y para el país o los países seleccionados.

Hay una sección **Llamadas entrantes** debajo del gráfico que muestra el número total de llamadas entrantes dentro del intervalo de tiempo seleccionado.

## <a name="using-the-report"></a>Usar el informe

En la parte inferior de la página hay una tabla que muestra desgloses de nivel de usuario con los siguientes títulos:

- Organizador de la reunión
- Username
- Minutos de usuario
- Crédito gastado
- Moneda

Si necesita buscar el uso de un usuario específico, hay una barra de búsqueda a la derecha encima del informe. Los nombres del organizador de la reunión son todos hipervínculos seleccionables que le llevarán a un informe de uso más detallado para el usuario. Esta vista de usuario tiene las mismas tres pestañas que el informe principal, pero el gráfico de la parte superior de la página mostrará los detalles de ese usuario específico.

Puede exportar cualquier informe que se muestra en esta tabla a un archivo CSV para analizarlo sin conexión. Selecciona **Exportar a Excel** y, a continuación, en la pestaña **Descargas**, selecciona **Descargar** para descargar el informe cuando esté listo.
