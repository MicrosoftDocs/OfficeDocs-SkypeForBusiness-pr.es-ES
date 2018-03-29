---
title: Tabla de puertas de enlace de Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabla de puertas de enlace es una tabla de soporte. Cada registro almacena información sobre una puerta de enlace que interviene en las llamadas (RTC) de la red telefónica pública conmutada que tengan registros en la base de datos.
ms.openlocfilehash: e9592b227e8ccff6829748230abd3e8ddb8edb75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Tabla de puertas de enlace de Skype para Business Server 2015
 
La tabla de puertas de enlace es una tabla de soporte. Cada registro almacena información sobre una puerta de enlace que interviene en las llamadas (RTC) de la red telefónica pública conmutada que tengan registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica esta puerta de enlace.  <br/> |
|**Puerta de enlace** <br/> |nvarchar(256)  <br/> | <br/> |Nombre de puerta de enlace.  <br/> |
   

