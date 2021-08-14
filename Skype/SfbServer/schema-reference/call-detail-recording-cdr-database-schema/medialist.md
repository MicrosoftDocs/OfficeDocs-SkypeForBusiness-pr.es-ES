---
title: Tabla MediaList
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La lista MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.
ms.openlocfilehash: 9242f20b3c2192fb1f5cd48c84784a3e8d283f6e91587aee408a9286d291add7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326276"
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
