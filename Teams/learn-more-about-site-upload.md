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
description: Obtenga información sobre cómo agregar y actualizar etiquetas de informes cargando un archivo de texto que contiene una lista de ubicaciones físicas y subredes asociadas.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 481e087a6cfe2b641f6b81fcfc893d50f27cbf47
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237490"
---
<a name="add-and-update-reporting-labels"></a>Agregar y actualizar etiquetas de informes
============================

Las etiquetas de informes se usan en su organización para indicar las ubicaciones físicas de oficinas, edificios o sitios de la organización. La página Etiquetas de informes del Centro de administración de Microsoft Teams le permite proporcionar un archivo de texto (.csv o .tsv) que contiene una lista de ubicaciones físicas y sus subredes de red asociadas. Este archivo lo usa Call Analytics para generar informes. Al cargar la asignación de subred, los informes proporcionados por estos servicios también contendrán los nombres de ubicación, lo que facilitará la comprender y usar los informes para corregir posibles problemas.

> [!IMPORTANT]
> Las etiquetas de informes que  cargue se administrarán como datos de soporte técnico conforme  a su contrato para Office 365, incluida cualquier información que de otro modo se consideraría Datos de cliente o *Datos personales.* No incluya datos que no desee proporcionar a Microsoft como datos de soporte *técnico,* ya que esta información será visible para los ingenieros de Microsoft con fines de soporte técnico.

Los datos de etiquetas y ubicaciones de informe que proporciona son una única estructura de datos: actualmente no hay ninguna interfaz disponible para realizar ediciones individuales de los datos.

**Para editar la tabla de subredes y ubicaciones**

1. En el panel de navegación izquierdo del centro Microsoft Teams administración, haga clic en **Etiquetas**  >  **de informes de ubicaciones.**
2. Haga **clic Upload datos**.
3. En el **Upload de** datos, haga clic en Seleccionar un archivo y, **a** continuación, busque y cargue el archivo editado .csv o .tsv.
4. Haga **clic Upload**.

Puede descargar una plantilla de ejemplo [aquí.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)

Use el siguiente ejemplo para ayudar a crear el archivo de datos.

> [!IMPORTANT]
> El archivo de datos no debe contener encabezados de columna (como Red, Nombre de red, etc.). Se usan aquí solo con fines informativos. <br>

|Red|Nombre de red|Rango de red|Nombre del edificio|Tipo de propiedad|Tipo de edificio|Tipo Office creación|Ciudad|Código postal|País|Estado|Region|Inside Corp|Ruta rápida|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Vista montaña|94043|EE. UU.|CA|EE. UU.|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Vista montaña|94043|EE. UU.|CA|EE. UU.|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Vista montaña|94043|EE. UU.|CA|EE. UU.|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Vista montaña|94043|EE. UU.|CA|EE. UU.|1|1|

Para obtener más información sobre cómo dar formato al archivo de datos, vea Formato de archivo de [datos de inquilino y Crear estructura de archivos de datos.](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>Temas relacionados

[Configurar el Análisis de llamadas](set-up-call-analytics.md)

[Usar análisis de llamadas para solucionar problemas de mala calidad de llamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)
