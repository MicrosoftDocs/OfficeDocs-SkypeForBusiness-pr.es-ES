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
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: La tabla PayloadDescription es una tabla de soporte. Cada registro representa un códec, que se usa en una sesión de audio o vídeo.
ms.openlocfilehash: 41819c8329802b224bd3848334eddbc9de6935f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294813"
---
# <a name="payloaddescription-table"></a>Tabla PayloadDescription
 
La tabla PayloadDescription es una tabla de soporte. Cada registro representa un códec, que se usa en una sesión de audio o vídeo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el códec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Solo  <br/> |Nombre de códec.  <br/> |
   

