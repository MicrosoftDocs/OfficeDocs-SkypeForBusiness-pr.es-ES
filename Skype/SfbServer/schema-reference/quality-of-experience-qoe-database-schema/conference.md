---
title: Tabla Conference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: En la tabla de conferencia es una tabla de apoyo. Cada registro representa una conferencia o sesión de punto a punto.
ms.openlocfilehash: bae144ff574f19155e11b8a2fbfd3548df356c2a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212266"
---
# <a name="conference-table"></a>Tabla Conference
 
En la tabla de conferencia es una tabla de apoyo. Cada registro representa una conferencia o sesión de punto a punto.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este registro de conferencia.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |único  <br/> |Si se trata de una conferencia, o DialogID, si este de URI de conferencia es una sesión de punto a punto.  <br/> |
|**Suma de comprobación** <br/> |int  <br/> |índice  <br/> |Suma de comprobación de la URI de conferencia. Se usa internamente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Sólo para uso interno.  <br/> |
   

