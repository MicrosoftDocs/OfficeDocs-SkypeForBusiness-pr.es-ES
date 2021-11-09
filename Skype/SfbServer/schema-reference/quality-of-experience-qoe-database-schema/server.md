---
title: Tabla de servidor
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabla Server es una tabla auxiliar. Cada registro representa a un servidor.
ms.openlocfilehash: c061176c7a3dbb30fbbe696241fccd54db8dc9b2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834928"
---
# <a name="server-table"></a>Tabla de servidor
 
La tabla Server es una tabla auxiliar. Cada registro representa a un servidor. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica el servidor.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |index  <br/> |Cadena de dirección MAC.  <br/> |
|**ServerType** <br/> |Entero  <br/> |Externo  <br/> |1: Servidor de mediación  <br/> 2: Servidor de conferencia A/V16394: Servicio perimetral A/V32769: Puerta de enlace  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||Grupo al que pertenece el servidor. Solo aplicable para el servidor de conferencia A/V.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Únicamente para uso interno.  <br/> |
   

