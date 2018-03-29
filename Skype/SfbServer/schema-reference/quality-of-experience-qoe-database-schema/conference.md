---
title: Tabla Conference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La mesa de conferencias es una tabla de soporte. Cada registro representa a una conferencia o sesión de peer-to-peer.
ms.openlocfilehash: 0390f1f9da264ab5269c7bfdcb4a86c08097b835
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conference-table"></a>Tabla Conference
 
La mesa de conferencias es una tabla de soporte. Cada registro representa a una conferencia o sesión de peer-to-peer.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este registro de conferencia.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |único  <br/> |Conferencia URI si se trata de una conferencia o DialogID si esta es una sesión de peer-to-peer.  <br/> |
|**Suma de comprobación** <br/> |int  <br/> |índice  <br/> |Suma de comprobación de la conferencia URI. Se utiliza internamente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Sólo para uso interno.  <br/> |
   

