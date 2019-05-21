---
title: Tabla Conference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabla de conferencia es una tabla de soporte técnico. Cada registro representa una sesión de conferencia o de punto a punto.
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295016"
---
# <a name="conference-table"></a>Tabla Conference
 
La tabla de conferencia es una tabla de soporte técnico. Cada registro representa una sesión de conferencia o de punto a punto.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este registro de conferencia.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |solo  <br/> |URI de conferencia si se trata de una conferencia o DialogID si se trata de una sesión de punto a punto.  <br/> |
|**Comprobación** <br/> |int  <br/> |clasificación  <br/> |Suma de comprobación del URI de la Conferencia. Esto se usa internamente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Solo para uso interno.  <br/> |
   

