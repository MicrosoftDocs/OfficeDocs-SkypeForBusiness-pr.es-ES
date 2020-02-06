---
title: Tabla CallType en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La tabla CallType es una tabla estática que almacena la lista de posibles tipos de llamadas.
ms.openlocfilehash: 294af58755e980200d75c899d6110322e2ff774d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815438"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabla CallType en Skype empresarial Server 2015
 
La tabla CallType es una tabla estática que almacena la lista de posibles tipos de llamadas.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0--desconocido <br/>  1-mensajería instantánea <br/>  2: uso compartido de aplicaciones <br/>  3: audio <br/>  4-audio y vídeo <br/>  5-transferencia de archivos <br/> |
   

