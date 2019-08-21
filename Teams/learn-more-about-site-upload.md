---
title: Agregar y actualizar datos de ubicaciones
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
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo cargar en un sitio.
ms.custom:
- NewAdminCenter_Update
f1keywords:
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: bed4487a944bafb8092f63fb4582b165375a1e83
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484031"
---
<a name="adding-and-updating-locations-data"></a>Agregar y actualizar datos de ubicaciones
============================

Las ubicaciones se usan en su organización para indicar las ubicaciones físicas de oficinas, edificios o sitios de la organización. La página ubicaciones proporciona a los administradores la posibilidad de proporcionar un archivo de texto (. csv o. TSV) que contiene una lista de ubicaciones físicas y sus subredes de red asociadas. Este archivo lo usa el análisis de llamadas y el panel de calidad de llamadas para generar informes. Cuando los clientes cargan su asignación de subred, los informes proporcionados por estos servicios también contendrán los nombres de ubicación, lo que facilitará la comprensión y el uso de los informes para corregir cualquier problema potencial.

Los datos de ubicaciones proporcionados son una única estructura de datos: actualmente no hay ninguna interfaz disponible para realizar ediciones individuales en datos de ubicación. 

**Para editar la tabla de subredes y ubicaciones**

1. Haga clic en **reemplazar datos de ubicaciones**.
2. En el panel **reemplazar datos de ubicación** , haga clic en **seleccionar un archivo**y, a continuación, busque y cargue el archivo. csv o. TSV editado. 
3. Haga clic en **cargar**. 


Puede descargar una plantilla de ejemplo [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Puede usar el ejemplo siguiente para ayudar a crear el archivo de datos. 

> [!IMPORTANT]
> El archivo de datos no debe contener encabezados de columna (como red, nombre de red, etc.). Se usan aquí solo con fines informativos. </br>

|Red|Nombre de red|Intervalo de red|Nombre del edificio|Tipo de propiedad|Tipo de edificio|Tipo de edificio de Office|Ciudad|Código postal|Tercer|Estado|Region|Inside Corp|Expressroute|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso alquilado RE&F|Office|RE&F|Vista de montaña|94043|DÉJEN|CA|DÉJEN|1|1|


Para obtener más información sobre cómo dar formato a un archivo de datos, vea [formato del archivo de datos de inquilinos y creación de una estructura de archivo de datos](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure).


## <a name="related-topics"></a>Temas relacionados

[Configurar el Análisis de llamadas](set-up-call-analytics.md)
