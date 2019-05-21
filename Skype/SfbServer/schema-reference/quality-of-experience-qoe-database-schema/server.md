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
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabla del servidor es una tabla de soporte técnico. Cada registro representa un servidor.
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294715"
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
   

