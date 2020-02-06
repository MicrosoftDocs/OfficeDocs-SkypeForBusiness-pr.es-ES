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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabla de conferencia es una tabla de soporte técnico. Cada registro representa una sesión de conferencia o de punto a punto.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810308"
---
# <a name="conference-table"></a>Tabla Conference
 
La tabla de conferencia es una tabla de soporte técnico. Cada registro representa una sesión de conferencia o de punto a punto.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este registro de conferencia.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |solo  <br/> |URI de conferencia si se trata de una conferencia o DialogID si se trata de una sesión de punto a punto.  <br/> |
|**Comprobación** <br/> |int  <br/> |clasificación  <br/> |Suma de comprobación del URI de la Conferencia. Esto se usa internamente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Solo para uso interno.  <br/> |
   

