---
title: Agregar y actualizar etiquetas de informes
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo cargar un archivo de texto que contiene una lista de ubicaciones físicas y subredes asociadas para usarlas como etiquetas de informes para análisis de llamadas y informes del panel de calidad de llamadas.
ms.custom:
- NewAdminCenter_Update
f1.keywords:
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19d3197d91b7139089a940c19ff23c1dcc99a290
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707866"
---
<a name="add-and-update-reporting-labels"></a>Agregar y actualizar etiquetas de informes
============================

Las etiquetas de informes se usan en su organización para indicar las ubicaciones físicas de oficinas, edificios o sitios de la organización. La página etiquetas de informes del centro de administración de Microsoft Teams le permite proporcionar un archivo de texto (. csv o. TSV) que contiene una lista de ubicaciones físicas y sus subredes de red asociadas. Este archivo lo usa el análisis de llamadas y el panel de calidad de llamadas para generar informes. Cuando cargue la asignación de subred, los informes proporcionados por estos servicios también contendrán los nombres de ubicación, lo que hace que los informes sean más fáciles de comprender y usar para corregir cualquier problema potencial.

Los datos de etiquetas y ubicaciones del informe que proporciona son una única estructura de datos: actualmente no hay ninguna interfaz disponible para realizar ediciones individuales de los datos.

**Para editar la tabla de subredes y ubicaciones**

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en **ubicaciones** > **etiquetas de informes**.
2. Haga clic en **reemplazar datos de ubicaciones**.
3. En el panel **reemplazar datos de ubicación** , haga clic en **seleccionar un archivo**y, a continuación, busque y cargue el archivo. csv o. TSV editado.
4. Haga clic en **cargar**.

Puede descargar una plantilla de ejemplo [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Use el ejemplo siguiente para ayudar a crear el archivo de datos.

> [!IMPORTANT]
> El archivo de datos no debe contener encabezados de columna (como red, nombre de red, etc.). Se usan aquí solo con fines informativos. <br>

|Red|Nombre de red|Intervalo de red|Nombre del edificio|Tipo de propiedad|Tipo de edificio|Tipo de edificio de Office|Ciudad|Código postal|Tercer|Estado|Region|Inside Corp|Expressroute|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|

Para obtener más información sobre cómo dar formato a un archivo de datos, vea [formato del archivo de datos de inquilinos y creación de una estructura de archivo de datos](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure).

## <a name="related-topics"></a>Temas relacionados

[Configurar el Análisis de llamadas](set-up-call-analytics.md)
