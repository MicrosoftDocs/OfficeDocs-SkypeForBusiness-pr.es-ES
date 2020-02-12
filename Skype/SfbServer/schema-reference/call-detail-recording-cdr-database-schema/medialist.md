---
title: Tabla MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La tabla MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.
ms.openlocfilehash: e7d739b27bf45b5f5a21183c30bd5b07108b4a9d
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888519"
---
# <a name="medialist-table"></a>Tabla MediaList
 
La tabla MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |Valores: 1-7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Asignación estática de los valores de MediaID y Media: <br/>  1 – MI <br/>  2-transferencia de archivos <br/>  3-asistencia remota <br/>  4-uso compartido de aplicaciones <br/>  5 – Audio <br/>  6 – Vídeo <br/>  7-invitación a la aplicación <br/> |
   
Si está intentando determinar el tipo de modalidad para los valores en LcsCDR.SessionDetailsView.MediaTypes, deberá usar el siguiente fragmento de código de JOIN.  
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
