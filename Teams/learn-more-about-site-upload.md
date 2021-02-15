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
description: Aprenda a agregar y actualizar etiquetas de informes cargando un archivo de texto que contiene una lista de ubicaciones físicas y subredes asociadas.
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

Las etiquetas de informes se usan en su organización para indicar la ubicación física de oficinas, edificios o sitios de la organización. La página Etiquetas de informes del Centro de administración de Microsoft Teams le permite proporcionar un archivo de texto (.csv o .tsv) que contiene una lista de ubicaciones físicas y sus subredes de red asociadas. Análisis de llamadas usa este archivo para generar informes. Al cargar la asignación de subred, los informes proporcionados por estos servicios también contendrán los nombres de ubicación, lo que facilita la lectura y el uso de los informes para corregir los posibles problemas.

> [!IMPORTANT]
> Las etiquetas de informes que  cargue se administrarán como Datos de soporte técnico en virtud  de su contrato para Office 365, incluida cualquier información que, de otro modo, se consideraría Datos del cliente o *Datos personales.* No incluya datos que no desee proporcionar a Microsoft como Datos de soporte *técnico,* ya que esta información será visible para los ingenieros de Microsoft a efectos de soporte técnico.

Los datos de ubicaciones y etiquetas de informe que proporciona son una sola estructura de datos; actualmente, no hay ninguna interfaz disponible para realizar modificaciones individuales en los datos.

**Para editar la tabla de subredes y ubicaciones**

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Etiquetas de**  >  **informes de ubicaciones.**
2. Haga clic **en Cargar datos.**
3. En el **panel Cargar datos,** haga clic en Seleccionar un archivo y, **a** continuación, busque y cargue el archivo .csv o .tsv editado.
4. Haga clic **en Cargar.**

Puede descargar una plantilla de ejemplo [aquí.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)

Use el siguiente ejemplo para ayudarle a crear el archivo de datos.

> [!IMPORTANT]
> El archivo de datos no debe contener encabezados de columna (como Red, Nombre de red, etc.). Se usan aquí solamente con fines informativos. <br>

|Red|Nombre de red|Intervalo de red|Nombre de edificio|Tipo de propiedad|Tipo de edificio|Tipo de oficina de edificio|Ciudad|Código postal|País|Estado|Region|Inside Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Arrendar re&F|Office|RE&F|Vista de montaña|94043|EE. UU.|CA|EE. UU.|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Arrendar re&F|Office|RE&F|Vista de montaña|94043|EE. UU.|CA|EE. UU.|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Arrendar re&F|Office|RE&F|Vista de montaña|94043|EE. UU.|CA|EE. UU.|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Arrendar re&F|Office|RE&F|Vista de montaña|94043|EE. UU.|CA|EE. UU.|1|1|

Para obtener más información sobre cómo dar formato al archivo de datos, vea Formato del archivo de [datos de inquilino y Crear la estructura del archivo de datos.](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>Temas relacionados

[Configurar el Análisis de llamadas](set-up-call-analytics.md)

[Usar análisis de llamadas para solucionar problemas de calidad de llamada deficiente](use-call-analytics-to-troubleshoot-poor-call-quality.md)
