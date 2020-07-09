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
description: Para obtener más información sobre cómo agregar y actualizar etiquetas de informes, cargue un archivo de texto que contenga una lista de ubicaciones físicas y subredes asociadas.
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
ms.openlocfilehash: 1b32e9db020b3498e8185b4d38e25d1d9a1feca5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085296"
---
<a name="add-and-update-reporting-labels"></a>Agregar y actualizar etiquetas de informes
============================

Las etiquetas de informes se usan en su organización para indicar las ubicaciones físicas de oficinas, edificios o sitios de la organización. La página etiquetas de informes del centro de administración de Microsoft Teams le permite proporcionar un archivo de texto (. csv o. TSV) que contiene una lista de ubicaciones físicas y sus subredes de red asociadas. Este archivo es utilizado por el análisis de llamadas para generar informes. Cuando cargue la asignación de subred, los informes proporcionados por estos servicios también contendrán los nombres de ubicación, lo que hace que los informes sean más fáciles de comprender y usar para corregir cualquier problema potencial.

> [!IMPORTANT]
> Las etiquetas de informes que cargue se tratarán como *datos de soporte técnico* de acuerdo con el contrato de Office 365, incluida cualquier información que de otro modo sería considerada como datos de los *clientes* o *datos personales*. No incluya datos que no desee proporcionar a Microsoft como *datos de soporte técnico*, ya que esta información será visible para los ingenieros de Microsoft a efectos de soporte técnico.

Los datos de etiquetas y ubicaciones del informe que proporciona son una única estructura de datos: actualmente no hay ninguna interfaz disponible para realizar ediciones individuales de los datos.

**Para editar la tabla de subredes y ubicaciones**

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en **ubicaciones**  >  **etiquetas de informes**.
2. Haga clic en **reemplazar datos de ubicaciones**.
3. En el panel **reemplazar datos de ubicaciones** , haga clic en **seleccionar un archivo**y, a continuación, busque y cargue el archivo. csv o. TSV editado.
4. Haga clic en **cargar**.

Puede descargar una plantilla de ejemplo [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Use el ejemplo siguiente para ayudar a crear el archivo de datos.

> [!IMPORTANT]
> El archivo de datos no debe contener encabezados de columna (como red, nombre de red, etc.). Se usan aquí solo con fines informativos. <br>

|Red|Nombre de red|Intervalo de red|Nombre del edificio|Tipo de propiedad|Tipo de edificio|Tipo de edificio de Office|Ciudad|Código postal|Tercer|Estado|Region|Inside Corp|Expressroute|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|

Para obtener más información sobre cómo dar formato a un archivo de datos, vea [formato del archivo de datos de inquilinos y creación de una estructura de archivo de datos](CQD-upload-tenant-building-data.md#upload-building-data-file).

## <a name="related-topics"></a>Temas relacionados

[Configurar el Análisis de llamadas](set-up-call-analytics.md)
