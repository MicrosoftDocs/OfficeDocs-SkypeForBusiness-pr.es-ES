---
title: Tabla Server
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabla del servidor es una tabla de soporte técnico. Cada registro representa un servidor.
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806138"
---
# <a name="server-table"></a>Tabla Server
 
La tabla del servidor es una tabla de soporte técnico. Cada registro representa un servidor. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el servidor.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |clasificación  <br/> |Cadena de dirección MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Extranjero  <br/> |1: servidor de mediación  <br/> 2: Server16394 de conferencia a/V: service32769 Edge: Gateway  <br/> |
|**Nombredegrupo** <br/> |nvarchar (512)  <br/> ||Grupo al que pertenece el servidor. Solo es aplicable para el servidor de conferencia A/V.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Solo para uso interno.  <br/> |
   

