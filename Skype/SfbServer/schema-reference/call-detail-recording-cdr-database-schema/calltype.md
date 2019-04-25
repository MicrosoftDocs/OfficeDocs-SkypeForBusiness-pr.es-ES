---
title: Tabla CallType en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: En la tabla CallType es una tabla estática que almacena la lista de posibles tipos de llamada.
ms.openlocfilehash: 29e5ed85de5917092ad00cd0e1aa60fec1a31b22
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213364"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabla CallType en Skype para Business Server 2015
 
En la tabla CallType es una tabla estática que almacena la lista de posibles tipos de llamada.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0--Unknown (desconocido) <br/>  1: instantánea de mensajería <br/>  2--Uso compartido de aplicaciones <br/>  3--audio <br/>  4 - audio y vídeo <br/>  5 - transferencia de archivos <br/> |
   

