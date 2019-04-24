---
title: Agregar y actualizar datos de ubicaciones
author: tonysmit
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo se carga a un sitio.
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: a84b022c7b5553a15ff8862a175ba5f856cdd149
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222320"
---
<a name="adding-and-updating-locations-data"></a>Agregar y actualizar datos de ubicaciones
============================

Las ubicaciones se usan en su organización para indicar las ubicaciones físicas de oficinas, edificios o sitios organizativos. La página ubicaciones de proporciona a los administradores de la capacidad de proporcionar un archivo de texto (.csv o .tsv) que contiene una lista de ubicaciones físicas y sus subredes de red asociados. Este archivo se usa en análisis de llamada y llame al panel de calidad para la generación de informes. Cuando los clientes cargar su asignación de subred, los informes proporcionados por estos servicios va a contener los nombres de ubicación, realizar más fácil de comprender y usar para solucionar los posibles problemas relativos a los informes.

Los datos de ubicaciones que proporciona están una estructura de datos única: actualmente no hay ninguna interfaz disponible para realizar cambios individuales a los datos de ubicación. 

**Para editar la tabla de ubicaciones y subredes**

1. Haga clic en **reemplazar datos de ubicaciones**.
2. En el panel **reemplazar datos de ubicación** , haga clic en **Seleccionar un archivo**y a continuación, busque y cargue su editado .csv o .tsv archivo. 
3. Haga clic en **cargar**. 


Puede descargar una plantilla de ejemplo [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Puede usar el siguiente ejemplo para ayudar a crear el archivo de datos. 

> [!IMPORTANT]
> El archivo de datos no debe contener encabezados de columna (por ejemplo, red, nombre de red, etcetera). Se utilizan aquí únicamente con fines informativos. </br>

|Red|Nombre de red|Intervalo de red|Nombre del edificio|Tipo de propiedad|Tipo de creación|Tipo de creación de Office|Ciudad|Código postal|País|Estado|Region|Corp interior|Ruta de Express|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso conexión alquilada RE&F|Office|RE&F|Mountain View|94043|NOSOTROS|CA|NOSOTROS|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso conexión alquilada RE&F|Office|RE&F|Mountain View|94043|NOSOTROS|CA|NOSOTROS|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso conexión alquilada RE&F|Office|RE&F|Mountain View|94043|NOSOTROS|CA|NOSOTROS|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso conexión alquilada RE&F|Office|RE&F|Mountain View|94043|NOSOTROS|CA|NOSOTROS|1|1|


Para obtener más información sobre cómo dar formato a su archivo de datos, vea [formato y estructura de archivos de datos de creación de archivos de datos de inquilinos](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-building-data-file-structure).


## <a name="related-topics"></a>Temas relacionados

[Configurar el Análisis de llamadas](set-up-call-analytics.md)