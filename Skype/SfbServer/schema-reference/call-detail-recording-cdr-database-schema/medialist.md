---
title: Tabla MediaList
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La lista MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.
ms.openlocfilehash: 00667806e5099db35cce29b07248569faf09ee24
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767498"
---
# <a name="medialist-table"></a>Tabla MediaList
 
La lista MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Principal  <br/> |Valores: 1-7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Asignación estática de valores MediaID y Media: <br/>  1 -- MI <br/>  2- Transferencia de archivos <br/>  3: Asistencia remota <br/>  4- Uso compartido de aplicaciones <br/>  5 -- Audio <br/>  6 -- Vídeo <br/>  7- Invitación a la aplicación <br/> |
   
Si está intentando determinar el tipo de modalidad para los valores de LcsCDR.SessionDetailsView.MediaTypes, debe usar el siguiente fragmento de código join: 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
