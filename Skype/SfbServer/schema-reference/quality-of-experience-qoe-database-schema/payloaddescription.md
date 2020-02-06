---
title: Tabla PayloadDescription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: La tabla PayloadDescription es una tabla de soporte. Cada registro representa un códec, que se usa en una sesión de audio o vídeo.
ms.openlocfilehash: 3a5719d7fbfe23eb8c1457565a36df0a02617fde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807498"
---
# <a name="payloaddescription-table"></a>Tabla PayloadDescription
 
La tabla PayloadDescription es una tabla de soporte. Cada registro representa un códec, que se usa en una sesión de audio o vídeo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el códec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Solo  <br/> |Nombre de códec.  <br/> |
   

