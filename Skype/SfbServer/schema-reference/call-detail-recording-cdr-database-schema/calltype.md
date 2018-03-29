---
title: Tabla de CallType en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La tabla de CallType es una tabla estática que almacena la lista de tipos posibles de llamada.
ms.openlocfilehash: e2353176a69db9eada137525561541d26caa7a8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabla de CallType en Skype para Business Server 2015
 
La tabla de CallType es una tabla estática que almacena la lista de tipos posibles de llamada.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0--desconocido <br/>  1 - instant Messaging <br/>  2: Uso compartido de aplicaciones <br/>  3: audio <br/>  4 - audio y vídeo <br/>  5 - transferencia de archivos <br/> |
   

