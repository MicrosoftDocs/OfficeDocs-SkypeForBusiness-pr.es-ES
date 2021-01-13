---
title: Tabla Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabla Server es una tabla auxiliar. Cada registro representa a un servidor.
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802710"
---
# <a name="server-table"></a>Tabla Server
 
La tabla Server es una tabla auxiliar. Cada registro representa a un servidor. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica el servidor.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |index  <br/> |Cadena de dirección MAC.  <br/> |
|**ServerType** <br/> |entero  <br/> |Externo  <br/> |1: Servidor de mediación  <br/> 2: Servidor de conferencia A/V16394: Servicio perimetral A/V32769: Puerta de enlace  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||Grupo al que pertenece el servidor. Solo aplicable para el servidor de conferencia A/V.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Únicamente para uso interno.  <br/> |
   

